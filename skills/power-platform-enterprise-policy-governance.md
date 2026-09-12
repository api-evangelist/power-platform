---
name: power-platform-enterprise-policy-governance
description: Create and attach Microsoft.PowerPlatform enterprise policies - customer-managed encryption keys, customer lockbox and virtual network injection - through the Azure Resource Manager contract Microsoft publishes.
api: microsoft-power-platform:microsoft-power-platform-enterprise-policies
operations:
  - EnterprisePolicies_CreateOrUpdate
  - EnterprisePolicies_Get
  - EnterprisePolicies_ListByResourceGroup
  - EnterprisePolicies_ListBySubscription
  - EnterprisePolicies_Update
  - EnterprisePolicies_Delete
  - PrivateEndpointConnections_ListByEnterprisePolicy
  - PrivateLinkResources_ListByEnterprisePolicy
  - Accounts_CreateOrUpdate
  - Operations_List
generated: '2026-09-06'
method: generated
source: >-
  openapi/_original/microsoft-power-platform-enterprise-policies-openapi.json - Microsoft's own
  Swagger 2.0 contract for the Microsoft.PowerPlatform resource provider, harvested verbatim from
  Azure/azure-rest-api-specs on 2026-09-06. Every operationId above was read from that document.
---

# Power Platform enterprise policies (Azure Resource Manager)

This is the *control plane* for the security posture of Power Platform environments, and it lives
on `https://management.azure.com`, not on a Power Platform host. That is not a mismatch: the
resource provider is `Microsoft.PowerPlatform`, and it is how Microsoft exposes encryption,
lockbox and network controls as Azure resources you can govern with Azure policy and RBAC.

Auth is standard ARM: a Microsoft Entra ID token for the `management.azure.com` audience
(`azure_auth`, scope `user_impersonation`), and the caller needs write permission on the resource
group.

## Discover what the provider supports

`Operations_List` — `GET /providers/Microsoft.PowerPlatform/operations`

Do this first in an unfamiliar tenant. It tells you which operations the provider actually exposes
in that cloud (Public, GCC, GCC High differ).

## Inventory existing policies

`EnterprisePolicies_ListBySubscription` —
`GET /subscriptions/{subscriptionId}/providers/Microsoft.PowerPlatform/enterprisePolicies`

`EnterprisePolicies_ListByResourceGroup` — the same, scoped to one resource group.

Each `EnterprisePolicy` carries a `kind` (`EnterprisePolicyKind`) that says what it governs, an
`identity` (`EnterprisePolicyIdentity`) and a `properties` object with three independent blocks:

- `encryption` → `KeyVaultProperties` → `keyProperties` — the customer-managed key
- `lockbox` — customer lockbox state
- `networkInjection` → `VirtualNetworkProperties` → `SubnetProperties` — VNet injection

## Create or change a policy

`EnterprisePolicies_CreateOrUpdate` — `PUT .../enterprisePolicies/{enterprisePolicyName}`

This is a PUT, so it is idempotent by construction: sending the same body twice converges on the
same resource. Responses are `200` (updated) or `201` (created) — treat both as success.

`EnterprisePolicies_Update` — `PATCH` — takes `PatchEnterprisePolicy` and changes only what you
send. Prefer it when you are adjusting one block and do not want to restate the others.

**Order matters.** Create the Key Vault, the key and the access grant before the policy references
them; a policy pointing at a key it cannot read reports an unhealthy `HealthStatus` rather than
failing loudly at creation.

## Private connectivity

`PrivateLinkResources_ListByEnterprisePolicy` tells you which group names are connectable.
`PrivateEndpointConnections_ListByEnterprisePolicy` shows what is currently attached, and
`PrivateEndpointConnections_CreateOrUpdate` approves or rejects a pending connection.

## Delete

`EnterprisePolicies_Delete` returns `200` or `204`.

Detach the policy from every Power Platform environment that uses it *before* deleting it.
Removing a customer-managed-key policy from under a live environment is not a reversible
convenience — the environment-level recovery windows (7 days of backups, 28 for production managed
environments) are the only safety net, and a restore requires the target environment to carry the
same customer-managed key as the source.

## What this API does NOT do

It does not create environments, move data, or touch Dataverse rows. Environment lifecycle lives
on the Power Platform API (`https://api.powerplatform.com/environmentmanagement/...`), and record
operations live on the Dataverse Web API. Three hosts, three contracts, one product.

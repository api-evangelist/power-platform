---
name: dataverse-schema-discovery
description: Discover which tables and columns exist in a Dataverse environment before writing any query, because the Power Platform schema is defined per environment and not by a shared contract.
api: microsoft-power-platform:microsoft-power-platform-metadata-api
operations:
  - listEntityDefinitions
  - getEntityDefinition
  - whoAmI
generated: '2026-09-06'
method: generated
source: >-
  openapi/microsoft-power-platform-metadata-api-openapi.yml (operationIds verified against the
  spec), data-model/microsoft-power-platform-data-model.yml,
  conformance/microsoft-power-platform-conformance.yml
---

# Dataverse schema discovery

The single most common mistake against Power Platform is assuming a schema. Dataverse tables are
created per environment — by first-party apps, by ISV solutions and by makers — so two
environments in the same tenant can differ. There is no published entity list to code against.
Discover, then act.

## 1. Establish context

`whoAmI` — `GET /WhoAmI`

Returns `UserId`, `BusinessUnitId` and `OrganizationId`. Call it first: it proves the token works,
proves you are pointed at the environment you think you are, and gives you the principal that will
own every row you create.

## 2. Enumerate tables

`listEntityDefinitions` — `GET /EntityDefinitions`

Returns the `EntityMetadata` collection. Narrow it, because the full set is large:

```http
GET /EntityDefinitions?$select=LogicalName,EntitySetName,DisplayName,IsCustomEntity
```

`EntitySetName` — not `LogicalName` — is what you put in the record-operation path. The table
`account` is addressed as `/accounts`. Getting this wrong is the usual cause of a 404.

## 3. Inspect one table

`getEntityDefinition` — `GET /EntityDefinitions(LogicalName='{logicalName}')`

Expand attributes to learn column names, types and required-ness:

```http
GET /EntityDefinitions(LogicalName='account')?$expand=Attributes($select=LogicalName,AttributeType,RequiredLevel)
```

Relationships live here too (`OneToManyRelationships`, `ManyToOneRelationships`,
`ManyToManyRelationships`) — they are not in the OpenAPI, so this is the only place to learn what
`$expand` targets are legal.

## 4. When you need the authoritative schema

The OData CSDL document at `{org}.api.crm.dynamics.com/api/data/v9.2/$metadata` is the real
machine-readable contract for the environment. It requires a tenant bearer token, so it cannot be
mirrored into a public catalogue — fetch it at runtime if you need full type fidelity.

## Cost discipline

Metadata reads are cheap in request count but not free: Microsoft excludes a small set of internal
system metadata operations from *licence entitlement* counting, but service protection limits
still apply to everything you send. Cache the entity list for the life of a session rather than
re-enumerating before every operation.

## Do not

- Do not hardcode `EntitySetName` values discovered in one environment and reuse them in another.
- Do not infer a column exists because it exists in Dynamics 365 documentation; solutions can be
  uninstalled.
- Do not use `create_table`, `update_table` or `delete_table` (the MCP equivalents) as a discovery
  side effect. `delete_table` removes the schema *and the data*, and there is no table-level undo.

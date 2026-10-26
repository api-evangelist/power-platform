# Microsoft Power Platform APIs (power-platform)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Collection of APIs for Microsoft Power Platform services including Power Apps, Power Automate, Power BI, Copilot Studio, Power Pages, and Dataverse.

**APIs.json:** [https://powerplatform.microsoft.com/apis.json](https://powerplatform.microsoft.com/apis.json)

## Tags

- Business Applications
- Copilot Studio
- Dataverse
- Low-Code
- Microsoft
- No-Code
- Power Pages
- Power Platform

## Timestamps

- **Created:** 2024-01-15
- **Modified:** 2026-05-19

## APIs

### Power Apps API

REST API for creating, managing, and deploying Power Apps applications including canvas apps and model-driven apps.

- **Human URL:** [https://learn.microsoft.com/en-us/power-apps/developer/data-platform/webapi/overview](https://learn.microsoft.com/en-us/power-apps/developer/data-platform/webapi/overview)
- **Base URL:** `https://api.powerapps.com`

#### Tags

- Applications
- Canvas Apps
- Model-Driven Apps
- Power Apps

#### Properties

- [Documentation](https://learn.microsoft.com/en-us/power-apps/developer/data-platform/webapi/overview)
- [OpenAPI](https://api.powerapps.com/openapi/v1) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Authentication](https://learn.microsoft.com/en-us/power-apps/developer/data-platform/authenticate-oauth)
- [Rate Limits](https://learn.microsoft.com/en-us/power-apps/developer/data-platform/api-limits)
- [Pricing](https://powerapps.microsoft.com/pricing/)
- [API Reference](https://learn.microsoft.com/en-us/rest/api/power-platform/powerapps/apps)
- [Postman Collection](collections/power-platform-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/power-platform-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Dataverse API (Common Data Service)

OData v4.0 compliant Web API for Microsoft Dataverse, providing RESTful data storage, business logic, and entity management capabilities across the Power Platform.

- **Human URL:** [https://learn.microsoft.com/en-us/power-apps/developer/data-platform/webapi/overview](https://learn.microsoft.com/en-us/power-apps/developer/data-platform/webapi/overview)
- **Base URL:** `https://[org].api.crm.dynamics.com/api/data/v9.2`

#### Tags

- CDS
- Data Platform
- Database
- Dataverse
- OData

#### Properties

- [Documentation](https://learn.microsoft.com/en-us/power-apps/developer/data-platform/webapi/overview)
- [API Reference](https://learn.microsoft.com/en-us/power-apps/developer/data-platform/webapi/reference/about)
- [Documentation](https://learn.microsoft.com/en-us/power-apps/developer/data-platform/webapi/web-api-types-operations)
- [Authentication](https://learn.microsoft.com/en-us/power-apps/developer/data-platform/webapi/authenticate-web-api)
- [SDK](https://learn.microsoft.com/en-us/power-apps/developer/data-platform/developer-tools)
- [Postman Collection](collections/power-platform-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/power-platform-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Power Automate API

API for creating, managing, and running automated cloud flows and desktop flows. Cloud flows are stored in Dataverse and can be managed via the Dataverse Web API.

- **Human URL:** [https://learn.microsoft.com/en-us/power-automate/web-api](https://learn.microsoft.com/en-us/power-automate/web-api)
- **Base URL:** `https://api.flow.microsoft.com`

#### Tags

- Automation
- Desktop Flows
- Flow
- Power Automate
- RPA
- Workflow

#### Properties

- [Documentation](https://learn.microsoft.com/en-us/power-automate/web-api)
- [OpenAPI](https://api.flow.microsoft.com/openapi/v1) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Authentication](https://learn.microsoft.com/en-us/power-automate/web-api)
- [Integrations](https://learn.microsoft.com/en-us/connectors/)
- [Pricing](https://powerautomate.microsoft.com/pricing/)
- [API Reference](https://learn.microsoft.com/en-us/rest/api/power-platform/powerautomate/flow-runs/list-flow-runs)
- [Postman Collection](collections/power-platform-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/power-platform-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Power BI REST API

REST API for embedding, managing, and interacting with Power BI reports, datasets, dashboards, and workspaces for embedded analytics and automation.

- **Human URL:** [https://learn.microsoft.com/en-us/rest/api/power-bi/](https://learn.microsoft.com/en-us/rest/api/power-bi/)
- **Base URL:** `https://api.powerbi.com`

#### Tags

- Analytics
- Business Intelligence
- Dashboards
- Embedded Analytics
- Power BI
- Reporting

#### Properties

- [Documentation](https://learn.microsoft.com/en-us/rest/api/power-bi/)
- [OpenAPI](https://api.powerbi.com/v1.0/myorg/swagger.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Authentication](https://learn.microsoft.com/en-us/power-bi/developer/embedded/embed-tokens)
- [SDK](https://learn.microsoft.com/en-us/javascript/api/overview/powerbi/)
- [Pricing](https://powerbi.microsoft.com/pricing/)
- [Postman Collection](collections/power-platform-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/power-platform-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Microsoft Copilot Studio API (formerly Power Virtual Agents)

API for building, managing, and deploying AI agents and conversational chatbots. Power Virtual Agents has been rebranded to Microsoft Copilot Studio with expanded AI agent capabilities.

- **Human URL:** [https://learn.microsoft.com/en-us/microsoft-copilot-studio/fundamentals-what-is-copilot-studio](https://learn.microsoft.com/en-us/microsoft-copilot-studio/fundamentals-what-is-copilot-studio)
- **Base URL:** `https://api.powerva.microsoft.com`

#### Tags

- AI Agents
- Chatbots
- Conversational AI
- Copilot Studio
- Power Virtual Agents
- Virtual Agents

#### Properties

- [Documentation](https://learn.microsoft.com/en-us/microsoft-copilot-studio/fundamentals-what-is-copilot-studio)
- [Authentication](https://learn.microsoft.com/en-us/microsoft-copilot-studio/configuration-end-user-authentication)
- [Pricing](https://www.microsoft.com/en-us/microsoft-copilot/microsoft-copilot-studio#pricing)
- [Console](https://copilotstudio.microsoft.com)
- [Postman Collection](collections/power-platform-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/power-platform-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Power Platform Admin API

API for administrative operations across Power Platform environments including environment management, governance, capacity, and licensing via the BAP (Business Application Platform) endpoint.

- **Human URL:** [https://learn.microsoft.com/en-us/power-platform/admin/admin-documentation](https://learn.microsoft.com/en-us/power-platform/admin/admin-documentation)
- **Base URL:** `https://api.bap.microsoft.com`

#### Tags

- Administration
- Environments
- Governance
- Licensing
- Management

#### Properties

- [Documentation](https://learn.microsoft.com/en-us/power-platform/admin/admin-documentation)
- [C L I](https://learn.microsoft.com/en-us/power-platform/developer/cli/introduction)
- [Getting Started](https://learn.microsoft.com/en-us/power-platform/admin/powerplatform-api-getting-started)
- [Postman Collection](collections/power-platform-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/power-platform-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Power Platform Connectors API

API for custom and certified connectors that extend Power Platform capabilities across Power Apps, Power Automate, Logic Apps, and Copilot Studio.

- **Human URL:** [https://learn.microsoft.com/en-us/connectors/](https://learn.microsoft.com/en-us/connectors/)
- **Base URL:** `https://api.connectors.microsoft.com`

#### Tags

- Connectors
- Custom Connectors
- Integration
- OpenAPI

#### Properties

- [Documentation](https://learn.microsoft.com/en-us/connectors/)
- [Documentation](https://learn.microsoft.com/en-us/connectors/custom-connectors/)
- [C L I](https://learn.microsoft.com/en-us/connectors/custom-connectors/paconn-cli)
- [GitHub Repository](https://github.com/microsoft/PowerPlatformConnectors)
- [Postman Collection](collections/power-platform-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/power-platform-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Power Platform Unified API

Unified RESTful API surface for all Power Platform administrative capabilities including licensing, app management, environment management, and governance. Provides a single endpoint at api.powerplatform.com.

- **Human URL:** [https://learn.microsoft.com/en-us/rest/api/power-platform/](https://learn.microsoft.com/en-us/rest/api/power-platform/)
- **Base URL:** `https://api.powerplatform.com`

#### Tags

- Administration
- App Management
- Governance
- Licensing
- Power Platform API
- Unified API

#### Properties

- [Documentation](https://learn.microsoft.com/en-us/rest/api/power-platform/)
- [Getting Started](https://learn.microsoft.com/en-us/power-platform/admin/powerplatform-api-getting-started)
- [Authentication](https://learn.microsoft.com/en-us/power-platform/admin/programmability-authentication-v2)
- [Versioning](https://learn.microsoft.com/en-us/power-platform/admin/programmability-versioning-support)
- [OpenAPI](openapi/power-platform-api-openapi.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/power-platform-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/power-platform-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [SDK](https://www.nuget.org/packages/Microsoft.PowerPlatform.Management)

### Power Pages Web API

Web API for Power Pages (formerly Power Apps Portals) enabling CRUD operations on Microsoft Dataverse tables from portal webpages for richer user experiences.

- **Human URL:** [https://learn.microsoft.com/en-us/power-pages/configure/web-api-overview](https://learn.microsoft.com/en-us/power-pages/configure/web-api-overview)
- **Base URL:** `https://[site].powerappsportals.com/_api`

#### Tags

- Dataverse
- Portals
- Power Pages
- Web API
- Websites

#### Properties

- [Documentation](https://learn.microsoft.com/en-us/power-pages/configure/web-api-overview)
- [Getting Started](https://learn.microsoft.com/en-us/power-pages/configure/webapi-how-to)
- [Postman Collection](collections/power-platform-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/power-platform-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [LinkedIn](https://www.linkedin.com/showcase/microsoft-power-platform)
- [Developer Portal](https://learn.microsoft.com/en-us/power-platform/developer/)
- [Documentation](https://learn.microsoft.com/en-us/power-platform/)
- [Blog](https://www.microsoft.com/en-us/power-platform/blog/)
- [GitHub Organization](https://github.com/microsoft/powerplatform)
- [Training](https://learn.microsoft.com/en-us/training/powerplatform/)
- [Status Page](https://status.cloud.microsoft/)
- [Privacy Policy](https://privacy.microsoft.com/privacystatement)
- [Terms of Service](https://www.microsoft.com/licensing/terms/)
- [API Reference](https://learn.microsoft.com/en-us/rest/api/power-platform/)
- [Support](https://admin.powerplatform.microsoft.com/)
- [Features](undefined)
- [Use Cases](undefined)
- [Integrations](undefined)
- [M C P Server](https://github.com/microsoft/powerbi-modeling-mcp)
- [Agent Skill](https://github.com/microsoft/power-platform-skills)

## Maintainers

**Email:** kin@apievangelist.com
**URL:** https://apievangelist.com

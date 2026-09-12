---
name: dataverse-record-operations
description: Read, create, update and delete Dataverse rows through the Power Platform Web API without tripping service protection limits or creating duplicates on retry.
api: microsoft-power-platform:microsoft-power-platform-records-api
operations:
  - listRecords
  - getRecord
  - createRecord
  - updateRecord
  - deleteRecord
generated: '2026-09-06'
method: generated
source: >-
  openapi/microsoft-power-platform-records-api-openapi.yml (operationIds verified against the
  spec), conventions/microsoft-power-platform-conventions.yml,
  rate-limits/microsoft-power-platform-rate-limits.yml,
  errors/microsoft-power-platform-problem-types.yml
---

# Dataverse record operations

Base URL: `https://{org}.api.crm.dynamics.com/api/data/v9.2` — `{org}` is the customer's own
environment, not a shared vendor host. You cannot call this API without knowing which
environment you are acting in.

## Before you start

1. Get a Microsoft Entra ID bearer token whose audience is the environment:
   `https://{org}.api.crm.dynamics.com/.default`. There are no API keys.
2. Confirm the connection and learn who you are acting as with `whoAmI`
   (`GET /WhoAmI`). Record the returned `UserId` — every write is attributed to it.
3. Resolve the entity set name with `listEntityDefinitions` before guessing. Dataverse tables are
   per-environment; `accounts` exists in most environments but nothing guarantees it.

## Read

`listRecords` — `GET /{entitySetName}`

Use the OData system query options the spec declares: `$select`, `$filter`, `$orderby`, `$top`,
`$expand`, `$count`. Always send `$select` — an unselected read returns every column and burns
execution time against the 1,200-second/300-second budget.

Paging is server-driven. Send `Prefer: odata.maxpagesize=<n>`, then follow the `@odata.nextLink`
URL in the response verbatim. Never construct `$skip` offsets.

`getRecord` — `GET /{entitySetName}({id})` — returns `@odata.etag`. Keep it; it is the token that
makes your subsequent write safe.

## Create

`createRecord` — `POST /{entitySetName}`

**This operation is not safe to retry.** There is no `Idempotency-Key` header in Dataverse. If a
POST times out you cannot tell whether the row was created, and retrying creates a second one.

Do this instead: generate the GUID yourself and upsert.

```http
PATCH /accounts(11111111-2222-3333-4444-555555555555)
If-None-Match: *
Content-Type: application/json

{ "name": "Contoso" }
```

`If-None-Match: *` makes it insert-only — a second attempt returns `412 Precondition Failed`
instead of creating a duplicate. That 412 is a success signal for a retry, not an error.

## Update

`updateRecord` — `PATCH /{entitySetName}({id})`

Send `If-Match: <the etag you read>`. If someone else changed the row since you read it you get
`412` instead of silently clobbering their write. `If-Match: *` makes it update-only (404 if the
row is gone).

Send only the columns you are changing. Set a lookup by binding a URI:
`"primarycontactid@odata.bind": "/contacts(<guid>)"`.

## Delete

`deleteRecord` — `DELETE /{entitySetName}({id})`

**There is no per-record undo.** The only documented recovery is restoring the whole environment
from a backup, and backups are retained for 7 days (28 for production managed environments; trial
environments are not backed up at all). Microsoft's own guidance for getting deleted rows back is
to restore the backup into a *new* environment so you do not lose everything written since.

Send `If-Match: <etag>` so you delete the version you actually inspected.

## Handling failure

| Status | What it means | What to do |
|---|---|---|
| 401 | Token missing, expired or wrong audience | Re-acquire the token for the environment resource |
| 403 | Authenticated but the security role does not permit it | Stop. Do not retry; this needs an admin |
| 404 | Entity set or row does not exist | Re-run `listEntityDefinitions` |
| 412 | ETag mismatch (or upsert precondition) | Re-read, re-apply, retry once |
| 429 | Service protection limit | Read `Retry-After` and sleep exactly that many seconds |
| 502/503/504 | Transient | Exponential backoff |

The 429 body carries a hexadecimal code that tells you *which* limit you hit:
`0x80072322` request count (6,000 / 300s), `0x80072321` execution time (1,200s / 300s),
`0x80072326` concurrency (52). Concurrency is returned immediately — if you see it, lower
parallelism rather than sleeping.

Do not compute your own backoff when `Retry-After` is present. Do not pace yourself off
`x-ms-ratelimit-burst-remaining-xrm-requests`; Microsoft documents that header as a debugging aid
that resets when you land on a different server.

## Throughput

Ramp up gradually and let the 429s tell you the ceiling. Prefer many small requests over large
`$batch` payloads — batching dodges the request-count limit but spends the execution-time budget
faster, and it never bypasses the 24-hour licence entitlement (40,000 requests for a standard
paid licence, 6,000 for per-app and seeded licences).

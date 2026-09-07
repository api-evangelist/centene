---
name: centene-find-in-network-provider
description: >-
  Search Centene's public FHIR Provider Directory for in-network practitioners, organizations,
  locations and plans. Requires no credential of any kind — this is the one Centene surface an
  agent can call immediately.
api: Centene FHIR Provider Directory API
base_url: https://iopc-pd.api.centene.com/iopc/pd/fhir/providerdirectory
spec: openapi/centene-fhir-provider-directory-openapi.json
generated: '2026-09-07'
method: generated
source: openapi/centene-fhir-provider-directory-openapi.json
operations:
  - searchPractitioner
  - readPractitioner
  - searchPractitionerRole
  - readPractitionerRole
  - searchOrganization
  - readOrganization
  - searchOrganizationAffiliation
  - searchLocation
  - readLocation
  - searchHealthcareService
  - searchInsurancePlan
  - searchEndpoint
  - getMetadata
---

# Find an in-network Centene provider

Centene's Provider Directory is public. There is no key, no OAuth flow and no registration —
verified 2026-09-07 with an anonymous request that returned HTTP 200 and a FHIR searchset Bundle.
It conforms to Da Vinci PDEX Plan Net 1.2.0 on FHIR R4 (4.0.1).

## Before you start

Call `getMetadata` once (`GET /metadata`) and read the CapabilityStatement. It is the authoritative
list of which search parameters each resource type actually supports on this server. Do not assume
a parameter exists because FHIR R4 defines it.

## Steps

1. **Find the practitioner.** `searchPractitioner` — `GET /Practitioner?family=SMITH`. Centene's own
   documentation uses exactly this example. Combine with `given` and `name` as needed.
2. **Page through the results.** The server returns at most **200 entries per page**. Read
   `link[]` and find the element whose `relation` is `next`, then GET its `url`. Repeat until no
   `next` link is present.
   Centene's guide tells you to read `link[1]` positionally — **do not do that**. FHIR does not
   guarantee link ordering; match on `relation == "next"`.
3. **Resolve what the practitioner actually does, and for whom.** A `Practitioner` on its own
   carries no network or location. Call `searchPractitionerRole` with
   `?practitioner=Practitioner/{id}` and follow the `organization`, `location`,
   `healthcareService` and `specialty` references. This is the join resource — skipping it is the
   most common mistake against a PDEX directory.
4. **Confirm network participation.** `searchOrganizationAffiliation` with `?participating-organization={orgId}`
   tells you which networks an organization participates in. "In-network" is a property of the
   affiliation, not of the practitioner.
5. **Resolve the plan.** `searchInsurancePlan` maps networks to the plans a member may hold.
6. **Get the address.** `searchLocation` / `readLocation` — Centene's documented example is
   `GET /Location?address-city=boston`.

## California

For California provider details, Centene directs you to a **different base URL**:
`https://iopc-provider.api.centene.com/iopc/provider/ca/fhir/providerdirectory`. It is a separate
deployment with its own CapabilityStatement. FHIR logical ids are **not** portable between the two
servers — do not cache an id from one and read it from the other.

## What can go wrong

- **You get XML on an error.** The gateway in front of this API answers 403 and 404 with a SOAP
  `env:Fault` body regardless of your `Accept` header. Do not assume an error body is
  `application/fhir+json`. Parse defensively.
- **429 with no guidance.** 429 is a declared response but Centene publishes no rate limit and
  returns no `RateLimit-*` or `Retry-After` header. Back off exponentially with jitter.
- **Correlation.** Every response carries an undocumented `x-request-id`. Log it; it is the only
  handle you will have if you need to raise something with
  `provider_search_support@centene.com`.

## Do not

- Do not send credentials to this API. It takes none, and the `Basic` scheme declared in the
  OpenAPI is stale — the catalogue entry and live behaviour both say anonymous.
- Do not call `servers[0]` from the spec. It names `dev-int-api-gw.centene.com`, a development
  gateway. Production is the `base_url` above.

---
name: centene-payer-to-payer-pdex
description: >-
  Retrieve Centene provider-directory data as an authorized payer partner via the Provider RTR
  FHIR PDEX Directory API, using OAuth 2.0 client credentials with a required audience.
api: Centene Provider RTR - FHIR PDEX Directory API (External)
base_url: https://prod.api.centene.com/prtc/external/fhir-pdex-plan-net/v1/
spec: openapi/centene-provider-rtr-fhir-pdex-openapi.json
generated: '2026-09-07'
method: generated
source: openapi/centene-provider-rtr-fhir-pdex-openapi.json
operations:
  - PractitionerAPIResponse
  - PractitionerRoleAPIResponse
  - OrganizationAPIResponse
  - OrganizationAffiliationAPIResponse
  - LocationAPIResponse
  - HealthcareServiceAPIResponse
  - InsurancePlanAPIResponse
  - EndpointAPIResponse
---

# Exchange provider directory data with Centene as a payer

This is the Da Vinci PDEX Plan Net 1.2.0 surface Centene exposes to authorized payer partners,
distinct from the public Provider Directory. It is machine-to-machine: there is no member and no
consent flow.

## Authorization

`client_credentials` only. Request a token from the EntryKey ID authorization server with scopes
`resource.read` and `openid`, and — this is the part that trips people — the **audience
`prtrdemographic`**. Centene's gateway validates the audience, so a token minted for another
Centene API returns 401 here even though the credential is valid.

Onboarding runs through `Provider_RTR_Support@centene.com`.

## Steps

1. Obtain a client-credentials token with audience `prtrdemographic`.
2. Read the resource you need — `PractitionerAPIResponse`, `PractitionerRoleAPIResponse`,
   `OrganizationAPIResponse`, `OrganizationAffiliationAPIResponse`, `LocationAPIResponse`,
   `HealthcareServiceAPIResponse`, `InsurancePlanAPIResponse`, `EndpointAPIResponse`.
3. Resolve relationships through `PractitionerRole` and `OrganizationAffiliation`, exactly as on
   the public directory — the PDEX Plan Net graph is the same shape.
4. Use `Endpoint` to discover the technical endpoints for onward payer-to-payer exchange.

## Environments

The spec declares two servers. `https://prod.api.centene.com/tst/prtc/external/fhir-pdex-plan-net/v1/`
is the test path; `https://prod.api.centene.com/prtc/external/fhir-pdex-plan-net/v1/` is
production. Both sit on the same hostname and differ only by a `/tst` path segment — verify which
one you are pointed at before writing anything into a downstream system.

## What can go wrong

- **401 that looks like a credential problem but is an audience problem.** Check the `aud` claim.
- **403/404 returned as a SOAP `env:Fault`**, in XML, regardless of `Accept`. Parse defensively.
- **No idempotency and no rate-limit headers.** 429 is declared; no `Retry-After` is returned.

## Do not

- Do not reuse a Patient Access member token here. Different grant, different audience.
- Do not treat FHIR logical ids from this API as interchangeable with those from
  `iopc-pd.api.centene.com` — they are separate deployments.

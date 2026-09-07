---
name: centene-member-record-access
description: >-
  Retrieve a Centene member's own clinical, coverage and claims data with their consent, via the
  CMS-mandated FHIR Patient Access API using the SMART on FHIR standalone launch flow.
api: Centene FHIR Patient Access API
base_url: https://iopc-pa.api.centene.com/iopc/pa
sandbox_url: https://iopc-sand.test.api.centene.com/iopc/sand
spec: openapi/centene-fhir-patient-access-openapi.json
generated: '2026-09-07'
method: generated
source: openapi/centene-fhir-patient-access-openapi.json
operations:
  - getMetadata
  - readPatient
  - searchCoverage
  - searchExplanationOfBenefit
  - searchMedicationRequest
  - searchMedicationKnowledge
  - readMedication
  - searchCondition
  - searchObservation
  - searchAllergyIntolerance
  - searchImmunization
  - searchCarePlan
  - searchCareTeam
  - searchEncounter
  - searchDiagnosticReport
  - searchGoal
  - searchProcedure
  - searchDevice
  - readProvenance
---

# Read a Centene member's record with their consent

This API exists because the CMS Interoperability and Patient Access Rule requires it. It returns
**protected health information** belonging to a real person who has explicitly authorized your
application. Treat every step below as consequential.

## Authorization — SMART on FHIR standalone launch

Centene implements HL7 SMART App Launch 2.0.0, **standalone launch only**. EHR launch is not
implemented; do not attempt it.

1. Register an application at https://partners.centene.com/applicationDeveloper-form to receive
   `clientId`, `clientSecret` and a registered `redirect_uri`.
2. Send the member to
   `https://sso.entrykeyid.com/as/authorization.oauth2?client_id={clientId}&redirect_uri={redirectUri}&response_type=code`
   (sandbox: `https://sandbox.entrykeyid.com/...`). Request scopes `patient/*.read` and `openid`.
3. Read the authorization code from the redirect. **It is valid for a single use** — Centene states
   this explicitly. A retry with the same code will fail.
4. Exchange it: `POST https://sso.entrykeyid.com/as/token.oauth2` with
   `Authorization: Basic base64(clientId:clientSecret)`, `Content-Type: application/json`, and a
   JSON body of `code`, `grant_type=authorization_code`, `redirect_uri`. The `redirect_uri` must
   match the one registered.
5. The response carries `access_token` (**expires in 3600 seconds**), `refresh_token`, and a
   top-level **`patient`** claim. That `patient` value is the FHIR logical id your token is scoped
   to — it is the compartment root for every call that follows.
6. When the token expires, exchange the `refresh_token` at the same endpoint with
   `grant_type=refresh_token`. Do not re-run the consent flow for a routine refresh.

## Steps

1. **Anchor on the patient.** `readPatient` — `GET /Patient/{patient}` using the id from the token
   response. Never guess or iterate patient ids; a token only opens its own compartment.
2. **Coverage first.** `searchCoverage` — `GET /Coverage?patient={patient}`. This tells you which
   Centene plan the member holds, which frames everything else.
3. **Claims and encounters.** `searchExplanationOfBenefit` — `GET /ExplanationOfBenefit?patient={patient}`.
   Profiled by CARIN BB 2.0.0.
4. **Medications and formulary.** `searchMedicationRequest`, then `readMedication` for each
   `medicationReference`. `searchMedicationKnowledge` returns Da Vinci US Drug Formulary 2.0.1
   content.
5. **Clinical record.** `searchCondition`, `searchObservation`, `searchAllergyIntolerance`,
   `searchImmunization`, `searchCarePlan`, `searchCareTeam`, `searchEncounter`,
   `searchDiagnosticReport`, `searchGoal`, `searchProcedure`, `searchDevice` — all US Core 6.1.0
   on FHIR R4.
6. **Provenance.** `readProvenance` tells you which source system supplied a resource. Under PDEX
   this matters: some data originated with another payer, not Centene.

## Paging

Same as the directory: follow `link[]` where `relation == "next"`. Match on the relation, not on
the array index.

## Test it first

Centene publishes six sandbox members (`CNCTESTTPA001` … `CNCTESTTPA006`, patient uuids 302, 352,
361, 370, 375, 381) with a shared published password. Use `https://sandbox.entrykeyid.com` and
`https://iopc-sand.test.api.centene.com/iopc/sand`. See `sandbox/centene-sandbox.yml`.

## Do not

- **Do not cache or re-derive the `patient` id across members.** It is bound to the token.
- **Do not persist PHI beyond what the member authorized.** The scope string granted is returned
  in the token response; honour it literally.
- **Do not retry a token exchange with a spent authorization code.** Restart the flow.
- Do not call `servers[0]` from the spec — it names `dev-int-api-gw.centene.com`, a dev gateway.

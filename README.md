# Centene

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

Centene Corporation is a Fortune 500 managed care organization delivering government-sponsored healthcare to roughly one in fifteen Americans through Medicaid, Medicare Advantage, TRICARE and Health Insurance Marketplace plans, operating under brands including Ambetter Health, Wellcare, Superior HealthPlan and Fidelis Care. Its public API surface exists to satisfy the 21st Century Cures Act and the CMS Interoperability and Patient Access Rule: HL7 FHIR R4 APIs for member record access (US Core 6.1.0, CARIN Blue Button 2.0.0, Da Vinci US Drug Formulary 2.0.1) and for provider directory (Da Vinci PDEX Plan Net 1.2.0), plus payer-to-payer PDEX exchange. Centene publishes twenty APIs through a partner portal at partners.centene.com, whose catalogue and OpenAPI documents are served anonymously; the FHIR Provider Directory is callable in production with no credential at all. Member data uses SMART on FHIR 2.0.0 standalone launch against a Ping Identity authorization server branded EntryKey ID; partner surfaces use OAuth client credentials with a per-API audience. Beyond the mandated interoperability estate Centene also publishes X12 / CAQH CORE EDI transaction, provider-search, product-mapping and care-management APIs.

**Areas:** Healthcare · Insurance · Managed Care · FHIR · HL7 · CMS Interoperability · Patient Access · Provider Directory · Payers · Medicaid · Medicare · Interoperability

## Centene on APIs.io

Everything profiled for Centene is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/centene/](https://apis.io/providers/centene/)** — or go straight to one of the APIs or properties below.

### APIs (58)

- [Centene Batch Results Ack Submit Transaction API](https://apis.io/apis/centene/centene-batchresultsacksubmittransaction-api/) — The BatchResultsAckSubmitTransaction API from Centene — 1 operation(s) for batchresultsacksubmittransaction.
- [Centene Batch Results Retrieval Transaction API](https://apis.io/apis/centene/centene-batchresultsretrievaltransaction-api/) — The BatchResultsRetrievalTransaction API from Centene — 1 operation(s) for batchresultsretrievaltransaction.
- [Centene Batch Submit Ack Retrieval Transaction API](https://apis.io/apis/centene/centene-batchsubmitackretrievaltransaction-api/) — The BatchSubmitAckRetrievalTransaction API from Centene — 1 operation(s) for batchsubmitackretrievaltransaction.
- [Centene Batch Submit Transaction API](https://apis.io/apis/centene/centene-batchsubmittransaction-api/) — The BatchSubmitTransaction API from Centene — 1 operation(s) for batchsubmittransaction.
- [Centene Care Team API](https://apis.io/apis/centene/centene-careteam-api/) — The CareTeam API from Centene — 2 operation(s) for careteam.
- [Centene Communication API](https://apis.io/apis/centene/centene-communication-api/) — The Communication API from Centene — 6 operation(s) for communication.
- [Centene Condition API](https://apis.io/apis/centene/centene-condition-api/) — The Condition API from Centene — 2 operation(s) for condition.
- [Centene Coverage API](https://apis.io/apis/centene/centene-coverage-api/) — The Coverage API from Centene — 2 operation(s) for coverage.
- [Centene Custom Mapping API](https://apis.io/apis/centene/centene-custom-mapping-api/) — check local mapping
- [Centene Custom Query Validator API](https://apis.io/apis/centene/centene-custom-query-validator-api/) — The custom-query-validator API from Centene — 1 operation(s) for custom-query-validator.
- [Centene Device API](https://apis.io/apis/centene/centene-device-api/) — The Device API from Centene — 2 operation(s) for device.
- [Centene Diagnostic Report API](https://apis.io/apis/centene/centene-diagnosticreport-api/) — The DiagnosticReport API from Centene — 2 operation(s) for diagnosticreport.
- [Centene Encounter API](https://apis.io/apis/centene/centene-encounter-api/) — The Encounter API from Centene — 2 operation(s) for encounter.
- [Centene Endpoint API](https://apis.io/apis/centene/centene-endpoint-api/) — The Endpoint API from Centene — 2 operation(s) for endpoint.
- [Centene Explanation Of Benefit API](https://apis.io/apis/centene/centene-explanationofbenefit-api/) — The ExplanationOfBenefit API from Centene — 2 operation(s) for explanationofbenefit.
- [Centene Extract API](https://apis.io/apis/centene/centene-extract-api/) — The Extract API from Centene — 3 operation(s) for extract.
- [Centene FHIR PDEX Plan Net API](https://apis.io/apis/centene/centene-fhir-pdex-plan-net-api-api/) — The FHIR-PDEX-Plan-Net-API API from Centene — 16 operation(s) for fhir-pdex-plan-net-api.
- [Centene Generic Batch Receipt Confirmation Transaction API](https://apis.io/apis/centene/centene-genericbatchreceiptconfirmationtransaction-api/) — The GenericBatchReceiptConfirmationTransaction API from Centene — 1 operation(s) for genericbatchreceiptconfirmationtransaction.
- [Centene Generic Batch Retrieval Transaction API](https://apis.io/apis/centene/centene-genericbatchretrievaltransaction-api/) — The GenericBatchRetrievalTransaction API from Centene — 1 operation(s) for genericbatchretrievaltransaction.
- [Centene Generic Batch Submission Transaction API](https://apis.io/apis/centene/centene-genericbatchsubmissiontransaction-api/) — The GenericBatchSubmissionTransaction API from Centene — 1 operation(s) for genericbatchsubmissiontransaction.
- [Centene Geo API](https://apis.io/apis/centene/centene-geo-api/) — The Geo API from Centene — 1 operation(s) for geo.
- [Centene Goal API](https://apis.io/apis/centene/centene-goal-api/) — The Goal API from Centene — 2 operation(s) for goal.
- [Centene Immunization API](https://apis.io/apis/centene/centene-immunization-api/) — The Immunization API from Centene — 2 operation(s) for immunization.
- [Centene List API](https://apis.io/apis/centene/centene-list-api/) — The List API from Centene — 2 operation(s) for list.
- [Centene Location API](https://apis.io/apis/centene/centene-location-api/) — The Location API from Centene — 2 operation(s) for location.
- [Centene Medication API](https://apis.io/apis/centene/centene-medication-api/) — The Medication API from Centene — 1 operation(s) for medication.
- [Centene Medication Knowledge API](https://apis.io/apis/centene/centene-medicationknowledge-api/) — The MedicationKnowledge API from Centene — 2 operation(s) for medicationknowledge.
- [Centene Member API](https://apis.io/apis/centene/centene-member-api/) — The Member API from Centene — 1 operation(s) for member.
- [Centene Metadata API](https://apis.io/apis/centene/centene-metadata-api/) — The metadata API from Centene — 1 operation(s) for metadata.
- [Centene Network API](https://apis.io/apis/centene/centene-network-api/) — The network API from Centene — 1 operation(s) for network.
- [Centene Observation API](https://apis.io/apis/centene/centene-observation-api/) — The Observation API from Centene — 2 operation(s) for observation.
- [Centene Organization API](https://apis.io/apis/centene/centene-organization-api/) — The Organization API from Centene — 2 operation(s) for organization.
- [Centene Organization Affiliation API](https://apis.io/apis/centene/centene-organizationaffiliation-api/) — The OrganizationAffiliation API from Centene — 2 operation(s) for organizationaffiliation.
- [Centene Patient API](https://apis.io/apis/centene/centene-patient-api/) — The Patient API from Centene — 2 operation(s) for patient.
- [Centene Practitioner API](https://apis.io/apis/centene/centene-practitioner-api-api/) — RESTful API endpoints for search Practitioners' and their networks/locations related information. More information can be found on the corresponding Alation…
- [Centene Practitioner API](https://apis.io/apis/centene/centene-practitioner-api/) — The Practitioner API from Centene — 2 operation(s) for practitioner.
- [Centene Practitioner Date API](https://apis.io/apis/centene/centene-practitioner-date-api-api/) — RESTful API endpoints for search Practitioners' date related information. More information can be found on the corresponding Alation page:…
- [Centene Practitioner Network API](https://apis.io/apis/centene/centene-practitioner-network-api-api/) — RESTful API endpoints for search Practitioners' network related information. More information can be found on the corresponding Alation page:…
- [Centene Practitioner Search API](https://apis.io/apis/centene/centene-practitioner-search-api-api/) — RESTful API endpoints for search Practitioners' related information. More information can be found on the corresponding Alation page:…
- [Centene Procedure API](https://apis.io/apis/centene/centene-procedure-api/) — The Procedure API from Centene — 2 operation(s) for procedure.
- [Centene Provenance API](https://apis.io/apis/centene/centene-provenance-api/) — The Provenance API from Centene — 1 operation(s) for provenance.
- [Centene Provider API](https://apis.io/apis/centene/centene-provider-api-api/) — RESTful API endpoints for search Providers' and their networks/locations related information. More information can be found on the corresponding Alation…
- [Centene Provider Date API](https://apis.io/apis/centene/centene-provider-date-api-api/) — RESTful API endpoints for search Providers' date related information. More information can be found on the corresponding Alation page:…
- [Centene Provider Network API](https://apis.io/apis/centene/centene-provider-network-api-api/) — RESTful API endpoints for search Providers' network related information. More information can be found on the corresponding Alation page:…
- [Centene Provider Search API](https://apis.io/apis/centene/centene-provider-search-api-api/) — RESTful API endpoints for search Providers' related information. More information can be found on the corresponding Alation page:…
- [Centene Query API](https://apis.io/apis/centene/centene-query-api/) — query elasticsearch
- [Centene query v2 API](https://apis.io/apis/centene/centene-query-v2-api/) — The query v2 API from Centene — 1 operation(s) for query v2.
- [Centene Query Validator API](https://apis.io/apis/centene/centene-query-validator-api/) — The query-validator API from Centene — 1 operation(s) for query-validator.
- [Centene Questionnaire Response API](https://apis.io/apis/centene/centene-questionnaireresponse-api/) — The QuestionnaireResponse API from Centene — 2 operation(s) for questionnaireresponse.
- [Centene Real Time Transaction API](https://apis.io/apis/centene/centene-realtimetransaction-api/) — The RealTimeTransaction API from Centene — 1 operation(s) for realtimetransaction.
- [Centene Search Healow Member CG API](https://apis.io/apis/centene/centene-searchhealowmembercg-api/) — The SearchHealowMemberCG API from Centene — 4 operation(s) for searchhealowmembercg.
- [Centene Utilities API](https://apis.io/apis/centene/centene-utilities-api/) — The Utilities API from Centene — 2 operation(s) for utilities.
- [Centene Allergy Intolerance API](https://apis.io/apis/centene/centene-allergy-intolerance-api/) — The Allergy Intolerance API from Centene — 2 operation(s) for allergy intolerance.
- [Centene Care plan API](https://apis.io/apis/centene/centene-care-plan-api/) — The Care plan API from Centene — 2 operation(s) for care plan.
- [Centene Healthcare Service API](https://apis.io/apis/centene/centene-healthcare-service-api/) — The Healthcare Service API from Centene — 2 operation(s) for healthcare service.
- [Centene Insurance Plan API](https://apis.io/apis/centene/centene-insurance-plan-api/) — The Insurance Plan API from Centene — 2 operation(s) for insurance plan.
- [Centene Medication Request API](https://apis.io/apis/centene/centene-medication-request-api/) — The Medication Request API from Centene — 2 operation(s) for medication request.
- [Centene Practitioner Role API](https://apis.io/apis/centene/centene-practitioner-role-api/) — The Practitioner Role API from Centene — 2 operation(s) for practitioner role.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Centene Webhooks](https://apis.io/asyncapis/centene/centene-webhooks/)

#### Overlays (12)

OpenAPI overlays, including conversational phrasing for each operation.

- [Centene Ccm Communication Overlay](https://apis.io/overlays/centene/centene-ccm-communication-overlay/)
- [Centene Ccm Sms Userresponse Overlay](https://apis.io/overlays/centene/centene-ccm-sms-userresponse-overlay/)
- [Centene Edi Core Realtime Overlay](https://apis.io/overlays/centene/centene-edi-core-realtime-overlay/)
- [Centene Fhir Patient Access Overlay](https://apis.io/overlays/centene/centene-fhir-patient-access-overlay/)
- [Centene Fhir Provider Directory Overlay](https://apis.io/overlays/centene/centene-fhir-provider-directory-overlay/)
- [Centene Healow Health Overlay](https://apis.io/overlays/centene/centene-healow-health-overlay/)
- [Centene Pces Extract Overlay](https://apis.io/overlays/centene/centene-pces-extract-overlay/)
- [Centene Pces Overlay](https://apis.io/overlays/centene/centene-pces-overlay/)
- [Centene Product Mapping V2 Overlay](https://apis.io/overlays/centene/centene-product-mapping-v2-overlay/)
- [Centene Provider Rtr Demographics Overlay](https://apis.io/overlays/centene/centene-provider-rtr-demographics-overlay/)
- [Centene Provider Rtr Fhir Pdex Overlay](https://apis.io/overlays/centene/centene-provider-rtr-fhir-pdex-overlay/)
- [Centene Provider Search Suggest Overlay](https://apis.io/overlays/centene/centene-provider-search-suggest-overlay/)

#### Security (4)

Authentication, trust centre, and vulnerability disclosure.

- [Centene Authentication](https://apis.io/security/centene/centene-authentication/)
- [Centene Domain Security](https://apis.io/security/centene/centene-domain-security/)
- [Centene Trust Center](https://apis.io/security/centene/centene-trust-center/)
- [Centene Vulnerability Disclosure](https://apis.io/security/centene/centene-vulnerability-disclosure/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Centene Scopes](https://apis.io/scopes/centene/centene-scopes/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Centene Plans Pricing](https://apis.io/plans/centene/centene-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Centene Rate Limits](https://apis.io/rate-limits/centene/centene-rate-limits/)

#### FinOps (1)

What the API costs to run, by operation.

- [Centene Finops](https://apis.io/finops/centene/centene-finops/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.centene.com)
- [Documentation](https://partners.centene.com/apis)
- [Getting started](https://partners.centene.com/applicationDeveloper)
- [API reference](https://iopc-pd.api.centene.com/iopc/pd/fhir/providerdirectory/metadata)
- [Sign up](https://partners.centene.com/applicationDeveloper-form)
- [Support](https://partners.centene.com/contact-us)
- [Blog](https://www.centene.com/news.html)
- [Terms of service](https://partners.centene.com/terms)
- [Privacy policy](https://partners.centene.com/policy)

## API Evangelist rating

**Kin Score 40.0** — developing · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 71.4 |
| Contract quality | 54.8 |
| Contract governance | 18.2 |
| Operational transparency | 18.4 |
| Developer ergonomics | 30.4 |
| Access clarity | 21.1 |

**Agent readiness 47.7** — agent-ready (gated down from agent-native)

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | — |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | served (partial credit) |
| Idempotency | — |
| Error Semantics | verified |
| OpenAPI Examples | verified |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | yes |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | served (partial credit) |
| Protected Resource Metadata | — |
| Dynamic Client Registration | yes |
| Agentic Commerce | — |
| Pagination Ratio | na |
| Operation Distinctiveness | distinct |

**Regulatory alignment 45.3** — Health

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/centene/](https://apis.io/providers/centene/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Centene: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/centene/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).

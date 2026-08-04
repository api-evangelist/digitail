# Digitail (digitail)

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
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Digitail is a cloud-based, AI-native veterinary practice management software (PIMS) that consolidates scheduling, electronic medical records, AI SOAP dictation, client communication, billing, inventory, and reporting into one platform, paired with a Pet Parent mobile app for booking, records access, and payments. The **Digitail Open API** is a documented REST API (base `https://developer.digitail.io/api/v1`) secured with OAuth 2.0 authorization-code grant with PKCE, giving clinics, technology partners, and ecosystem players (labs, insurers, pharmacies, telemedicine, analytics) programmatic, real-time access to clinic data.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/digitail/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/digitail/refs/heads/main/apis.yml)

## Access Model

Digitail publishes a full public API reference at [documentation.digitail.io](https://documentation.digitail.io/). The API is production-real and openly documented, but it is **credential-gated**: to obtain a `client_id`/`client_secret` and use the OAuth 2.0 authorization-code + PKCE flow, an organization completes an API access registration at [digitail.com/api/access](https://digitail.com/api/access). "Open API access" is listed as an included feature across Digitail subscription plans (Mobile, Growth, Growth AI, Enterprise), so API use is tied to being a Digitail customer or approved integration partner rather than being open to anonymous sign-up.

- **Authorization endpoint:** `https://vet.digitail.io/oauth/authorize`
- **Token endpoint:** `https://vet.digitail.io/oauth/token`
- **API base URL:** `https://developer.digitail.io/api/v1`
- **Auth:** OAuth 2.0 authorization-code grant with PKCE; bearer access token (long-lived), refresh token, CSRF `state`.
- **Headers:** `accept: application/json`, `content-type: application/json`.
- **Pagination:** `page` (default 1) and `per_page` (default 15) query parameters.
- **Rate limit:** 200 requests per minute.

The logical APIs below are grouped from the documented resource categories in the Digitail API reference. Endpoints marked confirmed were verified against the public documentation; the remaining resource operations are modeled from the documented resource list and standard REST/pagination conventions, and are flagged as modeled in the OpenAPI (`x-endpoints-modeled`).

## Tags

- Veterinary
- PIMS
- Practice Management
- Pets
- Healthcare
- Scheduling
- Billing
- SaaS

## Timestamps

- **Created:** 2026-07-04
- **Modified:** 2026-07-04

## APIs

### Digitail Pets API

List, retrieve, and manage patient records (pets) and their archive, along with supporting reference data - species, breeds, and blood types. Confirmed endpoints include `GET /pets` and `GET /pets/{id}`.

- **Human URL:** [https://documentation.digitail.io/list-all-pets](https://documentation.digitail.io/list-all-pets)
- **Base URL:** `https://developer.digitail.io/api/v1`

### Digitail Pet Parents and Clients API

Manage pet parents (owners) and client records - the people and accounts a clinic bills and communicates with - and their association to pets and clinics.

- **Human URL:** [https://documentation.digitail.io/](https://documentation.digitail.io/)
- **Base URL:** `https://developer.digitail.io/api/v1`

### Digitail Appointments API

List and retrieve appointments, change appointment status, and read visit types for scheduling integrations. Confirmed endpoints include `GET /appointments`, `GET /appointments/{id}`, and `PUT /appointment/{id}/change-status`.

- **Human URL:** [https://documentation.digitail.io/get-all-appointments](https://documentation.digitail.io/get-all-appointments)
- **Base URL:** `https://developer.digitail.io/api/v1`

### Digitail Clinical Records API

Read and manage clinical records - medical records, prescriptions, medications, periodical treatments, and reminder protocol usages - that make up a patient's health history.

- **Human URL:** [https://documentation.digitail.io/](https://documentation.digitail.io/)
- **Base URL:** `https://developer.digitail.io/api/v1`

### Digitail Labs API

Push and retrieve laboratory data - diagnostic orders and results - enabling reference labs and in-house analyzers to sync results into the patient record.

- **Human URL:** [https://documentation.digitail.io/](https://documentation.digitail.io/)
- **Base URL:** `https://developer.digitail.io/api/v1`

### Digitail Billing and Invoicing API

Read and sync financial data - invoices, charges, sales, patient estimates, and service packages - for accounting, payments, and revenue reporting integrations.

- **Human URL:** [https://documentation.digitail.io/](https://documentation.digitail.io/)
- **Base URL:** `https://developer.digitail.io/api/v1`

### Digitail Clinics and Staff API

Read clinic, veterinarian, and role records - including public clinic and public vet directories - and the logged-in user context. Confirmed endpoints include `GET /vets/{id}` and `GET /clinic/{id}`.

- **Human URL:** [https://documentation.digitail.io/retrieve-a-vet](https://documentation.digitail.io/retrieve-a-vet)
- **Base URL:** `https://developer.digitail.io/api/v1`

### Digitail Client Communication API

Send and manage client communications - SMS, chat, and email messaging with pet parents - for reminder, marketing, and telemedicine workflows.

- **Human URL:** [https://documentation.digitail.io/](https://documentation.digitail.io/)
- **Base URL:** `https://developer.digitail.io/api/v1`

### Digitail Files API

Upload, attach, and retrieve files and documents - such as imaging, scanned records, and attachments - tied to pets, clients, and records.

- **Human URL:** [https://documentation.digitail.io/](https://documentation.digitail.io/)
- **Base URL:** `https://developer.digitail.io/api/v1`

### Digitail Reports API

Retrieve reporting data and tags for building dashboards and financial, operational, and performance analytics on top of clinic data.

- **Human URL:** [https://documentation.digitail.io/](https://documentation.digitail.io/)
- **Base URL:** `https://developer.digitail.io/api/v1`

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/digitail-veterinary-software/)
- [Website](https://digitail.com/)
- [Documentation](https://documentation.digitail.io/)
- [Sign Up / API Access](https://digitail.com/api/access)
- [Plans](plans/digitail-plans-pricing.yml)
- [Rate Limits](rate-limits/digitail-rate-limits.yml)
- [Fin Ops](finops/digitail-finops.yml)
- [Integrations](https://digitail.com/integrations/)
- [Blog](https://digitail.com/blog/)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com

# Digitail (digitail)

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

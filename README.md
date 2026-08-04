# Strava (strava)

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

Strava is a popular fitness tracking app and social network that allows athletes to track and analyze workouts including running, cycling, swimming, and 200+ other sport types. The Strava API enables developers to access athlete profiles, activities, segments, routes, clubs, gear, and time-series data streams. OAuth 2.0 is used for authentication with granular scope control. Rate limits apply: 100 requests per 15 minutes, 1000 per day.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/strava/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/strava/refs/heads/main/apis.yml)

## Scope

- **Type:** Index
- **Position:** Consumer
- **Access:** 3rd-Party

## Tags

- Cycling
- Fitness
- Fitness Tracking
- Running
- Sports

## Timestamps

- **Created:** 2025-03-01
- **Modified:** 2026-05-30

## APIs

### Strava API

The Strava API provides access to athlete profiles, activities (workouts), segments, routes, clubs, gear, and time-series data streams. Supports OAuth 2.0 with fine-grained scopes for reading activities, accessing private data, and writing updates. Rate limited to 100 requests/15 min and 1000 requests/day for default applications.

- **Human URL:** [https://developers.strava.com/](https://developers.strava.com/)
- **Base URL:** `https://www.strava.com/api/v3`

#### Tags

- Cycling
- Fitness
- Fitness Tracking
- Running
- Sports

#### Properties

- [OpenAPI](https://raw.githubusercontent.com/api-evangelist/strava/refs/heads/main/openapi/strava-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://developers.strava.com/docs/reference/)
- [Authentication](https://developers.strava.com/docs/authentication/)
- [Getting Started](https://developers.strava.com/docs/getting-started/)
- [Rate Limits](https://developers.strava.com/docs/rate-limits/)
- [Webhooks](https://developers.strava.com/docs/webhooks/)
- [AsyncAPI](https://raw.githubusercontent.com/api-evangelist/strava/refs/heads/main/asyncapi/strava-webhooks-asyncapi.yml) — [AsyncAPI Specification](https://www.asyncapi.com/docs/reference/specification/latest)
- [Postman Collection](collections/strava.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/strava.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [GitHub Organization](https://github.com/strava)
- [Website](https://www.strava.com)
- [Developer  Portal](https://developers.strava.com/)
- [Documentation](https://developers.strava.com/docs/)
- [Authentication](https://developers.strava.com/docs/authentication/)
- [Terms of Service](https://www.strava.com/legal/api)
- [Privacy Policy](https://www.strava.com/legal/privacy)
- [Status Page](https://status.strava.com)
- [Blog](https://blog.strava.com)
- [Forum](https://communityhub.strava.com/developers)
- [Sign Up](https://www.strava.com/register)
- [Login](https://www.strava.com/login)
- [App  Registration](https://www.strava.com/settings/api)
- [OpenAPI](https://raw.githubusercontent.com/api-evangelist/strava/refs/heads/main/openapi/strava-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [AsyncAPI](https://raw.githubusercontent.com/api-evangelist/strava/refs/heads/main/asyncapi/strava-webhooks-asyncapi.yml) — [AsyncAPI Specification](https://www.asyncapi.com/docs/reference/specification/latest)
- [JSON Schema](https://raw.githubusercontent.com/api-evangelist/strava/refs/heads/main/json-schema/strava-activity-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [J S O N L D Context](https://raw.githubusercontent.com/api-evangelist/strava/refs/heads/main/json-ld/strava-context.jsonld)
- [Integrations](https://www.strava.com/apps)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com

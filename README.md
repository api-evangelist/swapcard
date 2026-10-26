# Swapcard (swapcard)

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

Swapcard is an AI-powered event and community engagement platform for in-person, virtual, and hybrid events - mobile and web event apps, attendee networking and matchmaking, exhibitor and lead management, registration, and onsite badging.

**Access model (honest summary):** Swapcard's developer platform is **GraphQL-first** - there is no documented REST API and no OpenAPI. All operations are GraphQL queries and mutations over HTTP `POST`. There are two separate GraphQL endpoints, each with its own schema and its own **access token passed in the `Authorization` header** (Swapcard's documented examples send the raw token with no `Bearer` prefix). Access is **provisioned to Swapcard customers and partners** (organizers for the Content API, exhibitors for the Leads API) - it is not an open, self-serve public API. There are **no GraphQL subscriptions and no WebSocket (`wss://`) transport**; real-time delivery is handled by Webhooks. A live probe on 2026-07-12 confirmed the endpoint is live and token-gated (an unauthenticated POST returns `UNAUTHORIZED`).

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/swapcard/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/swapcard/refs/heads/main/apis.yml)

## Tags

- Events
- Event Management
- Community
- Networking
- Event Platform
- GraphQL
- Attendees
- Exhibitors
- SaaS

## Timestamps

- **Created:** 2026-07-12
- **Modified:** 2026-07-12

## APIs

### Swapcard Content API

Organizer-facing GraphQL API (the Event Admin endpoint) to fetch, create, modify, and delete event content - events, people, exhibitors, plannings/sessions, and groups. Single GraphQL endpoint over HTTP POST, authenticated with an organizer access token in the `Authorization` header.

- **Human URL:** [https://swapcard.dev/content-api/about-the-graphql-api](https://swapcard.dev/content-api/about-the-graphql-api)
- **Base URL:** `https://developer.swapcard.com/event-admin/graphql`

#### Tags

- Events
- Event Management
- GraphQL
- Content

#### Properties

- [Documentation](https://swapcard.dev/content-api/about-the-graphql-api)
- [API Reference](https://swapcard.dev/content-api/reference/graphql-event-api-schema)
- [GraphQL](graphql/swapcard.graphql) — [GraphQL SDL](https://spec.graphql.org/)
- [Postman Collection](collections/swapcard.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/swapcard.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Swapcard Exhibitor Leads API

Exhibitor-facing GraphQL API to list accessible booths (`myExhibitors`), export event leads with cursor pagination (`myLeads`), and scan badges to create leads (`scanBadges`). Separate GraphQL endpoint and token from the Content API, created in the Exhibitor Center under Leads then API keys.

- **Human URL:** [https://swapcard.dev/leads-api/about-the-graphql-api](https://swapcard.dev/leads-api/about-the-graphql-api)
- **Base URL:** `https://developer.swapcard.com/exhibitor/graphql`

#### Tags

- Leads
- Exhibitors
- GraphQL
- Networking

#### Properties

- [Documentation](https://swapcard.dev/leads-api/about-the-graphql-api)
- [API Reference](https://swapcard.dev/leads-api/usage)
- [GraphQL](graphql/swapcard.graphql) — [GraphQL SDL](https://spec.graphql.org/)
- [Postman Collection](collections/swapcard.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/swapcard.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Swapcard Analytics API

GraphQL API to collect and leverage analytics on event performance and attendee behavior. Documented on the Swapcard Developer Hub; its schema is not modeled in this catalog entry.

- **Human URL:** [https://swapcard.dev/analytics-api/about-the-graphql-api](https://swapcard.dev/analytics-api/about-the-graphql-api)
- **Base URL:** `https://developer.swapcard.com/event-admin/graphql`

#### Tags

- Analytics
- Events
- GraphQL

#### Properties

- [Documentation](https://swapcard.dev/analytics-api/about-the-graphql-api)

## Common Properties

- [Domain Security](security/swapcard-domain-security.yml)
- [Authentication](authentication/swapcard-authentication.yml)
- [Website](https://www.swapcard.com/)
- [Documentation](https://swapcard.dev/)
- [LinkedIn](https://www.linkedin.com/company/swapcard)
- [Plans](plans/swapcard-plans-pricing.yml)
- [Rate Limits](rate-limits/swapcard-rate-limits.yml)
- [Fin Ops](finops/swapcard-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com

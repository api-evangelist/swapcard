# Swapcard (swapcard)

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

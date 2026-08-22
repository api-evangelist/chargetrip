# Chargetrip (chargetrip)

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

Chargetrip provides an EV routing GraphQL API used by automakers and e-mobility services. It plans range-aware routes with charging stops, exposes a curated charge station database, an EV vehicle/consumption database, isolines (reachability), and operator data, with real-time route updates delivered over WebSocket subscriptions.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/chargetrip/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/chargetrip/refs/heads/main/apis.yml)

## Tags

- EV
- Routing
- Charging Stations
- GraphQL
- Mobility

## Timestamps

- **Created:** 2026-06-21
- **Modified:** 2026-06-21

## APIs

### Chargetrip Route Planning API

Range-aware EV route planning over GraphQL. The newRoute mutation calculates a route with charging stops from vehicle, origin, and destination inputs and returns a route id; results are fetched with the route query or streamed in real time via the routeUpdatedById subscription over WebSocket.

- **Human URL:** [https://developers.chargetrip.com/api-reference/routes/introduction/](https://developers.chargetrip.com/api-reference/routes/introduction/)
- **Base URL:** `https://api.chargetrip.io/graphql`

#### Tags

- Routing
- EV
- Navigation

#### Properties

- [Documentation](https://developers.chargetrip.com/api-reference/routes/introduction/)
- [API Reference](https://developers.chargetrip.com/api-reference/routes/introduction/)
- [OpenAPI](openapi/chargetrip-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [GraphQL](graphql/chargetrip-graphql.md) — [GraphQL](https://spec.graphql.org/)
- [Postman Collection](collections/chargetrip.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/chargetrip.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [AsyncAPI](asyncapi/chargetrip-asyncapi.yml) — [AsyncAPI Specification](https://www.asyncapi.com/docs/reference/specification/latest)

### Chargetrip Stations API

OCPI 2.2-aligned charge station database accessed with the station, stationList, and stationAround queries, returning location, connector, power, pricing/tariff, and real-time or predicted availability for curated European charging points.

- **Human URL:** [https://developers.chargetrip.com/api-reference/stations/introduction/](https://developers.chargetrip.com/api-reference/stations/introduction/)
- **Base URL:** `https://api.chargetrip.io/graphql`

#### Tags

- Charging Stations
- OCPI
- Availability

#### Properties

- [Documentation](https://developers.chargetrip.com/api-reference/stations/introduction/)
- [API Reference](https://developers.chargetrip.com/api-reference/stations/introduction/)
- [OpenAPI](openapi/chargetrip-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [GraphQL](graphql/chargetrip-graphql.md) — [GraphQL](https://spec.graphql.org/)
- [Postman Collection](collections/chargetrip.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/chargetrip.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Chargetrip Car Database API

EV vehicle and consumption-model database. The vehicleList query returns paginated, filterable/searchable vehicles and the vehicle query returns full details by id; a vehicle id is required as input to route and isoline operations.

- **Human URL:** [https://developers.chargetrip.com/api-reference/vehicle/introduction/index.html](https://developers.chargetrip.com/api-reference/vehicle/introduction/index.html)
- **Base URL:** `https://api.chargetrip.io/graphql`

#### Tags

- Vehicles
- Consumption
- EV

#### Properties

- [Documentation](https://developers.chargetrip.com/api-reference/vehicle/introduction/index.html)
- [API Reference](https://developers.chargetrip.com/api-reference/vehicle/query-vehicles/)
- [OpenAPI](openapi/chargetrip-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [GraphQL](graphql/chargetrip-graphql.md) — [GraphQL](https://spec.graphql.org/)
- [Postman Collection](collections/chargetrip.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/chargetrip.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Chargetrip Isolines / Reachability API

Drivable reachability isolines. The createIsoline mutation returns an isoline id and the isoline query returns multipolygon shapes plus the maximum drivable distance, accounting for state of charge, climate, weight, temperature, and weather.

- **Human URL:** [https://developers.chargetrip.com/api-reference/isolines/query-isoline/](https://developers.chargetrip.com/api-reference/isolines/query-isoline/)
- **Base URL:** `https://api.chargetrip.io/graphql`

#### Tags

- Isolines
- Reachability
- Range

#### Properties

- [Documentation](https://developers.chargetrip.com/api-reference/isolines/query-isoline/)
- [API Reference](https://developers.chargetrip.com/api-reference/isolines/query-isoline/)
- [OpenAPI](openapi/chargetrip-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [GraphQL](graphql/chargetrip-graphql.md) — [GraphQL](https://spec.graphql.org/)
- [Postman Collection](collections/chargetrip.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/chargetrip.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Chargetrip Operators API

Charge point operator (CPO) data for the station database. The operatorList query returns operators with pagination and filters; operators can be used to tailor the routing algorithm toward preferred networks.

- **Human URL:** [https://developers.chargetrip.com/api-reference/stations/query-station-operators/](https://developers.chargetrip.com/api-reference/stations/query-station-operators/)
- **Base URL:** `https://api.chargetrip.io/graphql`

#### Tags

- Operators
- Networks
- Charging

#### Properties

- [Documentation](https://developers.chargetrip.com/api-reference/stations/query-station-operators/)
- [API Reference](https://developers.chargetrip.com/api-reference/stations/query-station-operators/)
- [OpenAPI](openapi/chargetrip-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [GraphQL](graphql/chargetrip-graphql.md) — [GraphQL](https://spec.graphql.org/)
- [Postman Collection](collections/chargetrip.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/chargetrip.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [GitHub Organization](https://github.com/chargetrip)
- [LinkedIn](https://www.linkedin.com/company/chargetrip)
- [Website](https://www.chargetrip.com)
- [Documentation](https://developers.chargetrip.com)
- [Plans](plans/chargetrip-plans-pricing.yml)
- [Rate Limits](rate-limits/chargetrip-rate-limits.yml)
- [Fin Ops](finops/chargetrip-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com

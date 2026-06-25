# Chargetrip (chargetrip)

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

# Chargetrip GraphQL API

The [Chargetrip](https://www.chargetrip.com) API is a **native GraphQL API** for
electric-vehicle routing. It plans range-aware routes with charging stops, serves a
curated charge station database, an EV vehicle/consumption database, isolines
(reachability), and operator data, and pushes real-time route updates over WebSocket
subscriptions.

**Endpoint:** `https://api.chargetrip.io/graphql` (queries and mutations, HTTP POST)
**Subscriptions:** `wss://api.chargetrip.io/subscription` (WebSocket, `graphql-transport-ws` protocol)
**Documentation:** https://developers.chargetrip.com

## Authentication

Every request must send two headers, obtained by creating a Chargetrip account:

| Header | Purpose |
|--------|---------|
| `x-client-id` | Identifies your Chargetrip client/account. |
| `x-app-id` | Identifies the application making the request. |

- Quick setup: <https://developers.chargetrip.com/api-reference/api/quick-setup-guide/>
- Schema: see [`chargetrip-schema.graphql`](./chargetrip-schema.graphql) (representative SDL — see note below)

---

## Note on the schema file

The accompanying [`chargetrip-schema.graphql`](./chargetrip-schema.graphql) is a
**representative SDL** of the documented operations and types. It is not a verbatim
export of Chargetrip's production schema; field-level detail should be confirmed
against the live API Playground (<https://playground.chargetrip.com/>) and the
Voyager schema explorer (<https://voyager.chargetrip.com/>).

---

## Operation inventory

### Mutations
| Operation | Purpose |
|-----------|---------|
| `newRoute` | Create a route from vehicle, origin, and destination (plus preferences). Returns a route `id`; the route is computed asynchronously. |
| `createIsoline` | Create a drivable-reachability isoline for a vehicle and origin. Returns an isoline `id`; computed asynchronously. |

### Queries
| Operation | Purpose |
|-----------|---------|
| `route` | Fetch a previously created route by `id` (re-fetch / on-demand). |
| `isoline` | Fetch a previously created isoline by `id`, including multipolygon shape and `maxDrivableDistance`. |
| `station` | Fetch a single charge station by `id`. |
| `stationList` | List charge stations with pagination, filter, and search. |
| `stationAround` | Fetch the stations closest to a GeoJSON location (radius/distance). |
| `vehicleList` | List EV vehicles with pagination, filter, and search. |
| `vehicle` | Fetch a single vehicle (consumption model and specs) by `id`. |
| `operatorList` | List charge point operators (CPOs) with pagination and filters. |

### Subscriptions (WebSocket)
| Operation | Purpose |
|-----------|---------|
| `routeUpdatedById` | Real-time route status and route details for an `id` returned by `newRoute`; emits until `status` is `done`. |

---

## Examples

### Create a route (mutation)
```graphql
mutation newRoute {
  newRoute(
    input: {
      ev: {
        id: "5d161be5c9eef46132d9d20a"
        battery: { stateOfCharge: { value: 70, type: kilowatt_hour } }
        climate: true
      }
      routeRequest: {
        origin: {
          type: Feature
          geometry: { type: Point, coordinates: [4.8951, 52.3702] }
        }
        destination: {
          type: Feature
          geometry: { type: Point, coordinates: [2.3522, 48.8566] }
        }
      }
    }
  )
}
```

### Watch the route in real time (subscription, WebSocket)
```graphql
subscription routeUpdatedById($id: ID!) {
  routeUpdatedById(id: $id) {
    status
    route {
      charges
      duration
      distance
      consumption
      legs {
        distance
        duration
        chargeTime
        stationId
      }
    }
  }
}
```

### Fetch a completed route (query)
```graphql
query route($id: ID!) {
  route(id: $id) {
    status
    route {
      distance
      duration
      charges
    }
  }
}
```

### Stations around a location (query)
```graphql
query stationAround {
  stationAround(
    query: {
      location: { type: Point, coordinates: [4.8951, 52.3702] }
      distance: 5000
    }
    size: 20
    page: 0
  ) {
    id
    name
    status
    coordinates { latitude longitude }
    evses {
      status
      connectors { standard power max_electric_power }
    }
  }
}
```

### List vehicles (query)
```graphql
query vehicleList {
  vehicleList(page: 0, size: 10, search: "Tesla") {
    id
    naming { make model version }
    battery { usable_kwh full_kwh }
    range { chargetrip_range { best worst } }
  }
}
```

### Create and read an isoline
```graphql
mutation createIsoline {
  createIsoline(
    input: {
      ev: { id: "5d161be5c9eef46132d9d20a", battery: { stateOfCharge: { value: 70, type: kilowatt_hour } } }
      origin: { type: Feature, geometry: { type: Point, coordinates: [4.8951, 52.3702] } }
    }
  )
}

query isoline($id: ID!) {
  isoline(id: $id) {
    status
    polygons
    maxDrivableDistance
  }
}
```

### List operators (query)
```graphql
query operatorList {
  operatorList(page: 0, size: 20) {
    id
    name
  }
}
```

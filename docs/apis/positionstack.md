# Positionstack API Integration

Positionstack is used to provide geocoding capabilities, converting airport names, cities, or coordinates into geographic location data.

This API enables geographic enrichment of aviation data and supports map visualizations and spatial analysis.

---

## Endpoints Used in This Project

| Endpoint | Purpose | Data Type |
|--------|--------|--------|
| forward | Convert place names or addresses into geographic coordinates | Geospatial |
| reverse | Convert coordinates into location information | Geospatial |

---

## Data Usage in This Project

Geocoding data is used to enrich airport and flight information with geographic context.

Typical use cases include:

- Converting airport names or cities into coordinates
- Mapping flight routes and airport locations
- Enabling geographic visualization of air traffic

Geographic data can be used in dashboards, map visualizations, and spatial analysis.

---

# Endpoints

## /forward

Forward geocoding converts a **free-text address or place name** into geographic coordinates and location metadata.


### Query Parameters

- **query** – Address, place name, or location to geocode.
- **limit** – Maximum number of results (1–80, default `10`).
- **country** – Country filter using ISO codes (e.g., `US`, `AUS`).
- **region** – Region filter (state, county, city name).
- **language** – Preferred language for returned fields (default `en`).

### Optional Modules

- **bbox_module** – Include bounding box coordinates (`0` or `1`).
- **country_module** – Include extended country information (`0` or `1`).
- **timezone_module** – Include timezone metadata (`0` or `1`).
- **sun_module** – Include solar data (sunrise/sunset).

### Other Parameters

- **fields** – Limit response fields to reduce payload.
- **output** – Response format (`json`, `xml`, `geojson`).
- **callback** – Optional JSONP callback.

---

## /reverse

Reverse geocoding converts **coordinates (latitude, longitude)** into location data.


### Query Parameters

- **query** – Latitude and longitude coordinates.
- **limit** – Maximum number of results (1–80).
- **country** – Country filter using ISO codes.
- **region** – Region filter.
- **language** – Preferred language for results.

### Optional Modules

- **bbox_module** – Include bounding box data.
- **country_module** – Include extended country metadata.
- **timezone_module** – Include timezone information.
- **sun_module** – Include solar information.

### Other Parameters

- **fields** – Limit response fields.
- **output** – Response format (`json`, `xml`, `geojson`).
- **callback** – Optional JSONP callback.

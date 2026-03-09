# Weatherstack API Integration

Weatherstack is used to enrich aviation data with weather conditions for airports and flight locations.

Weather information provides operational context such as delays, airport conditions, and weather trends.

---

## Endpoints Used in This Project

| Endpoint | Purpose | Data Type |
|--------|--------|--------|
| current | Real-time weather conditions | Variable data |
| forecast | Short-term weather forecast | Predictive / operational |
| historical | Historical weather data | Analytical |

---

## Data Usage in This Project

Weather data is used to enrich airport and flight information.

Typical use cases include:

- Weather conditions at departure and arrival airports
- Context for flight delays
- Weather trends affecting airport operations

Weather data may be stored alongside flight snapshots or used to generate derived analytics.

---

## Endpoints

## /current

The **Current Weather endpoint** returns real-time weather conditions for a specific location.

A location can be defined using a city name, airport location, or geographic coordinates.


### Query Parameters

- **access_key** – API authentication key (required).
- **units** – Units system:
  - `m` → Metric (default)
  - `s` → Scientific
  - `f` → Fahrenheit
- **language** – Optional ISO 2-letter language code for localized responses.
- **callback** – Optional JSONP callback function.

---

## /forecast

The **Forecast endpoint** provides weather predictions for up to **14 days into the future**.


### Query Parameters

- **forecast_days** – Number of forecast days (1–14).
- **hourly** – Include hourly forecast:
  - `1` → include hourly data
  - `0` → exclude hourly data (default)
- **interval** – Hourly forecast interval:
  - `1`, `3`, `6`, `12`, `24`
- **units** – Units system (`m`, `s`, `f`).
- **language** – ISO language code.
- **callback** – Optional JSONP callback.

---

## /historical

The **Historical endpoint** provides weather data for past dates (from 2015 onwards).

This endpoint can be used to analyze weather conditions affecting past flight operations.


### Query Parameters

- **historical_date_start** – Start date for historical time series.
- **historical_date_end** – End date for time series (max 60 days).
- **hourly** – Include hourly breakdown (`0` or `1`).
- **interval** – Hourly interval (`1`, `3`, `6`, `12`, `24`).
- **units** – Units system (`m`, `s`, `f`).
- **language** – Optional ISO language code.
- **callback** – Optional JSONP callback.

---



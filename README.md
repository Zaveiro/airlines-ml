# airlines-ml  


Build a reporting and exploration platform for air traffic based on batch ingestions from an aviation API.  
The system stores periodic snapshots of flight states and enables analysis and visualization through dashboards and APIs.

## Project Goal

The objective is to approximate an air traffic monitoring system (similar in concept to Flightradar24) using periodic data snapshots rather than real-time streaming.

## Batch Data Pipeline

The ingestion pipeline runs at regular intervals:

- A snapshot every **5, 10, 15, or 30 minutes**
- Store the state of flights
- Reconstruct an **approximate air traffic map**
- Generate analytics such as:
  - traffic by geographic area
  - arrivals and departures
  - delays
  - airport activity
  - temporal trends

## APIs Used (APILayer)

### Aviation Data Source

- **Aviationstack**
  Primary source of aviation data including flight status, schedules, airlines, airports, and routes.

### Data Enrichment APIs (APILayer)

- **Positionstack**  
  Geocoding and reverse geocoding for geographic enrichment of airports and flight locations.

- **Weatherstack**  
  Weather conditions (current weather, historical data, and forecasts) for origin and destination airports.

- **IPstack (optional)**  
  Used only for user experience, such as detecting the user's location.

## Data Storage Strategy

Since the APIs return **JSON** and flight states represent **variable data**, the architecture uses:

- **MongoDB**  
  Primary storage for batch snapshots of flight states.

- **SQL database**  
  Used for structured and derived data suitable for reporting and dashboards.

This approach allows preserving the original API payloads while enabling efficient analytical queries.
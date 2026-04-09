# Comic-Con Parking System - ER Diagram

ER diagram for a multi-zone event parking facility managing vehicles,
spot allocation, sessions, tickets and payments across Comic-Con India.

---

## Entities

| Entity | Purpose |
|---|---|
| VehicleCategory | BIKE, CAR, SUV, CAB, EV |
| Vehicle | Vehicle details and owner info |
| ParkingZone | Top level zone in the facility |
| ParkingLevel | A level within a zone |
| SpotCategory | GENERAL, VIP, EXHIBITOR, STAFF, EV_CHARGING, COSPLAYER |
| ParkingSpot | Individual spot inside a level |
| ParkingSession | One entry-to-exit cycle for a vehicle at a spot |
| ParkingTicket | Ticket issued at session start |
| Payment | Payment record per session |

---

## Key Relationships

- ParkingZone → ParkingLevel : one to many
- ParkingLevel → ParkingSpot : one to many
- Vehicle → ParkingSession : one to many
- ParkingSpot → ParkingSession : one to many
- ParkingSession → ParkingTicket : one to one
- ParkingSession → Payment : one to one

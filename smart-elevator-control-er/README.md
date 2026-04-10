# Smart Elevator Control - ER Diagram

ER diagram for LiftGrid Systems, a multi-building intelligent elevator
control platform managing elevators, floor requests, ride allocation,
status monitoring and maintenance tracking.

---

## Entities

| Entity | Purpose |
|---|---|
| Building | A commercial building connected to the platform |
| Floor | Each floor inside a building |
| Elevator | One elevator unit inside a building |
| ElevatorFloor | Junction table linking elevators to the floors they serve |
| ElevatorStatus | Live operational state of each elevator, kept separate |
| FloorRequest | A ride request generated from a floor |
| RideAllocation | Links a floor request to the elevator assigned to handle it |
| RideLog | Completed trip record used for analytics |
| MaintenanceLog | History of all maintenance events per elevator |

---

## Key Relationships

- Building → Floor : one to many
- Building → Elevator : one to many
- Elevator → Floor : many to many via ElevatorFloor
- Elevator → ElevatorStatus : one to one
- Floor → FloorRequest : one to many
- FloorRequest → RideAllocation : one to one
- Elevator → RideAllocation : one to many
- RideAllocation → RideLog : one to one
- Elevator → MaintenanceLog : one to many

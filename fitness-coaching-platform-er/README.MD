# Online Fitness Coaching Platform - ER Diagram

ER diagram for an online coaching business where trainers sell plans, schedule sessions, and track client progress.

---

## Entities

| Entity | Purpose |
|---|---|
| User | Both trainers and clients, separated by role field |
| CoachingPlan | Plans created and sold by a trainer |
| Subscription | Tracks which client bought which plan |
| Session | Scheduled live calls or consultations |
| CheckIn | Weekly check-in form submitted by client |
| ProgressLog | Raw body measurements tracked over time |
| TrainerNote | Trainer feedback on a client |
| Payment | Payment record per subscription |

---

## Key Relationships

- User (trainer) → CoachingPlan : one to many
- User (client) → Subscription → CoachingPlan : many to many
- User (trainer) + User (client) → Session : two FKs in one table
- User (client) → CheckIn → tied to Subscription
- User (client) → ProgressLog : one to many
- Subscription → Payment : one to one

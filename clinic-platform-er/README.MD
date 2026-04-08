# Clinic Appointment and Diagnostics Platform - ER Diagram

ER diagram for a clinic managing doctors, patients, appointments, consultations, diagnostic tests, reports, and payments.

---

## Entities

| Entity | Purpose |
|---|---|
| Patient | Stores patient details |
| Doctor | Stores doctor details and specialty |
| Department | Specialty or department a doctor belongs to |
| Appointment | A booking made by a patient with a doctor |
| Consultation | The actual visit that happens after an appointment |
| DiagnosticTest | Catalogue of available tests in the clinic |
| PrescribedTest | Junction table linking a consultation to ordered tests |
| TestReport | Report generated after a test is completed |
| Payment | Payment record per consultation |

---

## Key Relationships

- Department → Doctor : one to many
- Patient → Appointment : one to many
- Doctor → Appointment : one to many
- Appointment → Consultation : one to one
- Consultation → PrescribedTest → DiagnosticTest : many to many
- PrescribedTest → TestReport : one to one
- Consultation → Payment : one to one

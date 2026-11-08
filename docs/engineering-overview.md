# ServisPro engineering overview

ServisPro separates the customer, workshop and administrator experiences in the React frontend. ASP.NET Core controllers serve the application’s REST endpoints, and Entity Framework Core maps the relational model to SQL Server.

## Booking and follow-through

1. A customer picks a workshop, a service and a registered vehicle, then requests an appointment.
2. Workshop staff review appointments alongside their calendar and closed days. The workshop views distinguish upcoming bookings from work history.
3. The service history and review views let users revisit completed work. Admin views cover workshop review, vehicle and service catalogs, appointments, users, and reviews.

## Data model

- **Client and vehicle.** The client manages registered vehicles. Vehicle make and model are represented separately from a vehicle record.
- **Workshop and service type.** A workshop can offer multiple service types. The association is modeled separately from both the workshop and the service-type catalog.
- **Appointment and history.** Appointments capture booking activity. Vehicle history is a separate record of service work. Calendar closures are modeled separately from appointments.
- **Communication.** Conversations and messages have separate records. The frontend has distinct conversation views for customers and workshops.

This summary is a conceptual guide to the code. Use the [requirements model](../Specifikacija_zahteva_ServisPro.mdj) and [architecture model](../DetaljniArhitekturniProjekat.mdj) for the original diagrams.

## Design boundaries

The frontend groups pages by role. The API groups operations around responsibilities such as client bookings, workshop bookings and calendar management. SQL Server holds shared records, including catalogs used by more than one role.

The [test specification](../PSD_AV07_Test_specifikacija.docx) describes the original planned checks. It does not establish current automated test coverage or production readiness. See the [document index](../README.md#documentation-index) for the full course deliverables.

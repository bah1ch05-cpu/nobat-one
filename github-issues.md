# Architectural Design Document — Nobat One

## 1. Architecture Overview
Nobat One uses a simple client-server architecture.

### Main actors
- Customer
- Business staff
- Notification provider

### Main system parts
- Customer UI
- Business Dashboard
- Backend API
- PostgreSQL database
- Notification gateway

## 2. C4 Model
The following diagrams are included in `docs/diagrams/`:
- `c4-context.png`
- `c4-container.png`
- `c4-component.png`

## 3. Technology Stack Justification
### Frontend
**React** is suitable for reusable UI components and future scaling into a real product.

### Backend
**Node.js + Express** is lightweight, easy to prototype, and widely used for REST APIs.

### Database
**PostgreSQL** is a strong choice for structured business and queue data.

## 4. ADRs (Architecture Decision Records)
### ADR-001: Use web-first MVP
**Decision:** Build the MVP as a browser-based prototype.  
**Reason:** Faster development and easier live demonstration.

### ADR-002: Use REST API
**Decision:** Use REST endpoints for queue operations.  
**Reason:** Simpler than GraphQL for a midterm scope.

### ADR-003: Centralized queue logic in backend service
**Decision:** Place queue calculation and notification rules in a backend service layer.  
**Reason:** Keeps business logic consistent and easier to maintain.

## 5. Data Model
Main entities:
- users
- businesses
- queues
- queue_entries
- reservations
- notifications

See `docs/diagrams/erd.png`.

## 6. API Endpoints
### Customer endpoints
- `GET /api/businesses`
- `GET /api/businesses/:id`
- `POST /api/queue/join`
- `GET /api/queue/status/:entryId`
- `POST /api/notifications/subscribe`

### Business endpoints
- `GET /api/dashboard/queue/:businessId`
- `POST /api/dashboard/call-next`
- `POST /api/dashboard/update-entry`
- `GET /api/dashboard/analytics/:businessId`

## 7. Design Patterns
### Singleton
Used for database connection or shared configuration.

### Factory
Can be used to create notification objects for push, SMS, or email.

### Facade
A queue facade can simplify calls across queue logic, reservation logic, and notifications.

## 8. SOLID Notes
- **Single Responsibility:** queue, notification, and business modules are separated.
- **Open/Closed:** notification providers can be extended.
- **Dependency Inversion:** controllers depend on service interfaces.

## 9. Live Demo Scope
For the midterm, the live demo focuses on:
- joining a queue
- checking queue status
- calling the next customer
- updating the dashboard list

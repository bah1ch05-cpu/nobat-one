# Requirements — Nobat One

## Functional Requirements
1. The system shall allow customers to join a queue online before arriving at the service location.
2. The system shall display the customer’s current queue position and estimated waiting time.
3. The system shall send notifications to customers when their turn is approaching.
4. The system shall allow businesses to view and manage the live queue in a dashboard.
5. The system shall allow staff to call the next customer in line.
6. The system shall allow businesses to define service type, opening hours, and queue rules.
7. The system shall store customer queue history and visit records.
8. The system shall support multiple business categories such as restaurants, barbershops, clinics, and car washes.

## Non-Functional Requirements
1. **Performance:** The system should respond to user requests in less than 2 seconds under normal load.
2. **Availability:** The system should maintain at least 99% uptime during business hours.
3. **Scalability:** The system should support at least 1000 concurrent users.
4. **Usability:** A new user should be able to join a queue within 1 minute without training.
5. **Security:** User data must be stored securely and transmitted over HTTPS.
6. **Maintainability:** The codebase should follow a modular structure and clear naming conventions.
7. **Compatibility:** The customer interface should work on modern mobile and desktop browsers.

## User Stories
1. As a customer, I want to join a queue remotely so that I do not need to wait physically.
2. As a customer, I want to see my queue position so that I know how long I still need to wait.
3. As a customer, I want to receive a notification before my turn so that I can arrive on time.
4. As a customer, I want to choose a business category so that I can find the right service faster.
5. As a business owner, I want to see all waiting customers so that I can manage service flow efficiently.
6. As a staff member, I want to call the next customer so that the queue moves smoothly.
7. As a business owner, I want to set queue rules and service slots so that operations fit my business type.
8. As a business owner, I want to view queue history so that I can analyze busy hours and customer demand.

## Use Cases

### Use Case 1 — Join Queue
**Actor:** Customer  
**Precondition:** Customer has selected a business.

**Main Flow**
1. Customer opens the business page.
2. Customer clicks **Join Queue**.
3. System registers the customer in the queue.
4. System shows queue position and estimated waiting time.

**Acceptance Criteria**
- Customer is added to the active queue successfully.
- Queue position is displayed immediately.
- Estimated waiting time is visible.

### Use Case 2 — Call Next Customer
**Actor:** Staff / Business  
**Precondition:** At least one customer is waiting in the queue.

**Main Flow**
1. Staff opens the business dashboard.
2. Staff clicks **Call Next**.
3. System marks the first waiting customer as called.
4. System updates the queue for all users.

**Acceptance Criteria**
- The next customer is selected correctly.
- Queue order updates immediately.
- The called customer receives a notification.

### Use Case 3 — Receive Notification
**Actor:** Customer  
**Precondition:** Customer has already joined a queue.

**Main Flow**
1. Queue reaches a threshold.
2. System sends a notification to the customer.
3. Customer receives a message that the turn is approaching.

**Acceptance Criteria**
- Notification is sent before the customer’s turn.
- Notification contains business name and queue status.
- Customer can still view status in the app.

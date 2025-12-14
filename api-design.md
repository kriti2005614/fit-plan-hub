# API Design – Fit Plan Hub

This document explains the planned API structure and flow for the Fit Plan Hub platform.
The focus is on clarity of backend logic rather than implementation details.

---

## Authentication APIs

### 1. User / Trainer Signup
**Endpoint:** POST /signup  

**Description:**  
Used to register a new user or trainer.

**Request Body:**
- name
- email
- password
- role (user / trainer)

**Response:**
- success message
- user id

---

### 2. Login
**Endpoint:** POST /login  

**Description:**  
Authenticates a user and returns an access token.

**Request Body:**
- email
- password

**Response:**
- JWT token
- user role

---

## Trainer APIs

### 3. Create Fitness Plan
**Endpoint:** POST /plans  

**Access:** Trainer only  

**Description:**  
Allows a trainer to create a new fitness plan.

**Request Body:**
- title
- description
- price
- duration

---

### 4. View Own Plans
**Endpoint:** GET /plans/my  

**Access:** Trainer only  

**Description:**  
Returns all fitness plans created by the logged-in trainer.

---

### 5. Update Plan
**Endpoint:** PUT /plans/:planId  

**Access:** Trainer only  

**Description:**  
Used to update an existing fitness plan.

---

### 6. Delete Plan
**Endpoint:** DELETE /plans/:planId  

**Access:** Trainer only  

**Description:**  
Deletes a fitness plan created by the trainer.

---

## User APIs

### 7. View All Plans
**Endpoint:** GET /plans  

**Access:** User  

**Description:**  
Shows all available fitness plans.

- Non-subscribed users see limited details (title, trainer name, price)
- Subscribed users see full plan details

---

### 8. Subscribe to a Plan
**Endpoint:** POST /subscribe/:planId  

**Access:** User  

**Description:**  
Simulates subscription to a fitness plan.
No real payment gateway is used.

---

## Access Control Logic

- JWT token is required for protected routes
- Role-based access is enforced (user vs trainer)
- Subscription status controls visibility of plan details

---

## Notes
This API design focuses on core backend concepts such as authentication,
CRUD operations, and access control. Frontend integration can be added later.

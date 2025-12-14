# Fit Plan Hub

## Project Overview
Fit Plan Hub is a backend-focused project designed to understand how a fitness platform can work for trainers and users.  
In this platform, trainers can create fitness plans and users can explore and subscribe to those plans.  
The main goal of this project is to design the backend flow, database structure, and access control logic.

This project was created as part of an online task round.

---

## Tech Stack (Planned)
- Node.js
- Express.js
- MongoDB
- JWT for authentication

---

## User Roles
There are two types of users in the system:
1. Trainer – can create and manage fitness plans  
2. User – can view and subscribe to fitness plans  

---

## Core Features
- User and trainer signup/login
- Trainers can create, update, and delete fitness plans
- Users can view all available plans
- Subscription-based access to detailed fitness plans
- Role-based access control (trainer vs user)

---

## Database Design
### User
- Name
- Email
- Password (stored in hashed form)
- Role (user or trainer)

### Plan
- Title
- Description
- Price
- Duration
- Trainer ID (reference to trainer)

### Subscription
- User ID
- Plan ID
- Subscription date

---

## API Design (High Level)
- POST /signup – Register user or trainer  
- POST /login – Login and receive authentication token  
- POST /plans – Trainer creates a new fitness plan  
- GET /plans – Users view available fitness plans  
- POST /subscribe/:planId – User subscribes to a plan  

---

## Access Control Logic
- Trainers can manage only their own fitness plans
- Users who are not subscribed can see only basic plan details
- Subscribed users can access full plan information

---

## What Is Implemented
- Backend system design
- Database schema planning
- API structure and flow
- Role-based access logic

---

## What Is Pending
- Frontend user interface
- Real payment gateway integration
- Advanced features like personalized feed and trainer follow system

---

## Learning Outcome
Through this project, I gained a better understanding of backend system design, database relationships, authentication flow, and how role-based access works in real-world applications.

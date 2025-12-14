# Database Schema – Fit Plan Hub

This document explains the database structure planned for the Fit Plan Hub project.
The main focus is to clearly represent relationships between users, trainers, fitness plans,
subscriptions, and follows.

The schema is designed to be simple, readable, and scalable.

---

## 1. Users Collection

This collection stores both regular users and trainers.

### Fields:
- _id (ObjectId)
- name (String)
- email (String, unique)
- password (String – hashed)
- role (String: "user" or "trainer")
- createdAt (Date)

---

## 2. Fitness Plans Collection

This collection stores all fitness plans created by trainers.

### Fields:
- _id (ObjectId)
- title (String)
- description (String)
- price (Number)
- duration (Number – days)
- trainerId (ObjectId – reference to Users)
- createdAt (Date)

### Relationship:
- One trainer can create multiple fitness plans (one-to-many)

---

## 3. Subscriptions Collection

This collection tracks which users have subscribed to which plans.

### Fields:
- _id (ObjectId)
- userId (ObjectId – reference to Users)
- planId (ObjectId – reference to Fitness Plans)
- subscribedAt (Date)

### Relationship:
- One user can subscribe to many plans
- One plan can have many subscribers
- This forms a many-to-many relationship

---

## 4. Trainer Follows Collection

This collection stores information about users following trainers.

### Fields:
- _id (ObjectId)
- userId (ObjectId – reference to Users)
- trainerId (ObjectId – reference to Users)
- followedAt (Date)

### Relationship:
- A user can follow multiple trainers
- A trainer can have multiple followers

---

## Summary

The database design focuses on:
- Clear separation of responsibilities
- Proper use of references between collections
- Supporting role-based access and subscriptions

This structure supports all core features of the Fit Plan Hub platform
and can be easily extended in the future.

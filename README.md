Entire code  will be uploaded to github after semster end date 12/15/2025. 
Original github is private

# 🧳 Group Travel Planner – SaaS Trip Coordination Platform

## 📌 Project Overview

Group Travel Planner is a **multi-module Ruby on Rails SaaS platform** designed to help users collaboratively plan group trips. Users can create itineraries, choose destinations, add hotels and flights, and invite others to join—either publicly or privately.

Built **Team 3** for **CS-UY 4513 – Software Engineering**, the platform supports multiple user roles and encourages social, shared trip planning.

---

## 🚀 Features

### **🔐 User & Identity Management**

* Secure email/password authentication
* Role-based authorization

  * **Users:** join itineraries, view trip details
  * **Organizers:** create and manage itineraries
  * **Admins:** full platform oversight, ability to ban users

### **🧭 Itinerary Management**

* Create and edit group trips
* Add hotels, flights, and destinations
* Public or private itineraries (password-protected private trips)
* Users can join existing itineraries

### **🔍 Search & Filtering**

* Search itineraries by keyword
* Filters include: date, party size, privacy level, and more

### **💬 Communication & Notifications**

* In-group messaging system
* Track message senders & recipients
* Support for itinerary-related notifications

---

## 🛠️ Tech Stack

* **Language:** Ruby
* **Framework:** Ruby on Rails
* **Database:** SQLite
* **Testing:** RSpec

---

## 📂 Project Modules

### **1. User Management & Authentication**

* Handles user registration, login, and profile data
* Assigns roles (User, Organizer, Admin)
* Core dependency for all other modules

### **2. Itinerary Management**

* Organizers can create and edit itineraries
* Users can join itineraries
* Supports linking flights and hotels
* Depends on User Management

### **3. Search & Filtering Management**

* Allows searching itineraries by keyword
* Filtering by date, privacy, group size, etc.
* Depends on Itinerary Management

### **4. Communication / Notification Management**

* Stores and retrieves messages within itineraries
* Supports user notifications
* Depends on Itinerary Management

---

## 🗃️ Database Schema (Proposed)

### **Users & Roles**

* Users(UserID, FirstName, LastName, Username, Password, Age, Gender)
* Roles(RoleID, RoleName, RolePermissions)
* UserRoles(UserRoleID, UserID, RoleID)

### **Itinerary System**

* ItineraryGroup(ItineraryGroupID, GroupName, Date, Location, IsPrivate, OrganizerID)
* Hotels(HotelID, Name, Location, Rating, Cost, ArrivalTime, DepartureTime)
* Flights(FlightID, FlightNumber, DepartureLocation, ArrivalLocation, DepartureTime, ArrivalTime, Cost)
* Itinerary_Attendees(UserID, ItineraryGroupID)
* Itinerary_Hotels(HotelID, ItineraryGroupID)
* Itinerary_Flights(FlightID, ItineraryGroupID)

### **Communication System**

* Messages(MessageID, UserID, ItineraryGroupID, Text, Time, IsRead)

---

## 📡 API Overview

### **User & Identity Management API**

* `POST /api/user/register`
* `POST /api/user/login`
* `GET /api/user/:id`
* `GET /api/user/:id/roles`
* `POST /api/user/:id/roles/:role_id`

### **Itinerary Management API**

* `GET /api/itineraries/`
* `GET /api/itineraries/create`
* `POST /api/itineraries/create`
* `POST /api/itineraries/update/:id&:user_id`

### **Search / Filtering API**

* `GET /api/itineraries/search`
* `POST /api/itineraries/search?<keyword_args>`

### **Communication / Notification API**

* `GET /api/messages/:user_id&:group_id`
* `POST /api/messages/:user_id&:group_id`
* `GET /api/notifications/:user_id&:new_or_all`

---

## 📦 Deliverables  -
1. **Complete Source Code**
2. **README.md Documentation**
3. **API Documentation**
4. **Final Presentation & Demo**

---

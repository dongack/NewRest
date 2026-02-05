# Newrest — Android Food Ordering App (School Restaurant)

Android app that helps students **pre-order meals** from the school restaurant and helps the restaurant **anticipate demand** (reduce waste, avoid stockouts).

---

## Table of Contents
- [Overview](#overview)
- [Problem](#problem)
- [Solution](#solution)
- [Key Features](#key-features)
- [Screens / Activities](#screens--activities)
- [Tech Stack](#tech-stack)
- [Firebase Database Structure](#firebase-database-structure)
- [Project Structure](#project-structure)
- [Setup & Installation](#setup--installation)
- [Usage](#usage)
- [Constraints / Notes](#constraints--notes)
- [Roadmap](#roadmap)
- [Contributing](#contributing)
- [License](#license)
- [Acknowledgements](#acknowledgements)

---

## Overview
**NewrestECC** is a mobile ordering system built to improve the daily workflow of a school restaurant:
- Students can **register/login**, **browse the menu**, **select dishes**, and **place an order**.
- The restaurant can consult orders stored in **Firebase** to better plan production.

---

## Problem
The restaurant often faces:
- **overproduction / underproduction** because daily demand is hard to estimate
- student frustration when dishes run out too early

A previous solution (shared daily Excel file) was limited and inconvenient.

---

## Solution
A simple Android ordering app where:
- students **reserve meals in advance** (before a cutoff time)
- orders are stored in a centralized database (Firebase)
- the restaurant can **see demand per dish** early enough to adjust production

---

## Key Features
- **Authentication**
  - Sign up (phone number, name, password)
  - Sign in (phone number, password)
- **Menu browsing**
  - Categories: **Entrées**, **Plats**, **Desserts**
  - Dish listing per category
  - Dish detail view (description + selection)
- **Cart & Order**
  - Add dishes to cart
  - Order summary (items + total price)
  - Order status / history
  - Constraint: **1 order per day** (as described in the project report)
- **Admin (via Firebase Console)**
  - Menu updates + order consultation directly from Firebase console

---

## Screens / Activities
The application is organized around the following activities:
1. **MainActivity** — Welcome screen: Login / Register  
2. **SignIn** — Login (phone + password)  
3. **SignUp** — Registration (phone + name + password)  
4. **Home** — Categories (Entrée / Plat / Dessert)  
5. **FoodList** — Dishes list for a selected category  
6. **FoodDetail** — Dish details + add to cart  
7. **Cart** — Selected items + order summary  
8. **OrderStatus** — Order history/status (+ daily ordering rule)

---

## Tech Stack
- **Android Studio**
- **Java (Android)**
- **Firebase Realtime Database** (menu + users + orders)
- UI components based on Android layouts + RecyclerView pattern

---

## Firebase Database Structure
Firebase nodes used in the project:

### `Category`
Stores the 3 menu categories:
- `Name`
- `Image` (URL)

### `Food`
Stores dishes:
- `Name`
- `Description`
- `Price`
- `CategoryId` (or equivalent link to category)

### `User`
Stores users:
- `Phone` (identifier)
- `Name`
- `Password`

### `Requests`
Stores orders:
- `Name`
- `Phone`
- `Total`
- `Status` (picked up / not picked up, etc.)
- Ordered items (depending on your implementation)



---

## Project Structure
A typical structure looks like:



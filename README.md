# Marketplace Jasa

## Overview

Proyek ini merupakan sistem marketplace jasa yang dikembangkan menggunakan Node.js, Express.js, TypeScript, dan MySQL. Sistem ini dirancang untuk mendukung proses pengelolaan layanan jasa secara online, mulai dari autentikasi pengguna, pengelolaan layanan, proses booking, hingga sistem review dan analitik sederhana.

Project ini dibuat dengan pendekatan layered architecture agar struktur kode lebih rapi, mudah dikembangkan, dan lebih mudah dipelihara untuk pengembangan jangka panjang.

---

# Fitur Utama

## Authentication & Authorization

- JWT Authentication
- Protected Routes
- Ownership Validation
- bcrypt Password Hashing
- Login & Registration

## Service Marketplace

- Create Service Listings
- Update & Delete Services
- Service Categories
- Service Search & Filtering
- Service Image Upload

## Booking System

- Create Bookings
- Booking Workflow
- Booking Status Management
- Seller Authorization

## Review System

- Rating & Review Feature
- Booking Validation Before Review
- Review Retrieval Per Service

## User Profile

- Profile Management
- Avatar Upload
- Seller Bio
- Location & Contact Information

## Dashboard Analytics

- Total Users
- Total Services
- Total Bookings
- Total Reviews
- Top Rated Services

## Backend Architecture

- Layered Architecture
- Service Layer
- Middleware Layer
- Config Layer
- Centralized Error Handling
- Environment Validation

---

# Tech Stack

| Technology | Purpose                   |
| ---------- | ------------------------- |
| Node.js    | Runtime Environment       |
| Express.js | Backend Framework         |
| TypeScript | Strongly Typed JavaScript |
| MySQL      | Relational Database       |
| JWT        | Authentication            |
| bcrypt     | Password Hashing          |
| Multer     | File Upload               |
| Swagger UI | API Documentation         |
| mysql2     | Database Driver           |
| dotenv     | Environment Variables     |

---

# System Architecture

```text
Routes
  ↓
Middleware
  ↓
Controllers
  ↓
Services
  ↓
Database
```

## Folder Structure

```text
src/
├── config/
├── constants/
├── controllers/
├── middleware/
├── routes/
├── services/
├── utils/
├── app.ts
├── server.ts
```

---

# Database Schema

## users

| Column   | Type    |
| -------- | ------- |
| id       | INT     |
| username | VARCHAR |
| email    | VARCHAR |
| password | VARCHAR |
| bio      | TEXT    |
| avatar   | VARCHAR |
| phone    | VARCHAR |
| location | VARCHAR |

---

## categories

| Column | Type    |
| ------ | ------- |
| id     | INT     |
| name   | VARCHAR |

---

## services

| Column      | Type    |
| ----------- | ------- |
| id          | INT     |
| title       | VARCHAR |
| price       | INT     |
| user_id     | INT     |
| category_id | INT     |
| image       | VARCHAR |

---

## bookings

| Column     | Type    |
| ---------- | ------- |
| id         | INT     |
| service_id | INT     |
| buyer_id   | INT     |
| status     | VARCHAR |

---

## reviews

| Column      | Type      |
| ----------- | --------- |
| id          | INT       |
| service_id  | INT       |
| reviewer_id | INT       |
| rating      | INT       |
| comment     | TEXT      |
| created_at  | TIMESTAMP |

---

# Installation Guide

## 1. Clone Repository

```bash
git clone <github-repository-link>
```

---

## 2. Enter Project Folder

```bash
cd backend
```

---

## 3. Install Dependencies

```bash
npm install
```

---

## 4. Configure Environment Variables

Create a `.env` file:

```env
PORT=5000

JWT_SECRET=mysecretkey

DB_HOST=localhost
DB_USER=root
DB_PASSWORD=
DB_NAME=proyeksa_db
```

---

## 5. Run Development Server

```bash
npm run dev
```

---

# API Base URL

```text
http://localhost:5000/api/v1
```

---

# API Endpoints

# Authentication

| Method | Endpoint        |
| ------ | --------------- |
| POST   | /users/register |
| POST   | /users/login    |
| GET    | /users/me       |
| PUT    | /users/me       |

---

# Services

| Method | Endpoint      |
| ------ | ------------- |
| GET    | /services     |
| GET    | /services/:id |
| POST   | /services     |
| PUT    | /services/:id |
| DELETE | /services/:id |

---

# Bookings

| Method | Endpoint                    |
| ------ | --------------------------- |
| POST   | /bookings/:serviceId        |
| GET    | /bookings                   |
| PUT    | /bookings/:bookingId/status |

---

# Reviews

| Method | Endpoint            |
| ------ | ------------------- |
| POST   | /reviews/:serviceId |
| GET    | /reviews/:serviceId |

---

# Dashboard

| Method | Endpoint         |
| ------ | ---------------- |
| GET    | /dashboard/stats |

---

# Authentication Flow

```text
User Login
    ↓
Backend Generates JWT Token
    ↓
Frontend Stores Token
    ↓
Frontend Sends Bearer Token
    ↓
Protected Route Access
```

---

# Authorization System

The system uses ownership validation to ensure:

- Only service owners can edit/delete services
- Only sellers can update booking status
- Only buyers who booked a service can leave reviews

---

# Search & Filter

## Search Example

```text
GET /api/v1/services?search=logo
```

## Category Filter Example

```text
GET /api/v1/services?category=Graphic Design
```

---

# File Upload

The project uses Multer for image uploads.

Uploaded files are stored inside:

```text
/uploads
```

Example image URL:

```text
http://localhost:5000/uploads/example.png
```

---

# Error Handling

The project uses centralized error handling with custom AppError middleware.

Example response:

```json
{
  "success": false,
  "message": "Service not found"
}
```

---

# Future Improvements

- Real-time Chat
- Payment Gateway Integration
- Email Verification
- Push Notifications
- Cloud Storage Integration
- Admin Dashboard
- Service Favorites
- Recommendation System

---

# Dokumentasi API

Project ini menggunakan endpoint API berbasis REST untuk komunikasi antara backend dan frontend.

Dokumentasi endpoint utama telah dituliskan pada bagian Endpoint API untuk mempermudah proses testing dan integrasi frontend.

---

# Conclusion

Proyek Marketplace Jasa ini dikembangkan sebagai simulasi backend marketplace jasa dengan penerapan konsep software architecture modern seperti layered architecture, middleware, relational database, authentication, authorization, dan centralized error handling.

Selain fokus pada fitur marketplace, project ini juga menekankan struktur backend yang rapi dan scalable agar lebih mudah dikembangkan pada tahap berikutnya.


# SkillMentor – Online Mentoring Platform

![React](https://img.shields.io/badge/Frontend-React-blue)
![Spring Boot](https://img.shields.io/badge/Backend-SpringBoot-green)
![PostgreSQL](https://img.shields.io/badge/Database-PostgreSQL-blue)
![Clerk](https://img.shields.io/badge/Auth-Clerk-purple)
![Vercel](https://img.shields.io/badge/Deploy-Vercel-black)
![Render](https://img.shields.io/badge/API-Render-orange)

SkillMentor is a full-stack online mentoring platform that connects students with expert mentors for specialised subjects.

Students can browse mentors, explore their expertise, schedule one-on-one sessions, upload payment confirmations, and track their learning progress through a personalised dashboard.

The platform also provides an admin dashboard for managing mentors, subjects, and student bookings.

---

# Live Demo

Frontend  
https://skillmentor-frontend-zeta.vercel.app/

Backend API (Swagger) 

https://skill-mentor-springboot-backend.onrender.com/swagger-ui/index.html 

Repository  

https://github.com/thinethwic/skillmentor-platform.git

---

# Project Overview

SkillMentor demonstrates modern full-stack development practices including:

- REST API development
- Role-based authentication
- Complex entity relationships
- Production deployment
- Responsive UI design

---

# Features

## Student Features

- Secure authentication using Clerk
- Browse mentors and subjects
- View detailed mentor profiles
- Schedule mentoring sessions
- Select session date and duration
- Upload bank payment slip
- Track session status
- Personal dashboard
- Write reviews after completed sessions
- Prevent double booking

---

## Admin Features

Admin users can access an Admin Dashboard with management tools.

- Create subjects
- Create mentor profiles
- Assign subjects to mentors
- View all bookings
- Confirm payment submissions
- Mark sessions as completed
- Manage meeting links
- Platform analytics overview

---

# Tech Stack

| Layer | Technology |
|------|-----------|
Frontend | React, TypeScript, Vite |
UI | Tailwind CSS, shadcn/ui |
Backend | Spring Boot |
Authentication | Clerk |
Database | PostgreSQL (Supabase) |
Deployment | Vercel + Render |
Validation | Zod + React Hook Form |

---


Authentication is handled by Clerk JWT tokens, verified by Spring Boot using JWKS keys.

---

# User Roles

## Student

Default authenticated user.

Capabilities:

- View mentors
- Book mentoring sessions
- Upload payment proof
- Track session status
- Leave mentor reviews

---

## Admin

Users with Clerk metadata:


# System Architecture

React Frontend (Vite + Tailwind)
│
│ REST API
▼
Spring Boot Backend
│
│ JPA / Hibernate
▼
PostgreSQL Database (Supabase)



Authentication is handled by Clerk JWT tokens, verified by Spring Boot using JWKS keys.

---

# User Roles

## Student

Default authenticated user.

Capabilities:

- View mentors
- Book mentoring sessions
- Upload payment proof
- Track session status
- Leave mentor reviews

---

## Admin

Users with Clerk metadata:

publicMetadata.role = "admin"


Capabilities:

- Manage mentors
- Manage subjects
- Manage bookings
- Confirm payments
- Mark sessions completed

---

# Project Structure

skillmentor-platform
│
├── frontend
│ ├── src
│ │ ├── components
│ │ ├── pages
│ │ ├── layouts
│ │ ├── hooks
│ │ ├── lib
│ │ └── types
│ └── package.json
│
├── backend
│ ├── src/main/java/com/skillmentor
│ │ ├── controllers
│ │ ├── services
│ │ ├── repository
│ │ ├── entity
│ │ ├── dtos
│ │ └── configs
│ └── pom.xml
│
└── README.md


---

# Local Development Setup

## Clone Repository

git clone https://github.com/thinethwic/skillmentor-platform.git

cd skillmentor-platform


---

# Backend Setup (Spring Boot)

Navigate to backend folder

cd backend


Backend runs on

http://localhost:8081


Swagger API

http://localhost:8081/swagger-ui.html


---

# Frontend Setup (React)

Navigate to frontend folder

cd frontend


Install dependencies

npm install


Run development server

npm run dev


Frontend runs on

http://localhost:3001


---

# Environment Variables

## Frontend (.env)

VITE_API_BASE_URL=http://localhost:8081

VITE_CLERK_PUBLISHABLE_KEY=pk_test_ZW5oYW5jZWQtc2N1bHBpbi0xMy5jbGVyay5hY2NvdW50cy5kZXYk


---

## Backend (application.properties)

spring.datasource.url=jdbc:postgresql://host:5432/skillmentor
spring.datasource.username=your_username
spring.datasource.password=your_password

clerk.jwks.url=(https://enhanced-sculpin-13.clerk.accounts.dev/.well-known/jwks.json)

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true


---

# API Endpoints

## Mentors

| Method | Endpoint | Description |
|------|------|------|
GET | /api/v1/mentors | Get all mentors |
GET | /api/v1/mentors/{id} | Get mentor profile |

---

## Sessions

| Method | Endpoint | Description |
|------|------|------|
POST | /api/v1/sessions/enroll | Book mentoring session |
GET | /api/v1/sessions/my-sessions | Get student sessions |

---

## Admin

| Method | Endpoint | Description |
|------|------|------|
POST | /api/v1/subjects | Create subject |
POST | /api/v1/mentors | Create mentor |
GET | /api/v1/admin/sessions | Get all bookings |
PATCH | /api/v1/admin/sessions/{id}/confirm-payment | Confirm payment |
PATCH | /api/v1/admin/sessions/{id}/complete | Mark session complete |

---

# Mentor Discovery

The platform includes an enhanced mentor discovery system.

Features include:

- Dedicated mentor profile pages
- Subject enrollment statistics
- Student reviews and ratings
- Direct session booking

Example route:

/mentors/:mentorId


---

# Booking Validation Rules

The backend ensures valid bookings.

Rules include:

- Cannot book sessions in the past
- Cannot double book sessions
- Cannot book the same mentor at overlapping times
- Cannot duplicate subject sessions

If conflicts occur, the API returns a clear error message.

---

# Deployment

## Frontend

Deployed using Vercel

Example:
https://skillmentor-frontend-zeta.vercel.app/


---

## Backend

Deployed using Render

Example:
https://skill-mentor-springboot-backend.onrender.com


---

# Database

Database hosted on Supabase PostgreSQL.

Main tables include:

- mentor
- subject
- student
- session

Seed data includes:

- 3 mentors
- 5 subjects

---

# Future Improvements

- Real-time mentor availability calendar
- Online payment gateway integration
- Video session integration
- Messaging between students and mentors
- Advanced analytics dashboard

---

# Author

Thineth Wick  
BHSc IT – Final Year Student

Users with Clerk metadata:

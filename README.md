
# Real-Time Analytics Service API

A **scalable, event-driven real-time analytics backend** built with **NestJS**, designed to track, process, and broadcast live user events with low latency. The system supports **JWT-based authentication**, **role-based authorization**, **PostgreSQL-based persistence**, and **real-time data streaming via WebSockets (Socket.IO)**.

---

## Overview

This service enables **real-time event tracking and analytics processing** for modern web and mobile applications. It collects user-generated events such as **page views, clicks, logins, and custom actions**, stores them efficiently, and broadcasts them instantly to connected clients for **live dashboards, monitoring systems, and analytics pipelines**.

The architecture is designed with **scalability, low-latency, and modularity** in mind, following **clean architecture and event-driven design principles**.

---

##  Key Features

-  **JWT-based Authentication & Authorization**
  - Secure user registration and login
  - Role-based access control

- **Real-Time Analytics Event Tracking**
  - Capture user events such as page views, clicks, and logins
  - Extensible event schema for custom analytics needs

-  **Live Data Streaming via WebSockets (Socket.IO)**
  - Instantly broadcast analytics events to connected clients
  - Suitable for real-time dashboards and monitoring tools

-  **Persistent Storage with PostgreSQL**
  - Reliable and scalable event storage using TypeORM
  - Optimized schema design for analytical workloads

-  **Modular & Scalable Architecture**
  - Clean separation of concerns
  - Designed for horizontal scaling and high-throughput systems

---

## System Architecture



                
Client ────────▶   REST API            
            ┌──────────┴──────────┐
            ↓                     ↓
 
        Business            WebSocket    
         Logic               Server       
  
          ↓                      ↓
      PostgreSQL            Live Analytics
               
                              Dashboard


A NestJS-based backend application for tracking and broadcasting real-time user events. It supports JWT authentication, PostgreSQL for data storage, and WebSocket (Socket.IO) for live event streaming to connected clients.

PostgreSQL User & Database Setup

The following commands create a new PostgreSQL user and database, 
and grant the necessary privileges for application access.
(
CREATE USER nest_user WITH ENCRYPTED PASSWORD 'password123';
CREATE DATABASE analytics_db;
GRANT ALL PRIVILEGES ON DATABASE analytics_db TO nest_user;
\c analytics_db
GRANT ALL PRIVILEGES ON SCHEMA public TO nest_user;
ALTER DEFAULT PRIVILEGES IN SCHEMA public GRANT ALL ON TABLES TO nest_user;
ALTER DEFAULT PRIVILEGES IN SCHEMA public GRANT ALL ON SEQUENCES TO nest_user;)


Features

User registration & login with JWT

Role-based authentication (user)

Track analytics events (page views, clicks, logins, etc.)

Store events in PostgreSQL

Real-time event broadcasting via WebSockets

 Tech Stack

NestJS

TypeORM

PostgreSQL

Socket.IO

 Installation
# Install dependencies
npm install

# Run the app (development)
npm run start:dev

 Authentication

Use /auth/register to create an account

Use /auth/login to get a JWT token

Add Authorization: Bearer <token> header for protected routes

 WebSocket

Connect via Socket.IO

Listen for real-time events on channel: event

Emit new events to newEvent







# 🎫 IT Ticket Manager

> RESTful API for IT incident and technical support management built with Java and Spring Boot.

🚧 **Project Status: In Development**

---

## 📌 Overview

**IT Ticket Manager** is a backend service designed to manage enterprise IT incidents and support workflows.

The application enables logging, retrieving, and updating technical support tickets, categorizing them by priority and status, and tracking incident lifecycles through threaded user comments.

Example incident lifecycle:

```text
OPEN → IN_PROGRESS → RESOLVED
```

This project represents the architectural evolution of my Vocational Degree (DAM) Capstone Project, **TaskMaster Flow**, transitioning from a standalone desktop application built with JavaFX and raw JDBC to a scalable, distributed backend based on RESTful microservices.

The primary objective is to deepen practical expertise across the Java enterprise ecosystem and master modern Spring Boot patterns through an end-to-end implementation.

---

## 🎯 Engineering Goals

Key architectural patterns and core concepts explored throughout this project:

- REST API development and design with Spring Boot.
- Clean layered architecture (Controller-Service-Repository).
- Object-Relational Mapping (ORM) and persistence with Spring Data JPA & Hibernate.
- Data Transfer Object (DTO) pattern design and mapping.
- Declarative input validation (Bean Validation / Jakarta).
- Global exception handling and RFC 7807 problem details.
- Automated testing (unit and integration tests).
- Authentication and role-based access control (RBAC).
- Multi-container orchestration using Docker Compose.
- Self-documenting interactive API contracts with OpenAPI / Swagger.

The engineering focus is not merely using these frameworks, but understanding the responsibilities, lifecycle, and design trade-offs of each layer within enterprise backend systems.

---

## 🛠️ Tech Stack

### Core Foundation

- **Java 21**
- **Spring Boot**
- **Spring Web**
- **Spring Data JPA**
- **PostgreSQL**
- **Maven**

### Tools & Libraries in Progress

- **Bean Validation (Hibernate Validator)**
- **JUnit 5**
- **Mockito**
- **Spring Security**
- **JWT (JSON Web Tokens)**
- **Docker & Docker Compose**
- **Swagger / OpenAPI 3**

---

## 🧱 Architecture

The system follows a strict layered architecture pattern:

```text
HTTP Request
     │
     ▼
Controller Layer
     │
     ▼
Service Layer
     │
     ▼
Repository Layer
     │
     ▼
PostgreSQL Database
```

Target package organization:

```text
src/main/java/...
│
├── controller/
├── service/
├── repository/
├── entity/
├── dto/
├── exception/
├── security/
└── config/
```

### Layer Responsibilities

**Controller Layer**
- Handles inbound HTTP traffic and deserializes request payloads.
- Validates client DTO inputs.
- Delegates business execution to domain services.
- Formats response envelopes and enforces semantic HTTP status codes.

**Service Layer**
- Encapsulates business logic, domain rules, and transactional boundaries (`@Transactional`).
- Orchestrates multi-repository queries.
- Manages bidirectional entity-to-DTO transformations.

**Repository Layer**
- Abstracted persistence interface using Spring Data JPA.
- Manages relational queries, derived lookups, and transaction persistence.

---

## ⚙️ Core Features

### 👤 Identity & Access Management

- User registration and account provisioning.
- Stateless authentication and JWT generation.
- Role-based authorization: `USER` and `ADMIN`.
- Secure password hashing with BCrypt.

### 🎫 Incident & Ticket Management

- Full CRUD lifecycle for support tickets.
- Categorization and priority assignment.
- Dynamic status transitions with validation rules.
- Multidimensional filtering (status, priority, category).
- Soft deletion / logical resolution of closed tickets.

Target ticket statuses:

```text
OPEN
IN_PROGRESS
RESOLVED
CLOSED
```

Priority levels:

```text
LOW
MEDIUM
HIGH
```

### 💬 Threaded Discussion & Comments

Authenticated users and technical staff can post audit-trailed comments to track resolution milestones and progress.

### 📊 Aggregated Metrics & Reporting

Dedicated reporting endpoints for incident resolution ratios, priority distribution, and custom analytics using optimized aggregated JPQL queries.

---

## 🔗 Target Endpoints

### Authentication

```http
POST /api/auth/register
POST /api/auth/login
```

### Ticket Management

```http
GET    /api/tickets
GET    /api/tickets/{id}
POST   /api/tickets
PUT    /api/tickets/{id}
DELETE /api/tickets/{id}
```

### Search & Filtering

```http
GET /api/tickets?status=OPEN
GET /api/tickets?priority=HIGH
```

### Metrics & Analytics

```http
GET /api/tickets/stats
```

---

## 🗃️ Data Model

Conceptual entity relationships:

```text
User 1 -------- N Ticket
User 1 -------- N Comment
Ticket N ------ 1 Category
Ticket 1 ------ N Comment
```

Core domain entities:

- `User`
- `Ticket`
- `Category`
- `Comment`

---

## 🗺️ Implementation Roadmap

### ✅ Phase 1 — Project Scaffold & Persistence
- [ ] Initialize Spring Boot starter project.
- [ ] Configure PostgreSQL datasource.
- [ ] Model domain JPA entities.
- [ ] Define Spring Data JPA repositories.
- [ ] Validate schema migrations and persistence baseline.

### 🌐 Phase 2 — REST API & Domain Logic
- [ ] Implement Ticket CRUD operations.
- [ ] Build business logic layer (`@Service`).
- [ ] Define Request / Response DTO contracts.
- [ ] Implement entity-DTO mapping logic.

### 🧪 Phase 3 — Validation & Automated Testing
- [ ] Add declarative validation using Jakarta Bean Validation.
- [ ] Centralize error handling with `@RestControllerAdvice`.
- [ ] Write unit tests with JUnit 5.
- [ ] Mock external dependencies with Mockito.

### 🔐 Phase 4 — Security & Access Control
- [ ] Configure Spring Security filter chain.
- [ ] Implement BCrypt password encoder.
- [ ] Integrate JWT token generation and validation filters.
- [ ] Restrict endpoint permissions based on `USER` and `ADMIN` roles.

### 🐳 Phase 5 — Containerization
- [ ] Author optimized multi-stage `Dockerfile`.
- [ ] Containerize application runtime.
- [ ] Configure multi-service orchestration with `docker-compose.yml`.
- [ ] Manage persistent database volumes and environment variables.

### 📚 Phase 6 — API Documentation
- [ ] Configure SpringDoc OpenAPI / Swagger UI.
- [ ] Document request/response contracts and schema schemas.
- [ ] Write local installation and deployment guides.
- [ ] Finalize technical documentation.

---

## 🚀 Getting Started

*Local development setup and execution instructions will be published upon completion of the initial baseline.*

---

## 📚 Technical Context

This project forms an integral part of my transition toward enterprise-grade Java backend development.

Having completed **TaskMaster Flow** as my DAM Capstone Project—building a desktop solution with Java, JavaFX, raw JDBC, and MySQL—this project represents the step toward modern distributed architectures, leveraging Spring Boot, RESTful services, JPA/Hibernate, PostgreSQL, and Docker.

---

## 👨‍💻 Author

**Ruben Flores**

GitHub: [@Rubenzt8](https://github.com/Rubenzt8)

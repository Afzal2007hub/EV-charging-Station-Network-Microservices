# ⚡ GreenCharge – EV Charging Station Network

> **A Spring Boot Microservices Capstone Project**
> **Find • Book • Charge • Pay**

![Java](https://img.shields.io/badge/Java-17-orange)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-3.x-brightgreen)
![Microservices](https://img.shields.io/badge/Microservices-Architecture-blue)
![H2](https://img.shields.io/badge/Database-H2-lightgrey)

---

## 📖 Overview

GreenCharge is a **Spring Boot Microservices** application that enables users to:

* 🔍 Find EV charging stations
* 📅 Book charging slots
* 🔌 Start & stop charging sessions
* 💳 Generate invoices & make payments
* 📜 View charging history

The project follows a **Layered Architecture** and uses **RestTemplate** for service-to-service communication.

---

## 📦 Microservices

| Service             | Port | Responsibility                         |
| ------------------- | ---- | -------------------------------------- |
| ⚡ Charging Station  | 8081 | Manage stations & connectors           |
| 📅 Booking          | 8082 | Book & cancel charging slots           |
| 🔌 Charging Session | 8083 | Start/Stop charging & calculate energy |
| 💳 Payment          | 8084 | Generate invoices & process payments   |

---

## 🛠 Tech Stack

* Java 17
* Spring Boot
* Spring Data JPA
* H2 Database
* RestTemplate
* Jakarta Validation
* Lombok & SLF4J
* Maven
* Postman

---

## 🏗 Project Structure

```text
controller
service
repository
entity
dto
client
config
exception
```

---

## ✨ Features

* ✅ CRUD Operations
* ✅ Bean Validation
* ✅ Global Exception Handling
* ✅ REST API Development
* ✅ RestTemplate Communication
* ✅ Structured Logging
* ✅ H2 Database
* ✅ Layered Architecture
* ✅ Duplicate Booking Prevention
* ✅ Automatic Cost Calculation

---

## 🔄 Communication Flow

```text
Client
   │
API Gateway
   │
Charging Session
   ├── Booking Service
   ├── Charging Station Service
   └── Payment Service
```

---

## 🌐 API Endpoints

### ⚡ Charging Station

* POST `/stations`
* GET `/stations`
* GET `/stations/{id}`

### 📅 Booking

* POST `/bookings`
* PUT `/bookings/{id}/cancel`

### 🔌 Charging Session

* POST `/charging/start`
* PUT `/charging/{id}/stop`
* GET `/charging/history/{customerId}`

### 💳 Payment

* POST `/payments`
* GET `/payments/{id}`

---

## ✅ Validation

* Station name required
* Valid connector type
* Battery: 0–100%
* Positive energy consumed
* Positive charging duration
* Future booking date
* Valid email & mobile number

---

## ⚠ Exception Handling

* StationNotFoundException
* BookingNotFoundException
* SlotUnavailableException
* ConnectorNotSupportedException
* LowBatteryException
* PaymentFailedException
* MethodArgumentNotValidException
* Global Exception Handler

---

## 🚀 Run the Project

```bash
mvn spring-boot:run
```

| Service | URL            |
| ------- | -------------- |
| Station | localhost:8081 |
| Booking | localhost:8082 |
| Session | localhost:8083 |
| Payment | localhost:8084 |

---

## 💾 H2 Console

| Service | Console                   |
| ------- | ------------------------- |
| Station | localhost:8081/h2-console |
| Booking | localhost:8082/h2-console |
| Session | localhost:8083/h2-console |
| Payment | localhost:8084/h2-console |

**Username:** `sa`
**Password:** *(blank)*

---

## 🧪 Testing

* ✔ Postman Collection
* ✔ API Documentation
* ✔ H2 Database
* ✔ Execution Screenshots

---

## 📂 Deliverables

* Source Code
* README
* Postman Collection
* Architecture Diagram
* API Documentation
* SQL Script
* Screenshots

---

## 👨‍💻 Author

**Mohamed Afzal**
**B.Tech – Information Technology**
**Saveetha Engineering College**

⭐ *If you like this project, don't forget to Star the repository!*

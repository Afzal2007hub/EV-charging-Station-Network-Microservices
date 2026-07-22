# ⚡ EV Charging Station Network - Microservices Project

## 📖 Overview

The **EV Charging Station Network** is an Industry Capstone Project developed using **Java 17** and **Spring Boot Microservices**. The system enables customers to locate EV charging stations, reserve charging slots, start and stop charging sessions, calculate charging costs, process payments, and maintain charging history.

The project follows a **Microservices Architecture** with REST API communication through **API Gateway** and inter-service communication using **RestTemplate**.

---

# 🏢 Business Scenario

GreenCharge Pvt. Ltd. operates hundreds of EV charging stations across multiple cities.

The company requires a scalable microservices-based platform that allows customers to:

- Locate nearby charging stations
- Book charging slots
- Start and stop charging sessions
- Calculate charging costs
- Process payments
- View charging history

---

# 🎯 Project Objectives

- Develop Enterprise REST APIs using Spring Boot
- Follow Layered Architecture (Controller → Service → Repository)
- Implement CRUD Operations
- Validate all incoming requests using Bean Validation
- Handle exceptions globally using `@ControllerAdvice`
- Integrate Microservices using RestTemplate
- Configure API Gateway for centralized routing
- Test all APIs using Postman

---

# 🛠 Technology Stack

| Technology | Version |
|------------|----------|
| Java | 17 |
| Spring Boot | 3.x |
| Spring Data JPA | Latest |
| H2 Database (Development) | Latest |
| MySQL (Production Ready) | Latest |
| Maven | Latest |
| Validation | Jakarta Validation |
| RestTemplate | Spring Boot |
| API Gateway | Spring Cloud Gateway |
| Lombok | Latest |
| Postman | API Testing |
| Git & GitHub | Version Control |

---

# 🏗 Microservices

## 1️⃣ Charging Station Service

Responsible for managing charging stations.

### Features

- Register Charging Station
- Update Station
- Delete Station
- View All Stations
- View Station By ID
- Search Station By City
- Search Available Stations
- Manage Connector Details
- Manage Station Status

---

## 2️⃣ Booking Service

Responsible for booking charging slots.

### Features

- Create Booking
- Cancel Booking
- View Booking
- View All Bookings
- Prevent Duplicate Booking
- Verify Slot Availability

---

## 3️⃣ Charging Session Service

Responsible for charging operations.

### Features

- Verify Booking
- Verify Connector Availability
- Start Charging
- Stop Charging
- Auto Stop at 100%
- Calculate Duration
- Calculate Energy Consumed
- Calculate Charging Cost
- View Charging History

---

## 4️⃣ Payment Service

Responsible for payment processing.

### Features

- Generate Invoice
- Record Payment
- Update Payment Status
- Get Payment Details

---

# 🔄 Microservice Communication

```
Client
   │
   ▼
API Gateway
   │
   ├────────────► Charging Station Service
   │
   ├────────────► Booking Service
   │
   ├────────────► Charging Session Service
   │                     │
   │                     ├────────► Booking Service
   │                     ├────────► Charging Station Service
   │                     └────────► Payment Service
   │
   └────────────► Payment Service
```

Communication is implemented using **RestTemplate**.

---

# 📌 Functional Requirements

## Charging Station

- Register charging stations
- Unique Station ID
- Multiple connectors per station
- Search by city
- Search by availability

Supported Connectors

- CCS
- CHAdeMO
- Type-2
- GB/T

---

## Booking

- Book charging slot
- Verify slot availability
- Prevent duplicate bookings
- Cancel booking
- Booking lifecycle management

---

## Charging Session

Before starting charging

- Verify booking
- Verify connector availability

Charging Rules

- Battery level must be less than 95%
- Fast charging only for compatible connectors
- Record

  - Start Time
  - Stop Time
  - Duration
  - Energy Consumed

Calculate

- Charging Duration
- Units Consumed
- Charging Cost

Automatically stop charging when battery reaches **100%**.

---

## Payment

- Generate Invoice
- Record Payment
- Update Payment Status
- Maintain Invoice History

---

## Charging History

Maintain charging history for every customer.

---

# 📡 REST Communication Flow

```
Charging Session Service
        │
        ├────────► Booking Service
        │          Verify Booking
        │
        ├────────► Charging Station Service
        │          Verify Connector
        │
        └────────► Payment Service
                   Generate Bill
```

---

# ✅ Validation Rules

- Station Name is mandatory
- Connector Type must be valid
- Battery Percentage must be between 0 and 100
- Charging Duration must be greater than zero
- Energy Consumed must be positive
- Booking Date cannot be in the past
- Customer Mobile Number must be valid
- Customer Email must be valid

---

# 📋 Business Rules

- One charging slot can have only one active booking.
- Charging cannot start without a confirmed booking.
- Charging automatically stops when battery reaches 100%.
- Fast charging is available only on supported connectors.
- Payment failure changes invoice status to **PENDING**.
- Connector availability updates automatically after charging completion.
- Station Status can be

```
ACTIVE
INACTIVE
UNDER_MAINTENANCE
```

---

# 🌐 REST APIs

## Charging Station Service

| Method | Endpoint |
|----------|----------------|
| POST | /stations |
| GET | /stations |
| GET | /stations/{id} |
| PUT | /stations/{id} |
| DELETE | /stations/{id} |

---

## Booking Service

| Method | Endpoint |
|----------|---------------------------|
| POST | /bookings |
| GET | /bookings |
| GET | /bookings/{id} |
| PUT | /bookings/{id}/cancel |

---

## Charging Session Service

| Method | Endpoint |
|----------|----------------------------|
| POST | /charging/start |
| PUT | /charging/{id}/stop |
| GET | /charging/history/{customerId} |

---

## Payment Service

| Method | Endpoint |
|----------|----------------|
| POST | /payments |
| GET | /payments/{id} |

---

# ⚠ Global Exception Handling

Custom Exceptions

- StationNotFoundException
- BookingNotFoundException
- SlotUnavailableException
- ConnectorNotSupportedException
- LowBatteryException
- PaymentFailedException

Framework Exceptions

- MethodArgumentNotValidException

Generic Exception

- Global Exception Handler

---

# 📂 Project Structure

```
EV-Charging-Station-Network
│
├── API-Gateway
│
├── Charging-Station-Service
│
├── Booking-Service
│
├── Charging-Session-Service
│
├── Payment-Service
│
└── README.md
```

Each service follows:

```
controller
service
repository
entity
dto
exception
config
client
```

---

# 🚀 Implementation Milestones

| Phase | Description |
|----------|-------------------------------|
| Phase 1 | Create Spring Boot Projects |
| Phase 2 | Charging Station Service |
| Phase 3 | Booking Service |
| Phase 4 | Charging Session Service |
| Phase 5 | Payment Service |
| Phase 6 | Bean Validation |
| Phase 7 | Global Exception Handler |
| Phase 8 | RestTemplate Integration |
| Phase 9 | API Gateway |
| Phase 10 | API Testing & Documentation |

---

# 🧪 Testing

All APIs were tested using **Postman**.

Testing includes

- CRUD Operations
- Validation
- Exception Handling
- REST Communication
- API Gateway Routing

---

# 📦 Deliverables

- ✅ Complete Source Code
- ✅ Database SQL Script
- ✅ Postman Collection
- ✅ README Documentation
- ✅ Architecture Diagram
- ✅ API Documentation
- ✅ Execution Screenshots

---

# ▶️ How to Run

## Clone Repository

```bash
git clone https://github.com/your-username/EV-Charging-Station-Network.git
```

---

## Build Project

```bash
mvn clean install
```

---

## Run Services

Start services in the following order:

1. Charging Station Service
2. Booking Service
3. Payment Service
4. Charging Session Service
5. API Gateway

---

## Access Through API Gateway

```
http://localhost:8080
```

Example

```
POST /stations

POST /bookings

POST /charging/start

PUT /charging/{id}/stop

POST /payments
```

---

# 📈 Future Enhancements

- Authentication using Spring Security & JWT
- Service Discovery using Eureka Server
- Distributed Configuration using Config Server
- Circuit Breaker using Resilience4j
- Docker Containerization
- Kubernetes Deployment
- CI/CD Pipeline with GitHub Actions
- Monitoring using Prometheus & Grafana

---

# 👨‍💻 Author

**Mohamed Afzal**

B.Tech Information Technology

Saveetha Engineering College

---

# ⭐ If you like this project

Give this repository a ⭐ on GitHub.

# ⚡ EV Charging Station Network - Microservices Project

## 📖 Overview

The **EV Charging Station Network** is an Industry Capstone Project developed using **Java 17** and **Spring Boot Microservices**. The system enables customers to locate EV charging stations, reserve charging slots, start and stop charging sessions, calculate charging costs, process payments, and maintain charging history.

The project follows a **Microservices Architecture** with REST API communication through **API Gateway** and inter-service communication using **RestTemplate**.

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

# System Architecture
                          🌐 API Gateway
                               │
      ┌────────────────────────┼────────────────────────┐
      │                        │                        │
      ▼                        ▼                        ▼
┌───────────────┐      ┌────────────────┐      ┌─────────────────┐
│ Charging      │◄────►│ Booking        │◄────►│ Charging        │
│ Station       │      │ Service        │      │ Session Service │
│ Service       │      └────────────────┘      └─────────────────┘
└──────┬────────┘                                      │
       │                                               │
       ▼                                               ▼
 Station DB                                      ┌───────────────┐
                                                  │ Payment      │
                                                  │ Service      │
                                                  └──────┬────────┘
                                                         │
                                                         ▼
                                                    Payment DB

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



# 👨‍💻 Author

**Mohamed Afzal**

B.Tech Information Technology

Saveetha Engineering College

---

# ⭐ If you like this project

Give this repository a ⭐ on GitHub.

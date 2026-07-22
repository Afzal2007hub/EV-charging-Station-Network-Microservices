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

~~~
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


~~~
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

# OUTPUT

### Charging Station Service

<img width="1083" height="727" alt="Screenshot 2026-07-22 231510 - Copy" src="https://github.com/user-attachments/assets/b98aaf5d-264e-4ec7-9140-af94970bac50" />


<img width="1063" height="912" alt="Screenshot 2026-07-22 231540 - Copy" src="https://github.com/user-attachments/assets/6071f029-d73e-4b82-8db1-21d08817f0ab" />

<img width="1472" height="540" alt="Screenshot 2026-07-22 232450" src="https://github.com/user-attachments/assets/492001e5-bf44-4969-b4d4-a731edb61b4d" />



### Booking Service

<img width="1047" height="942" alt="Screenshot 2026-07-22 231850 - Copy" src="https://github.com/user-attachments/assets/6aac1dfa-4fb5-48ef-b9e3-bf0189a96a95" />


<img width="1067" height="887" alt="Screenshot 2026-07-22 231908 - Copy" src="https://github.com/user-attachments/assets/1b5d1f2e-dd08-48dc-b409-702c42f7bcd3" />


<img width="1686" height="585" alt="Screenshot 2026-07-22 232535" src="https://github.com/user-attachments/assets/defc63d3-2637-4c20-bc62-418eca32c841" />




### Charging Session Service

<img width="1053" height="935" alt="Screenshot 2026-07-22 231926 - Copy" src="https://github.com/user-attachments/assets/b92767a3-76df-404b-b775-ed79d69247b4" />

<img width="1057" height="927" alt="Screenshot 2026-07-22 231942 - Copy" src="https://github.com/user-attachments/assets/619ff931-2732-4fff-b329-d3fda16f1cc2" />


<img width="1751" height="632" alt="Screenshot 2026-07-22 232556" src="https://github.com/user-attachments/assets/5e1425ac-edb7-4b7d-8b4d-f64e7ebf2bad" />



### Payment Service

<img width="1060" height="903" alt="Screenshot 2026-07-22 232105 - Copy" src="https://github.com/user-attachments/assets/da69d8f5-188a-4656-a555-96924ecbe39a" />


<img width="1637" height="590" alt="Screenshot 2026-07-22 232619" src="https://github.com/user-attachments/assets/19f3d926-9a1c-4a62-8c24-df6bb854c201" />



# 👨‍💻 Author

**Mohamed Afzal**

B.Tech Information Technology

Saveetha Engineering College

---

# ⭐ If you like this project

Give this repository a ⭐ on GitHub.

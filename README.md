# 🏥 PatientHUB – Microservices-Based Healthcare Management System

PatientHUB is a scalable, event-driven microservices project that simulates a real-world hospital management system. It handles patient records, authentication, billing, and analytics using modern enterprise technologies like **Spring Boot**, **gRPC**, **Kafka**, **Docker**, and **JWT-secured API Gateway**.

---

## 🚀 Tech Stack

- **Spring Boot** – REST API development
- **Spring Security + JWT** – Authentication and Authorization
- **gRPC** – Inter-service communication (Patient → Billing)
- **Apache Kafka** – Real-time event streaming (Patient → Analytics)
- **Docker** – Containerization for each service
- **PostgreSQL / H2** – Databases
- **OpenAPI (Swagger)** – API documentation
- **Spring Cloud Gateway** – Central API Gateway for routing

---

## 🎯 Project Goals

- Build a production-grade healthcare backend system
- Handle secure patient CRUD operations
- Automate billing upon patient creation via gRPC
- Stream patient data for analytics via Kafka
- Secure and centralize access with API Gateway and JWT

---

## 🧩 Microservices Overview

### 🩺 Patient Service
- CRUD operations on patient data
- Validates input and throws custom exceptions
- Calls Billing Service via gRPC upon creation
- Publishes Kafka events for analytics

### 💳 Billing Service
- Receives gRPC requests from Patient Service
- Creates billing accounts for new patients
- Future-ready for invoice/payment integration

### 🧠 Analytics Service
- Kafka consumer for patient data events
- Processes and logs insights for real-time analytics
- Can be extended with dashboards (Grafana, ELK)

### 🔐 Auth Service
- User login and registration
- Secure token generation using JWT
- Validates users for protected routes

### 🧾 API Gateway
- Single entry-point to all services
- Applies JWT token filters
- Handles route mapping and security policies

---

## 🔄 Service Communication

```

Client ⇄ API Gateway ⇄ Auth / Patient Services
⇓
Patient Service ⇄ gRPC ⇄ Billing Service
⇓
Kafka (Patient Events)
⇓
Analytics Service (Consumer)

````

---

## 🛠️ Running the Project

### Requirements
- Docker & Docker Compose
- Java 17+
- Maven
- Postman / IntelliJ HTTP Client

### Steps

1. Clone the repo:
   ```bash
   git clone https://github.com/your-username/patienthub.git


2. Build and run services:

   ```bash
   ./mvnw clean package -DskipTests
   docker-compose up --build
   ```

3. Access APIs:

   * API Gateway: `http://localhost:8080`
   * Swagger Docs: `http://localhost:8080/swagger-ui.html`

---

## 📂 Project Structure

```
patienthub/
├── api-gateway/
├── auth-service/
├── patient-service/
├── billing-service/
├── analytics-service/
├── docker-compose.yml
└── api-requests/
```

---

## 📌 Key Highlights

* ✅ Secure and centralized routing
* ⚙️ Event-driven and reactive communication
* 📈 Real-time analytics via Kafka
* 🧪 Manual API testing using `.http` request files
* 📦 Production-ready with Docker and DB setup


## 💡 Future Enhancements

* Admin dashboard with patient and billing insights
* Email notifications using Kafka Consumers
* Role-based access control (RBAC)
* CI/CD integration with GitHub Actions

---

## 🙌 Credits

This project is built as a hands-on implementation of a full-stack enterprise architecture inspired by real healthcare systems and YouTube tutorials.

---

## 📄 License

[MIT](LICENSE)


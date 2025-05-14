# 🛠️ System Design Guide

This document outlines the **common steps involved in designing a scalable, reliable, and maintainable system**. It serves as a reference for system design interviews or planning production-grade software architecture.

---

## 📌 Step-by-Step System Design Process

### 1. Clarify Requirements

- Define **core use cases**.
- Ask about **non-functional needs** (performance, security, availability).
- Identify **out-of-scope** features.

### 2. Define Functional & Non-Functional Requirements

#### ✅ Functional:
- What should the system *do*?
- Examples: shorten URLs, upload files, chat, etc.

#### 🚦 Non-Functional:
- Performance (latency, throughput)
- Scalability (users, data size)
- Availability, reliability, maintainability
- Security & compliance

---

### 3. Estimate Scale and Constraints

- Number of users (DAU/MAU)
- Requests per second (RPS)
- Storage requirements
- Latency and uptime SLAs (e.g., 99.9%)

---

### 4. High-Level Design

- Identify **major components**:
  - Clients
  - API Gateway
  - Application Server(s)
  - Databases
  - Caches
  - Queues
  - Load Balancer
- Draw an **architecture diagram** showing data flow.

---

### 5. Component Design

Design each subsystem:

- **API Layer**: Handles HTTP/gRPC requests
- **Business Logic Layer**: Validates and processes input
- **Data Layer**: Communicates with storage/caches

Include rate-limiting, retries, and error handling.

---

### 6. Data Modeling and Storage

- Choose between **SQL** and **NoSQL** depending on access patterns.
- Design schemas:
  - Normalize for relational DBs
  - Denormalize or document-based for NoSQL
- Index frequently accessed fields.
- Use **sharding** and **replication** for scalability and availability.

---

### 7. Caching Strategy

- Use **Redis** or **Memcached** to cache:
  - Hot data

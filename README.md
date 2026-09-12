# architecture-docs

# 🏛️ [System Name] Architecture Documentation

This repository houses the core architecture documentation, system design principles, and data flow models for the SADHGURU.ORG ecosystem. It serves as the centralized **Single Source of Truth**  for engineering teams. 

---

## 🗺️ High-Level System Context
Below is the high-level representation of how our system interacts with internal and external users and dependency services.

Refer: ISHA LIFE 2.0 ECOMMERCE SYSTEM CONTEXT
---

## 📁 Repository Directory Structure

Please navigate the documentation via the directories below:

* **[/decisions](./decisions)**: Architecture Decision Records (ADRs). Refer to this directory to understand *why* historical and current design choices were made.
* **[/diagrams](./diagrams)**: Raw asset files (`.drawio`, `.svg`) for all architecture diagrams.
* **[/platforms](./platforms)**: Deep-dives into our infrastructure layout, cloud topography (AWS/Azure/GCP), and CI/CD pipelines.
* **[/services](./services)**: Individual domain microservice breakdowns, API specs, and sequence diagrams.
* **[/security](./security)**: Type of security applied for data in transit and at rest and for Authentication and Authorization[IAM]of services (TLS 1.3, OAuth 2.1, etc).

---

---
## 🔑 Core Design Invariants
Every architectural change or implementation must adhere to these rigid invariants:
1. **Security First:** All data in transit must be encrypted using TLS 1.3.
2. **Resiliency:** Services must implement retry mechanisms with exponential backoff and circuit breakers.
3. **Decoupling:** Subsystems must communicate asynchronously via the event bus unless synchronous data is strictly required.

---

## ✍️ How to Contribute & Update Docs

We welcome contributions to keep our documentation accurate! Please follow these standards:

### 1. Creating Diagrams
* If using an external tool like **Draw.io**, export the asset as an **Editable SVG** and save both the image and source file (*.drawio) inside the `/diagrams` folder.

### 2. Submitting an ADR
When proposing an architectural change:
1. Copy the template found in `/decisions/template.md`.
2. Give it the next sequential number (e.g., `ADR-0024-implement-redis-cache.md`).
3. Open a Pull Request for review by the architecture guild.

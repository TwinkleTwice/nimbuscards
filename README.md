<div align="center">

# NimbusCards

### Open-source virtual card issuing platform built with Go

*A production-oriented backend platform for issuing, managing and processing virtual payment cards.*

---

![Go](https://img.shields.io/badge/Go-1.24+-00ADD8?logo=go)
![License](https://img.shields.io/badge/license-MIT-green)
![Status](https://img.shields.io/badge/status-In%20Development-orange)
![Architecture](https://img.shields.io/badge/architecture-Modular%20Monolith-blue)

</div>

---

## About

NimbusCards is an open-source backend platform that simulates a modern virtual card issuing system.

The goal of the project is **not** to build another CRUD application, but to demonstrate how production-grade backend systems are designed using modern Go technologies and engineering practices.

The project is intentionally designed as a **modular monolith** with clearly defined domain boundaries, making it easy to evolve into microservices when required.

---

## Why NimbusCards?

Modern virtual card platforms are becoming increasingly popular for:

- SaaS subscriptions
- Expense management
- Team spending
- Secure online payments
- Temporary virtual cards

NimbusCards aims to demonstrate how such a platform could be built from scratch while keeping the codebase clean, maintainable and production-ready.

---

# Features (MVP)

- JWT Authentication
- Subscription Plans
- Purchase & Refund Subscriptions
- Virtual Card Issuing
- Card Management
- Transaction History
- Issuer Integration (Fake Issuer)
- Webhook Processing
- Event-Driven Architecture
- Notifications

---

# Tech Stack

## Backend

- Go
- PostgreSQL
- Redis
- Kafka
- gRPC
- REST API

## Infrastructure

- Docker
- Docker Compose
- Prometheus
- OpenTelemetry
- Grafana

## Development

- sqlc
- golang-migrate
- Makefile
- GitHub Actions
- Swagger / OpenAPI

---

# Architecture

NimbusCards follows a **Modular Monolith** architecture.

```
                REST API
                    │
                    ▼
          Application Layer
                    │
     ┌──────────────┼──────────────┐
     ▼              ▼              ▼
 Identity     Subscription      Card
     │              │              │
     └──────────────┼──────────────┘
                    ▼
              Transaction
                    │
                    ▼
                 Issuer
                    │
                    ▼
              Kafka Events
                    │
                    ▼
             Notification
```

Each module owns its own business logic and communicates through explicit interfaces and domain events.

---

# Project Goals

This project focuses on engineering practices rather than simply implementing features.

Main goals include:

- Clean Architecture
- Domain-Driven Design principles
- Modular Monolith
- Event-Driven Architecture
- Idempotency
- Observability
- Graceful Shutdown
- Distributed Tracing
- Production-ready Logging
- High Test Coverage
- Docker-first Development

---

# Roadmap

### Phase 1

- [ ] Authentication
- [ ] User Management
- [ ] Subscription Plans

### Phase 2

- [ ] Virtual Card Issuing
- [ ] Fake Issuer
- [ ] Card Lifecycle

### Phase 3

- [ ] Kafka Integration
- [ ] Webhooks
- [ ] Notifications

### Phase 4

- [ ] Redis
- [ ] Idempotency
- [ ] Retry Mechanisms

### Phase 5

- [ ] Metrics
- [ ] Tracing
- [ ] CI/CD

---

# Repository Structure

```
cmd/
configs/
deployments/
docs/

internal/

    identity/
    subscription/
    card/
    transaction/
    issuer/
    notification/

pkg/
test/
```

---

# Design Principles

NimbusCards is built around several principles:

- Business logic comes first.
- Infrastructure is replaceable.
- Explicit dependencies over magic.
- Small packages with clear responsibilities.
- Code should be easy to read six months later.
- Every architectural decision must have a reason.

---

# Current Status

NimbusCards is currently under active development.

The project is being built in public as a learning journey toward production-grade backend engineering in Go.

The architecture, ADRs, and implementation decisions will be documented throughout the development process.

---

# License

MIT

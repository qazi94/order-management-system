# Event-Driven Order Management System

Microservices-based backend using Java, Spring Boot, Apache Kafka, and Keycloak.

## Architecture
- **API Gateway** — verifies Keycloak JWT
- **Order Service** — create/cancel order, publishes `order.created`
- **Inventory Service** — consumes events, updates stock
- **Notification Service** — email/log alerts from events
- **Keycloak** — login + roles (`USER`, `ADMIN`)

## Tech Stack
Java • Spring Boot • Apache Kafka • Keycloak • REST APIs • Microservices

## Flow
1. User logs in with Keycloak
2. Order Service creates an order
3. Kafka event `order.created` is published
4. Inventory Service updates stock
5. Notification Service sends confirmation

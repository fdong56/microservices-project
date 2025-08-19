# Microservices E-Commerce Platform

A comprehensive microservices-based e-commerce platform built with Spring Boot, featuring distributed tracing, monitoring, event-driven architecture, and security.

## 🏗️ Architecture Overview

This project implements a modern microservices architecture with the following components:

- **API Gateway** - Single entry point with routing, security, and circuit breaker patterns
- **Product Service** - Manages product catalog with MongoDB
- **Order Service** - Handles order processing with MySQL and event publishing
- **Inventory Service** - Manages inventory levels with MySQL
- **Notification Service** - Handles email notifications via Kafka events
- **Observability Stack** - Prometheus, Grafana, Tempo, and Loki for monitoring
- **Security** - Keycloak for authentication and authorization
- **Message Broker** - Apache Kafka with Schema Registry for event streaming

## 🛠️ Technology Stack

### Backend
- **Java 21**
- **Spring Boot 3.4.2**
- **Spring Cloud 2024.0.1**
- **Spring Security + OAuth2**
- **Spring Data JPA**
- **Spring Data MongoDB**

### Databases
- **MySQL 8.3.0** - For orders and inventory
- **MongoDB 7.0.5** - For products

### Message Broker
- **Apache Kafka 7.5.0**
- **Confluent Schema Registry**
- **Avro** for schema management

### Observability
- **Prometheus** - Metrics collection
- **Grafana** - Visualization and dashboards
- **Tempo** - Distributed tracing
- **Loki** - Log aggregation

### Security
- **Keycloak 24.0.1** - Identity and access management

### Development Tools
- **Maven** - Build tool
- **Docker Compose** - Container orchestration
- **Kafka UI** - Kafka management interface


## 📚 API Documentation

Each service provides Swagger UI documentation:

- **API Gateway**: http://localhost:9000/swagger-ui.html
- **Product Service**: http://localhost:8080/swagger-ui.html
- **Order Service**: http://localhost:8081/swagger-ui.html
- **Inventory Service**: http://localhost:8082/swagger-ui.html

## 🔐 Security

### Keycloak Setup
1. Access Keycloak Admin Console: http://localhost:8181
2. Login with: `admin/admin`
3. Import realm configuration from `docker/keycloak/realms/`
4. Configure clients and users as needed

### JWT Authentication
The API Gateway validates JWT tokens from Keycloak. Configure the issuer URI in `api-gateway/src/main/resources/application.properties`.


## 🔧 Configuration

### Environment Variables
Key configuration files:
- `application.properties` in each service
- `docker-compose.yml` for infrastructure
- `docker/prometheus/prometheus.yml` for monitoring

### Database Migrations
- **Order Service**: Flyway migrations in `order-service/src/main/resources/db/migration/`
- **Inventory Service**: Flyway migrations in `inventory-service/src/main/resources/db/migration/`


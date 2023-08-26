# Microservices Communication, Responsibilities, and Key Concepts

## Microservices Overview

- **Product Service:** Responsible for creating and viewing products, acting as the product catalog.

- **Order Service:** Allows customers to order products.

- **Inventory Service:** Provides functionality to check if a product is in stock or not.

- **Notification Service:** Handles sending notifications after an order is placed.

- The **Order Service**, **Inventory Service**, and **Notification Service** are going to interact with each other.

## Communication Methods

### Synchronous Communication

- Synchronous communication involves direct request-response interactions between microservices.
- In this scenario, a microservice sends a request and waits for a response before proceeding.
- Suitable for scenarios where immediate response or coordination is required.

### Asynchronous Communication

- Asynchronous communication involves sending messages between microservices without waiting for an immediate response.
- Microservices can continue processing without waiting for the result.
- Suitable for scenarios where real-time responses are not required and to ensure loose coupling.

## Responsibilities of Each Service

### Product Service

- Create and manage products.
- Provide information about available products in the catalog.
- Respond to requests for product details.

### Order Service

- Handle customer orders for products.
- Communicate with the Inventory Service to check product availability.
- Initiate the process of sending notifications via the Notification Service after an order is placed.

### Inventory Service

- Keep track of product stock levels.
- Provide an interface to check if a product is in stock.
- Respond to requests from the Order Service to verify product availability.

### Notification Service

- Send notifications after an order is successfully placed.
- Receive requests from the Order Service to send notifications to customers.
- Handle the asynchronous communication of notifying customers without affecting the main order processing flow.

## Interactions between Services

- **Order Service and Inventory Service:** The Order Service communicates with the Inventory Service to verify if a product is in stock before processing an order. This communication ensures that orders are placed for products that are available.

- **Order Service and Notification Service:** The Order Service communicates with the Notification Service to trigger notifications to customers once an order is successfully placed. This interaction happens asynchronously to avoid delaying the order processing flow.

- **Inventory Service and Order Service:** The Inventory Service responds to requests from the Order Service to provide information about product availability. This communication is synchronous and helps ensure that only products in stock are ordered.

## Key Microservices Concepts

### Service Discovery

- Implement service discovery to dynamically locate and register services within the network.
- Service discovery enables efficient communication between microservices without hard-coded URLs.

### Centralized Configuration

- Centralize configuration management to externalize application configuration from code.
- This allows changes to be made without modifying and redeploying individual microservices.

### Distributed Tracing

- Use distributed tracing to monitor and visualize the flow of requests across microservices.
- Trace requests to identify performance bottlenecks and troubleshoot issues.

### Event Driven Architecture

- Adopt event-driven architecture to facilitate communication and decoupling between microservices.
- Microservices communicate through events, promoting scalability and flexibility.

### Centralized Logging

- Implement centralized logging to collect and analyze logs from multiple microservices.
- Centralized logs assist in diagnosing problems and monitoring system behavior.

### Circuit Breaker

- Apply circuit breaker pattern to prevent cascading failures in a microservices environment.
- Circuit breakers detect failures and provide fallback mechanisms to maintain system stability.

### Secure Microservices Using Keycloak

- Secure microservices with Keycloak, an open-source identity and access management solution.
- Use Keycloak to manage user authentication, authorization, and token-based security.

## Conclusion

Microservices interact through various communication methods and follow specific design principles to ensure modularity, scalability, and maintainability. Key concepts such as service discovery, centralized configuration, distributed tracing, event-driven architecture, centralized logging, circuit breakers, and secure microservices contribute to building robust and resilient microservices-based applications.

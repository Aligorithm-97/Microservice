# My Self Study Notes

# Event-Driven Architecture and Reactive Programming in Java

## Table of Contents
1. [Event-Driven Architecture](#event-driven-architecture)
2. [Microservices Communication](#microservices-communication)
3. [Java Naming Conventions](#java-naming-conventions)
4. [Reactive Programming](#reactive-programming)
5. [WebFlux](#webflux)
6. [Gateway Architecture](#gateway-architecture)
7. [Service Discovery and Communication](#service-discovery-and-communication)
8. [Event-Driven Messaging Systems](#event-driven-messaging-systems)
9. [Security and Configuration](#security-and-configuration)
10. [Additional Concepts](#additional-concepts)

---

## Event-Driven Architecture
Event-driven architecture revolves around systems reacting to events such as user actions or messages from other systems. It's crucial for building scalable, decoupled applications.

### Path Variables vs Request Parameters
- **Path Variables** (`@PathVariable`): Used to identify resources in endpoints like `/products/{catId}`.
- **Request Parameters** (`@RequestParam`): Used for query strings such as `/products?name=ABC&priceMin=300`.

---

## Microservices Communication
For communication between microservices, Java provides tools like `RestTemplate` and `WebClient`. 
- **RestTemplate**: Suitable for synchronous communication.
- **WebClient**: Preferred for reactive programming and can be used in both reactive and non-reactive applications.

---

## Java Naming Conventions
Follow the standard Java naming conventions for clarity and maintainability. Use meaningful names for classes, methods, and variables that describe their purpose.

---

## Reactive Programming
Reactive programming in Java is based on the **Publisher-Subscriber** model:
- **Mono**: Represents a single item or event.
- **Flux**: Represents a stream of multiple items or events.

Use `WebClient` for non-blocking reactive data access. This approach can significantly enhance performance, especially when dealing with high concurrency.

### Polling vs Reactive
- **Polling**: Continuously checks for updates.
- **Reactive**: Reacts to events as they occur, improving efficiency.

### Error Handling in Reactive Streams
In a reactive flow, if an error occurs, additional streams or error handlers can be triggered to deal with it. The **Saga Pattern** ensures data integrity through compensating transactions in case of failure.

---

## WebFlux
**WebFlux** is a framework for building non-blocking, reactive web applications in Java. It supports asynchronous and reactive processing using `Mono` and `Flux`.

- **WebFlux Blocking**: Can be used similarly to `await` in asynchronous programming.
- **Incremental Data Loading**: Use `Flux` to fetch data from multiple sources incrementally, e.g., for hotel booking applications.

---

## Gateway Architecture
A **Gateway** serves as an entry point for all incoming requests, routing them to appropriate services. This ensures security and separation between client requests and service logic.

- Use `/**` to capture all paths, and `/*` to capture a single path.

---

## Service Discovery and Communication
- **Eureka Server and Discovery Client**: Used for service registration and discovery in microservice architectures. Services register with **Eureka** and can discover each other.
- **Feign Client**: A declarative web service client, making it easier to communicate with other services as if they were local.
  
Eureka and Feign are often used together for efficient service discovery and communication.

---

## Event-Driven Messaging Systems
- **RabbitMQ**: Commonly used for event-driven systems.
- **Kafka**: Ideal for both event-driven architectures and big data processing.

### Messaging Models
- **Publisher-Subscriber (Topic)**: Subscribers receive the events they are interested in.
- **Producer-Consumer (Queue)**: Messages are produced specifically for designated consumers.

---

## Security and Configuration
- **Configuration Files**: Should never be publicly exposed to protect sensitive data.
- **Library vs Framework**: You use libraries in your code, while frameworks control the flow and use your code.
  
### Authentication vs Authorization
- **Authentication**: Verifies the identity of a user (e.g., Are you who you claim to be?).
- **Authorization**: Verifies what actions the authenticated user is allowed to perform (e.g., Do you have the right permissions?).

### OAuth2 and Keycloak
OAuth2 and Keycloak are commonly used for managing authentication and authorization in modern applications.

---

## Additional Concepts
- **Saga Pattern**: Ensures data integrity through compensating transactions in case of failure during complex workflows.
- **.NET Convention over Configuration**: In .NET, routing and method behavior can often be inferred from naming conventions.
- **LDAP**: A protocol for directory services and authentication.
- **Cryptography**: Important security practices include SSL, HTTPS, TLS, and certificates to ensure secure data transmission.

## Web Architecture

Web architecture refers to the structural design of web applications and systems, including the components, communication protocols, data storage mechanisms, operating systems, and design principles used to build and maintain them.

## Evolution of Web Architecture

### Monolithic

- Initially, web applications were built as monolithic systems where all the functionality was tightly coupled into a single codebase.
- Monolithic architecture is characterized by a single, self-contained application that handles all aspects of the application, including the user interface, business logic, and data access layers.

### Front-Back Separation

- Front-back separation introduced a clear division between the client-side (frontend) and server-side (backend) components of a web application.
- Frontend communicates with the backend via HTTP requests for data retrieval and manipulation.
- Technologies like web sockets enable real-time bidirectional communication between the client and server.

### SOA: Service-Oriented Architecture

- Service-Oriented Architecture (SOA) breaks down application functionality into loosely coupled, reusable components called services.
- Enterprise Service Bus (ESB) facilitates communication and integration between these services.

### Microservices

- Microservices architecture decomposes applications into smaller, independently deployable services, each responsible for a specific business function.
- Each microservice typically has its own database, enabling greater scalability, flexibility, and resilience.
- Microservices communicate via lightweight protocols such as HTTP/REST or messaging queues.

### Micro Frontends

- Micro Frontends extends the microservices concept to the frontend, allowing different parts of the user interface to be developed, deployed, and scaled independently.
- Tools like Webpack facilitate the integration of micro frontends into a unified user experience.

### Communication

- REST (Representational State Transfer), SOAP (Simple Object Access Protocol), RPC (Remote Procedure Call), and GraphQL are common communication protocols used in web architecture.
- RESTful APIs typically use JSON, XML, or HTML for data exchange, while SOAP relies on XML.
- RPC enables communication between distributed systems by invoking remote procedures.
- GraphQL provides a flexible query language for fetching data from a server.

### Data Store

- Web applications utilize various types of data stores, including relational databases (e.g., MySQL, Oracle, SQL Server), NoSQL databases (e.g., MongoDB, Cassandra), and caching solutions (e.g., Redis, Memcached).

### Operation System

- Web applications can run on different operating systems, including Linux, Windows, and macOS, depending on the deployment environment and requirements.

### SOLID Principles

- SOLID principles are design principles for writing clean, maintainable, and scalable code:
    - Single Responsibility Principle
    - Open-Closed Principle
    - Liskov Substitution Principle
    - Interface Segregation Principle
    - Dependency Inversion Principle

### Microservice Components

- Microservice architecture relies on various components such as DNS, load balancers, databases, cache databases, job queues/servers, full-text search engines, cloud storage, and content delivery networks (CDNs) to function effectively.

### Spring Cloud

- Spring Cloud is a suite of tools and frameworks for building and deploying microservices-based applications on the JVM (Java Virtual Machine).
- Components of Spring Cloud include:
    - Config Server
    - Service Discovery (Eureka, Consul, Zookeeper)
    - Distributed Tracing (Zipkin, Sleuth)
    - Client-Side Load Balancing (Ribbon)
    - Circuit Breaker (Hystrix, Resilience4j)
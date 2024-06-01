# Day 14
# CICD, Jenkins, DEV/TEST/UAT/Prod env, Agile, Jira

## Environment

### Development Environment (Dev Env)
- **Description**: This is where developers write and test their code. The environment is set up to resemble production but is more flexible to allow for frequent changes and updates.
- **Users**: Developers
- **Usage Frequency**: Very frequently
- **Purpose**: Code development, unit testing, and initial debugging. The goal is to ensure that the new features or fixes work as intended on a small scale before moving to more extensive testing.

### Testing Environment (Test Env) / Integration Environment
- **Description**: This environment is used for various types of testing, including integration testing and penetration testing. It simulates the production environment more closely than the development environment.
- **Users**: Testers, Business Analysts (BA), Product Managers
- **Usage Frequency**: Regularly, following development cycles
- **Purpose**:
    - **Integration Testing**: To ensure that different modules and services work together as expected.
    - **Penetration Testing**: To identify security vulnerabilities.
    - Other types of testing like regression and performance testing might also be conducted here.

### User Acceptance Testing (UAT) / Staging / Pre-Production Environment
- **Description**: This environment mimics the production environment as closely as possible. It is used for final testing before deployment to production.
- **Users**: Internal users, such as stakeholders and end-users within the company, for final validation.
- **Usage Frequency**: Less frequently, typically on a scheduled basis, often monthly
- **Purpose**:
    - **User Acceptance Testing (UAT)**: To validate the end-to-end business flow. It involves testing by the actual users or stakeholders to ensure the system meets their requirements and is ready for production.
    - **Staging**: To perform final checks before production, ensuring no bugs have been missed and the system performs as expected.

### Production Environment (Prod Env)
- **Description**: This is the live environment where the application is available to end-users. Stability, performance, and security are paramount.
- **Users**: End-users, Customers
- **Usage Frequency**: Continuously, 24/7
- **Purpose**:
    - **Release**: Deploying the final, stable version of the application.
    - **Deploy Period**: Typically on a scheduled basis, often monthly or as per the release plan.
    - To serve the end-users with the actual application and ensure that it runs smoothly and reliably.

## CICD Pipeline

### Jenkins
- **Role**: Jenkins is an open-source automation server used for building, testing, and deploying code.
- **Usage**:
    - Automate the CI/CD pipelines.
    - Integrate with various testing and deployment tools.
    - Manage and monitor multiple pipelines and jobs.

### Jenkinsfile
- **Description**: A `Jenkinsfile` is a text file that contains the definition of a Jenkins pipeline and is checked into source control.
- **Purpose**:
    - Define the pipeline stages and steps in a code repository.
    - Enable pipeline as code, allowing versioning and sharing of the pipeline configuration.

## Monitoring

### Prometheus Server
- **Role**: Prometheus is an open-source monitoring and alerting toolkit.
- **Usage**:
    - Collect metrics from applications and infrastructure.
    - Store metrics data.
    - Provide powerful querying capabilities.

### Grafana Server
- **Role**: Grafana is an open-source platform for monitoring and observability.
- **Usage**:
    - Visualize metrics data from Prometheus.
    - Create interactive and customizable dashboards.

### Spring Actuator
- **Role**: Spring Actuator provides production-ready features to help monitor and manage Spring Boot applications.
- **Usage**:
    - Expose various endpoints to gather application metrics and health information.

### Exporter /metrics
- **Description**: Exporters are tools that expose application metrics in a format that Prometheus can scrape.
- **Usage**:
    - Collect and export metrics data from various sources to Prometheus.

## Agile

### Team Roles
- **BA (Business Analyst)**
- **QA (Quality Assurance)**
- **DBA (Database Administrator)**
- **DevOps**
- **Developers (Devel)**
- **Team Lead (TL)**
- **Architect**
- **Manager**

### Agile Roles
- **Scrum Master**: Facilitates the Agile process, removes impediments, and ensures the team follows Agile practices.
- **Product Owner**: Represents the stakeholders, prioritizes the backlog, and ensures the team delivers value.

### Agile Methodology
- **Sprint Planning**: Meeting to plan the tasks for the upcoming sprint.
- **Sprint Review**: Meeting to review the work completed in the sprint.
- **Sprint Retrospective**: Meeting to reflect on the past sprint and identify improvements.
- **Daily Standup Meeting**: Short daily meeting for team members to sync up on progress and impediments.

### Waterfall Methodology
- **Description**: A linear and sequential approach to software development where each phase must be completed before the next begins.

### Jira
- **Role**: Jira is a tool developed by Atlassian used for bug tracking, issue tracking, and project management.
- **Usage**:
    - Plan, track, and manage agile software development projects.
    - Create user stories, plan sprints, and distribute tasks across the team.
    - Monitor progress with real-time reporting and visualization tools like burndown charts, sprint reports, and velocity charts.

### Story Points
- **Definition**: A unit of measure used to estimate the effort required to implement a user story.
- **Example**:
    - 1 point = 2 hours
    - If one sprint is one week (40 hours), it equates to approximately 16 points, allowing some margin for uncertainties and non-coding activities.
# Day 15
## Security

### Authentication vs Authorization
- **Authentication**: The process of validating the identity of a user. It answers the question, "Who are you?"
- **Authorization**: The process of checking if a user has permission to perform a certain action or access specific resources. It answers the question, "What are you allowed to do?"

### Encryption, Hashing, Encoding

#### Encryption
- **Symmetric Encryption**: Uses the same key for both encryption and decryption.
    - **Examples**: AES, 3-DES, SNOW
- **Asymmetric Encryption**: Uses a pair of keys (public and private) for encryption and decryption.
    - **Examples**: RSA
- **Purpose**: Protect data by ensuring that it can only be accessed by authorized parties.

#### Hashing
- **Description**: A one-way process that converts data into a fixed-length hash value. It cannot be reversed to get the original data.
    - **Examples**: MD5, SHA-256
- **Usage**:
    - Data integrity verification
    - Password storage
    - File management
- **Concepts**:
    - **Rainbow Table**: A precomputed table for reversing cryptographic hash functions, typically used to crack password hashes.
    - **Salt**: Random data added to a password before hashing to ensure that identical passwords produce different hashes.

#### Encoding
- **Description**: The process of converting data into a different format using a scheme that is publicly available.
    - **Examples**: Base64
- **Purpose**: Encode data for safe transmission or storage. It is reversible and does not provide security.
- **Use Cases**:
    - URL encoding
    - File encoding

### JWT (JSON Web Token)
- **Components**:
    - **Header**: Contains the type of token and the hashing algorithm used.
    - **Payload**: Contains the claims, which are statements about an entity (typically the user) and additional data.
    - **Signature**: Ensures that the token has not been altered. It is created by encoding the header and payload and then hashing it with a secret key.

### OAuth 2.0
- **Description**: A framework for authorization that allows third-party services to exchange authentication and authorization information.
- **Purpose**: Enable third-party applications to access user resources without exposing user credentials.

### SSO (Single Sign-On)
- **Description**: An authentication process that allows a user to access multiple applications with one set of login credentials.
- **Purpose**: Improve user convenience by reducing the number of times a user has to log in.

### Spring Security
- **Description**: A powerful and highly customizable authentication and access control framework for Java applications, particularly Spring-based applications.
- **Usage**:
    - Secure Spring applications by providing comprehensive security services.
    - Handle common security tasks such as authentication, authorization, and protection against common vulnerabilities.

# Day 16 
# Message System

## Why Message System
Message systems, or messaging systems, enable asynchronous communication between different components of a distributed system. They decouple the producers of messages from the consumers, allowing each to operate independently and at their own pace. This leads to better scalability, fault tolerance, and load balancing.

## Message System Model

### Point to Point Model
- **Description**: In the point-to-point model, messages are sent from one producer to one consumer through a queue.
- **Characteristics**:
    - Each message is consumed by only one consumer.
    - The producer sends a message to a specific queue.
    - Consumers listen to the queue and receive messages.
- **Use Cases**: Task distribution, job scheduling.

### Publish-Subscribe Model
- **Description**: In the publish-subscribe model, messages are sent from producers (publishers) to multiple consumers (subscribers) through topics.
- **Characteristics**:
    - Each message can be consumed by multiple consumers.
    - Producers publish messages to a topic.
    - Consumers subscribe to the topic to receive messages.
- **Use Cases**: Event notification systems, real-time data feeds.

## Kafka Architecture

### Producer
- **Role**: Producers send data to Kafka topics.
- **Partitioning**:
    - If a partition is specified, the producer sends data directly to that partition.
    - If no partition is specified but a key is provided, the partition is determined using a hash of the key (modulus operation).
    - If neither a partition nor a key is provided, the producer selects a partition randomly.

### Consumer
- **Role**: Consumers read data from Kafka topics.
- **Offset**: Consumers maintain the offset, which indicates the position of the last message they have consumed. This allows consumers to resume reading from where they left off in case of failure.

### Broker
- **Role**: Brokers are Kafka servers that store and manage messages in topics.
- **Functionality**: Brokers handle message storage, replication, and retrieval.

### Topic (Partition/Replica)
- **Topic**: A logical channel to which messages are sent by producers and from which messages are consumed by consumers.
    - **Partition**: Topics are divided into partitions, which are the basic unit of parallelism in Kafka.
    - **Replica**: Each partition has multiple replicas for fault tolerance.
- **Leader/Follower**: Each partition has one leader and multiple followers. The leader handles all reads and writes, while followers replicate the data.

### Message (Key, Value)
- **Structure**: Messages consist of a key and a value.
- **Serialization**: Messages can be serialized using formats like Apache Avro.

### Batch
- **Description**: Producers can send messages in batches to improve efficiency and throughput.

### Acknowledgment
- **acks = 0**: The producer does not wait for an acknowledgment from the broker.
- **acks = 1**: The producer waits for an acknowledgment from the leader.
- **acks = -1**: The producer waits for acknowledgments from all in-sync replicas (ISR).

## Interview Questions

### Message Accumulated in Kafka, Consumer Can't Consume All Data on Time, What Should You Do?
- **Scale Up Consumers**: Increase the number of consumers to process messages faster.
- **Optimize Consumer Logic**: Improve the efficiency of the consumer logic to process messages more quickly.
- **Increase Partitions**: Increase the number of partitions to allow more consumers to read in parallel.

### How Does Kafka Deal with Expired Data?
- **log.cleanup.policy=delete**: Kafka deletes old data based on the configured retention period or size.
- **log.cleanup.policy=compact**: Kafka retains the latest version of a message with the same key and removes older versions.

### Data Volume in Kafka
- **Daily Total Data Size**: 100 GB
- **Each Log Size**: 0.5k - 2k (average 1k)
- **Daily Log Number**: 100 Million logs
- **Logs per Second**: 1150 logs/s (average), 2300-23000 logs/s (highest), 50 logs/s (lowest)
- **Data Volume per Second**: 1MB/s -> 2MB-20MB

### How to Calculate Partition Number?
- **Total Throughput (Tt)**: MB/s
- **Producer Throughput (Tp)**: MB/s
- **Consumer Throughput (Tc)**: MB/s
- **Formula**:
    - Partition Number = Tt / min(Tp, Tc)
    - Example:
        - Producer Tp = 20 MB/s
        - Consumer Tc = 50 MB/s
        - Total Tt = 100 MB/s
        - Partition Number = 100 / 20 = 5
## Docker
Docker is an open-source platform that allows developers to automate the deployment, scaling, and management of applications. Docker uses container technology to package an application and its dependencies together, ensuring consistent operation across different environments.

### Core Concepts
- **Docker Image**: A read-only template used to create Docker containers. Images can include the operating system, application, configuration files, and dependencies.
- **Docker Container**: A runnable instance of an image. Containers are lightweight, portable units that encapsulate an application and its environment.
- **Dockerfile**: A text file used to define the contents of an image. It contains a series of instructions that specify the build process of the image.
- **Docker Hub**: A cloud-based registry service for storing and sharing Docker images. It provides a centralized resource for container image discovery, distribution, and collaboration.

## AWS Services

### EC2 (Elastic Compute Cloud)
EC2 provides scalable computing capacity in the AWS cloud. It allows you to launch virtual servers, configure security and networking, and manage storage.

### ECS (Elastic Container Service)
ECS is a fully managed container orchestration service. It supports Docker containers and allows you to easily run and scale containerized applications on AWS.

### ECR (Elastic Container Registry)
ECR is a fully managed Docker container registry that makes it easy to store, manage, and deploy Docker container images.

### RDS (Relational Database Service)
RDS is a managed relational database service that supports several database engines, including MySQL, PostgreSQL, MariaDB, Oracle, and SQL Server. It automates tasks such as hardware provisioning, database setup, patching, and backups.

### DocumentDB
DocumentDB is a managed document database service that supports MongoDB workloads. It is designed to be fast, scalable, and highly available.

### DynamoDB
DynamoDB is a fully managed NoSQL database service that provides fast and predictable performance with seamless scalability. It is designed for applications that require consistent, single-digit millisecond latency at any scale.

### Lambda Function
AWS Lambda allows you to run code without provisioning or managing servers. You can run code for virtually any type of application or backend service with zero administration.

### API Gateway
API Gateway is a fully managed service that makes it easy for developers to create, publish, maintain, monitor, and secure APIs at any scale. It handles all the tasks involved in accepting and processing up to hundreds of thousands of concurrent API calls.

### AWS Kinesis
AWS Kinesis is a platform on AWS to collect, process, and analyze real-time, streaming data. It enables you to process and analyze data as it arrives, responding in real-time.

### IAM (Identity and Access Management)
IAM is a web service for securely controlling access to AWS services. It allows you to manage users, groups, and permissions, ensuring that only authorized users have access to specific resources.

### SNS (Simple Notification Service)
SNS is a fully managed messaging service for both application-to-application (A2A) and application-to-person (A2P) communication. It enables you to send messages to multiple subscribers through various transport protocols.

### SQS (Simple Queue Service)
SQS is a fully managed message queuing service that enables you to decouple and scale microservices, distributed systems, and serverless applications. It ensures the delivery of messages between software components.
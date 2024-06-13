# Property Management Platform Design Document

**Project Name:** Property Management Platform  
**Client:** CBRE Group, Inc.  
**Location:** Boston, MA  
**Duration:** July 2022 – Present  
**Developed by:** Andy, Senior Software Engineer

## Table of Contents
1. Introduction
    - System Purpose and Overview
2. Features and Functionalities
3. Database Schema
4. High-Level Design
    - Microservice Architecture
    - Module Pictures
5. REST API Design
6. Data Flow Diagrams
7. Message Queue
8. Technical Challenges
9. AWS Integration

---

## 1. Introduction

### System Purpose and Overview
The Property Management Platform is designed to improve work efficiency for community staff and enhance customer service quality. The platform offers comprehensive management services, including community asset management, visitor management, online repair reporting, and complaint management. The primary objective is to build a high-quality service platform that better serves community residents.

## 2. Features and Functionalities
- **Community Asset Management:** Manage and monitor community assets, including facilities and equipment.
- **Visitor Management:** Track and manage visitor information and access.
- **Online Repair Reporting:** Allow residents to report repair issues and track their status.
- **Complaint Management:** Enable residents to file complaints and monitor resolutions.
- **Role and User Management:** Manage user roles, permissions, and authentication.
- **Reporting:** Import and export reports, generate custom templates for data processing.

## 3. Database Schema

### Tables


#### Community Asset Module

- **Community Table: community**

| Field Name                | Data Type      | Nullable | Description           |
| ------------------------- | -------------- | -------- | --------------------- |
| community_id              | bigint(20)     | NO       | Community ID          |
| community_name            | varchar(128)   | YES      | Community Name        |
| community_code            | varchar(128)   | YES      | Community Code        |
| community_province_code   | varchar(32)    | YES      | Province Code         |
| community_city_code       | varchar(32)    | YES      | City Code             |
| community_town_code       | varchar(32)    | YES      | Town Code             |
| community_detailed_address| varchar(128)   | YES      | Detailed Address      |
| community_longitude       | varchar(32)    | YES      | Longitude             |
| community_latitude        | varchar(32)    | YES      | Latitude              |
| dept_id                   | bigint(32)     | YES      | Property ID           |
| community_sort            | int(11)        | YES      | Sort Order            |
| create_by                 | varchar(32)    | YES      | Creator               |
| create_time               | datetime       | YES      | Creation Time         |
| update_by                 | varchar(32)    | YES      | Updater               |
| update_time               | datetime       | YES      | Update Time           |
| remark                    | varchar(1024)  | YES      | Remark                |
|                           |                |          |                       |

- **Building Table: building**

| Field Name         | Data Type       | Nullable | Description   |
| ------------------ | --------------- | -------- | ------------- |
| building_id        | bigint(20)      | YES      | Building ID   |
| building_name      | varchar(32)     | YES      | Building Name |
| building_code      | varchar(32)     | YES      | Building Code |
| building_acreage   | decimal(32,10)  | YES      | Building Area |
| community_id       | bigint(20)      | YES      | Community ID  |
| create_by          | varchar(32)     | YES      | Creator       |
| create_time        | datetime        | YES      | Creation Time |
| update_by          | varchar(32)     | YES      | Updater       |
| update_time        | datetime        | YES      | Update Time   |
| remark             | varchar(1024)   | YES      | Remark        |
|                    |                 |          |               |

- **Unit Table: unit**

| Field Name           | Data Type       | Nullable | Description      |
| -------------------- | --------------- | -------- | ---------------- |
| unit_id              | bigint(20)      | YES      | Unit ID          |
| community_id         | bigint(20)      | YES      | Community ID     |
| building_id          | bigint(20)      | YES      | Building ID      |
| unit_name            | varchar(32)     | YES      | Unit Name        |
| unit_code            | varchar(128)    | YES      | Unit Code        |
| unit_level           | int(11)         | YES      | Number of Floors |
| unit_acreage         | decimal(32,10)  | YES      | Building Area    |
| unit_have_elevator   | varchar(32)     | YES      | Has Elevator     |
| create_by            | varchar(32)     | YES      | Creator          |
| create_time          | datetime        | YES      | Creation Time    |
| update_by            | varchar(32)     | YES      | Updater          |
| update_time          | datetime        | YES      | Update Time      |
| remark               | varchar(1024)   | YES      | Remark           |
|                      |                 |          |                  |

- **Room Table: room**

| Field Name                | Data Type       | Nullable | Description           |
| ------------------------- | --------------- | -------- | --------------------- |
| room_id                   | bigint(20)      | YES      | Room ID               |
| community_id              | bigint(20)      | YES      | Community ID          |
| building_id               | bigint(20)      | YES      | Building ID           |
| unit_id                   | bigint(20)      | YES      | Unit ID               |
| room_level                | int(11)         | YES      | Floor Number          |
| room_code                 | varchar(32)     | YES      | Room Code             |
| room_name                 | varchar(32)     | YES      | Room Name             |
| room_acreage              | decimal(32,10)  | YES      | Building Area         |
| room_cost                 | decimal(32,10)  | YES      | Cost Factor           |
| room_status               | varchar(32)     | YES      | Room Status           |
| room_is_shop              | varchar(32)     | YES      | Is Shop               |
| room_is_commercial_house  | varchar(32)     | YES      | Is Commercial House   |
| room_house_type           | varchar(32)     | YES      | House Type            |
| create_by                 | varchar(32)     | YES      | Creator               |
| create_time               | datetime        | YES      | Creation Time         |
| update_by                 | varchar(32)     | YES      | Updater               |
| update_time               | datetime        | YES      | Update Time           |
| remark                    | varchar(1024)   | YES      | Remark                |
|                           |                 |          |                       |

- **Community Interaction Table: community_interaction**

| Field Name       | Data Type      | Nullable | Description           |
| ---------------- | -------------- | -------- | --------------------- |
| interaction_id   | bigint(20)     | NO       | Interaction ID        |
| community_id     | bigint(20)     | YES      | Community ID          |
| create_by        | varchar(32)    | YES      | Creator ID            |
| update_by        | varchar(32)    | YES      | Updater ID            |
| create_time      | datetime       | YES      | Creation Time         |
| update_time      | datetime       | YES      | Update Time           |
| content          | varchar(1024)  | YES      | Content               |
| del_flag         | int(2)         | YES      | Deletion Status (0 default, 1 deleted) |
| remark           | varchar(255)   | YES      | Remark                |
| user_id          | bigint(20)     | YES      | User ID               |
|                  |                |          |                       |

#### Community Management Module

- **Owner Table: zy_owner**

| Field Name           | Data Type      | Nullable | Description                     |
| -------------------- | -------------- | -------- | ------------------------------- |
| owner_id             | bigint(20)     | NO       | Owner ID                        |
| owner_nickname       | varchar(30)    | YES      | Nickname                        |
| owner_real_name      | varchar(30)    | YES      | Real Name                       |
| owner_gender         | varchar(10)    | YES      | Gender (unknown/male/female)    |
| owner_age            | int(3)         | YES      | Age                             |
| owner_id_card        | varchar(20)    | YES      | ID Card Number                  |
| owner_phone_number   | varchar(11)    | YES      | Phone Number                    |
| owner_open_id        | varchar(64)    | YES      | OpenID                          |
| owner_wechat_id      | varchar(64)    | YES      | WeChat ID                       |
| owner_qq_number      | varchar(20)    | YES      | QQ Number                       |
| owner_birthday       | date           | YES      | Birthday                        |
| owner_portrait       | varchar(256)   | YES      | Portrait                        |
| owner_signature      | varchar(64)    | YES      | Signature                       |
| owner_status         | varchar(10)    | YES      | Status (enable/disable)         |
| owner_logon_mode     | varchar(10)    | YES      | Registration Mode (WeChat/app/web) |
| owner_type           | varchar(32)    | YES      | Owner Type                      |
| owner_password       | varchar(128)   | YES      | Password                        |
| create_by            | varchar(32)    | YES      | Creator                         |
| create_time          | datetime       | YES      | Creation Time                   |
| update_by            | varchar(32)    | YES      | Updater                         |
| update_time          | datetime       | YES      | Update Time                     |
| remark               | varchar(1024)  | YES      | Remark                          |

- **House Binding Table**

| Field Name      | Data Type      | Nullable | Description                        |
| --------------- | -------------- | -------- | ---------------------------------- |
| owner_room_id   | bigint(20)     | NO       | House Binding ID                   |
| community_id    | bigint(20)     | YES      | Community ID                       |
| building_id     | bigint(20)     | YES      | Building ID                        |
| unit_id         | bigint(20)     | YES      | Unit ID                            |
| room_id         | bigint(20)     | YES      | Room ID                            |
| owner_id        | bigint(20)     | YES      | Owner ID                           |
| owner_type      | varchar(32)    | YES      |

## 4. High-Level Design

### Microservice Architecture

- **User Service:** Manages user authentication, roles, and permissions.
- **Asset Service:** Handles community asset management.
- **Visitor Service:** Manages visitor information and tracking.
- **Report Service:** Facilitates report generation and management.
- **Notification Service:** Sends notifications and alerts to users.

### Module Pictures
![Microservice Architecture](https://via.placeholder.com/600x400.png?text=Microservice+Architecture)

## 5. REST API Design

### User Service
1. **Create User**
    - **Endpoint:** `POST /api/users`
    - **Request Body:**
        ```json
        {
            "username": "johndoe",
            "password": "password123",
            "email": "johndoe@example.com",
            "role_id": 1
        }
        ```
    - **Response:**
        ```json
        {
            "message": "User created successfully",
            "user_id": 101
        }
        ```

2. **Authenticate User**
    - **Endpoint:** `POST /api/auth`
    - **Request Body:**
        ```json
        {
            "username": "johndoe",
            "password": "password123"
        }
        ```
    - **Response:**
        ```json
        {
            "token": "jwt_token_here",
            "expires_in": 3600
        }
        ```

### Asset Service
3. **Get All Assets**
    - **Endpoint:** `GET /api/assets`
    - **Response:**
        ```json
        [
            {
                "asset_id": 1,
                "name": "Swimming Pool",
                "location": "Community Center",
                "status": "Operational"
            },
            {
                "asset_id": 2,
                "name": "Gym",
                "location": "Building A",
                "status": "Under Maintenance"
            }
        ]
        ```

4. **Update Asset Status**
    - **Endpoint:** `PUT /api/assets/{asset_id}`
    - **Request Body:**
        ```json
        {
            "status": "Operational"
        }
        ```
    - **Response:**
        ```json
        {
            "message": "Asset status updated successfully"
        }
        ```

## 6. Data Flow Diagrams

### Data Flow Diagram 1: User Authentication
![Data Flow Diagram 1](https://via.placeholder.com/600x400.png?text=User+Authentication)

1. User submits login credentials via the frontend.
2. The frontend sends the login request to the User Service.
3. User Service validates the credentials and generates a JWT token.
4. The token is returned to the frontend.
5. The frontend stores the token and uses it for subsequent requests.

### Data Flow Diagram 2: Report Generation
![Data Flow Diagram 2](https://via.placeholder.com/600x400.png?text=Report+Generation)

1. User requests a report via the frontend.
2. The request is sent to the Report Service.
3. Report Service generates the report using EasyPOI and stores it.
4. The report path is returned to the frontend.
5. User can download the report from the provided path.

## 7. Message Queue

### Kafka Integration
- **Purpose:** Used for asynchronous communication between services.
- **Example Use Case:** Notifications for report generation completion.
- **Implementation:**
    - Producer Service (Report Service) sends a message when a report is generated.
    - Consumer Service (Notification Service) receives the message and sends a notification to the user.

## 8. Technical Challenges

### Data Consistency
- **Challenge:** Ensuring data consistency across microservices.
- **Solution:** Implemented distributed transactions using the Saga pattern.

### Performance Optimization
- **Challenge:** Maintaining performance under high user load.
- **Solution:** Used Redis for caching frequently accessed data, reducing database load by 30%.

### Scalability
- **Challenge:** Scaling the system to handle increasing traffic.
- **Solution:** Deployed services on Kubernetes, enabling horizontal scaling and better resource management.

## 9. AWS Integration

### AWS Services Used
- **Amazon RDS:** Hosted Oracle Database.
- **Amazon S3:** Storage for reports and logs.
- **Amazon EC2:** Instances for deploying microservices.
- **Amazon CloudWatch:** Monitoring and logging.

### Deployment Strategy
- **Containerization:** Docker used for containerizing services.
- **Orchestration:** Kubernetes for managing containerized applications.
- **CI/CD:** Jenkins for continuous integration and deployment.

---

## 10. Additional Project Insights

### Multithreading Usage
In the Property Management Platform, we used multithreading to handle concurrent processing of visitor check-ins and asset status updates. This ensured that our system could efficiently manage multiple operations simultaneously without performance degradation.

### Builder Design Pattern
The Builder design pattern was employed in the Report Service to construct complex report objects. This pattern helped in managing the creation process, especially when reports required multiple optional parameters and complex configurations.

### Team Composition
As the team leader, I oversaw a team of six members:
- **Backend Developers (2):** Focused on developing and maintaining the microservices.
- **Frontend Developer (1):** Developed the user interface and ensured seamless user experience.
- **QA Engineer (1):** Responsible for testing the platform and ensuring high-quality releases.
- **DevOps Engineer (1):** Managed our CI/CD pipeline, AWS infrastructure, and ensured system reliability.
- **Product Manager (1):** Coordinated requirements and worked with stakeholders to define features.

### Jenkins Pipeline Design
Our Jenkins pipeline for AWS included the following stages:
1. **Code Checkout:** Retrieve the latest code from the repository.
2. **Build:** Compile the code and run unit tests.
3. **Docker Build:** Build Docker images for each microservice.
4. **Security Scan:** Perform security checks on the Docker images.
5. **Deploy to Staging:** Deploy the Docker images to the staging environment on AWS ECS.
6. **Integration Tests:** Run integration tests in the staging environment.
7. **Deploy to Production:** Upon successful tests, deploy the Docker images to the production environment on AWS ECS.
8. **Notification:** Send deployment notifications to the team via Slack.

### Monitoring Strategy
Our monitoring setup included:
- **AWS CloudWatch:** Used for monitoring the health and performance of our AWS resources.
- **Prometheus and Grafana:** Implemented for detailed application metrics and dashboard visualizations.
- **ELK Stack:** Utilized for log aggregation, searching, and analysis.

### Usage Metrics
- **Daily Users:** Approximately 2,000 active users daily.
- **Transactions Per Second (TPS):** Average TPS of 50 during peak hours.
- **Queries Per Second (QPS):** Average QPS of 100 for our database.

### Frontend Story
Our frontend, developed using React, provided an intuitive and responsive interface for users. We focused on creating a seamless user experience with features like real

-time notifications, user-friendly forms for reporting issues, and dashboards for monitoring asset status and visitor information. The frontend communicated with backend microservices via REST APIs, ensuring efficient data exchange and updates.

---



### 7. Message Queue

The message queue system is crucial for handling asynchronous communication between various microservices within the Property Management Platform. It ensures reliable message delivery, decouples microservices, and enhances system scalability and resilience.

#### Overview

**Purpose:**
- To facilitate asynchronous communication between different services.
- To decouple service dependencies.
- To handle high throughput and ensure reliable message delivery.

**Components:**
- **Message Broker:** Manages the message queues.
- **Producers:** Services that send messages.
- **Consumers:** Services that receive and process messages.

**Technology:** RabbitMQ (chosen for its robustness and extensive support in the industry)

#### Key Message Queues

1. **User Registration Queue:**
    - **Producer:** User Service
    - **Consumer:** Email Notification Service
    - **Purpose:** To send a confirmation email after a user registers.

2. **Asset Management Queue:**
    - **Producer:** Asset Service
    - **Consumer:** Reporting Service
    - **Purpose:** To update reports when new assets are added or updated.

3. **Visitor Management Queue:**
    - **Producer:** Visitor Service
    - **Consumer:** Security Notification Service
    - **Purpose:** To notify security staff about visitor arrivals.

4. **Repair Request Queue:**
    - **Producer:** Repair Service
    - **Consumer:** Maintenance Staff Notification Service
    - **Purpose:** To inform maintenance staff about new repair requests.

5. **Complaint Management Queue:**
    - **Producer:** Complaint Service
    - **Consumer:** Customer Service Notification Service
    - **Purpose:** To notify customer service about new complaints filed by residents.

6. **Reporting Queue:**
    - **Producer:** Various Services (User, Asset, Visitor, etc.)
    - **Consumer:** Reporting Service
    - **Purpose:** To aggregate data for generating reports.

7. **Notification Queue:**
    - **Producer:** Various Services (User, Asset, Repair, Complaint, etc.)
    - **Consumer:** Notification Service
    - **Purpose:** To send notifications to users, admins, and staff about various events and updates.

#### Detailed Steps for Each Queue

##### User Registration Queue

**Detailed Steps:**

1. **User Registers:**
    - User submits registration details.
2. **User Service Publishes Message:**
    - User Service validates data and publishes a message to the User Registration Queue.
3. **Email Notification Service Consumes Message:**
    - Email Notification Service retrieves the message from the queue.
4. **Send Confirmation Email:**
    - Email Notification Service sends a confirmation email to the user.

```
User Registers --> User Service Publishes Message --> Message Broker (User Registration Queue) --> Email Notification Service Consumes Message --> Send Confirmation Email
```

##### Asset Management Queue

**Detailed Steps:**

1. **Add/Update Asset Info:**
    - Community staff add or update asset information.
2. **Asset Service Publishes Message:**
    - Asset Service validates data and publishes a message to the Asset Management Queue.
3. **Reporting Service Consumes Message:**
    - Reporting Service retrieves the message from the queue.
4. **Update Reports:**
    - Reporting Service updates asset-related reports.

```
Add/Update Asset Info --> Asset Service Publishes Message --> Message Broker (Asset Management Queue) --> Reporting Service Consumes Message --> Update Reports
```

##### Visitor Management Queue

**Detailed Steps:**

1. **Register Visitor:**
    - Visitor provides details at the entrance.
2. **Visitor Service Publishes Message:**
    - Visitor Service validates data and publishes a message to the Visitor Management Queue.
3. **Security Notification Service Consumes Message:**
    - Security Notification Service retrieves the message from the queue.
4. **Notify Security Staff:**
    - Security Notification Service sends notifications to security staff about visitor arrivals.

```
Register Visitor --> Visitor Service Publishes Message --> Message Broker (Visitor Management Queue) --> Security Notification Service Consumes Message --> Notify Security Staff
```

##### Repair Request Queue

**Detailed Steps:**

1. **Submit Repair Request:**
    - Resident submits a repair request.
2. **Repair Service Publishes Message:**
    - Repair Service validates data and publishes a message to the Repair Request Queue.
3. **Maintenance Staff Notification Service Consumes Message:**
    - Maintenance Staff Notification Service retrieves the message from the queue.
4. **Notify Maintenance Staff:**
    - Maintenance Staff Notification Service notifies maintenance staff about the repair request.

```
Submit Repair Request --> Repair Service Publishes Message --> Message Broker (Repair Request Queue) --> Maintenance Staff Notification Service Consumes Message --> Notify Maintenance Staff
```

##### Complaint Management Queue

**Detailed Steps:**

1. **Submit Complaint:**
    - Resident files a complaint.
2. **Complaint Service Publishes Message:**
    - Complaint Service validates data and publishes a message to the Complaint Management Queue.
3. **Customer Service Notification Service Consumes Message:**
    - Customer Service Notification Service retrieves the message from the queue.
4. **Notify Customer Service:**
    - Customer Service Notification Service notifies customer service staff about the new complaint.

```
Submit Complaint --> Complaint Service Publishes Message --> Message Broker (Complaint Management Queue) --> Customer Service Notification Service Consumes Message --> Notify Customer Service
```

##### Reporting Queue

**Detailed Steps:**

1. **Data Changes:**
    - Various services trigger data changes (User, Asset, Visitor, etc.).
2. **Service Publishes Message:**
    - Relevant service publishes a message to the Reporting Queue.
3. **Reporting Service Consumes Message:**
    - Reporting Service retrieves the message from the queue.
4. **Update Reports:**
    - Reporting Service updates reports based on the new data.

```
Data Changes --> Service Publishes Message --> Message Broker (Reporting Queue) --> Reporting Service Consumes Message --> Update Reports
```

##### Notification Queue

**Detailed Steps:**

1. **Event Triggers:**
    - Various events (User registration, asset update, repair request, etc.) occur.
2. **Service Publishes Message:**
    - Relevant service publishes a message to the Notification Queue.
3. **Notification Service Consumes Message:**
    - Notification Service retrieves the message from the queue.
4. **Send Notification:**
    - Notification Service sends notifications to the intended recipients.

```
Event Triggers --> Service Publishes Message --> Message Broker (Notification Queue) --> Notification Service Consumes Message --> Send Notification
```

### Benefits of Using Message Queues

1. **Decoupling:** Services can operate independently without needing to wait for each other’s processes.
2. **Scalability:** The system can handle increased load by scaling the message queue infrastructure.
3. **Reliability:** Ensures messages are delivered even if some services are temporarily down.
4. **Flexibility:** New services can be added to consume messages from existing queues without impacting the producers.
5. **Resilience:** Provides fault tolerance, as messages are persisted in the queue until successfully processed.
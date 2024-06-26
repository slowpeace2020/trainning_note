11. A company has an application that runs on Amazon EC2 instances and uses an Amazon Aurora database. The EC2 instances connect to the database by using usernames and passwords that are stored locally in a file. The company wants to minimize the operational overhead of credential management.
    What should a solutions architect do to accomplish this goal?

A. Use AWS Secrets Manager. Turn on automatic rotation.  
B. Use AWS Systems Manager Parameter Store. Turn on automatic rotation.  
C. Create an Amazon S3 bucket to store objects that are encrypted with an AWS Key Management Service (AWS KMS) encryption key. Migrate the credential file to the S3 bucket. Point the application to the S3 bucket.  
D. Create an encrypted Amazon Elastic Block Store (Amazon EBS) volume for each EC2 instance. Attach the new EBS volume to each EC2 instance. Migrate the credential file to the new EBS volume. Point the application to the new EBS volume  

12. A global company hosts its web application on Amazon EC2 instances behind an Application Load Balancer (ALB). The web application has static data and dynamic data. The company stores its static data in an Amazon S3 bucket. The company wants to improve performance and reduce latency for the static data and dynamic data. The company is using its own domain name registered with Amazon Route 53.
What should a solutions architect do to meet these requirements?
A. Create an Amazon CloudFront distribution that has the S3 bucket and the ALB as origins. Configure Route 53 to route tra c to the CloudFront distribution.
B. Create an Amazon CloudFront distribution that has the ALB as an origin. Create an AWS Global Accelerator standard accelerator that has the S3 bucket as an endpoint Con gure Route 53 to route tra c to the CloudFront distribution.
C. Create an Amazon CloudFront distribution that has the S3 bucket as an origin. Create an AWS Global Accelerator standard accelerator that has the ALB and the CloudFront distribution as endpoints. Create a custom domain name that points to the accelerator DNS name. Use the custom domain name as an endpoint for the web application.
D. Create an Amazon CloudFront distribution that has the ALB as an origin. Create an AWS Global Accelerator standard accelerator that has the S3 bucket as an endpoint. Create two domain names. Point one domain name to the CloudFront DNS name for dynamic content. Point the other domain name to the accelerator DNS name for static content. Use the domain names as endpoints for the web application.

13. A company performs monthly maintenance on its AWS infrastructure. During these maintenance activities, the company needs to rotate the credentials for its Amazon RDS for MySQL databases across multiple AWS Regions.
    Which solution will meet these requirements with the LEAST operational overhead?

A. Store the credentials as secrets in AWS Secrets Manager. Use multi-Region secret replication for the required Regions. Congure Secrets Manager to rotate the secrets on a schedule.
B. Store the credentials as secrets in AWS Systems Manager by creating a secure string parameter. Use multi-Region secret replication for the required Regions. Congure Systems Manager to rotate the secrets on a schedule.
C. Store the credentials in an Amazon S3 bucket that has server-side encryption (SSE) enabled. Use Amazon EventBridge (Amazon CloudWatch Events) to invoke an AWS Lambda function to rotate the credentials.
D. Encrypt the credentials as secrets by using AWS Key Management Service (AWS KMS) multi-Region customer managed keys. Store the secrets in an Amazon DynamoDB global table. Use an AWS Lambda function to retrieve the secrets from DynamoDB. Use the RDS API to rotate the secrets.

14. A company runs an ecommerce application on Amazon EC2 instances behind an Application Load Balancer. The instances run in an Amazon EC2 Auto Scaling group across multiple Availability Zones. The Auto Scaling group scales based on CPU utilization metrics. The ecommerce application stores the transaction data in a MySQL 8.0 database that is hosted on a large EC2 instance.
    The database's performance degrades quickly as application load increases. The application handles more read requests than write transactions. The company wants a solution that will automatically scale the database to meet the demand of unpredictable read workloads while maintaining high availability.
    Which solution will meet these requirements?
    A. Use Amazon Redshift with a single node for leader and compute functionality.
    B. Use Amazon RDS with a Single-AZ deployment Congure Amazon RDS to add reader instances in a different Availability Zone.
    C. Use Amazon Aurora with a Multi-AZ deployment. Congure Aurora Auto Scaling with Aurora Replicas.
    D. Use Amazon ElastiCache for Memcached with EC2 Spot Instances.
15. A company recently migrated to AWS and wants to implement a solution to protect the trac that ows in and out of the production VPC. The company had an inspection server in its on-premises data center. The inspection server performed specic operations such as trac ow inspection and trac ltering. The company wants to have the same functionalities in the AWS Cloud.
    Which solution will meet these requirements?
    A. Use Amazon GuardDuty for trac inspection and trac ltering in the production VPC.
    B. Use Trac Mirroring to mirror trac from the production VPC for trac inspection and ltering.
    C. Use AWS Network Firewall to create the required rules for trac inspection and trac ltering for the production VPC.
    D. Use AWS Firewall Manager to create the required rules for trac inspection and trac ltering for the production VPC.
16. A company hosts a data lake on AWS. The data lake consists of data in Amazon S3 and Amazon RDS for PostgreSQL. The company needs a reporting solution that provides data visualization and includes all the data sources within the data lake. Only the company's management team should have full access to all the visualizations. The rest of the company should have only limited access.
    Which solution will meet these requirements?
    A. Create an analysis in Amazon QuickSight. Connect all the data sources and create new datasets. Publish dashboards to visualize the data. Share the dashboards with the appropriate IAM roles.  
    B. Create an analysis in Amazon QuickSight. Connect all the data sources and create new datasets. Publish dashboards to visualize the data. Share the dashboards with the appropriate users and groups.  
    C. Create an AWS Glue table and crawler for the data in Amazon S3. Create an AWS Glue extract, transform, and load (ETL) job to produce reports. Publish the reports to Amazon S3. Use S3 bucket policies to limit access to the reports.  
    D. Create an AWS Glue table and crawler for the data in Amazon S3. Use Amazon Athena Federated Query to access data within Amazon RDS for PostgreSQL. Generate reports by using Amazon Athena. Publish the reports to Amazon S3. Use S3 bucket policies to limit access to the reports.  
17. A company is implementing a new business application. The application runs on two Amazon EC2 instances and uses an Amazon S3 bucket for document storage. A solutions architect needs to ensure that the EC2 instances can access the S3 bucket.  
    What should the solutions architect do to meet this requirement?
    A. Create an IAM role that grants access to the S3 bucket. Attach the role to the EC2 instances.
    B. Create an IAM policy that grants access to the S3 bucket. Attach the policy to the EC2 instances.
    C. Create an IAM group that grants access to the S3 bucket. Attach the group to the EC2 instances.
    D. Create an IAM user that grants access to the S3 bucket. Attach the user account to the EC2 instances.
18. An application development team is designing a microservice that will convert large images to smaller, compressed images. When a user uploads an image through the web interface, the microservice should store the image in an Amazon S3 bucket, process and compress the image with an AWS Lambda function, and store the image in its compressed form in a different S3 bucket.
    A solutions architect needs to design a solution that uses durable, stateless components to process the images automatically.
    Which combination of actions will meet these requirements? (Choose two.)
    A. Create an Amazon Simple Queue Service (Amazon SQS) queue. Congure the S3 bucket to send a notication to the SQS queue when an image is uploaded to the S3 bucket.
    B. Congure the Lambda function to use the Amazon Simple Queue Service (Amazon SQS) queue as the invocation source. When the SQS message is successfully processed, delete the message in the queue.
    C. Congure the Lambda function to monitor the S3 bucket for new uploads. When an uploaded image is detected, write the le name to a text le in memory and use the text le to keep track of the images that were processed.
    D. Launch an Amazon EC2 instance to monitor an Amazon Simple Queue Service (Amazon SQS) queue. When items are added to the queue, log the le name in a text le on the EC2 instance and invoke the Lambda function.
    E. Congure an Amazon EventBridge (Amazon CloudWatch Events) event to monitor the S3 bucket. When an image is uploaded, send an alert to an Amazon ample Notication Service (Amazon SNS) topic with the application owner's email address for further processing.  
19. A company has a three-tier web application that is deployed on AWS. The web servers are deployed in a public subnet in a VPC. The application servers and database servers are deployed in private subnets in the same VPC. The company has deployed a third-party virtual firewall appliance from AWS Marketplace in an inspection VPC. The appliance is configured with an IP interface that can accept IP packets. A solutions architect needs to integrate the web application with the appliance to inspect all traffic to the application before the traffic reaches the web server.
    Which solution will meet these requirements with the LEAST operational overhead?

A. Create a Network Load Balancer in the public subnet of the application's VPC to route the traffic to the appliance for packet inspection.
B. Create an Application Load Balancer in the public subnet of the application's VPC to route the traffic to the appliance for packet inspection.
C. Deploy a transit gateway in the inspection VPC and configure route tables to route the incoming packets through the transit gateway.
D. Deploy a Gateway Load Balancer in the inspection VPC. Create a Gateway Load Balancer endpoint to receive the incoming packets and forward the packets to the appliance.

20. A company wants to improve its ability to clone large amounts of production data into a test environment in the same AWS Region. The data is stored in Amazon EC2 instances on Amazon Elastic Block Store (Amazon EBS) volumes. Modications to the cloned data must not affect the production environment. The software that accesses this data requires consistently high I/O performance.
    A solutions architect needs to minimize the time that is required to clone the production data into the test environment.
    Which solution will meet these requirements?
    A. Take EBS snapshots of the production EBS volumes. Restore the snapshots onto EC2 instance store volumes in the test environment.
    B. Congure the production EBS volumes to use the EBS Multi-Attach feature. Take EBS snapshots of the production EBS volumes. Attach the production EBS volumes to the EC2 instances in the test environment.
    C. Take EBS snapshots of the production EBS volumes. Create and initialize new EBS volumes. Attach the new EBS volumes to EC2 instances in the test environment before restoring the volumes from the production EBS snapshots.
    D. Take EBS snapshots of the production EBS volumes. Turn on the EBS fast snapshot restore feature on the EBS snapshots. Restore the snapshots into new EBS volumes. Attach the new EBS volumes to EC2 instances in the test environment.
21. An ecommerce company wants to launch a one-deal-a-day website on AWS. Each day will feature exactly one product on sale for a period of 24 hours. The company wants to be able to handle millions of requests each hour with millisecond latency during peak hours.
    Which solution will meet these requirements with the LEAST operational overhead?
    A. Use Amazon S3 to host the full website in different S3 buckets. Add Amazon CloudFront distributions. Set the S3 buckets as origins for the distributions. Store the order data in Amazon S3.
    B. Deploy the full website on Amazon EC2 instances that run in Auto Scaling groups across multiple Availability Zones. Add an Application Load Balancer (ALB) to distribute the website trac. Add another ALB for the backend APIs. Store the data in Amazon RDS for MySQL.
    C. Migrate the full application to run in containers. Host the containers on Amazon Elastic Kubernetes Service (Amazon EKS). Use the Kubernetes Cluster Autoscaler to increase and decrease the number of pods to process bursts in trac. Store the data in Amazon RDS for MySQL.
    D. Use an Amazon S3 bucket to host the website's static content. Deploy an Amazon CloudFront distribution. Set the S3 bucket as the origin. Use Amazon API Gateway and AWS Lambda functions for the backend APIs. Store the data in Amazon DynamoDB.
22. A solutions architect is using Amazon S3 to design the storage architecture of a new digital media application. The media les must be resilient to the loss of an Availability Zone. Some les are accessed frequently while other les are rarely accessed in an unpredictable pattern. The solutions architect must minimize the costs of storing and retrieving the media les.
    Which storage option meets these requirements?
    A. S3 Standard
    B. S3 Intelligent-Tiering
    C. S3 Standard-Infrequent Access (S3 Standard-IA)
    D. S3 One Zone-Infrequent Access (S3 One Zone-IA)
23. A company is storing backup les by using Amazon S3 Standard storage. The les are accessed frequently for 1 month. However, the les are not accessed after 1 month. The company must keep the les indenitely.
    Which storage solution will meet these requirements MOST cost-effectively?
    A. Congure S3 Intelligent-Tiering to automatically migrate objects.
    B. Create an S3 Lifecycle conguration to transition objects from S3 Standard to S3 Glacier Deep Archive after 1 month.
    C. Create an S3 Lifecycle conguration to transition objects from S3 Standard to S3 Standard-Infrequent Access (S3 Standard-IA) after 1 month.
    D. Create an S3 Lifecycle conguration to transition objects from S3 Standard to S3 One Zone-Infrequent Access (S3 One Zone-IA) after 1 month.
24. A  company observes an increase in Amazon EC2 costs in its most recent bill. The billing team notices unwanted vertical scaling of instance types for a couple of EC2 instances. A solutions architect needs to create a graph comparing the last 2 months of EC2 costs and perform an in-depth analysis to identify the root cause of the vertical scaling.
    How should the solutions architect generate the information with the LEAST operational overhead?
    A. Use AWS Budgets to create a budget report and compare EC2 costs based on instance types.
    B. Use Cost Explorer's granular ltering feature to perform an in-depth analysis of EC2 costs based on instance types.
    C. Use graphs from the AWS Billing and Cost Management dashboard to compare EC2 costs based on instance types for the last 2 months.
    D. Use AWS Cost and Usage Reports to create a report and send it to an Amazon S3 bucket. Use Amazon QuickSight with Amazon S3 as a source to generate an interactive graph based on instance types.
25. A company is designing an application. The application uses an AWS Lambda function to receive information through Amazon API Gateway and to store the information in an Amazon Aurora PostgreSQL database.
    During the proof-of-concept stage, the company has to increase the Lambda quotas signicantly to handle the high volumes of data that the company needs to load into the database. A solutions architect must recommend a new design to improve scalability and minimize the conguration effort.
    Which solution will meet these requirements?
    A. Refactor the Lambda function code to Apache Tomcat code that runs on Amazon EC2 instances. Connect the database by using native Java Database Connectivity (JDBC) drivers.
    B. Change the platform from Aurora to Amazon DynamoDProvision a DynamoDB Accelerator (DAX) cluster. Use the DAX client SDK to point the existing DynamoDB API calls at the DAX cluster.
    C. Set up two Lambda functions. Congure one function to receive the information. Congure the other function to load the information into the database. Integrate the Lambda functions by using Amazon Simple Notication Service (Amazon SNS).
    D. Set up two Lambda functions. Congure one function to receive the information. Congure the other function to load the information into the database. Integrate the Lambda functions by using an Amazon Simple Queue Service (Amazon SQS) queue.
26. A company needs to review its AWS Cloud deployment to ensure that its Amazon S3 buckets do not have unauthorized conguration changes. What should a solutions architect do to accomplish this goal?
    A. Turn on AWS Cong with the appropriate rules.
    B. Turn on AWS Trusted Advisor with the appropriate checks.
    C. Turn on Amazon Inspector with the appropriate assessment template.
    D. Turn on Amazon S3 server access logging. Congure Amazon EventBridge (Amazon Cloud Watch Events).
27. A company is launching a new application and will display application metrics on an Amazon CloudWatch dashboard. The company's product manager needs to access this dashboard periodically. The product manager does not have an AWS account. A solutions architect must provide access to the product manager by following the principle of least privilege.
    Which solution will meet these requirements?
    A. Share the dashboard from the CloudWatch console. Enter the product manager's email address, and complete the sharing steps. Provide a shareable link for the dashboard to the product manager.
    B. Create an IAM user specically for the product manager. Attach the CloudWatchReadOnlyAccess AWS managed policy to the user. Share the new login credentials with the product manager. Share the browser URL of the correct dashboard with the product manager.
    C. Create an IAM user for the company's employees. Attach the ViewOnlyAccess AWS managed policy to the IAM user. Share the new login credentials with the product manager. Ask the product manager to navigate to the CloudWatch console and locate the dashboard by name in the Dashboards section.
    D. Deploy a bastion server in a public subnet. When the product manager requires access to the dashboard, start the server and share the RDP credentials. On the bastion server, ensure that the browser is congured to open the dashboard URL with cached AWS credentials that have appropriate permissions to view the dashboard.
28. A company is migrating applications to AWS. The applications are deployed in different accounts. The company manages the accounts centrally by using AWS Organizations. The company's security team needs a single sign-on (SSO) solution across all the company's accounts. The company must continue managing the users and groups in its on-premises self-managed Microsoft Active Directory.
    Which solution will meet these requirements?
    A. Enable AWS Single Sign-On (AWS SSO) from the AWS SSO console. Create a one-way forest trust or a one-way domain trust to connect the company's self-managed Microsoft Active Directory with AWS SSO by using AWS Directory Service for Microsoft Active Directory.
    B. Enable AWS Single Sign-On (AWS SSO) from the AWS SSO console. Create a two-way forest trust to connect the company's self-managed Microsoft Active Directory with AWS SSO by using AWS Directory Service for Microsoft Active Directory.
    C. Use AWS Directory Service. Create a two-way trust relationship with the company's self-managed Microsoft Active Directory.
    D. Deploy an identity provider (IdP) on premises. Enable AWS Single Sign-On (AWS SSO) from the AWS SSO console.
29. A company provides a Voice over Internet Protocol (VoIP) service that uses UDP connections. The service consists of Amazon EC2 instances that run in an Auto Scaling group. The company has deployments across multiple AWS Regions.
    The company needs to route users to the Region with the lowest latency. The company also needs automated failover between Regions. Which solution will meet these requirements?
    A. Deploy a Network Load Balancer (NLB) and an associated target group. Associate the target group with the Auto Scaling group. Use the NLB as an AWS Global Accelerator endpoint in each Region.
    B. Deploy an Application Load Balancer (ALB) and an associated target group. Associate the target group with the Auto Scaling group. Use the ALB as an AWS Global Accelerator endpoint in each Region.
    C. Deploy a Network Load Balancer (NLB) and an associated target group. Associate the target group with the Auto Scaling group. Create an Amazon Route 53 latency record that points to aliases for each NLB. Create an Amazon CloudFront distribution that uses the latency record as an origin.
    D. Deploy an Application Load Balancer (ALB) and an associated target group. Associate the target group with the Auto Scaling group. Create an Amazon Route 53 weighted record that points to aliases for each ALB. Deploy an Amazon CloudFront distribution that uses the weighted record as an origin.
30. A development team runs monthly resource-intensive tests on its general purpose Amazon RDS for MySQL DB instance with Performance Insights enabled. The testing lasts for 48 hours once a month and is the only process that uses the database. The team wants to reduce the cost of running the tests without reducing the compute and memory attributes of the DB instance.
    Which solution meets these requirements MOST cost-effectively?
    A. Stop the DB instance when tests are completed. Restart the DB instance when required.
    B. Use an Auto Scaling policy with the DB instance to automatically scale when tests are completed.
    C. Create a snapshot when tests are completed. Terminate the DB instance and restore the snapshot when required.
    D. Modify the DB instance to a low-capacity instance when tests are completed. Modify the DB instance again when required.
31. A company that hosts its web application on AWS wants to ensure all Amazon EC2 instances. Amazon RDS DB instances. and Amazon Redshift clusters are congured with tags. The company wants to minimize the effort of conguring and operating this check.
    What should a solutions architect do to accomplish this?
    A. Use AWS Cong rules to dene and detect resources that are not properly tagged.
    B. Use Cost Explorer to display resources that are not properly tagged. Tag those resources manually.
    C. Write API calls to check all resources for proper tag allocation. Periodically run the code on an EC2 instance.
    D. Write API calls to check all resources for proper tag allocation. Schedule an AWS Lambda function through Amazon CloudWatch to periodically run the code.
32. A development team needs to host a website that will be accessed by other teams. The website contents consist of HTML, CSS, client-side JavaScript, and images.
    Which method is the MOST cost-effective for hosting the website?
    A. Containerize the website and host it in AWS Fargate.
    B. Create an Amazon S3 bucket and host the website there.
    C. Deploy a web server on an Amazon EC2 instance to host the website.
    D. Congure an Application Load Balancer with an AWS Lambda target that uses the Express.js framework.
33. A company runs an online marketplace web application on AWS. The application serves hundreds of thousands of users during peak hours. The company needs a scalable, near-real-time solution to share the details of millions of nancial transactions with several other internal applications. Transactions also need to be processed to remove sensitive data before being stored in a document database for low-latency retrieval.
    What should a solutions architect recommend to meet these requirements?
    A. Store the transactions data into Amazon DynamoDB. Set up a rule in DynamoDB to remove sensitive data from every transaction upon write. Use DynamoDB Streams to share the transactions data with other applications.
    B. Stream the transactions data into Amazon Kinesis Data Firehose to store data in Amazon DynamoDB and Amazon S3. Use AWS Lambda integration with Kinesis Data Firehose to remove sensitive data. Other applications can consume the data stored in Amazon S3.
    C. Stream the transactions data into Amazon Kinesis Data Streams. Use AWS Lambda integration to remove sensitive data from every transaction and then store the transactions data in Amazon DynamoDB. Other applications can consume the transactions data off the Kinesis data stream.
    D. Store the batched transactions data in Amazon S3 as les. Use AWS Lambda to process every le and remove sensitive data before updating the les in Amazon S3. The Lambda function then stores the data in Amazon DynamoDB. Other applications can consume transaction les stored in Amazon S3.
34. A company runs an online marketplace web application on AWS. The application serves hundreds of thousands of users during peak hours. The company needs a scalable, near-real-time solution to share the details of millions of nancial transactions with several other internal applications. Transactions also need to be processed to remove sensitive data before being stored in a document database for low-latency retrieval.
    What should a solutions architect recommend to meet these requirements?
    A. Store the transactions data into Amazon DynamoDB. Set up a rule in DynamoDB to remove sensitive data from every transaction upon write. Use DynamoDB Streams to share the transactions data with other applications.
    B. Stream the transactions data into Amazon Kinesis Data Firehose to store data in Amazon DynamoDB and Amazon S3. Use AWS Lambda integration with Kinesis Data Firehose to remove sensitive data. Other applications can consume the data stored in Amazon S3.
    C. Stream the transactions data into Amazon Kinesis Data Streams. Use AWS Lambda integration to remove sensitive data from every transaction and then store the transactions data in Amazon DynamoDB. Other applications can consume the transactions data off the Kinesis data stream.
    D. Store the batched transactions data in Amazon S3 as les. Use AWS Lambda to process every le and remove sensitive data before updating the les in Amazon S3. The Lambda function then stores the data in Amazon DynamoDB. Other applications can consume transaction les stored in Amazon S3.
35. A company is preparing to launch a public-facing web application in the AWS Cloud. The architecture consists of Amazon EC2 instances within a VPC behind an Elastic Load Balancer (ELB). A third-party service is used for the DNS. The company's solutions architect must recommend a solution to detect and protect against large-scale DDoS attacks.
    Which solution meets these requirements?
    A. Enable Amazon GuardDuty on the account.
    B. Enable Amazon Inspector on the EC2 instances.
    C. Enable AWS Shield and assign Amazon Route 53 to it.
    D. Enable AWS Shield Advanced and assign the ELB to it.
36. A company is building an application in the AWS Cloud. The application will store data in Amazon S3 buckets in two AWS Regions. The company must use an AWS Key Management Service (AWS KMS) customer managed key to encrypt all data that is stored in the S3 buckets. The data in both S3 buckets must be encrypted and decrypted with the same KMS key. The data and the key must be stored in each of the two Regions.
    Which solution will meet these requirements with the LEAST operational overhead?
    A. Create an S3 bucket in each Region. Congure the S3 buckets to use server-side encryption with Amazon S3 managed encryption keys (SSE-S3). Congure replication between the S3 buckets.
    B. Create a customer managed multi-Region KMS key. Create an S3 bucket in each Region. Congure replication between the S3 buckets. Congure the application to use the KMS key with client-side encryption.
    C. Create a customer managed KMS key and an S3 bucket in each Region. Congure the S3 buckets to use server-side encryption with Amazon S3 managed encryption keys (SSE-S3). Congure replication between the S3 buckets.
    D. Create a customer managed KMS key and an S3 bucket in each Region. Congure the S3 buckets to use server-side encryption with AWS KMS keys (SSE-KMS). Congure replication between the S3 buckets.
37. A company recently launched a variety of new workloads on Amazon EC2 instances in its AWS account. The company needs to create a strategy to access and administer the instances remotely and securely. The company needs to implement a repeatable process that works with native AWS services and follows the AWS Well-Architected Framework.
    Which solution will meet these requirements with the LEAST operational overhead?
    A. Use the EC2 serial console to directly access the terminal interface of each instance for administration.
    B. Attach the appropriate IAM role to each existing instance and new instance. Use AWS Systems Manager Session Manager to establish a remote SSH session.
    C. Create an administrative SSH key pair. Load the public key into each EC2 instance. Deploy a bastion host in a public subnet to provide a tunnel for administration of each instance.
    D. Establish an AWS Site-to-Site VPN connection. Instruct administrators to use their local on-premises machines to connect directly to the instances by using SSH keys across the VPN tunnel.
38. A company is hosting a static website on Amazon S3 and is using Amazon Route 53 for DNS. The website is experiencing increased demand from around the world. The company must decrease latency for users who access the website.
    Which solution meets these requirements MOST cost-effectively?
    A. Replicate the S3 bucket that contains the website to all AWS Regions. Add Route 53 geolocation routing entries.
    B. Provision accelerators in AWS Global Accelerator. Associate the supplied IP addresses with the S3 bucket. Edit the Route 53 entries to point to the IP addresses of the accelerators.
    C. Add an Amazon CloudFront distribution in front of the S3 bucket. Edit the Route 53 entries to point to the CloudFront distribution.
    D. Enable S3 Transfer Acceleration on the bucket. Edit the Route 53 entries to point to the new endpoint.
39. A company maintains a searchable repository of items on its website. The data is stored in an Amazon RDS for MySQL database table that contains more than 10 million rows. The database has 2 TB of General Purpose SSD storage. There are millions of updates against this data every day through the company's website.
    The company has noticed that some insert operations are taking 10 seconds or longer. The company has determined that the database storage performance is the problem.
    Which solution addresses this performance issue?
    A. Change the storage type to Provisioned IOPS SSD.
    B. Change the DB instance to a memory optimized instance class.
    C. Change the DB instance to a burstable performance instance class.
    D. Enable Multi-AZ RDS read replicas with MySQL native asynchronous replication.
40. A company has thousands of edge devices that collectively generate 1 TB of status alerts each day. Each alert is approximately 2 KB in size. A solutions architect needs to implement a solution to ingest and store the alerts for future analysis.
    The company wants a highly available solution. However, the company needs to minimize costs and does not want to manage additional infrastructure. Additionally, the company wants to keep 14 days of data available for immediate analysis and archive any data older than 14 days.
    What is the MOST operationally ecient solution that meets these requirements?
    A. Create an Amazon Kinesis Data Firehose delivery stream to ingest the alerts. Congure the Kinesis Data Firehose stream to deliver the alerts to an Amazon S3 bucket. Set up an S3 Lifecycle conguration to transition data to Amazon S3 Glacier after 14 days.
    B. Launch Amazon EC2 instances across two Availability Zones and place them behind an Elastic Load Balancer to ingest the alerts. Create a script on the EC2 instances that will store the alerts in an Amazon S3 bucket. Set up an S3 Lifecycle conguration to transition data to Amazon S3 Glacier after 14 days.
    C. Create an Amazon Kinesis Data Firehose delivery stream to ingest the alerts. Congure the Kinesis Data Firehose stream to deliver the alerts to an Amazon OpenSearch Service (Amazon Elasticsearch Service) cluster. Set up the Amazon OpenSearch Service (Amazon Elasticsearch Service) cluster to take manual snapshots every day and delete data from the cluster that is older than 14 days.
    D. Create an Amazon Simple Queue Service (Amazon SQS) standard queue to ingest the alerts, and set the message retention period to 14 days. Congure consumers to poll the SQS queue, check the age of the message, and analyze the message data as needed. If the message is 14 days old, the consumer should copy the message to an Amazon S3 bucket and delete the message from the SQS queue.
41. A company's application integrates with multiple software-as-a-service (SaaS) sources for data collection. The company runs Amazon EC2 instances to receive the data and to upload the data to an Amazon S3 bucket for analysis. The same EC2 instance that receives and uploads the data also sends a notication to the user when an upload is complete. The company has noticed slow application performance and wants to improve the performance as much as possible.
    Which solution will meet these requirements with the LEAST operational overhead?
    A. Create an Auto Scaling group so that EC2 instances can scale out. Congure an S3 event notication to send events to an Amazon Simple Notication Service (Amazon SNS) topic when the upload to the S3 bucket is complete.
    B. Create an Amazon AppFlow ow to transfer data between each SaaS source and the S3 bucket. Congure an S3 event notication to send events to an Amazon Simple Notication Service (Amazon SNS) topic when the upload to the S3 bucket is complete.
    C. Create an Amazon EventBridge (Amazon CloudWatch Events) rule for each SaaS source to send output data. Congure the S3 bucket as the rule's target. Create a second EventBridge (Cloud Watch Events) rule to send events when the upload to the S3 bucket is complete. Congure an Amazon Simple Notication Service (Amazon SNS) topic as the second rule's target.
    D. Create a Docker container to use instead of an EC2 instance. Host the containerized application on Amazon Elastic Container Service (Amazon ECS). Congure Amazon CloudWatch Container Insights to send events to an Amazon Simple Notication Service (Amazon SNS) topic when the upload to the S3 bucket is complete.
42. A company runs a highly available image-processing application on Amazon EC2 instances in a single VPC. The EC2 instances run inside several subnets across multiple Availability Zones. The EC2 instances do not communicate with each other. However, the EC2 instances download images from Amazon S3 and upload images to Amazon S3 through a single NAT gateway. The company is concerned about data transfer charges.
    What is the MOST cost-effective way for the company to avoid Regional data transfer charges?
    A. Launch the NAT gateway in each Availability Zone.
    B. Replace the NAT gateway with a NAT instance.
    C. Deploy a gateway VPC endpoint for Amazon S3.
    D. Provision an EC2 Dedicated Host to run the EC2 instances.
43. A company has an on-premises application that generates a large amount of time-sensitive data that is backed up to Amazon S3. The application has grown and there are user complaints about internet bandwidth limitations. A solutions architect needs to design a long-term solution that allows for both timely backups to Amazon S3 and with minimal impact on internet connectivity for internal users.
    Which solution meets these requirements?
    A. Establish AWS VPN connections and proxy all trac through a VPC gateway endpoint.
    B. Establish a new AWS Direct Connect connection and direct backup trac through this new connection.
    C. Order daily AWS Snowball devices. Load the data onto the Snowball devices and return the devices to AWS each day.
    D. Submit a support ticket through the AWS Management Console. Request the removal of S3 service limits from the account.
44. A company has an Amazon S3 bucket that contains critical data. The company must protect the data from accidental deletion. Which combination of steps should a solutions architect take to meet these requirements? (Choose two.)
    A. Enable versioning on the S3 bucket.
    B. Enable MFA Delete on the S3 bucket.
    C. Create a bucket policy on the S3 bucket.
    D. Enable default encryption on the S3 bucket.
    E. Create a lifecycle policy for the objects in the S3 bucket.
45. A company has a data ingestion workflow that consists of the following:
    • An Amazon Simple Notication Service (Amazon SNS) topic for notications about new data deliveries
    • An AWS Lambda function to process the data and record metadata
    The company observes that the ingestion workow fails occasionally because of network connectivity issues. When such a failure occurs, the Lambda function does not ingest the corresponding data unless the company manually reruns the job.
    Which combination of actions should a solutions architect take to ensure that the Lambda function ingests all data in the future? (Choose two.)

A. Deploy the Lambda function in multiple Availability Zones.
B. Create an Amazon Simple Queue Service (Amazon SQS) queue, and subscribe it to the SNS topic. C. Increase the CPU and memory that are allocated to the Lambda function.
D. Increase provisioned throughput for the Lambda function.
E. Modify the Lambda function to read from an Amazon Simple Queue Service (Amazon SQS) queue.

46. A company has an application that provides marketing services to stores. The services are based on previous purchases by store customers. The stores upload transaction data to the company through SFTP, and the data is processed and analyzed to generate new marketing offers. Some of the les can exceed 200 GB in size.
Recently, the company discovered that some of the stores have uploaded les that contain personally identiable information (PII) that should not have been included. The company wants administrators to be alerted if PII is shared again. The company also wants to automate remediation.
What should a solutions architect do to meet these requirements with the LEAST development effort?
A. Use an Amazon S3 bucket as a secure transfer point. Use Amazon Inspector to scan the objects in the bucket. If objects contain PII, trigger an S3 Lifecycle policy to remove the objects that contain PII.
B. Use an Amazon S3 bucket as a secure transfer point. Use Amazon Macie to scan the objects in the bucket. If objects contain PII, use Amazon Simple Notication Service (Amazon SNS) to trigger a notication to the administrators to remove the objects that contain PII.
C. Implement custom scanning algorithms in an AWS Lambda function. Trigger the function when objects are loaded into the bucket. If objects contain PII, use Amazon Simple Notication Service (Amazon SNS) to trigger a notication to the administrators to remove the objects that contain PII.
D. Implement custom scanning algorithms in an AWS Lambda function. Trigger the function when objects are loaded into the bucket. If objects contain PII, use Amazon Simple Email Service (Amazon SES) to trigger a notication to the administrators and trigger an S3 Lifecycle policy to remove the meats that contain PII.
47. A company needs guaranteed Amazon EC2 capacity in three specic Availability Zones in a specic AWS Region for an upcoming event that will last 1 week.
    What should the company do to guarantee the EC2 capacity?
    A. Purchase Reserved Instances that specify the Region needed.
    B. Create an On-Demand Capacity Reservation that species the Region needed.
    C. Purchase Reserved Instances that specify the Region and three Availability Zones needed.
    D. Create an On-Demand Capacity Reservation that species the Region and three Availability Zones needed.
48. A company's website uses an Amazon EC2 instance store for its catalog of items. The company wants to make sure that the catalog is highly available and that the catalog is stored in a durable location.
    What should a solutions architect do to meet these requirements?
    A. Move the catalog to Amazon ElastiCache for Redis.
    B. Deploy a larger EC2 instance with a larger instance store.
    C. Move the catalog from the instance store to Amazon S3 Glacier Deep Archive.
    D. Move the catalog to an Amazon Elastic File System (Amazon EFS) le system.
49. A company stores call transcript les on a monthly basis. Users access the les randomly within 1 year of the call, but users access the les infrequently after 1 year. The company wants to optimize its solution by giving users the ability to query and retrieve les that are less than 1- year-old as quickly as possible. A delay in retrieving older les is acceptable.
    Which solution will meet these requirements MOST cost-effectively?
    A. Store individual les with tags in Amazon S3 Glacier Instant Retrieval. Query the tags to retrieve the les from S3 Glacier Instant Retrieval.
    B. Store individual les in Amazon S3 Intelligent-Tiering. Use S3 Lifecycle policies to move the les to S3 Glacier Flexible Retrieval after 1 year. Query and retrieve the les that are in Amazon S3 by using Amazon Athena. Query and retrieve the les that are in S3 Glacier by using S3 Glacier Select.
    C. Store individual les with tags in Amazon S3 Standard storage. Store search metadata for each archive in Amazon S3 Standard storage. Use S3 Lifecycle policies to move the les to S3 Glacier Instant Retrieval after 1 year. Query and retrieve the les by searching for metadata from Amazon S3.
    D. Store individual les in Amazon S3 Standard storage. Use S3 Lifecycle policies to move the les to S3 Glacier Deep Archive after 1 year. Store search metadata in Amazon RDS. Query the les from Amazon RDS. Retrieve the les from S3 Glacier Deep Archive.
50. A company has a production workload that runs on 1,000 Amazon EC2 Linux instances. The workload is powered by third-party software. The company needs to patch the third-party software on all EC2 instances as quickly as possible to remediate a critical security vulnerability. What should a solutions architect do to meet these requirements?
    A. Create an AWS Lambda function to apply the patch to all EC2 instances.
    B. Congure AWS Systems Manager Patch Manager to apply the patch to all EC2 instances.
    C. Schedule an AWS Systems Manager maintenance window to apply the patch to all EC2 instances.
    D. Use AWS Systems Manager Run Command to run a custom command that applies the patch to all EC2 instances.
51. A company is developing an application that provides order shipping statistics for retrieval by a REST API. The company wants to extract the shipping statistics, organize the data into an easy-to-read HTML format, and send the report to several email addresses at the same time every morning.
    Which combination of steps should a solutions architect take to meet these requirements? (Choose two.)
    A. Congure the application to send the data to Amazon Kinesis Data Firehose.
    B. Use Amazon Simple Email Service (Amazon SES) to format the data and to send the report by email.
    C. Create an Amazon EventBridge (Amazon CloudWatch Events) scheduled event that invokes an AWS Glue job to query the application's API for the data.
    D. Create an Amazon EventBridge (Amazon CloudWatch Events) scheduled event that invokes an AWS Lambda function to query the application's API for the data.
    E. Store the application data in Amazon S3. Create an Amazon Simple Notication Service (Amazon SNS) topic as an S3 event destination to send the report by email.
52. A company wants to migrate its on-premises application to AWS. The application produces output les that vary in size from tens of gigabytes to hundreds of terabytes. The application data must be stored in a standard le system structure. The company wants a solution that scales automatically. is highly available, and requires minimum operational overhead.
    Which solution will meet these requirements?
    A. Migrate the application to run as containers on Amazon Elastic Container Service (Amazon ECS). Use Amazon S3 for storage.
    B. Migrate the application to run as containers on Amazon Elastic Kubernetes Service (Amazon EKS). Use Amazon Elastic Block Store (Amazon EBS) for storage.
    C. Migrate the application to Amazon EC2 instances in a Multi-AZ Auto Scaling group. Use Amazon Elastic File System (Amazon EFS) for storage.
    D. Migrate the application to Amazon EC2 instances in a Multi-AZ Auto Scaling group. Use Amazon Elastic Block Store (Amazon EBS) for storage.
53. A company needs to store its accounting records in Amazon S3. The records must be immediately accessible for 1 year and then must be archived for an additional 9 years. No one at the company, including administrative users and root users, can be able to delete the records during the entire 10-year period. The records must be stored with maximum resiliency.
    Which solution will meet these requirements?
    A. Store the records in S3 Glacier for the entire 10-year period. Use an access control policy to deny deletion of the records for a period of 10 years.
    B. Store the records by using S3 Intelligent-Tiering. Use an IAM policy to deny deletion of the records. After 10 years, change the IAM policy to allow deletion.
    C. Use an S3 Lifecycle policy to transition the records from S3 Standard to S3 Glacier Deep Archive after 1 year. Use S3 Object Lock in compliance mode for a period of 10 years.
    D. Use an S3 Lifecycle policy to transition the records from S3 Standard to S3 One Zone-Infrequent Access (S3 One Zone-IA) after 1 year. Use S3 Object Lock in governance mode for a period of 10 years.
54. A company runs multiple Windows workloads on AWS. The company's employees use Windows le shares that are hosted on two Amazon EC2 instances. The le shares synchronize data between themselves and maintain duplicate copies. The company wants a highly available and durable storage solution that preserves how users currently access the les.
    What should a solutions architect do to meet these requirements?

A. Migrate all the data to Amazon S3. Set up IAM authentication for users to access les.
B. Set up an Amazon S3 File Gateway. Mount the S3 File Gateway on the existing EC2 instances.
C. Extend the le share environment to Amazon FSx for Windows File Server with a Multi-AZ conguration. Migrate all the data to FSx for Windows File Server.
D. Extend the le share environment to Amazon Elastic File System (Amazon EFS) with a Multi-AZ conguration. Migrate all the data to Amazon EFS.

55. A solutions architect is developing a VPC architecture that includes multiple subnets. The architecture will host applications that use Amazon EC2 instances and Amazon RDS DB instances. The architecture consists of six subnets in two Availability Zones. Each Availability Zone includes a public subnet, a private subnet, and a dedicated subnet for databases. Only EC2 instances that run in the private subnets can have access to the RDS databases.
    Which solution will meet these requirements?
    A. Create a new route table that excludes the route to the public subnets' CIDR blocks. Associate the route table with the database subnets.
    B. Create a security group that denies inbound trac from the security group that is assigned to instances in the public subnets. Attach the security group to the DB instances.
    C. Create a security group that allows inbound trac from the security group that is assigned to instances in the private subnets. Attach the security group to the DB instances.
    D. Create a new peering connection between the public subnets and the private subnets. Create a different peering connection between the private subnets and the database subnets.
56. A company has registered its domain name with Amazon Route 53. The company uses Amazon API Gateway in the ca-central-1 Region as a public interface for its backend microservice APIs. Third-party services consume the APIs securely. The company wants to design its API Gateway URL with the company's domain name and corresponding certicate so that the third-party services can use HTTPS.
    Which solution will meet these requirements?
    A. Create stage variables in API Gateway with Name="Endpoint-URL" and Value="Company Domain Name" to overwrite the default URL. Import the public certicate associated with the company's domain name into AWS Certicate Manager (ACM).
    B. Create Route 53 DNS records with the company's domain name. Point the alias record to the Regional API Gateway stage endpoint. Import the public certicate associated with the company's domain name into AWS Certicate Manager (ACM) in the us-east-1 Region.
    C. Create a Regional API Gateway endpoint. Associate the API Gateway endpoint with the company's domain name. Import the public certicate associated with the company's domain name into AWS Certicate Manager (ACM) in the same Region. Attach the certicate to the API Gateway endpoint. Congure Route 53 to route trac to the API Gateway endpoint.
    D. Create a Regional API Gateway endpoint. Associate the API Gateway endpoint with the company's domain name. Import the public certicate associated with the company's domain name into AWS Certicate Manager (ACM) in the us-east-1 Region. Attach the certicate to the API Gateway APIs. Create Route 53 DNS records with the company's domain name. Point an A record to the company's domain name.
57. A company is running a popular social media website. The website gives users the ability to upload images to share with other users. The company wants to make sure that the images do not contain inappropriate content. The company needs a solution that minimizes development effort.
    What should a solutions architect do to meet these requirements?
    A. Use Amazon Comprehend to detect inappropriate content. Use human review for low-condence predictions.
    B. Use Amazon Rekognition to detect inappropriate content. Use human review for low-condence predictions.
    C. Use Amazon SageMaker to detect inappropriate content. Use ground truth to label low-condence predictions.
    D. Use AWS Fargate to deploy a custom machine learning model to detect inappropriate content. Use ground truth to label low-condence predictions.
58. A company wants to run its critical applications in containers to meet requirements for scalability and availability. The company prefers to focus on maintenance of the critical applications. The company does not want to be responsible for provisioning and managing the underlying infrastructure that runs the containerized workload.
    What should a solutions architect do to meet these requirements?
    A. Use Amazon EC2 instances, and install Docker on the instances.
    B. Use Amazon Elastic Container Service (Amazon ECS) on Amazon EC2 worker nodes.
    C. Use Amazon Elastic Container Service (Amazon ECS) on AWS Fargate.
    D. Use Amazon EC2 instances from an Amazon Elastic Container Service (Amazon ECS)-optimized Amazon Machine Image (AMI).
59. A company hosts more than 300 global websites and applications. The company requires a platform to analyze more than 30 TB of clickstream data each day.
    What should a solutions architect do to transmit and process the clickstream data?
    A. Design an AWS Data Pipeline to archive the data to an Amazon S3 bucket and run an Amazon EMR cluster with the data to generate analytics.
    B. Create an Auto Scaling group of Amazon EC2 instances to process the data and send it to an Amazon S3 data lake for Amazon Redshift to use for analysis.
    C. Cache the data to Amazon CloudFront. Store the data in an Amazon S3 bucket. When an object is added to the S3 bucket. run an AWS Lambda function to process the data for analysis.
    D. Collect the data from Amazon Kinesis Data Streams. Use Amazon Kinesis Data Firehose to transmit the data to an Amazon S3 data lake. Load the data in Amazon Redshift for analysis.
60. A company has a website hosted on AWS. The website is behind an Application Load Balancer (ALB) that is congured to handle HTTP and HTTPS separately. The company wants to forward all requests to the website so that the requests will use HTTPS.
    What should a solutions architect do to meet this requirement?
    A. Update the ALB's network ACL to accept only HTTPS trac.
    B. Create a rule that replaces the HTTP in the URL with HTTPS.
    C. Create a listener rule on the ALB to redirect HTTP trac to HTTPS.
    D. Replace the ALB with a Network Load Balancer congured to use Server Name Indication (SNI).
61. A company is developing a two-tier web application on AWS. The company's developers have deployed the application on an Amazon EC2 instance that connects directly to a backend Amazon RDS database. The company must not hardcode database credentials in the application. The company must also implement a solution to automatically rotate the database credentials on a regular basis.
    Which solution will meet these requirements with the LEAST operational overhead?
    A. Store the database credentials in the instance metadata. Use Amazon EventBridge (Amazon CloudWatch Events) rules to run a scheduled AWS Lambda function that updates the RDS credentials and instance metadata at the same time.
    B. Store the database credentials in a conguration le in an encrypted Amazon S3 bucket. Use Amazon EventBridge (Amazon CloudWatch Events) rules to run a scheduled AWS Lambda function that updates the RDS credentials and the credentials in the conguration le at the same time. Use S3 Versioning to ensure the ability to fall back to previous values.
    C. Store the database credentials as a secret in AWS Secrets Manager. Turn on automatic rotation for the secret. Attach the required permission to the EC2 role to grant access to the secret.
    D. Store the database credentials as encrypted parameters in AWS Systems Manager Parameter Store. Turn on automatic rotation for the encrypted parameters. Attach the required permission to the EC2 role to grant access to the encrypted parameters.
62. A company is deploying a new public web application to AWS. The application will run behind an Application Load Balancer (ALB). The application needs to be encrypted at the edge with an SSL/TLS certicate that is issued by an external certicate authority (CA). The certicate must be rotated each year before the certicate expires.
    What should a solutions architect do to meet these requirements?  
A. Use AWS Certicate Manager (ACM) to issue an SSL/TLS certicate. Apply the certicate to the ALB. Use the managed renewal feature to automatically rotate the certicate.
B. Use AWS Certicate Manager (ACM) to issue an SSL/TLS certicate. Import the key material from the certicate. Apply the certicate to the ALUse the managed renewal feature to automatically rotate the certicate.
C. Use AWS Certicate Manager (ACM) Private Certicate Authority to issue an SSL/TLS certicate from the root CA. Apply the certicate to the ALB. Use the managed renewal feature to automatically rotate the certicate.
D. Use AWS Certicate Manager (ACM) to import an SSL/TLS certicate. Apply the certicate to the ALB. Use Amazon EventBridge (Amazon CloudWatch Events) to send a notication when the certicate is nearing expiration. Rotate the certicate manually.
63. A company runs its infrastructure on AWS and has a registered base of 700,000 users for its document management application. The company intends to create a product that converts large .pdf les to .jpg image les. The .pdf les average 5 MB in size. The company needs to store the original les and the converted les. A solutions architect must design a scalable solution to accommodate demand that will grow rapidly over time.
    Which solution meets these requirements MOST cost-effectively?
    A. Save the .pdf les to Amazon S3. Congure an S3 PUT event to invoke an AWS Lambda function to convert the les to .jpg format and store them back in Amazon S3.
    B. Save the .pdf les to Amazon DynamoDUse the DynamoDB Streams feature to invoke an AWS Lambda function to convert the les to .jpg format and store them back in DynamoDB.
    C. Upload the .pdf les to an AWS Elastic Beanstalk application that includes Amazon EC2 instances, Amazon Elastic Block Store (Amazon EBS) storage, and an Auto Scaling group. Use a program in the EC2 instances to convert the les to .jpg format. Save the .pdf les and the .jpg les in the EBS store.
    D. Upload the .pdf les to an AWS Elastic Beanstalk application that includes Amazon EC2 instances, Amazon Elastic File System (Amazon EFS) storage, and an Auto Scaling group. Use a program in the EC2 instances to convert the le to .jpg format. Save the .pdf les and the .jpg les in the EBS store.
64. A company has more than 5 TB of le data on Windows le servers that run on premises. Users and applications interact with the data each day.
    The company is moving its Windows workloads to AWS. As the company continues this process, the company requires access to AWS and on- premises le storage with minimum latency. The company needs a solution that minimizes operational overhead and requires no signicant changes to the existing le access patterns. The company uses an AWS Site-to-Site VPN connection for connectivity to AWS.
    What should a solutions architect do to meet these requirements?
    A. Deploy and congure Amazon FSx for Windows File Server on AWS. Move the on-premises le data to FSx for Windows File Server. Recongure the workloads to use FSx for Windows File Server on AWS.
    B. Deploy and congure an Amazon S3 File Gateway on premises. Move the on-premises le data to the S3 File Gateway. Recongure the on-premises workloads and the cloud workloads to use the S3 File Gateway.
    C. Deploy and congure an Amazon S3 File Gateway on premises. Move the on-premises le data to Amazon S3. Recongure the workloads to use either Amazon S3 directly or the S3 File Gateway. depending on each workload's location.
    D. Deploy and congure Amazon FSx for Windows File Server on AWS. Deploy and congure an Amazon FSx File Gateway on premises. Move the on-premises le data to the FSx File Gateway. Congure the cloud workloads to use FSx for Windows File Server on AWS. Congure the on-premises workloads to use the FSx File Gateway.
65. A hospital recently deployed a RESTful API with Amazon API Gateway and AWS Lambda. The hospital uses API Gateway and Lambda to upload reports that are in PDF format and JPEG format. The hospital needs to modify the Lambda code to identify protected health information (PHI) in the reports.
    Which solution will meet these requirements with the LEAST operational overhead?
    A. Use existing Python libraries to extract the text from the reports and to identify the PHI from the extracted text.
    B. Use Amazon Textract to extract the text from the reports. Use Amazon SageMaker to identify the PHI from the extracted text.
    C. Use Amazon Textract to extract the text from the reports. Use Amazon Comprehend Medical to identify the PHI from the extracted text.
    D. Use Amazon Rekognition to extract the text from the reports. Use Amazon Comprehend Medical to identify the PHI from the extracted text.
66. A company has an application that generates a large number of les, each approximately 5 MB in size. The les are stored in Amazon S3. Company policy requires the les to be stored for 4 years before they can be deleted. Immediate accessibility is always required as the les contain critical business data that is not easy to reproduce. The les are frequently accessed in the rst 30 days of the object creation but are rarely accessed after the rst 30 days.
    Which storage solution is MOST cost-effective?
    A. Create an S3 bucket lifecycle policy to move les from S3 Standard to S3 Glacier 30 days from object creation. Delete the les 4 years after object creation.
    B. Create an S3 bucket lifecycle policy to move les from S3 Standard to S3 One Zone-Infrequent Access (S3 One Zone-IA) 30 days from object creation. Delete the les 4 years after object creation.
    C. Create an S3 bucket lifecycle policy to move les from S3 Standard to S3 Standard-Infrequent Access (S3 Standard-IA) 30 days from object creation. Delete the les 4 years after object creation.
    D. Create an S3 bucket lifecycle policy to move les from S3 Standard to S3 Standard-Infrequent Access (S3 Standard-IA) 30 days from object creation. Move the les to S3 Glacier 4 years after object creation.
67. A company hosts an application on multiple Amazon EC2 instances. The application processes messages from an Amazon SQS queue, writes to an Amazon RDS table, and deletes the message from the queue. Occasional duplicate records are found in the RDS table. The SQS queue does not contain any duplicate messages.
    What should a solutions architect do to ensure messages are being processed once only?
    A. Use the CreateQueue API call to create a new queue.
    B. Use the AddPermission API call to add appropriate permissions.
    C. Use the ReceiveMessage API call to set an appropriate wait time.
    D. Use the ChangeMessageVisibility API call to increase the visibility timeout.
68. A solutions architect is designing a new hybrid architecture to extend a company's on-premises infrastructure to AWS. The company requires a highly available connection with consistent low latency to an AWS Region. The company needs to minimize costs and is willing to accept slower trac if the primary connection fails.
    What should the solutions architect do to meet these requirements?
    A. Provision an AWS Direct Connect connection to a Region. Provision a VPN connection as a backup if the primary Direct Connect connection fails.
    B. Provision a VPN tunnel connection to a Region for private connectivity. Provision a second VPN tunnel for private connectivity and as a backup if the primary VPN connection fails.
    C. Provision an AWS Direct Connect connection to a Region. Provision a second Direct Connect connection to the same Region as a backup if the primary Direct Connect connection fails.
    D. Provision an AWS Direct Connect connection to a Region. Use the Direct Connect failover attribute from the AWS CLI to automatically create a backup connection if the primary Direct Connect connection fails.
69. A company is running a business-critical web application on Amazon EC2 instances behind an Application Load Balancer. The EC2 instances are in an Auto Scaling group. The application uses an Amazon Aurora PostgreSQL database that is deployed in a single Availability Zone. The company wants the application to be highly available with minimum downtime and minimum loss of data.
    Which solution will meet these requirements with the LEAST operational effort?
    A. Place the EC2 instances in different AWS Regions. Use Amazon Route 53 health checks to redirect trac. Use Aurora PostgreSQL Cross- Region Replication.
    B. Congure the Auto Scaling group to use multiple Availability Zones. Congure the database as Multi-AZ. Congure an Amazon RDS Proxy instance for the database.
    C. Congure the Auto Scaling group to use one Availability Zone. Generate hourly snapshots of the database. Recover the database from the snapshots in the event of a failure.
    D. Congure the Auto Scaling group to use multiple AWS Regions. Write the data from the application to Amazon S3. Use S3 Event Notications to launch an AWS Lambda function to write the data to the database.
70. A company's HTTP application is behind a Network Load Balancer (NLB). The NLB's target group is congured to use an Amazon EC2 Auto Scaling group with multiple EC2 instances that run the web service.
    The company notices that the NLB is not detecting HTTP errors for the application. These errors require a manual restart of the EC2 instances that run the web service. The company needs to improve the application's availability without writing custom scripts or code.
    What should a solutions architect do to meet these requirements?
    A. Enable HTTP health checks on the NLB, supplying the URL of the company's application.
    B. Add a cron job to the EC2 instances to check the local application's logs once each minute. If HTTP errors are detected. the application will restart.
    C. Replace the NLB with an Application Load Balancer. Enable HTTP health checks by supplying the URL of the company's application. Congure an Auto Scaling action to replace unhealthy instances.
    D. Create an Amazon Cloud Watch alarm that monitors the UnhealthyHostCount metric for the NLB. Congure an Auto Scaling action to replace unhealthy instances when the alarm is in the ALARM state.
71. A company runs a shopping application that uses Amazon DynamoDB to store customer information. In case of data corruption, a solutions architect needs to design a solution that meets a recovery point objective (RPO) of 15 minutes and a recovery time objective (RTO) of 1 hour. What should the solutions architect recommend to meet these requirements?
    A. Congure DynamoDB global tables. For RPO recovery, point the application to a different AWS Region.
    B. Congure DynamoDB point-in-time recovery. For RPO recovery, restore to the desired point in time.
    C. Export the DynamoDB data to Amazon S3 Glacier on a daily basis. For RPO recovery, import the data from S3 Glacier to DynamoDB.
    D. Schedule Amazon Elastic Block Store (Amazon EBS) snapshots for the DynamoDB table every 15 minutes. For RPO recovery, restore the DynamoDB table by using the EBS snapshot.
72. A company runs a photo processing application that needs to frequently upload and download pictures from Amazon S3 buckets that are located in the same AWS Region. A solutions architect has noticed an increased cost in data transfer fees and needs to implement a solution to reduce these costs.
    How can the solutions architect meet this requirement?
    A. Deploy Amazon API Gateway into a public subnet and adjust the route table to route S3 calls through it.
    B. Deploy a NAT gateway into a public subnet and attach an endpoint policy that allows access to the S3 buckets.
    C. Deploy the application into a public subnet and allow it to route through an internet gateway to access the S3 buckets.
    D. Deploy an S3 VPC gateway endpoint into the VPC and attach an endpoint policy that allows access to the S3 buckets.
73. A company recently launched Linux-based application instances on Amazon EC2 in a private subnet and launched a Linux-based bastion host on an Amazon EC2 instance in a public subnet of a VPC. A solutions architect needs to connect from the on-premises network, through the company's internet connection, to the bastion host, and to the application servers. The solutions architect must make sure that the security groups of all the EC2 instances will allow that access.
    Which combination of steps should the solutions architect take to meet these requirements? (Choose two.)
    A. Replace the current security group of the bastion host with one that only allows inbound access from the application instances.
    B. Replace the current security group of the bastion host with one that only allows inbound access from the internal IP range for the company.
    C. Replace the current security group of the bastion host with one that only allows inbound access from the external IP range for the company.
    D. Replace the current security group of the application instances with one that allows inbound SSH access from only the private IP address of the bastion host.
    E. Replace the current security group of the application instances with one that allows inbound SSH access from only the public IP address of the bastion host.
74. A solutions architect is designing a two-tier web application. The application consists of a public-facing web tier hosted on Amazon EC2 in public subnets. The database tier consists of Microsoft SQL Server running on Amazon EC2 in a private subnet. Security is a high priority for the company.
    How should security groups be congured in this situation? (Choose two.)
    A. Congure the security group for the web tier to allow inbound trac on port 443 from 0.0.0.0/0.
    B. Congure the security group for the web tier to allow outbound trac on port 443 from 0.0.0.0/0.
    C. Congure the security group for the database tier to allow inbound trac on port 1433 from the security group for the web tier.
    D. Congure the security group for the database tier to allow outbound trac on ports 443 and 1433 to the security group for the web tier.
    E. Congure the security group for the database tier to allow inbound trac on ports 443 and 1433 from the security group for the web tier.
75. A company wants to move a multi-tiered application from on premises to the AWS Cloud to improve the application's performance. The application consists of application tiers that communicate with each other by way of RESTful services. Transactions are dropped when one tier becomes overloaded. A solutions architect must design a solution that resolves these issues and modernizes the application.
    Which solution meets these requirements and is the MOST operationally ecient?
    A. Use Amazon API Gateway and direct transactions to the AWS Lambda functions as the application layer. Use Amazon Simple Queue Service (Amazon SQS) as the communication layer between application services.
    B. Use Amazon CloudWatch metrics to analyze the application performance history to determine the servers' peak utilization during the performance failures. Increase the size of the application server's Amazon EC2 instances to meet the peak requirements.
    C. Use Amazon Simple Notication Service (Amazon SNS) to handle the messaging between application servers running on Amazon EC2 in an Auto Scaling group. Use Amazon CloudWatch to monitor the SNS queue length and scale up and down as required.
    D. Use Amazon Simple Queue Service (Amazon SQS) to handle the messaging between application servers running on Amazon EC2 in an Auto Scaling group. Use Amazon CloudWatch to monitor the SQS queue length and scale up when communication failures are detected.
76. A company receives 10 TB of instrumentation data each day from several machines located at a single factory. The data consists of JSON les stored on a storage area network (SAN) in an on-premises data center located within the factory. The company wants to send this data to Amazon S3 where it can be accessed by several additional systems that provide critical near-real-time analytics. A secure transfer is important because the data is considered sensitive.
    Which solution offers the MOST reliable data transfer?
    A. AWS DataSync over public internet
    B. AWS DataSync over AWS Direct Connect
    C. AWS Database Migration Service (AWS DMS) over public internet
    D. AWS Database Migration Service (AWS DMS) over AWS Direct Connect
77. A company needs to congure a real-time data ingestion architecture for its application. The company needs an API, a process that transforms data as the data is streamed, and a storage solution for the data.
    Which solution will meet these requirements with the LEAST operational overhead?
    A. Deploy an Amazon EC2 instance to host an API that sends data to an Amazon Kinesis data stream. Create an Amazon Kinesis Data Firehose delivery stream that uses the Kinesis data stream as a data source. Use AWS Lambda functions to transform the data. Use the Kinesis Data Firehose delivery stream to send the data to Amazon S3.
    B. Deploy an Amazon EC2 instance to host an API that sends data to AWS Glue. Stop source/destination checking on the EC2 instance. Use AWS Glue to transform the data and to send the data to Amazon S3.
    C. Congure an Amazon API Gateway API to send data to an Amazon Kinesis data stream. Create an Amazon Kinesis Data Firehose delivery stream that uses the Kinesis data stream as a data source. Use AWS Lambda functions to transform the data. Use the Kinesis Data Firehose delivery stream to send the data to Amazon S3.
    D. Congure an Amazon API Gateway API to send data to AWS Glue. Use AWS Lambda functions to transform the data. Use AWS Glue to send the data to Amazon S3.
78. A company needs to keep user transaction data in an Amazon DynamoDB table. The company must retain the data for 7 years. What is the MOST operationally ecient solution that meets these requirements?
    A. Use DynamoDB point-in-time recovery to back up the table continuously.
    B. Use AWS Backup to create backup schedules and retention policies for the table.
    C. Create an on-demand backup of the table by using the DynamoDB console. Store the backup in an Amazon S3 bucket. Set an S3 Lifecycle conguration for the S3 bucket.
    D. Create an Amazon EventBridge (Amazon CloudWatch Events) rule to invoke an AWS Lambda function. Congure the Lambda function to back up the table and to store the backup in an Amazon S3 bucket. Set an S3 Lifecycle conguration for the S3 bucket
79. A company is planning to use an Amazon DynamoDB table for data storage. The company is concerned about cost optimization. The table will not be used on most mornings. In the evenings, the read and write trac will often be unpredictable. When trac spikes occur, they will happen very quickly.
    What should a solutions architect recommend?
    A. Create a DynamoDB table in on-demand capacity mode.
    B. Create a DynamoDB table with a global secondary index.
    C. Create a DynamoDB table with provisioned capacity and auto scaling.
    D. Create a DynamoDB table in provisioned capacity mode, and congure it as a global table.
80. A company recently signed a contract with an AWS Managed Service Provider (MSP) Partner for help with an application migration initiative. A solutions architect needs ta share an Amazon Machine Image (AMI) from an existing AWS account with the MSP Partner's AWS account. The AMI is backed by Amazon Elastic Block Store (Amazon EBS) and uses an AWS Key Management Service (AWS KMS) customer managed key to encrypt EBS volume snapshots.
    What is the MOST secure way for the solutions architect to share the AMI with the MSP Partner's AWS account?
    A. Make the encrypted AMI and snapshots publicly available. Modify the key policy to allow the MSP Partner's AWS account to use the key.
    B. Modify the launchPermission property of the AMI. Share the AMI with the MSP Partner's AWS account only. Modify the key policy to allow the MSP Partner's AWS account to use the key.
    C. Modify the launchPermission property of the AMI. Share the AMI with the MSP Partner's AWS account only. Modify the key policy to trust a new KMS key that is owned by the MSP Partner for encryption.
    D. Export the AMI from the source account to an Amazon S3 bucket in the MSP Partner's AWS account, Encrypt the S3 bucket with a new KMS key that is owned by the MSP Partner. Copy and launch the AMI in the MSP Partner's AWS account.
81. A solutions architect is designing the cloud architecture for a new application being deployed on AWS. The process should run in parallel while adding and removing application nodes as needed based on the number of jobs to be processed. The processor application is stateless. The solutions architect must ensure that the application is loosely coupled and the job items are durably stored.
    Which design should the solutions architect use?
    A. Create an Amazon SNS topic to send the jobs that need to be processed. Create an Amazon Machine Image (AMI) that consists of the processor application. Create a launch conguration that uses the AMI. Create an Auto Scaling group using the launch conguration. Set the scaling policy for the Auto Scaling group to add and remove nodes based on CPU usage.
    B. Create an Amazon SQS queue to hold the jobs that need to be processed. Create an Amazon Machine Image (AMI) that consists of the processor application. Create a launch conguration that uses the AMI. Create an Auto Scaling group using the launch conguration. Set the scaling policy for the Auto Scaling group to add and remove nodes based on network usage.
    C. Create an Amazon SQS queue to hold the jobs that need to be processed. Create an Amazon Machine Image (AMI) that consists of the processor application. Create a launch template that uses the AMI. Create an Auto Scaling group using the launch template. Set the scaling policy for the Auto Scaling group to add and remove nodes based on the number of items in the SQS queue.
    D. Create an Amazon SNS topic to send the jobs that need to be processed. Create an Amazon Machine Image (AMI) that consists of the processor application. Create a launch template that uses the AMI. Create an Auto Scaling group using the launch template. Set the scaling policy for the Auto Scaling group to add and remove nodes based on the number of messages published to the SNS topic.
82. A company hosts its web applications in the AWS Cloud. The company congures Elastic Load Balancers to use certicates that are imported into AWS Certicate Manager (ACM). The company's security team must be notied 30 days before the expiration of each certicate.
    What should a solutions architect recommend to meet this requirement?
    A. Add a rule in ACM to publish a custom message to an Amazon Simple Notication Service (Amazon SNS) topic every day, beginning 30 days before any certicate will expire.
    B. Create an AWS Cong rule that checks for certicates that will expire within 30 days. Congure Amazon EventBridge (Amazon CloudWatch Events) to invoke a custom alert by way of Amazon Simple Notication Service (Amazon SNS) when AWS Cong reports a noncompliant resource.
    C. Use AWS Trusted Advisor to check for certicates that will expire within 30 days. Create an Amazon CloudWatch alarm that is based on Trusted Advisor metrics for check status changes. Congure the alarm to send a custom alert by way of Amazon Simple Notication Service (Amazon SNS).
    D. Create an Amazon EventBridge (Amazon CloudWatch Events) rule to detect any certicates that will expire within 30 days. Congure the rule to invoke an AWS Lambda function. Congure the Lambda function to send a custom alert by way of Amazon Simple Notication Service (Amazon SNS).
83. A company's dynamic website is hosted using on-premises servers in the United States. The company is launching its product in Europe, and it wants to optimize site loading times for new European users. The site's backend must remain in the United States. The product is being launched in a few days, and an immediate solution is needed.
    What should the solutions architect recommend?
    A. Launch an Amazon EC2 instance in us-east-1 and migrate the site to it.
    B. Move the website to Amazon S3. Use Cross-Region Replication between Regions.
    C. Use Amazon CloudFront with a custom origin pointing to the on-premises servers.
    D. Use an Amazon Route 53 geoproximity routing policy pointing to on-premises servers.
84. A company wants to reduce the cost of its existing three-tier web architecture. The web, application, and database servers are running on Amazon EC2 instances for the development, test, and production environments. The EC2 instances average 30% CPU utilization during peak hours and 10% CPU utilization during non-peak hours.
    The production EC2 instances run 24 hours a day. The development and test EC2 instances run for at least 8 hours each day. The company plans to implement automation to stop the development and test EC2 instances when they are not in use.
    Which EC2 instance purchasing solution will meet the company's requirements MOST cost-effectively?
    A. Use Spot Instances for the production EC2 instances. Use Reserved Instances for the development and test EC2 instances.
    B. Use Reserved Instances for the production EC2 instances. Use On-Demand Instances for the development and test EC2 instances.
    C. Use Spot blocks for the production EC2 instances. Use Reserved Instances for the development and test EC2 instances.
    D. Use On-Demand Instances for the production EC2 instances. Use Spot blocks for the development and test EC2 instances.
85. A company has a production web application in which users upload documents through a web interface or a mobile app. According to a new regulatory requirement. new documents cannot be modied or deleted after they are stored.
    What should a solutions architect do to meet this requirement?
    A. Store the uploaded documents in an Amazon S3 bucket with S3 Versioning and S3 Object Lock enabled.
    B. Store the uploaded documents in an Amazon S3 bucket. Congure an S3 Lifecycle policy to archive the documents periodically.
    C. Store the uploaded documents in an Amazon S3 bucket with S3 Versioning enabled. Congure an ACL to restrict all access to read-only.
    D. Store the uploaded documents on an Amazon Elastic File System (Amazon EFS) volume. Access the data by mounting the volume in read-only mode.
86. A company has several web servers that need to frequently access a common Amazon RDS MySQL Multi-AZ DB instance. The company wants a secure method for the web servers to connect to the database while meeting a security requirement to rotate user credentials frequently. Which solution meets these requirements?
    A. Store the database user credentials in AWS Secrets Manager. Grant the necessary IAM permissions to allow the web servers to access AWS Secrets Manager.
    B. Store the database user credentials in AWS Systems Manager OpsCenter. Grant the necessary IAM permissions to allow the web servers to access OpsCenter.
    C. Store the database user credentials in a secure Amazon S3 bucket. Grant the necessary IAM permissions to allow the web servers to retrieve credentials and access the database.
    D. Store the database user credentials in les encrypted with AWS Key Management Service (AWS KMS) on the web server le system. The web server should be able to decrypt the les and access the database.
87. A company hosts an application on AWS Lambda functions that are invoked by an Amazon API Gateway API. The Lambda functions save customer data to an Amazon Aurora MySQL database. Whenever the company upgrades the database, the Lambda functions fail to establish database connections until the upgrade is complete. The result is that customer data is not recorded for some of the event.
    A solutions architect needs to design a solution that stores customer data that is created during database upgrades.
    Which solution will meet these requirements?
    A. Provision an Amazon RDS proxy to sit between the Lambda functions and the database. Congure the Lambda functions to connect to the RDS proxy.
    B. Increase the run time of the Lambda functions to the maximum. Create a retry mechanism in the code that stores the customer data in the database.
    C. Persist the customer data to Lambda local storage. Congure new Lambda functions to scan the local storage to save the customer data to the database.
    D. Store the customer data in an Amazon Simple Queue Service (Amazon SQS) FIFO queue. Create a new Lambda function that polls the queue and stores the customer data in the database.
88. A survey company has gathered data for several years from areas in the United States. The company hosts the data in an Amazon S3 bucket that is 3 TB in size and growing. The company has started to share the data with a European marketing rm that has S3 buckets. The company wants to ensure that its data transfer costs remain as low as possible.
    Which solution will meet these requirements?
    A. Congure the Requester Pays feature on the company's S3 bucket.
    B. Congure S3 Cross-Region Replication from the company's S3 bucket to one of the marketing rm's S3 buckets.
    C. Congure cross-account access for the marketing rm so that the marketing rm has access to the company's S3 bucket.
    D. Congure the company's S3 bucket to use S3 Intelligent-Tiering. Sync the S3 bucket to one of the marketing rm's S3 buckets.
89. A company uses Amazon S3 to store its condential audit documents. The S3 bucket uses bucket policies to restrict access to audit team IAM user credentials according to the principle of least privilege. Company managers are worried about accidental deletion of documents in the S3 bucket and want a more secure solution.
    What should a solutions architect do to secure the audit documents?
    A. Enable the versioning and MFA Delete features on the S3 bucket.
    B. Enable multi-factor authentication (MFA) on the IAM user credentials for each audit team IAM user account.
    C. Add an S3 Lifecycle policy to the audit team's IAM user accounts to deny the s3:DeleteObject action during audit dates.
    D. Use AWS Key Management Service (AWS KMS) to encrypt the S3 bucket and restrict audit team IAM user accounts from accessing the KMS key.
90. A company is using a SQL database to store movie data that is publicly accessible. The database runs on an Amazon RDS Single-AZ DB instance. A script runs queries at random intervals each day to record the number of new movies that have been added to the database. The script must report a final total during business hours.
    The company's development team notices that the database performance is inadequate for development tasks when the script is running. A solutions architect must recommend a solution to resolve this issue.
    Which solution will meet this requirement with the LEAST operational overhead?
    A. Modify the DB instance to be a Multi-AZ deployment.
    B. Create a read replica of the database. Congure the script to query only the read replica.
    C. Instruct the development team to manually export the entries in the database at the end of each day.
    D. Use Amazon ElastiCache to cache the common queries that the script runs against the database.
91. A company has applications that run on Amazon EC2 instances in a VPC. One of the applications needs to call the Amazon S3 API to store and read objects. According to the company's security regulations, no trac from the applications is allowed to travel across the internet. Which solution will meet these requirements?
    A. Congure an S3 gateway endpoint.
    B. Create an S3 bucket in a private subnet.
    C. Create an S3 bucket in the same AWS Region as the EC2 instances.   
    D. Congure a NAT gateway in the same subnet as the EC2 instances
92. A company is storing sensitive user information in an Amazon S3 bucket. The company wants to provide secure access to this bucket from the application tier running on Amazon EC2 instances inside a VPC.
    Which combination of steps should a solutions architect take to accomplish this? (Choose two.)
    A. Congure a VPC gateway endpoint for Amazon S3 within the VPC.
    B. Create a bucket policy to make the objects in the S3 bucket public.
    C. Create a bucket policy that limits access to only the application tier running in the VPC.
    D. Create an IAM user with an S3 access policy and copy the IAM credentials to the EC2 instance.
    E. Create a NAT instance and have the EC2 instances use the NAT instance to access the S3 bucket.
93. A company runs an on-premises application that is powered by a MySQL database. The company is migrating the application to AWS to increase the application's elasticity and availability.
    The current architecture shows heavy read activity on the database during times of normal operation. Every 4 hours, the company's development team pulls a full export of the production database to populate a database in the staging environment. During this period, users experience unacceptable application latency. The development team is unable to use the staging environment until the procedure completes. A solutions architect must recommend replacement architecture that alleviates the application latency issue. The replacement architecture also must give the development team the ability to continue using the staging environment without delay.
    Which solution meets these requirements?
    A. Use Amazon Aurora MySQL with Multi-AZ Aurora Replicas for production. Populate the staging database by implementing a backup and restore process that uses the mysqldump utility.
    B. Use Amazon Aurora MySQL with Multi-AZ Aurora Replicas for production. Use database cloning to create the staging database on- demand.
    C. Use Amazon RDS for MySQL with a Multi-AZ deployment and read replicas for production. Use the standby instance for the staging database.
    D. Use Amazon RDS for MySQL with a Multi-AZ deployment and read replicas for production. Populate the staging database by implementing a backup and restore process that uses the mysqldump utility.
94. A company is designing an application where users upload small les into Amazon S3. After a user uploads a le, the le requires one-time simple processing to transform the data and save the data in JSON format for later analysis.
    Each le must be processed as quickly as possible after it is uploaded. Demand will vary. On some days, users will upload a high number of les. On other days, users will upload a few les or no les.
    Which solution meets these requirements with the LEAST operational overhead?
    A. Congure Amazon EMR to read text les from Amazon S3. Run processing scripts to transform the data. Store the resulting JSON le in an Amazon Aurora DB cluster.
    B. Congure Amazon S3 to send an event notication to an Amazon Simple Queue Service (Amazon SQS) queue. Use Amazon EC2 instances to read from the queue and process the data. Store the resulting JSON le in Amazon DynamoDB.
    C. Congure Amazon S3 to send an event notication to an Amazon Simple Queue Service (Amazon SQS) queue. Use an AWS Lambda function to read from the queue and process the data. Store the resulting JSON le in Amazon DynamoDB.
    D. Congure Amazon EventBridge (Amazon CloudWatch Events) to send an event to Amazon Kinesis Data Streams when a new le is uploaded. Use an AWS Lambda function to consume the event from the stream and process the data. Store the resulting JSON le in an Amazon Aurora DB cluster.
95. An application allows users at a company's headquarters to access product data. The product data is stored in an Amazon RDS MySQL DB instance. The operations team has isolated an application performance slowdown and wants to separate read trac from write trac. A solutions architect needs to optimize the application's performance quickly.
    What should the solutions architect recommend?
    A. Change the existing database to a Multi-AZ deployment. Serve the read requests from the primary Availability Zone. 
    B. Change the existing database to a Multi-AZ deployment. Serve the read requests from the secondary Availability Zone.
    C. Create read replicas for the database. Congure the read replicas with half of the compute and storage resources as the source database.
    D. Create read replicas for the database. Congure the read replicas with the same compute and storage resources as the source database.

96. 看原文档
97. A  company has a large Microsoft SharePoint deployment running on-premises that requires Microsoft Windows shared le storage. The company wants to migrate this workload to the AWS Cloud and is considering various storage options. The storage solution must be highly available and integrated with Active Directory for access control.
    Which solution will satisfy these requirements?
    A. Congure Amazon EFS storage and set the Active Directory domain for authentication.
    B. Create an SMB le share on an AWS Storage Gateway le gateway in two Availability Zones.
    C. Create an Amazon S3 bucket and congure Microsoft Windows Server to mount it as a volume.
    D. Create an Amazon FSx for Windows File Server le system on AWS and set the Active Directory domain for authentication.
98. An image-processing company has a web application that users use to upload images. The application uploads the images into an Amazon S3 bucket. The company has set up S3 event notications to publish the object creation events to an Amazon Simple Queue Service (Amazon SQS) standard queue. The SQS queue serves as the event source for an AWS Lambda function that processes the images and sends the results to users through email.
    Users report that they are receiving multiple email messages for every uploaded image. A solutions architect determines that SQS messages are invoking the Lambda function more than once, resulting in multiple email messages.
    What should the solutions architect do to resolve this issue with the LEAST operational overhead?
    A. Set up long polling in the SQS queue by increasing the ReceiveMessage wait time to 30 seconds.
    B. Change the SQS standard queue to an SQS FIFO queue. Use the message deduplication ID to discard duplicate messages.
    C. Increase the visibility timeout in the SQS queue to a value that is greater than the total of the function timeout and the batch window timeout.
    D. Modify the Lambda function to delete each message from the SQS queue immediately after the message is read before processing.
99. A company is implementing a shared storage solution for a gaming application that is hosted in an on-premises data center. The company needs the ability to use Lustre clients to access data. The solution must be fully managed.
    Which solution meets these requirements?
    A. Create an AWS Storage Gateway le gateway. Create a le share that uses the required client protocol. Connect the application server to the le share.
    B. Create an Amazon EC2 Windows instance. Install and congure a Windows le share role on the instance. Connect the application server to the le share.
    C. Create an Amazon Elastic File System (Amazon EFS) le system, and congure it to support Lustre. Attach the le system to the origin server. Connect the application server to the le system.
    D. Create an Amazon FSx for Lustre le system. Attach the le system to the origin server. Connect the application server to the le system.
100. A company's containerized application runs on an Amazon EC2 instance. The application needs to download security certicates before it can communicate with other business applications. The company wants a highly secure solution to encrypt and decrypt the certicates in near real time. The solution also needs to store data in highly available storage after the data is encrypted.
     Which solution will meet these requirements with the LEAST operational overhead?
     A. Create AWS Secrets Manager secrets for encrypted certicates. Manually update the certicates as needed. Control access to the data by using ne-grained IAM access.
     B. Create an AWS Lambda function that uses the Python cryptography library to receive and perform encryption operations. Store the function in an Amazon S3 bucket.
     C. Create an AWS Key Management Service (AWS KMS) customer managed key. Allow the EC2 role to use the KMS key for encryption operations. Store the encrypted data on Amazon S3.
     D. Create an AWS Key Management Service (AWS KMS) customer managed key. Allow the EC2 role to use the KMS key for encryption operations. Store the encrypted data on Amazon Elastic Block Store (Amazon EBS) volumes.
101. A solutions architect is designing a VPC with public and private subnets. The VPC and subnets use IPv4 CIDR blocks. There is one public subnet and one private subnet in each of three Availability Zones (AZs) for high availability. An internet gateway is used to provide internet access for the public subnets. The private subnets require access to the internet to allow Amazon EC2 instances to download software updates.
     What should the solutions architect do to enable Internet access for the private subnets?
     A. Create three NAT gateways, one for each public subnet in each AZ. Create a private route table for each AZ that forwards non-VPC trac to the NAT gateway in its AZ.
     B. Create three NAT instances, one for each private subnet in each AZ. Create a private route table for each AZ that forwards non-VPC trac to the NAT instance in its AZ.
     C. Create a second internet gateway on one of the private subnets. Update the route table for the private subnets that forward non-VPC trac to the private internet gateway.
     D. Create an egress-only internet gateway on one of the public subnets. Update the route table for the private subnets that forward non- VPC trac to the egress-only Internet gateway.
102. A company wants to migrate an on-premises data center to AWS. The data center hosts an SFTP server that stores its data on an NFS-based le system. The server holds 200 GB of data that needs to be transferred. The server must be hosted on an Amazon EC2 instance that uses an Amazon Elastic File System (Amazon EFS) le system.
     Which combination of steps should a solutions architect take to automate this task? (Choose two.)
     A. Launch the EC2 instance into the same Availability Zone as the EFS le system.
     B. Install an AWS DataSync agent in the on-premises data center.
     C. Create a secondary Amazon Elastic Block Store (Amazon EBS) volume on the EC2 instance for the data.
     D. Manually use an operating system copy command to push the data to the EC2 instance.
     E. Use AWS DataSync to create a suitable location conguration for the on-premises SFTP server.
103. A company has an AWS Glue extract, transform, and load (ETL) job that runs every day at the same time. The job processes XML data that is in an Amazon S3 bucket. New data is added to the S3 bucket every day. A solutions architect notices that AWS Glue is processing all the data during each run.
     What should the solutions architect do to prevent AWS Glue from reprocessing old data?
     A. Edit the job to use job bookmarks.
     B. Edit the job to delete data after the data is processed.
     C. Edit the job by setting the NumberOfWorkers eld to 1.
     D. Use a FindMatches machine learning (ML) transform.
104. A solutions architect must design a highly available infrastructure for a website. The website is powered by Windows web servers that run on Amazon EC2 instances. The solutions architect must implement a solution that can mitigate a large-scale DDoS attack that originates from thousands of IP addresses. Downtime is not acceptable for the website.
     Which actions should the solutions architect take to protect the website from such an attack? (Choose two.)
     A. Use AWS Shield Advanced to stop the DDoS attack.
     B. Congure Amazon GuardDuty to automatically block the attackers.
     C. Congure the website to use Amazon CloudFront for both static and dynamic content.
     D. Use an AWS Lambda function to automatically add attacker IP addresses to VPC network ACLs.
     E. Use EC2 Spot Instances in an Auto Scaling group with a target tracking scaling policy that is set to 80% CPU utilization.
105. A company is preparing to deploy a new serverless workload. A solutions architect must use the principle of least privilege to congure permissions that will be used to run an AWS Lambda function. An Amazon EventBridge (Amazon CloudWatch Events) rule will invoke the function.
     Which solution meets these requirements?
     A. Add an execution role to the function with lambda:InvokeFunction as the action and * as the principal.
     B. Add an execution role to the function with lambda:InvokeFunction as the action and Service: lambda.amazonaws.com as the principal.
     C. Add a resource-based policy to the function with lambda:* as the action and Service: events.amazonaws.com as the principal.
     D. Add a resource-based policy to the function with lambda:InvokeFunction as the action and Service: events.amazonaws.com as the principal.
106. A company is preparing to store condential data in Amazon S3. For compliance reasons, the data must be encrypted at rest. Encryption key usage must be logged for auditing purposes. Keys must be rotated every year.
     Which solution meets these requirements and is the MOST operationally ecient?
     A. Server-side encryption with customer-provided keys (SSE-C)
     B. Server-side encryption with Amazon S3 managed keys (SSE-S3)
     C. Server-side encryption with AWS KMS keys (SSE-KMS) with manual rotation
     D. Server-side encryption with AWS KMS keys (SSE-KMS) with automatic rotation
107. A bicycle sharing company is developing a multi-tier architecture to track the location of its bicycles during peak operating hours. The company wants to use these data points in its existing analytics platform. A solutions architect must determine the most viable multi-tier option to support this architecture. The data points must be accessible from the REST API.
     Which action meets these requirements for storing and retrieving location data?
     A. Use Amazon Athena with Amazon S3.
     B. Use Amazon API Gateway with AWS Lambda.
     C. Use Amazon QuickSight with Amazon Redshift.
     D. Use Amazon API Gateway with Amazon Kinesis Data Analytics.
108. A company has an automobile sales website that stores its listings in a database on Amazon RDS. When an automobile is sold, the listing needs to be removed from the website and the data must be sent to multiple target systems.
     Which design should a solutions architect recommend?
     A. Create an AWS Lambda function triggered when the database on Amazon RDS is updated to send the information to an Amazon Simple Queue Service (Amazon SQS) queue for the targets to consume.
     B. Create an AWS Lambda function triggered when the database on Amazon RDS is updated to send the information to an Amazon Simple Queue Service (Amazon SQS) FIFO queue for the targets to consume.
     C. Subscribe to an RDS event notication and send an Amazon Simple Queue Service (Amazon SQS) queue fanned out to multiple Amazon Simple Notication Service (Amazon SNS) topics. Use AWS Lambda functions to update the targets.
     D. Subscribe to an RDS event notication and send an Amazon Simple Notication Service (Amazon SNS) topic fanned out to multiple Amazon Simple Queue Service (Amazon SQS) queues. Use AWS Lambda functions to update the targets.
109. A company needs to store data in Amazon S3 and must prevent the data from being changed. The company wants new objects that are uploaded to Amazon S3 to remain unchangeable for a nonspecic amount of time until the company decides to modify the objects. Only specic users in the company's AWS account can have the ability 10 delete the objects.
     What should a solutions architect do to meet these requirements?
     A. Create an S3 Glacier vault. Apply a write-once, read-many (WORM) vault lock policy to the objects.
     B. Create an S3 bucket with S3 Object Lock enabled. Enable versioning. Set a retention period of 100 years. Use governance mode as the S3 bucket’s default retention mode for new objects.
     C. Create an S3 bucket. Use AWS CloudTrail to track any S3 API events that modify the objects. Upon notication, restore the modied objects from any backup versions that the company has.
     D. Create an S3 bucket with S3 Object Lock enabled. Enable versioning. Add a legal hold to the objects. Add the s3:PutObjectLegalHold permission to the IAM policies of users who need to delete the objects.
110. A social media company allows users to upload images to its website. The website runs on Amazon EC2 instances. During upload requests, the website resizes the images to a standard size and stores the resized images in Amazon S3. Users are experiencing slow upload requests to the website.
     The company needs to reduce coupling within the application and improve website performance. A solutions architect must design the most operationally ecient process for image uploads.
     Which combination of actions should the solutions architect take to meet these requirements? (Choose two.)
     A. Congure the application to upload images to S3 Glacier.
     B. Congure the web server to upload the original images to Amazon S3.
     C. Congure the application to upload images directly from each user's browser to Amazon S3 through the use of a presigned URL
     D. Congure S3 Event Notications to invoke an AWS Lambda function when an image is uploaded. Use the function to resize the image.
     E. Create an Amazon EventBridge (Amazon CloudWatch Events) rule that invokes an AWS Lambda function on a schedule to resize uploaded images. 
111. A company recently migrated a message processing system to AWS. The system receives messages into an ActiveMQ queue running on an Amazon EC2 instance. Messages are processed by a consumer application running on Amazon EC2. The consumer application processes the messages and writes results to a MySQL database running on Amazon EC2. The company wants this application to be highly available with low operational complexity.
     Which architecture offers the HIGHEST availability?
     A. Add a second ActiveMQ server to another Availability Zone. Add an additional consumer EC2 instance in another Availability Zone. Replicate the MySQL database to another Availability Zone.
     B. Use Amazon MQ with active/standby brokers congured across two Availability Zones. Add an additional consumer EC2 instance in another Availability Zone. Replicate the MySQL database to another Availability Zone.
     C. Use Amazon MQ with active/standby brokers congured across two Availability Zones. Add an additional consumer EC2 instance in another Availability Zone. Use Amazon RDS for MySQL with Multi-AZ enabled.
     D. Use Amazon MQ with active/standby brokers congured across two Availability Zones. Add an Auto Scaling group for the consumer EC2 instances across two Availability Zones. Use Amazon RDS for MySQL with Multi-AZ enabled.
112. A company hosts a containerized web application on a eet of on-premises servers that process incoming requests. The number of requests is growing quickly. The on-premises servers cannot handle the increased number of requests. The company wants to move the application to AWS with minimum code changes and minimum development effort.
     Which solution will meet these requirements with the LEAST operational overhead?
     A. Use AWS Fargate on Amazon Elastic Container Service (Amazon ECS) to run the containerized web application with Service Auto Scaling. Use an Application Load Balancer to distribute the incoming requests.
     B. Use two Amazon EC2 instances to host the containerized web application. Use an Application Load Balancer to distribute the incoming requests.
     C. Use AWS Lambda with a new code that uses one of the supported languages. Create multiple Lambda functions to support the load. Use Amazon API Gateway as an entry point to the Lambda functions.
     D. Use a high performance computing (HPC) solution such as AWS ParallelCluster to establish an HPC cluster that can process the incoming requests at the appropriate scale.
113. A company uses 50 TB of data for reporting. The company wants to move this data from on premises to AWS. A custom application in the company’s data center runs a weekly data transformation job. The company plans to pause the application until the data transfer is complete and needs to begin the transfer process as soon as possible.
     The data center does not have any available network bandwidth for additional workloads. A solutions architect must transfer the data and must congure the transformation job to continue to run in the AWS Cloud.
     Which solution will meet these requirements with the LEAST operational overhead?
     A. Use AWS DataSync to move the data. Create a custom transformation job by using AWS Glue.
     B. Order an AWS Snowcone device to move the data. Deploy the transformation application to the device.
     C. Order an AWS Snowball Edge Storage Optimized device. Copy the data to the device. Create a custom transformation job by using AWS Glue.
     D. Order an AWS Snowball Edge Storage Optimized device that includes Amazon EC2 compute. Copy the data to the device. Create a new EC2 instance on AWS to run the transformation application.
114. A company has created an image analysis application in which users can upload photos and add photo frames to their images. The users upload images and metadata to indicate which photo frames they want to add to their images. The application uses a single Amazon EC2 instance and Amazon DynamoDB to store the metadata.
     The application is becoming more popular, and the number of users is increasing. The company expects the number of concurrent users to vary signicantly depending on the time of day and day of week. The company must ensure that the application can scale to meet the needs of the growing user base.
     Which solution meats these requirements?
     A. Use AWS Lambda to process the photos. Store the photos and metadata in DynamoDB.
     B. Use Amazon Kinesis Data Firehose to process the photos and to store the photos and metadata.
     C. Use AWS Lambda to process the photos. Store the photos in Amazon S3. Retain DynamoDB to store the metadata.
     D. Increase the number of EC2 instances to three. Use Provisioned IOPS SSD (io2) Amazon Elastic Block Store (Amazon EBS) volumes to store the photos and metadata.
115. A medical records company is hosting an application on Amazon EC2 instances. The application processes customer data les that are stored on Amazon S3. The EC2 instances are hosted in public subnets. The EC2 instances access Amazon S3 over the internet, but they do not require any other network access.
     A new requirement mandates that the network trac for le transfers take a private route and not be sent over the internet.
     Which change to the network architecture should a solutions architect recommend to meet this requirement?
     A. Create a NAT gateway. Congure the route table for the public subnets to send trac to Amazon S3 through the NAT gateway.
     B. Congure the security group for the EC2 instances to restrict outbound trac so that only trac to the S3 prex list is permitted.
     C. Move the EC2 instances to private subnets. Create a VPC endpoint for Amazon S3, and link the endpoint to the route table for the private subnets.
     D. Remove the internet gateway from the VPC. Set up an AWS Direct Connect connection, and route trac to Amazon S3 over the Direct Connect connection.
116. A company uses a popular content management system (CMS) for its corporate website. However, the required patching and maintenance are burdensome. The company is redesigning its website and wants anew solution. The website will be updated four times a year and does not need to have any dynamic content available. The solution must provide high scalability and enhanced security.
     Which combination of changes will meet these requirements with the LEAST operational overhead? (Choose two.)
     A. Congure Amazon CloudFront in front of the website to use HTTPS functionality.
     B. Deploy an AWS WAF web ACL in front of the website to provide HTTPS functionality.
     C. Create and deploy an AWS Lambda function to manage and serve the website content.
     D. Create the new website and an Amazon S3 bucket. Deploy the website on the S3 bucket with static website hosting enabled.
     E. Create the new website. Deploy the website by using an Auto Scaling group of Amazon EC2 instances behind an Application Load Balancer.
117. A company stores its application logs in an Amazon CloudWatch Logs log group. A new policy requires the company to store all application logs in Amazon OpenSearch Service (Amazon Elasticsearch Service) in near-real time.
     Which solution will meet this requirement with the LEAST operational overhead?
     A. Congure a CloudWatch Logs subscription to stream the logs to Amazon OpenSearch Service (Amazon Elasticsearch Service).
     B. Create an AWS Lambda function. Use the log group to invoke the function to write the logs to Amazon OpenSearch Service (Amazon Elasticsearch Service).
     C. Create an Amazon Kinesis Data Firehose delivery stream. Congure the log group as the delivery streams sources. Congure Amazon OpenSearch Service (Amazon Elasticsearch Service) as the delivery stream's destination.
     D. Install and congure Amazon Kinesis Agent on each application server to deliver the logs to Amazon Kinesis Data Streams. Congure Kinesis Data Streams to deliver the logs to Amazon OpenSearch Service (Amazon Elasticsearch Service).
118. A company is building a web-based application running on Amazon EC2 instances in multiple Availability Zones. The web application will provide access to a repository of text documents totaling about 900 TB in size. The company anticipates that the web application will experience periods of high demand. A solutions architect must ensure that the storage component for the text documents can scale to meet the demand of the application at all times. The company is concerned about the overall cost of the solution.
     Which storage solution meets these requirements MOST cost-effectively?
     A. Amazon Elastic Block Store (Amazon EBS)
     B. Amazon Elastic File System (Amazon EFS)
     C. Amazon OpenSearch Service (Amazon Elasticsearch Service)
     D. Amazon S3
119. A global company is using Amazon API Gateway to design REST APIs for its loyalty club users in the us-east-1 Region and the ap-southeast-2 Region. A solutions architect must design a solution to protect these API Gateway managed REST APIs across multiple accounts from SQL injection and cross-site scripting attacks.
     Which solution will meet these requirements with the LEAST amount of administrative effort?
     A. Set up AWS WAF in both Regions. Associate Regional web ACLs with an API stage.
     B. Set up AWS Firewall Manager in both Regions. Centrally congure AWS WAF rules.
     C. Set up AWS Shield in bath Regions. Associate Regional web ACLs with an API stage.
     D. Set up AWS Shield in one of the Regions. Associate Regional web ACLs with an API stage.
120. A company has implemented a self-managed DNS solution on three Amazon EC2 instances behind a Network Load Balancer (NLB) in the us- west-2 Region. Most of the company's users are located in the United States and Europe. The company wants to improve the performance and availability of the solution. The company launches and congures three EC2 instances in the eu-west-1 Region and adds the EC2 instances as targets for a new NLB.
     Which solution can the company use to route trac to all the EC2 instances?
     A. Create an Amazon Route 53 geolocation routing policy to route requests to one of the two NLBs. Create an Amazon CloudFront distribution. Use the Route 53 record as the distribution’s origin.
     B. Create a standard accelerator in AWS Global Accelerator. Create endpoint groups in us-west-2 and eu-west-1. Add the two NLBs as endpoints for the endpoint groups.
     C. Attach Elastic IP addresses to the six EC2 instances. Create an Amazon Route 53 geolocation routing policy to route requests to one of the six EC2 instances. Create an Amazon CloudFront distribution. Use the Route 53 record as the distribution's origin.
     D. Replace the two NLBs with two Application Load Balancers (ALBs). Create an Amazon Route 53 latency routing policy to route requests to one of the two ALBs. Create an Amazon CloudFront distribution. Use the Route 53 record as the distribution’s origin.
121. A company is running an online transaction processing (OLTP) workload on AWS. This workload uses an unencrypted Amazon RDS DB instance in a Multi-AZ deployment. Daily database snapshots are taken from this instance.
     What should a solutions architect do to ensure the database and snapshots are always encrypted moving forward?
     A. Encrypt a copy of the latest DB snapshot. Replace existing DB instance by restoring the encrypted snapshot.
     B. Create a new encrypted Amazon Elastic Block Store (Amazon EBS) volume and copy the snapshots to it. Enable encryption on the DB instance.
     C. Copy the snapshots and enable encryption using AWS Key Management Service (AWS KMS) Restore encrypted snapshot to an existing DB instance.
     D. Copy the snapshots to an Amazon S3 bucket that is encrypted using server-side encryption with AWS Key Management Service (AWS KMS) managed keys (SSE-KMS).
122. A company wants to build a scalable key management infrastructure to support developers who need to encrypt data in their applications. What should a solutions architect do to reduce the operational burden?
     A. Use multi-factor authentication (MFA) to protect the encryption keys.
     B. Use AWS Key Management Service (AWS KMS) to protect the encryption keys.
     C. Use AWS Certicate Manager (ACM) to create, store, and assign the encryption keys.
     D. Use an IAM policy to limit the scope of users who have access permissions to protect the encryption keys.
123. A company has a dynamic web application hosted on two Amazon EC2 instances. The company has its own SSL certicate, which is on each instance to perform SSL termination.
     There has been an increase in trac recently, and the operations team determined that SSL encryption and decryption is causing the compute capacity of the web servers to reach their maximum limit.
     What should a solutions architect do to increase the application's performance?
     A. Create a new SSL certicate using AWS Certicate Manager (ACM). Install the ACM certicate on each instance.
     B. Create an Amazon S3 bucket Migrate the SSL certicate to the S3 bucket. Congure the EC2 instances to reference the bucket for SSL termination.
     C. Create another EC2 instance as a proxy server. Migrate the SSL certicate to the new instance and congure it to direct connections to the existing EC2 instances.
     D. Import the SSL certicate into AWS Certicate Manager (ACM). Create an Application Load Balancer with an HTTPS listener that uses the SSL certicate from ACM.
124. A company has a highly dynamic batch processing job that uses many Amazon EC2 instances to complete it. The job is stateless in nature, can be started and stopped at any given time with no negative impact, and typically takes upwards of 60 minutes total to complete. The company has asked a solutions architect to design a scalable and cost-effective solution that meets the requirements of the job.
     What should the solutions architect recommend?
     A. Implement EC2 Spot Instances.
     B. Purchase EC2 Reserved Instances.
     C. Implement EC2 On-Demand Instances.
     D. Implement the processing on AWS Lambda.
125. A company runs its two-tier ecommerce website on AWS. The web tier consists of a load balancer that sends trac to Amazon EC2 instances. The database tier uses an Amazon RDS DB instance. The EC2 instances and the RDS DB instance should not be exposed to the public internet. The EC2 instances require internet access to complete payment processing of orders through a third-party web service. The application must be highly available.
     Which combination of conguration options will meet these requirements? (Choose two.)
     A. Use an Auto Scaling group to launch the EC2 instances in private subnets. Deploy an RDS Multi-AZ DB instance in private subnets.
     B. Congure a VPC with two private subnets and two NAT gateways across two Availability Zones. Deploy an Application Load Balancer in the private subnets.
     C. Use an Auto Scaling group to launch the EC2 instances in public subnets across two Availability Zones. Deploy an RDS Multi-AZ DB instance in private subnets.
     D. Congure a VPC with one public subnet, one private subnet, and two NAT gateways across two Availability Zones. Deploy an Application Load Balancer in the public subnet.
     E. Congure a VPC with two public subnets, two private subnets, and two NAT gateways across two Availability Zones. Deploy an Application Load Balancer in the public subnets.
126. A solutions architect needs to implement a solution to reduce a company's storage costs. All the company's data is in the Amazon S3 Standard storage class. The company must keep all data for at least 25 years. Data from the most recent 2 years must be highly available and immediately retrievable.
     Which solution will meet these requirements?
     A. Set up an S3 Lifecycle policy to transition objects to S3 Glacier Deep Archive immediately.
     B. Set up an S3 Lifecycle policy to transition objects to S3 Glacier Deep Archive after 2 years.
     C. Use S3 Intelligent-Tiering. Activate the archiving option to ensure that data is archived in S3 Glacier Deep Archive.
     D. Set up an S3 Lifecycle policy to transition objects to S3 One Zone-Infrequent Access (S3 One Zone-IA) immediately and to S3 Glacier Deep Archive after 2 years.
127. A media company is evaluating the possibility of moving its systems to the AWS Cloud. The company needs at least 10 TB of storage with the maximum possible I/O performance for video processing, 300 TB of very durable storage for storing media content, and 900 TB of storage to meet requirements for archival media that is not in use anymore.
     Which set of services should a solutions architect recommend to meet these requirements?
     A. Amazon EBS for maximum performance, Amazon S3 for durable data storage, and Amazon S3 Glacier for archival storage
     B. Amazon EBS for maximum performance, Amazon EFS for durable data storage, and Amazon S3 Glacier for archival storage
     C. Amazon EC2 instance store for maximum performance, Amazon EFS for durable data storage, and Amazon S3 for archival storage
     D. Amazon EC2 instance store for maximum performance, Amazon S3 for durable data storage, and Amazon S3 Glacier for archival storage
128. A company wants to run applications in containers in the AWS Cloud. These applications are stateless and can tolerate disruptions within the underlying infrastructure. The company needs a solution that minimizes cost and operational overhead.
     What should a solutions architect do to meet these requirements?
     A. Use Spot Instances in an Amazon EC2 Auto Scaling group to run the application containers.
     B. Use Spot Instances in an Amazon Elastic Kubernetes Service (Amazon EKS) managed node group.
     C. Use On-Demand Instances in an Amazon EC2 Auto Scaling group to run the application containers.
     D. Use On-Demand Instances in an Amazon Elastic Kubernetes Service (Amazon EKS) managed node group.
129. A company is running a multi-tier web application on premises. The web application is containerized and runs on a number of Linux hosts connected to a PostgreSQL database that contains user records. The operational overhead of maintaining the infrastructure and capacity planning is limiting the company's growth. A solutions architect must improve the application's infrastructure.
     Which combination of actions should the solutions architect take to accomplish this? (Choose two.)
     A. Migrate the PostgreSQL database to Amazon Aurora.
     B. Migrate the web application to be hosted on Amazon EC2 instances.
     C. Set up an Amazon CloudFront distribution for the web application content.
     D. Set up Amazon ElastiCache between the web application and the PostgreSQL database.
     E. Migrate the web application to be hosted on AWS Fargate with Amazon Elastic Container Service (Amazon ECS).
130. An application runs on Amazon EC2 instances across multiple Availability Zonas. The instances run in an Amazon EC2 Auto Scaling group behind an Application Load Balancer. The application performs best when the CPU utilization of the EC2 instances is at or near 40%. What should a solutions architect do to maintain the desired performance across all instances in the group?
     A. Use a simple scaling policy to dynamically scale the Auto Scaling group.
     B. Use a target tracking policy to dynamically scale the Auto Scaling group.
     C. Use an AWS Lambda function ta update the desired Auto Scaling group capacity.
     D. Use scheduled scaling actions to scale up and scale down the Auto Scaling group.
131. A company is developing a le-sharing application that will use an Amazon S3 bucket for storage. The company wants to serve all the les through an Amazon CloudFront distribution. The company does not want the les to be accessible through direct navigation to the S3 URL. What should a solutions architect do to meet these requirements?
     A. Write individual policies for each S3 bucket to grant read permission for only CloudFront access.
     B. Create an IAM user. Grant the user read permission to objects in the S3 bucket. Assign the user to CloudFront.
     C. Write an S3 bucket policy that assigns the CloudFront distribution ID as the Principal and assigns the target S3 bucket as the Amazon Resource Name (ARN).
     D. Create an origin access identity (OAI). Assign the OAI to the CloudFront distribution. Congure the S3 bucket permissions so that only the OAI has read permission.
132. A company’s website provides users with downloadable historical performance reports. The website needs a solution that will scale to meet the company’s website demands globally. The solution should be cost-effective, limit the provisioning of infrastructure resources, and provide the fastest possible response time.
     Which combination should a solutions architect recommend to meet these requirements?
     A. Amazon CloudFront and Amazon S3
     B. AWS Lambda and Amazon DynamoDB
     C. Application Load Balancer with Amazon EC2 Auto Scaling
     D. Amazon Route 53 with internal Application Load Balancers
133. A company runs an Oracle database on premises. As part of the company’s migration to AWS, the company wants to upgrade the database to the most recent available version. The company also wants to set up disaster recovery (DR) for the database. The company needs to minimize the operational overhead for normal operations and DR setup. The company also needs to maintain access to the database's underlying operating system.
     Which solution will meet these requirements?
     A. Migrate the Oracle database to an Amazon EC2 instance. Set up database replication to a different AWS Region.
     B. Migrate the Oracle database to Amazon RDS for Oracle. Activate Cross-Region automated backups to replicate the snapshots to another AWS Region.
     C. Migrate the Oracle database to Amazon RDS Custom for Oracle. Create a read replica for the database in another AWS Region.
     D. Migrate the Oracle database to Amazon RDS for Oracle. Create a standby database in another Availability Zone.
134. A  company wants to move its application to a serverless solution. The serverless solution needs to analyze existing and new data by using SL. The company stores the data in an Amazon S3 bucket. The data requires encryption and must be replicated to a different AWS Region.
     Which solution will meet these requirements with the LEAST operational overhead?
     A. Create a new S3 bucket. Load the data into the new S3 bucket. Use S3 Cross-Region Replication (CRR) to replicate encrypted objects to an S3 bucket in another Region. Use server-side encryption with AWS KMS multi-Region kays (SSE-KMS). Use Amazon Athena to query the data.
     B. Create a new S3 bucket. Load the data into the new S3 bucket. Use S3 Cross-Region Replication (CRR) to replicate encrypted objects to an S3 bucket in another Region. Use server-side encryption with AWS KMS multi-Region keys (SSE-KMS). Use Amazon RDS to query the data.
     C. Load the data into the existing S3 bucket. Use S3 Cross-Region Replication (CRR) to replicate encrypted objects to an S3 bucket in another Region. Use server-side encryption with Amazon S3 managed encryption keys (SSE-S3). Use Amazon Athena to query the data.
     D. Load the data into the existing S3 bucket. Use S3 Cross-Region Replication (CRR) to replicate encrypted objects to an S3 bucket in another Region. Use server-side encryption with Amazon S3 managed encryption keys (SSE-S3). Use Amazon RDS to query the data.
135. A company runs workloads on AWS. The company needs to connect to a service from an external provider. The service is hosted in the provider's VPC. According to the company’s security team, the connectivity must be private and must be restricted to the target service. The connection must be initiated only from the company’s VPC.
     Which solution will mast these requirements?
     A. Create a VPC peering connection between the company's VPC and the provider's VPC. Update the route table to connect to the target service.
     B. Ask the provider to create a virtual private gateway in its VPC. Use AWS PrivateLink to connect to the target service.
     C. Create a NAT gateway in a public subnet of the company’s VPUpdate the route table to connect to the target service.
     D. Ask the provider to create a VPC endpoint for the target service. Use AWS PrivateLink to connect to the target service.
136. A company is migrating its on-premises PostgreSQL database to Amazon Aurora PostgreSQL. The on-premises database must remain online and accessible during the migration. The Aurora database must remain synchronized with the on-premises database.
     Which combination of actions must a solutions architect take to meet these requirements? (Choose two.)
     A. Create an ongoing replication task.
     B. Create a database backup of the on-premises database.
     C. Create an AWS Database Migration Service (AWS DMS) replication server.
     D. Convert the database schema by using the AWS Schema Conversion Tool (AWS SCT).
     E. Create an Amazon EventBridge (Amazon CloudWatch Events) rule to monitor the database synchronization.
137. A company uses AWS Organizations to create dedicated AWS accounts for each business unit to manage each business unit's account independently upon request. The root email recipient missed a notication that was sent to the root user email address of one account. The company wants to ensure that all future notications are not missed. Future notications must be limited to account administrators.
     Which solution will meet these requirements?
     A. Congure the company’s email server to forward notication email messages that are sent to the AWS account root user email address to all users in the organization.
     B. Congure all AWS account root user email addresses as distribution lists that go to a few administrators who can respond to alerts. Congure AWS account alternate contacts in the AWS Organizations console or programmatically.
     C. Congure all AWS account root user email messages to be sent to one administrator who is responsible for monitoring alerts and forwarding those alerts to the appropriate groups.
     D. Congure all existing AWS accounts and all newly created accounts to use the same root user email address. Congure AWS account alternate contacts in the AWS Organizations console or programmatically.
138. A company runs its ecommerce application on AWS. Every new order is published as a massage in a RabbitMQ queue that runs on an Amazon EC2 instance in a single Availability Zone. These messages are processed by a different application that runs on a separate EC2 instance. This application stores the details in a PostgreSQL database on another EC2 instance. All the EC2 instances are in the same Availability Zone. The company needs to redesign its architecture to provide the highest availability with the least operational overhead.
     What should a solutions architect do to meet these requirements?
     A. Migrate the queue to a redundant pair (active/standby) of RabbitMQ instances on Amazon MQ. Create a Multi-AZ Auto Scaling group for EC2 instances that host the application. Create another Multi-AZ Auto Scaling group for EC2 instances that host the PostgreSQL database.
     B. Migrate the queue to a redundant pair (active/standby) of RabbitMQ instances on Amazon MQ. Create a Multi-AZ Auto Scaling group for EC2 instances that host the application. Migrate the database to run on a Multi-AZ deployment of Amazon RDS for PostgreSQL.
     C. Create a Multi-AZ Auto Scaling group for EC2 instances that host the RabbitMQ queue. Create another Multi-AZ Auto Scaling group for EC2 instances that host the application. Migrate the database to run on a Multi-AZ deployment of Amazon RDS for PostgreSQL.
     D. Create a Multi-AZ Auto Scaling group for EC2 instances that host the RabbitMQ queue. Create another Multi-AZ Auto Scaling group for EC2 instances that host the application. Create a third Multi-AZ Auto Scaling group for EC2 instances that host the PostgreSQL database
139. A reporting team receives les each day in an Amazon S3 bucket. The reporting team manually reviews and copies the les from this initial S3 bucket to an analysis S3 bucket each day at the same time to use with Amazon QuickSight. Additional teams are starting to send more les in larger sizes to the initial S3 bucket.
     The reporting team wants to move the les automatically analysis S3 bucket as the les enter the initial S3 bucket. The reporting team also wants to use AWS Lambda functions to run pattern-matching code on the copied data. In addition, the reporting team wants to send the data les to a pipeline in Amazon SageMaker Pipelines.
     What should a solutions architect do to meet these requirements with the LEAST operational overhead?
     A. Create a Lambda function to copy the les to the analysis S3 bucket. Create an S3 event notication for the analysis S3 bucket. Congure Lambda and SageMaker Pipelines as destinations of the event notication. Congure s3:ObjectCreated:Put as the event type.
     B. Create a Lambda function to copy the les to the analysis S3 bucket. Congure the analysis S3 bucket to send event notications to Amazon EventBridge (Amazon CloudWatch Events). Congure an ObjectCreated rule in EventBridge (CloudWatch Events). Congure Lambda and SageMaker Pipelines as targets for the rule.
     C. Congure S3 replication between the S3 buckets. Create an S3 event notication for the analysis S3 bucket. Congure Lambda and SageMaker Pipelines as destinations of the event notication. Congure s3:ObjectCreated:Put as the event type.
     D. Congure S3 replication between the S3 buckets. Congure the analysis S3 bucket to send event notications to Amazon EventBridge (Amazon CloudWatch Events). Congure an ObjectCreated rule in EventBridge (CloudWatch Events). Congure Lambda and SageMaker Pipelines as targets for the rule.
140. A solutions architect needs to help a company optimize the cost of running an application on AWS. The application will use Amazon EC2 instances, AWS Fargate, and AWS Lambda for compute within the architecture.
     The EC2 instances will run the data ingestion layer of the application. EC2 usage will be sporadic and unpredictable. Workloads that run on EC2 instances can be interrupted at any time. The application front end will run on Fargate, and Lambda will serve the API layer. The front-end utilization and API layer utilization will be predictable over the course of the next year.
     Which combination of purchasing options will provide the MOST cost-effective solution for hosting this application? (Choose two.)
     A. Use Spot Instances for the data ingestion layer
     B. Use On-Demand Instances for the data ingestion layer
     C. Purchase a 1-year Compute Savings Plan for the front end and API layer.
     D. Purchase 1-year All Upfront Reserved instances for the data ingestion layer.
     E. Purchase a 1-year EC2 instance Savings Plan for the front end and API layer.
141. A company runs a web-based portal that provides users with global breaking news, local alerts, and weather updates. The portal delivers each user a personalized view by using mixture of static and dynamic content. Content is served over HTTPS through an API server running on an Amazon EC2 instance behind an Application Load Balancer (ALB). The company wants the portal to provide this content to its users across the world as quickly as possible.
     How should a solutions architect design the application to ensure the LEAST amount of latency for all users?
     A. Deploy the application stack in a single AWS Region. Use Amazon CloudFront to serve all static and dynamic content by specifying the ALB as an origin.
     B. Deploy the application stack in two AWS Regions. Use an Amazon Route 53 latency routing policy to serve all content from the ALB in the closest Region.
     C. Deploy the application stack in a single AWS Region. Use Amazon CloudFront to serve the static content. Serve the dynamic content directly from the ALB.
     D. Deploy the application stack in two AWS Regions. Use an Amazon Route 53 geolocation routing policy to serve all content from the ALB in the closest Region.
142. A gaming company is designing a highly available architecture. The application runs on a modied Linux kernel and supports only UDP-based trac. The company needs the front-end tier to provide the best possible user experience. That tier must have low latency, route trac to the nearest edge location, and provide static IP addresses for entry into the application endpoints.
     What should a solutions architect do to meet these requirements?
     A. Congure Amazon Route 53 to forward requests to an Application Load Balancer. Use AWS Lambda for the application in AWS Application Auto Scaling.
     B. Congure Amazon CloudFront to forward requests to a Network Load Balancer. Use AWS Lambda for the application in an AWS Application Auto Scaling group.
     C. Congure AWS Global Accelerator to forward requests to a Network Load Balancer. Use Amazon EC2 instances for the application in an EC2 Auto Scaling group.
     D. Congure Amazon API Gateway to forward requests to an Application Load Balancer. Use Amazon EC2 instances for the application in an EC2 Auto Scaling group.
143. A company wants to migrate its existing on-premises monolithic application to AWS. The company wants to keep as much of the front-end code and the backend code as possible. However, the company wants to break the application into smaller applications. A different team will manage each application. The company needs a highly scalable solution that minimizes operational overhead.
     Which solution will meet these requirements?
     A. Host the application on AWS Lambda. Integrate the application with Amazon API Gateway.
     B. Host the application with AWS Amplify. Connect the application to an Amazon API Gateway API that is integrated with AWS Lambda.
     C. Host the application on Amazon EC2 instances. Set up an Application Load Balancer with EC2 instances in an Auto Scaling group as targets.
     D. Host the application on Amazon Elastic Container Service (Amazon ECS). Set up an Application Load Balancer with Amazon ECS as the target.
144. A company recently started using Amazon Aurora as the data store for its global ecommerce application. When large reports are run, developers report that the ecommerce application is performing poorly. After reviewing metrics in Amazon CloudWatch, a solutions architect nds that the ReadIOPS and CPUUtilizalion metrics are spiking when monthly reports run.
     What is the MOST cost-effective solution?
     A. Migrate the monthly reporting to Amazon Redshift.
     B. Migrate the monthly reporting to an Aurora Replica.
     C. Migrate the Aurora database to a larger instance class.
     D. Increase the Provisioned IOPS on the Aurora instance.
145. A company hosts a website analytics application on a single Amazon EC2 On-Demand Instance. The analytics software is written in PHP and uses a MySQL database. The analytics software, the web server that provides PHP, and the database server are all hosted on the EC2 instance. The application is showing signs of performance degradation during busy times and is presenting 5xx errors. The company needs to make the application scale seamlessly.
     Which solution will meet these requirements MOST cost-effectively?
     A. Migrate the database to an Amazon RDS for MySQL DB instance. Create an AMI of the web application. Use the AMI to launch a second EC2 On-Demand Instance. Use an Application Load Balancer to distribute the load to each EC2 instance.
     B. Migrate the database to an Amazon RDS for MySQL DB instance. Create an AMI of the web application. Use the AMI to launch a second EC2 On-Demand Instance. Use Amazon Route 53 weighted routing to distribute the load across the two EC2 instances.
     C. Migrate the database to an Amazon Aurora MySQL DB instance. Create an AWS Lambda function to stop the EC2 instance and change the instance type. Create an Amazon CloudWatch alarm to invoke the Lambda function when CPU utilization surpasses 75%.
     D. Migrate the database to an Amazon Aurora MySQL DB instance. Create an AMI of the web application. Apply the AMI to a launch template. Create an Auto Scaling group with the launch template Congure the launch template to use a Spot Fleet. Attach an Application Load Balancer to the Auto Scaling group.
146. A company runs a stateless web application in production on a group of Amazon EC2 On-Demand Instances behind an Application Load Balancer. The application experiences heavy usage during an 8-hour period each business day. Application usage is moderate and steady overnight. Application usage is low during weekends.
     The company wants to minimize its EC2 costs without affecting the availability of the application.
     Which solution will meet these requirements?
     A. Use Spot Instances for the entire workload.
     B. Use Reserved Instances for the baseline level of usage. Use Spot instances for any additional capacity that the application needs.
     C. Use On-Demand Instances for the baseline level of usage. Use Spot Instances for any additional capacity that the application needs.
     D. Use Dedicated Instances for the baseline level of usage. Use On-Demand Instances for any additional capacity that the application needs.
147. A company needs to retain application log les for a critical application for 10 years. The application team regularly accesses logs from the past month for troubleshooting, but logs older than 1 month are rarely accessed. The application generates more than 10 TB of logs per month.
     Which storage option meets these requirements MOST cost-effectively?
     A. Store the logs in Amazon S3. Use AWS Backup to move logs more than 1 month old to S3 Glacier Deep Archive.
     B. Store the logs in Amazon S3. Use S3 Lifecycle policies to move logs more than 1 month old to S3 Glacier Deep Archive.
     C. Store the logs in Amazon CloudWatch Logs. Use AWS Backup to move logs more than 1 month old to S3 Glacier Deep Archive.
     D. Store the logs in Amazon CloudWatch Logs. Use Amazon S3 Lifecycle policies to move logs more than 1 month old to S3 Glacier Deep Archive.
148. A company has a data ingestion workow that includes the following components:
     An Amazon Simple Notication Service (Amazon SNS) topic that receives notications about new data deliveries
     An AWS Lambda function that processes and stores the data
     The ingestion workow occasionally fails because of network connectivity issues. When failure occurs, the corresponding data is not ingested unless the company manually reruns the job.
     What should a solutions architect do to ensure that all notications are eventually processed?
     A. Congure the Lambda function for deployment across multiple Availability Zones.
     B. Modify the Lambda function's conguration to increase the CPU and memory allocations for the function.
     C. Congure the SNS topic’s retry strategy to increase both the number of retries and the wait time between retries.
     D. Congure an Amazon Simple Queue Service (Amazon SQS) queue as the on-failure destination. Modify the Lambda function to process messages in the queue.
149. A company has a service that produces event data. The company wants to use AWS to process the event data as it is received. The data is written in a specic order that must be maintained throughout processing. The company wants to implement a solution that minimizes operational overhead.
     How should a solutions architect accomplish this?
     A. Create an Amazon Simple Queue Service (Amazon SQS) FIFO queue to hold messages. Set up an AWS Lambda function to process messages from the queue.
     B. Create an Amazon Simple Notication Service (Amazon SNS) topic to deliver notications containing payloads to process. Congure an AWS Lambda function as a subscriber.
     C. Create an Amazon Simple Queue Service (Amazon SQS) standard queue to hold messages. Set up an AWS Lambda function to process messages from the queue independently.
     D. Create an Amazon Simple Notication Service (Amazon SNS) topic to deliver notications containing payloads to process. Congure an Amazon Simple Queue Service (Amazon SQS) queue as a subscriber.
150. A company is migrating an application from on-premises servers to Amazon EC2 instances. As part of the migration design requirements, a solutions architect must implement infrastructure metric alarms. The company does not need to take action if CPU utilization increases to more than 50% for a short burst of time. However, if the CPU utilization increases to more than 50% and read IOPS on the disk are high at the same time, the company needs to act as soon as possible. The solutions architect also must reduce false alarms.
     What should the solutions architect do to meet these requirements?
     A. Create Amazon CloudWatch composite alarms where possible.
     B. Create Amazon CloudWatch dashboards to visualize the metrics and react to issues quickly.
     C. Create Amazon CloudWatch Synthetics canaries to monitor the application and raise an alarm.
     D. Create single Amazon CloudWatch metric alarms with multiple metric thresholds where possible.
151. A company wants to migrate its on-premises data center to AWS. According to the company's compliance requirements, the company can use only the ap-northeast-3 Region. Company administrators are not permitted to connect VPCs to the internet.
     Which solutions will meet these requirements? (Choose two.)
     A. Use AWS Control Tower to implement data residency guardrails to deny internet access and deny access to all AWS Regions except ap- northeast-3.
     B. Use rules in AWS WAF to prevent internet access. Deny access to all AWS Regions except ap-northeast-3 in the AWS account settings.
     C. Use AWS Organizations to congure service control policies (SCPS) that prevent VPCs from gaining internet access. Deny access to all AWS Regions except ap-northeast-3.
     D. Create an outbound rule for the network ACL in each VPC to deny all trac from 0.0.0.0/0. Create an IAM policy for each user to prevent the use of any AWS Region other than ap-northeast-3.
     E. Use AWS Cong to activate managed rules to detect and alert for internet gateways and to detect and alert for new resources deployed outside of ap-northeast-3.
152. A company uses a three-tier web application to provide training to new employees. The application is accessed for only 12 hours every day. The company is using an Amazon RDS for MySQL DB instance to store information and wants to minimize costs.
     What should a solutions architect do to meet these requirements?
     A. Congure an IAM policy for AWS Systems Manager Session Manager. Create an IAM role for the policy. Update the trust relationship of the role. Set up automatic start and stop for the DB instance.
     B. Create an Amazon ElastiCache for Redis cache cluster that gives users the ability to access the data from the cache when the DB instance is stopped. Invalidate the cache after the DB instance is started.
     C. Launch an Amazon EC2 instance. Create an IAM role that grants access to Amazon RDS. Attach the role to the EC2 instance. Congure a cron job to start and stop the EC2 instance on the desired schedule.
     D. Create AWS Lambda functions to start and stop the DB instance. Create Amazon EventBridge (Amazon CloudWatch Events) scheduled rules to invoke the Lambda functions. Congure the Lambda functions as event targets for the rules.
153. A company sells ringtones created from clips of popular songs. The les containing the ringtones are stored in Amazon S3 Standard and are at least 128 KB in size. The company has millions of les, but downloads are infrequent for ringtones older than 90 days. The company needs to save money on storage while keeping the most accessed les readily available for its users.
     Which action should the company take to meet these requirements MOST cost-effectively?
     A. Congure S3 Standard-Infrequent Access (S3 Standard-IA) storage for the initial storage tier of the objects.
     B. Move the les to S3 Intelligent-Tiering and congure it to move objects to a less expensive storage tier after 90 days.
     C. Congure S3 inventory to manage objects and move them to S3 Standard-Infrequent Access (S3 Standard-1A) after 90 days.
     D. Implement an S3 Lifecycle policy that moves the objects from S3 Standard to S3 Standard-Infrequent Access (S3 Standard-1A) after 90 days.
154. A company needs to save the results from a medical trial to an Amazon S3 repository. The repository must allow a few scientists to add new les and must restrict all other users to read-only access. No users can have the ability to modify or delete any les in the repository. The company must keep every le in the repository for a minimum of 1 year after its creation date.
     Which solution will meet these requirements?
     A. Use S3 Object Lock in governance mode with a legal hold of 1 year.
     B. Use S3 Object Lock in compliance mode with a retention period of 365 days.
     C. Use an IAM role to restrict all users from deleting or changing objects in the S3 bucket. Use an S3 bucket policy to only allow the IAM role.
     D. Congure the S3 bucket to invoke an AWS Lambda function every time an object is added. Congure the function to track the hash of the saved object so that modied objects can be marked accordingly.
155. A large media company hosts a web application on AWS. The company wants to start caching condential media les so that users around the world will have reliable access to the les. The content is stored in Amazon S3 buckets. The company must deliver the content quickly, regardless of where the requests originate geographically.
     Which solution will meet these requirements?
     A. Use AWS DataSync to connect the S3 buckets to the web application.
     B. Deploy AWS Global Accelerator to connect the S3 buckets to the web application.
     C. Deploy Amazon CloudFront to connect the S3 buckets to CloudFront edge servers.
     D. Use Amazon Simple Queue Service (Amazon SQS) to connect the S3 buckets to the web application.
156. A company produces batch data that comes from different databases. The company also produces live stream data from network sensors and application APIs. The company needs to consolidate all the data into one place for business analytics. The company needs to process the incoming data and then stage the data in different Amazon S3 buckets. Teams will later run one-time queries and import the data into a business intelligence tool to show key performance indicators (KPIs).
     Which combination of steps will meet these requirements with the LEAST operational overhead? (Choose two.)
     A. Use Amazon Athena for one-time queries. Use Amazon QuickSight to create dashboards for KPIs.
     B. Use Amazon Kinesis Data Analytics for one-time queries. Use Amazon QuickSight to create dashboards for KPIs.
     C. Create custom AWS Lambda functions to move the individual records from the databases to an Amazon Redshift cluster.
     D. Use an AWS Glue extract, transform, and load (ETL) job to convert the data into JSON format. Load the data into multiple Amazon OpenSearch Service (Amazon Elasticsearch Service) clusters.
     E. Use blueprints in AWS Lake Formation to identify the data that can be ingested into a data lake. Use AWS Glue to crawl the source, extract the data, and load the data into Amazon S3 in Apache Parquet format.
157. A company stores data in an Amazon Aurora PostgreSQL DB cluster. The company must store all the data for 5 years and must delete all the data after 5 years. The company also must indenitely keep audit logs of actions that are performed within the database. Currently, the company has automated backups congured for Aurora.
     Which combination of steps should a solutions architect take to meet these requirements? (Choose two.)
     A. Take a manual snapshot of the DB cluster.
     B. Create a lifecycle policy for the automated backups.
     C. Congure automated backup retention for 5 years.
     D. Congure an Amazon CloudWatch Logs export for the DB cluster.
     E. Use AWS Backup to take the backups and to keep the backups for 5 years.
158. A solutions architect is optimizing a website for an upcoming musical event. Videos of the performances will be streamed in real time and then will be available on demand. The event is expected to attract a global online audience.
     Which service will improve the performance of both the real-time and on-demand streaming?
     A. Amazon CloudFront
     B. AWS Global Accelerator
     C. Amazon Route 53
     D. Amazon S3 Transfer Acceleration
159. A company is running a publicly accessible serverless application that uses Amazon API Gateway and AWS Lambda. The application’s trac recently spiked due to fraudulent requests from botnets.
     Which steps should a solutions architect take to block requests from unauthorized users? (Choose two.)
     A. Create a usage plan with an API key that is shared with genuine users only.
     B. Integrate logic within the Lambda function to ignore the requests from fraudulent IP addresses.
     C. Implement an AWS WAF rule to target malicious requests and trigger actions to lter them out.
     D. Convert the existing public API to a private API. Update the DNS records to redirect users to the new API endpoint.
     E. Create an IAM role for each user attempting to access the API. A user will assume the role when making the API call.
160. An ecommerce company hosts its analytics application in the AWS Cloud. The application generates about 300 MB of data each month. The data is stored in JSON format. The company is evaluating a disaster recovery solution to back up the data. The data must be accessible in milliseconds if it is needed, and the data must be kept for 30 days.
     Which solution meets these requirements MOST cost-effectively?
     A. Amazon OpenSearch Service (Amazon Elasticsearch Service) 
     B. Amazon S3 Glacier
     C. Amazon S3 Standard
     D. Amazon RDS for PostgreSQL
161. A company has a small Python application that processes JSON documents and outputs the results to an on-premises SQL database. The application runs thousands of times each day. The company wants to move the application to the AWS Cloud. The company needs a highly available solution that maximizes scalability and minimizes operational overhead.
     Which solution will meet these requirements?
     A. Place the JSON documents in an Amazon S3 bucket. Run the Python code on multiple Amazon EC2 instances to process the documents. Store the results in an Amazon Aurora DB cluster.
     B. Place the JSON documents in an Amazon S3 bucket. Create an AWS Lambda function that runs the Python code to process the documents as they arrive in the S3 bucket. Store the results in an Amazon Aurora DB cluster.
     C. Place the JSON documents in an Amazon Elastic Block Store (Amazon EBS) volume. Use the EBS Multi-Attach feature to attach the volume to multiple Amazon EC2 instances. Run the Python code on the EC2 instances to process the documents. Store the results on an Amazon RDS DB instance.
     D. Place the JSON documents in an Amazon Simple Queue Service (Amazon SQS) queue as messages. Deploy the Python code as a container on an Amazon Elastic Container Service (Amazon ECS) cluster that is congured with the Amazon EC2 launch type. Use the container to process the SQS messages. Store the results on an Amazon RDS DB instance.
162. A company wants to use high performance computing (HPC) infrastructure on AWS for nancial risk modeling. The company’s HPC workloads run on Linux. Each HPC workow runs on hundreds of Amazon EC2 Spot Instances, is short-lived, and generates thousands of output les that are ultimately stored in persistent storage for analytics and long-term future use.
     The company seeks a cloud storage solution that permits the copying of on-premises data to long-term persistent storage to make data available for processing by all EC2 instances. The solution should also be a high performance le system that is integrated with persistent storage to read and write datasets and output les.
     Which combination of AWS services meets these requirements?
     A. Amazon FSx for Lustre integrated with Amazon S3
     B. Amazon FSx for Windows File Server integrated with Amazon S3
     C. Amazon S3 Glacier integrated with Amazon Elastic Block Store (Amazon EBS)
     D. Amazon S3 bucket with a VPC endpoint integrated with an Amazon Elastic Block Store (Amazon EBS) General Purpose SSD (gp2) volume
163. A company is building a containerized application on premises and decides to move the application to AWS. The application will have thousands of users soon after it is deployed. The company is unsure how to manage the deployment of containers at scale. The company needs to deploy the containerized application in a highly available architecture that minimizes operational overhead.
     Which solution will meet these requirements?
     A. Store container images in an Amazon Elastic Container Registry (Amazon ECR) repository. Use an Amazon Elastic Container Service (Amazon ECS) cluster with the AWS Fargate launch type to run the containers. Use target tracking to scale automatically based on demand.
     B. Store container images in an Amazon Elastic Container Registry (Amazon ECR) repository. Use an Amazon Elastic Container Service (Amazon ECS) cluster with the Amazon EC2 launch type to run the containers. Use target tracking to scale automatically based on demand.
     C. Store container images in a repository that runs on an Amazon EC2 instance. Run the containers on EC2 instances that are spread across multiple Availability Zones. Monitor the average CPU utilization in Amazon CloudWatch. Launch new EC2 instances as needed.
     D. Create an Amazon EC2 Amazon Machine Image (AMI) that contains the container image. Launch EC2 instances in an Auto Scaling group across multiple Availability Zones. Use an Amazon CloudWatch alarm to scale out EC2 instances when the average CPU utilization threshold is breached.
164. A company has two applications: a sender application that sends messages with payloads to be processed and a processing application intended to receive the messages with payloads. The company wants to implement an AWS service to handle messages between the two applications. The sender application can send about 1,000 messages each hour. The messages may take up to 2 days to be processed: If the messages fail to process, they must be retained so that they do not impact the processing of any remaining messages.
     Which solution meets these requirements and is the MOST operationally ecient?
     A. Set up an Amazon EC2 instance running a Redis database. Congure both applications to use the instance. Store, process, and delete the messages, respectively.
     B. Use an Amazon Kinesis data stream to receive the messages from the sender application. Integrate the processing application with the Kinesis Client Library (KCL).
     C. Integrate the sender and processor applications with an Amazon Simple Queue Service (Amazon SQS) queue. Congure a dead-letter queue to collect the messages that failed to process.
     D. Subscribe the processing application to an Amazon Simple Notication Service (Amazon SNS) topic to receive notications to process. Integrate the sender application to write to the SNS topic.
165. A solutions architect must design a solution that uses Amazon CloudFront with an Amazon S3 origin to store a static website. The company’s security policy requires that all website trac be inspected by AWS WAF.
     How should the solutions architect comply with these requirements?
     A. Congure an S3 bucket policy to accept requests coming from the AWS WAF Amazon Resource Name (ARN) only.
     B. Congure Amazon CloudFront to forward all incoming requests to AWS WAF before requesting content from the S3 origin.
     C. Congure a security group that allows Amazon CloudFront IP addresses to access Amazon S3 only. Associate AWS WAF to CloudFront.
     D. Congure Amazon CloudFront and Amazon S3 to use an origin access identity (OAI) to restrict access to the S3 bucket. Enable AWS WAF on the distribution.
166. Organizers for a global event want to put daily reports online as static HTML pages. The pages are expected to generate millions of views from users around the world. The les are stored in an Amazon S3 bucket. A solutions architect has been asked to design an ecient and effective solution.
     Which action should the solutions architect take to accomplish this?
     A. Generate presigned URLs for the les.
     B. Use cross-Region replication to all Regions.
     C. Use the geoproximity feature of Amazon Route 53.
     D. Use Amazon CloudFront with the S3 bucket as its origin.
167. A company runs a production application on a eet of Amazon EC2 instances. The application reads the data from an Amazon SQS queue and processes the messages in parallel. The message volume is unpredictable and often has intermittent trac. This application should continually process messages without any downtime.
     Which solution meets these requirements MOST cost-effectively?
     A. Use Spot Instances exclusively to handle the maximum capacity required.
     B. Use Reserved Instances exclusively to handle the maximum capacity required.
     C. Use Reserved Instances for the baseline capacity and use Spot Instances to handle additional capacity.
     D. Use Reserved Instances for the baseline capacity and use On-Demand Instances to handle additional capacity.
168. A security team wants to limit access to specic services or actions in all of the team’s AWS accounts. All accounts belong to a large organization in AWS Organizations. The solution must be scalable and there must be a single point where permissions can be maintained.
     What should a solutions architect do to accomplish this?
     A. Create an ACL to provide access to the services or actions.
     B. Create a security group to allow accounts and attach it to user groups.
     C. Create cross-account roles in each account to deny access to the services or actions.
     D. Create a service control policy in the root organizational unit to deny access to the services or actions.
169. A company is concerned about the security of its public web application due to recent web attacks. The application uses an Application Load Balancer (ALB). A solutions architect must reduce the risk of DDoS attacks against the application.
     What should the solutions architect do to meet this requirement?
     A. Add an Amazon Inspector agent to the ALB.
     B. Congure Amazon Macie to prevent attacks.
     C. Enable AWS Shield Advanced to prevent attacks.
     D. Congure Amazon GuardDuty to monitor the ALB.
170. A company’s web application is running on Amazon EC2 instances behind an Application Load Balancer. The company recently changed its policy, which now requires the application to be accessed from one specic country only.
     Which conguration will meet this requirement?
     A. Congure the security group for the EC2 instances.
     B. Congure the security group on the Application Load Balancer.
     C. Congure AWS WAF on the Application Load Balancer in a VPC.
     D. Congure the network ACL for the subnet that contains the EC2 instances.
171. A company provides an API to its users that automates inquiries for tax computations based on item prices. The company experiences a larger number of inquiries during the holiday season only that cause slower response times. A solutions architect needs to design a solution that is scalable and elastic.
     What should the solutions architect do to accomplish this?
     A. Provide an API hosted on an Amazon EC2 instance. The EC2 instance performs the required computations when the API request is made.
     B. Design a REST API using Amazon API Gateway that accepts the item names. API Gateway passes item names to AWS Lambda for tax computations.
     C. Create an Application Load Balancer that has two Amazon EC2 instances behind it. The EC2 instances will compute the tax on the received item names.
     D. Design a REST API using Amazon API Gateway that connects with an API hosted on an Amazon EC2 instance. API Gateway accepts and passes the item names to the EC2 instance for tax computations.
172. A solutions architect is creating a new Amazon CloudFront distribution for an application. Some of the information submitted by users is sensitive. The application uses HTTPS but needs another layer of security. The sensitive information should be protected throughout the entire application stack, and access to the information should be restricted to certain applications.
     Which action should the solutions architect take?
     A. Congure a CloudFront signed URL.
     B. Congure a CloudFront signed cookie.
     C. Congure a CloudFront eld-level encryption prole.
     D. Congure CloudFront and set the Origin Protocol Policy setting to HTTPS Only for the Viewer Protocol Policy.
173. A gaming company hosts a browser-based application on AWS. The users of the application consume a large number of videos and images that are stored in Amazon S3. This content is the same for all users.
     The application has increased in popularity, and millions of users worldwide accessing these media les. The company wants to provide the les to the users while reducing the load on the origin.
     Which solution meets these requirements MOST cost-effectively?
     A. Deploy an AWS Global Accelerator accelerator in front of the web servers.
     B. Deploy an Amazon CloudFront web distribution in front of the S3 bucket.
     C. Deploy an Amazon ElastiCache for Redis instance in front of the web servers.
     D. Deploy an Amazon ElastiCache for Memcached instance in front of the web servers.
174. A company has a multi-tier application that runs six front-end web servers in an Amazon EC2 Auto Scaling group in a single Availability Zone behind an Application Load Balancer (ALB). A solutions architect needs to modify the infrastructure to be highly available without modifying the application.
     Which architecture should the solutions architect choose that provides high availability?
     A. Create an Auto Scaling group that uses three instances across each of two Regions.
     B. Modify the Auto Scaling group to use three instances across each of two Availability Zones.
     C. Create an Auto Scaling template that can be used to quickly create more instances in another Region.
     D. Change the ALB in front of the Amazon EC2 instances in a round-robin conguration to balance trac to the web tier.
175. An ecommerce company has an order-processing application that uses Amazon API Gateway and an AWS Lambda function. The application stores data in an Amazon Aurora PostgreSQL database. During a recent sales event, a sudden surge in customer orders occurred. Some customers experienced timeouts, and the application did not process the orders of those customers.
     A solutions architect determined that the CPU utilization and memory utilization were high on the database because of a large number of open connections. The solutions architect needs to prevent the timeout errors while making the least possible changes to the application.
     Which solution will meet these requirements?
     A. Congure provisioned concurrency for the Lambda function. Modify the database to be a global database in multiple AWS Regions.
     B. Use Amazon RDS Proxy to create a proxy for the database. Modify the Lambda function to use the RDS Proxy endpoint instead of the database endpoint.
     C. Create a read replica for the database in a different AWS Region. Use query string parameters in API Gateway to route trac to the read replica.
     D. Migrate the data from Aurora PostgreSQL to Amazon DynamoDB by using AWS Database Migration Service (AWS DMS). Modify the Lambda function to use the DynamoDB table.
176. An application runs on Amazon EC2 instances in private subnets. The application needs to access an Amazon DynamoDB table. What is the MOST secure way to access the table while ensuring that the trac does not leave the AWS network?
     A. Use a VPC endpoint for DynamoDB.
     B. Use a NAT gateway in a public subnet.
     C. Use a NAT instance in a private subnet.
     D. Use the internet gateway attached to the VPC.
177. An entertainment company is using Amazon DynamoDB to store media metadata. The application is read intensive and experiencing delays. The company does not have staff to handle additional operational overhead and needs to improve the performance eciency of DynamoDB without reconguring the application.
     What should a solutions architect recommend to meet this requirement?
     A. Use Amazon ElastiCache for Redis.
     B. Use Amazon DynamoDB Accelerator (DAX).
     C. Replicate data by using DynamoDB global tables.
     D. Use Amazon ElastiCache for Memcached with Auto Discovery enabled.
178. A company’s infrastructure consists of Amazon EC2 instances and an Amazon RDS DB instance in a single AWS Region. The company wants to back up its data in a separate Region.
     Which solution will meet these requirements with the LEAST operational overhead?
     A. Use AWS Backup to copy EC2 backups and RDS backups to the separate Region.
     B. Use Amazon Data Lifecycle Manager (Amazon DLM) to copy EC2 backups and RDS backups to the separate Region.
     C. Create Amazon Machine Images (AMIs) of the EC2 instances. Copy the AMIs to the separate Region. Create a read replica for the RDS DB instance in the separate Region.
     D. Create Amazon Elastic Block Store (Amazon EBS) snapshots. Copy the EBS snapshots to the separate Region. Create RDS snapshots. Export the RDS snapshots to Amazon S3. Congure S3 Cross-Region Replication (CRR) to the separate Region.
179. A solutions architect needs to securely store a database user name and password that an application uses to access an Amazon RDS DB instance. The application that accesses the database runs on an Amazon EC2 instance. The solutions architect wants to create a secure parameter in AWS Systems Manager Parameter Store.
     What should the solutions architect do to meet this requirement?
     A. Create an IAM role that has read access to the Parameter Store parameter. Allow Decrypt access to an AWS Key Management Service (AWS KMS) key that is used to encrypt the parameter. Assign this IAM role to the EC2 instance.
     B. Create an IAM policy that allows read access to the Parameter Store parameter. Allow Decrypt access to an AWS Key Management Service (AWS KMS) key that is used to encrypt the parameter. Assign this IAM policy to the EC2 instance.
     C. Create an IAM trust relationship between the Parameter Store parameter and the EC2 instance. Specify Amazon RDS as a principal in the trust policy.
     D. Create an IAM trust relationship between the DB instance and the EC2 instance. Specify Systems Manager as a principal in the trust policy.
180. A company is designing a cloud communications platform that is driven by APIs. The application is hosted on Amazon EC2 instances behind a Network Load Balancer (NLB). The company uses Amazon API Gateway to provide external users with access to the application through APIs. The company wants to protect the platform against web exploits like SQL injection and also wants to detect and mitigate large, sophisticated DDoS attacks.
     Which combination of solutions provides the MOST protection? (Choose two.)
     A. Use AWS WAF to protect the NLB.
     B. Use AWS Shield Advanced with the NLB.
     C. Use AWS WAF to protect Amazon API Gateway.
     D. Use Amazon GuardDuty with AWS Shield Standard
     E. Use AWS Shield Standard with Amazon API Gateway.
181. A company has a legacy data processing application that runs on Amazon EC2 instances. Data is processed sequentially, but the order of results does not matter. The application uses a monolithic architecture. The only way that the company can scale the application to meet increased demand is to increase the size of the instances.
     The company’s developers have decided to rewrite the application to use a microservices architecture on Amazon Elastic Container Service (Amazon ECS).
     What should a solutions architect recommend for communication between the microservices?
     A. Create an Amazon Simple Queue Service (Amazon SQS) queue. Add code to the data producers, and send data to the queue. Add code to the data consumers to process data from the queue.
     B. Create an Amazon Simple Notication Service (Amazon SNS) topic. Add code to the data producers, and publish notications to the topic. Add code to the data consumers to subscribe to the topic.
     C. Create an AWS Lambda function to pass messages. Add code to the data producers to call the Lambda function with a data object. Add code to the data consumers to receive a data object that is passed from the Lambda function.
     D. Create an Amazon DynamoDB table. Enable DynamoDB Streams. Add code to the data producers to insert data into the table. Add code to the data consumers to use the DynamoDB Streams API to detect new table entries and retrieve the data.
182. A company wants to migrate its MySQL database from on premises to AWS. The company recently experienced a database outage that signicantly impacted the business. To ensure this does not happen again, the company wants a reliable database solution on AWS that minimizes data loss and stores every transaction on at least two nodes.
     Which solution meets these requirements?
     A. Create an Amazon RDS DB instance with synchronous replication to three nodes in three Availability Zones.
     B. Create an Amazon RDS MySQL DB instance with Multi-AZ functionality enabled to synchronously replicate the data.
     C. Create an Amazon RDS MySQL DB instance and then create a read replica in a separate AWS Region that synchronously replicates the data.
     D. Create an Amazon EC2 instance with a MySQL engine installed that triggers an AWS Lambda function to synchronously replicate the data to an Amazon RDS MySQL DB instance.
183. A company is building a new dynamic ordering website. The company wants to minimize server maintenance and patching. The website must be highly available and must scale read and write capacity as quickly as possible to meet changes in user demand.
     Which solution will meet these requirements?
     A. Host static content in Amazon S3. Host dynamic content by using Amazon API Gateway and AWS Lambda. Use Amazon DynamoDB with on-demand capacity for the database. Congure Amazon CloudFront to deliver the website content.
     B. Host static content in Amazon S3. Host dynamic content by using Amazon API Gateway and AWS Lambda. Use Amazon Aurora with Aurora Auto Scaling for the database. Congure Amazon CloudFront to deliver the website content.
     C. Host all the website content on Amazon EC2 instances. Create an Auto Scaling group to scale the EC2 instances. Use an Application Load Balancer to distribute trac. Use Amazon DynamoDB with provisioned write capacity for the database.
     D. Host all the website content on Amazon EC2 instances. Create an Auto Scaling group to scale the EC2 instances. Use an Application Load Balancer to distribute trac. Use Amazon Aurora with Aurora Auto Scaling for the database.
184. A company has an AWS account used for software engineering. The AWS account has access to the company’s on-premises data center through a pair of AWS Direct Connect connections. All non-VPC trac routes to the virtual private gateway.
     A development team recently created an AWS Lambda function through the console. The development team needs to allow the function to access a database that runs in a private subnet in the company’s data center.
     Which solution will meet these requirements?
     A. Congure the Lambda function to run in the VPC with the appropriate security group.
     B. Set up a VPN connection from AWS to the data center. Route the trac from the Lambda function through the VPN.
     C. Update the route tables in the VPC to allow the Lambda function to access the on-premises data center through Direct Connect.
     D. Create an Elastic IP address. Congure the Lambda function to send trac through the Elastic IP address without an elastic network interface.
185. A company runs an application using Amazon ECS. The application creates resized versions of an original image and then makes Amazon S3 API calls to store the resized images in Amazon S3.
     How can a solutions architect ensure that the application has permission to access Amazon S3?
     A. Update the S3 role in AWS IAM to allow read/write access from Amazon ECS, and then relaunch the container.
     B. Create an IAM role with S3 permissions, and then specify that role as the taskRoleArn in the task denition.
     C. Create a security group that allows access from Amazon ECS to Amazon S3, and update the launch conguration used by the ECS cluster.
     D. Create an IAM user with S3 permissions, and then relaunch the Amazon EC2 instances for the ECS cluster while logged in as this account.  
186. A company has a Windows-based application that must be migrated to AWS. The application requires the use of a shared Windows le system attached to multiple Amazon EC2 Windows instances that are deployed across multiple Availability Zone:
     What should a solutions architect do to meet this requirement?
     A. Congure AWS Storage Gateway in volume gateway mode. Mount the volume to each Windows instance.
     B. Congure Amazon FSx for Windows File Server. Mount the Amazon FSx le system to each Windows instance.
     C. Congure a le system by using Amazon Elastic File System (Amazon EFS). Mount the EFS le system to each Windows instance.
     D. Congure an Amazon Elastic Block Store (Amazon EBS) volume with the required size. Attach each EC2 instance to the volume. Mount the le system within the volume to each Windows instance.
187. A company is developing an ecommerce application that will consist of a load-balanced front end, a container-based application, and a relational database. A solutions architect needs to create a highly available solution that operates with as little manual intervention as possible.
     Which solutions meet these requirements? (Choose two.)
     A. Create an Amazon RDS DB instance in Multi-AZ mode.
     B. Create an Amazon RDS DB instance and one or more replicas in another Availability Zone.
     C. Create an Amazon EC2 instance-based Docker cluster to handle the dynamic application load.
     D. Create an Amazon Elastic Container Service (Amazon ECS) cluster with a Fargate launch type to handle the dynamic application load.
     E. Create an Amazon Elastic Container Service (Amazon ECS) cluster with an Amazon EC2 launch type to handle the dynamic application load.
188. A company uses Amazon S3 as its data lake. The company has a new partner that must use SFTP to upload data les. A solutions architect needs to implement a highly available SFTP solution that minimizes operational overhead.
     Which solution will meet these requirements?
     A. Use AWS Transfer Family to congure an SFTP-enabled server with a publicly accessible endpoint. Choose the S3 data lake as the destination.
     B. Use Amazon S3 File Gateway as an SFTP server. Expose the S3 File Gateway endpoint URL to the new partner. Share the S3 File Gateway endpoint with the new partner.
     C. Launch an Amazon EC2 instance in a private subnet in a VPInstruct the new partner to upload les to the EC2 instance by using a VPN. Run a cron job script, on the EC2 instance to upload les to the S3 data lake.
     D. Launch Amazon EC2 instances in a private subnet in a VPC. Place a Network Load Balancer (NLB) in front of the EC2 instances. Create an SFTP listener port for the NLB. Share the NLB hostname with the new partner. Run a cron job script on the EC2 instances to upload les to the S3 data lake.
189. A company needs to store contract documents. A contract lasts for 5 years. During the 5-year period, the company must ensure that the documents cannot be overwritten or deleted. The company needs to encrypt the documents at rest and rotate the encryption keys automatically every year.
     Which combination of steps should a solutions architect take to meet these requirements with the LEAST operational overhead? (Choose two.)
     A. Store the documents in Amazon S3. Use S3 Object Lock in governance mode.
     B. Store the documents in Amazon S3. Use S3 Object Lock in compliance mode.
     C. Use server-side encryption with Amazon S3 managed encryption keys (SSE-S3). Congure key rotation.
     D. Use server-side encryption with AWS Key Management Service (AWS KMS) customer managed keys. Congure key rotation.
     E. Use server-side encryption with AWS Key Management Service (AWS KMS) customer provided (imported) keys. Congure key rotation.
190. A company has a web application that is based on Java and PHP. The company plans to move the application from on premises to AWS. The company needs the ability to test new site features frequently. The company also needs a highly available and managed solution that requires minimum operational overhead.
     Which solution will meet these requirements?
     A. Create an Amazon S3 bucket. Enable static web hosting on the S3 bucket. Upload the static content to the S3 bucket. Use AWS Lambda to process all dynamic content.
     B. Deploy the web application to an AWS Elastic Beanstalk environment. Use URL swapping to switch between multiple Elastic Beanstalk environments for feature testing.
     C. Deploy the web application to Amazon EC2 instances that are congured with Java and PHP. Use Auto Scaling groups and an Application Load Balancer to manage the website’s availability.
     D. Containerize the web application. Deploy the web application to Amazon EC2 instances. Use the AWS Load Balancer Controller to dynamically route trac between containers that contain the new site features for testing
191. A company has an ordering application that stores customer information in Amazon RDS for MySQL. During regular business hours, employees run one-time queries for reporting purposes. Timeouts are occurring during order processing because the reporting queries are taking a long time to run. The company needs to eliminate the timeouts without preventing employees from performing queries.
     What should a solutions architect do to meet these requirements?
     A. Create a read replica. Move reporting queries to the read replica.
     B. Create a read replica. Distribute the ordering application to the primary DB instance and the read replica.
     C. Migrate the ordering application to Amazon DynamoDB with on-demand capacity.
     D. Schedule the reporting queries for non-peak hours.
192. A hospital wants to create digital copies for its large collection of historical written records. The hospital will continue to add hundreds of new documents each day. The hospital’s data team will scan the documents and will upload the documents to the AWS Cloud.
     A solutions architect must implement a solution to analyze the documents, extract the medical information, and store the documents so that an application can run SQL queries on the data. The solution must maximize scalability and operational eciency.
     Which combination of steps should the solutions architect take to meet these requirements? (Choose two.)
     A. Write the document information to an Amazon EC2 instance that runs a MySQL database.
     B. Write the document information to an Amazon S3 bucket. Use Amazon Athena to query the data.
     C. Create an Auto Scaling group of Amazon EC2 instances to run a custom application that processes the scanned les and extracts the medical information.
     D. Create an AWS Lambda function that runs when new documents are uploaded. Use Amazon Rekognition to convert the documents to raw text. Use Amazon Transcribe Medical to detect and extract relevant medical information from the text.
     E. Create an AWS Lambda function that runs when new documents are uploaded. Use Amazon Textract to convert the documents to raw text. Use Amazon Comprehend Medical to detect and extract relevant medical information from the text.
193. A company is running a batch application on Amazon EC2 instances. The application consists of a backend with multiple Amazon RDS databases. The application is causing a high number of reads on the databases. A solutions architect must reduce the number of database reads while ensuring high availability.
     What should the solutions architect do to meet this requirement?
     A. Add Amazon RDS read replicas.
     B. Use Amazon ElastiCache for Redis.
     C. Use Amazon Route 53 DNS caching
     D. Use Amazon ElastiCache for Memcached.
194. A company needs to run a critical application on AWS. The company needs to use Amazon EC2 for the application’s database. The database must be highly available and must fail over automatically if a disruptive event occurs.
     Which solution will meet these requirements?
     A. Launch two EC2 instances, each in a different Availability Zone in the same AWS Region. Install the database on both EC2 instances. Congure the EC2 instances as a cluster. Set up database replication.
     B. Launch an EC2 instance in an Availability Zone. Install the database on the EC2 instance. Use an Amazon Machine Image (AMI) to back up the data. Use AWS CloudFormation to automate provisioning of the EC2 instance if a disruptive event occurs.
     C. Launch two EC2 instances, each in a different AWS Region. Install the database on both EC2 instances. Set up database replication. Fail over the database to a second Region.
     D. Launch an EC2 instance in an Availability Zone. Install the database on the EC2 instance. Use an Amazon Machine Image (AMI) to back up the data. Use EC2 automatic recovery to recover the instance if a disruptive event occurs.
195. A company’s order system sends requests from clients to Amazon EC2 instances. The EC2 instances process the orders and then store the orders in a database on Amazon RDS. Users report that they must reprocess orders when the system fails. The company wants a resilient solution that can process orders automatically if a system outage occurs.
     What should a solutions architect do to meet these requirements?
     A. Move the EC2 instances into an Auto Scaling group. Create an Amazon EventBridge (Amazon CloudWatch Events) rule to target an Amazon Elastic Container Service (Amazon ECS) task.
     B. Move the EC2 instances into an Auto Scaling group behind an Application Load Balancer (ALB). Update the order system to send messages to the ALB endpoint.
     C. Move the EC2 instances into an Auto Scaling group. Congure the order system to send messages to an Amazon Simple Queue Service (Amazon SQS) queue. Congure the EC2 instances to consume messages from the queue.
     D. Create an Amazon Simple Notication Service (Amazon SNS) topic. Create an AWS Lambda function, and subscribe the function to the SNS topic. Congure the order system to send messages to the SNS topic. Send a command to the EC2 instances to process the messages by using AWS Systems Manager Run Command.
196. A company runs an application on a large eet of Amazon EC2 instances. The application reads and writes entries into an Amazon DynamoDB table. The size of the DynamoDB table continuously grows, but the application needs only data from the last 30 days. The company needs a solution that minimizes cost and development effort.
     Which solution meets these requirements?
     A. Use an AWS CloudFormation template to deploy the complete solution. Redeploy the CloudFormation stack every 30 days, and delete the original stack.
     B. Use an EC2 instance that runs a monitoring application from AWS Marketplace. Congure the monitoring application to use Amazon DynamoDB Streams to store the timestamp when a new item is created in the table. Use a script that runs on the EC2 instance to delete items that have a timestamp that is older than 30 days.
     C. Congure Amazon DynamoDB Streams to invoke an AWS Lambda function when a new item is created in the table. Congure the Lambda function to delete items in the table that are older than 30 days.
     D. Extend the application to add an attribute that has a value of the current timestamp plus 30 days to each new item that is created in the table. Congure DynamoDB to use the attribute as the TTL attribute.
197. A company has a Microsoft .NET application that runs on an on-premises Windows Server. The application stores data by using an Oracle Database Standard Edition server. The company is planning a migration to AWS and wants to minimize development changes while moving the application. The AWS application environment should be highly available.
     Which combination of actions should the company take to meet these requirements? (Choose two.)
     A. Refactor the application as serverless with AWS Lambda functions running .NET Core.
     B. Rehost the application in AWS Elastic Beanstalk with the .NET platform in a Multi-AZ deployment.
     C. Replatform the application to run on Amazon EC2 with the Amazon Linux Amazon Machine Image (AMI).
     D. Use AWS Database Migration Service (AWS DMS) to migrate from the Oracle database to Amazon DynamoDB in a Multi-AZ deployment.
     E. Use AWS Database Migration Service (AWS DMS) to migrate from the Oracle database to Oracle on Amazon RDS in a Multi-AZ deployment.
198. A company runs a containerized application on a Kubernetes cluster in an on-premises data center. The company is using a MongoDB database for data storage. The company wants to migrate some of these environments to AWS, but no code changes or deployment method changes are possible at this time. The company needs a solution that minimizes operational overhead.
     Which solution meets these requirements?
     A. Use Amazon Elastic Container Service (Amazon ECS) with Amazon EC2 worker nodes for compute and MongoDB on EC2 for data storage.
     B. Use Amazon Elastic Container Service (Amazon ECS) with AWS Fargate for compute and Amazon DynamoDB for data storage
     C. Use Amazon Elastic Kubernetes Service (Amazon EKS) with Amazon EC2 worker nodes for compute and Amazon DynamoDB for data storage.
     D. Use Amazon Elastic Kubernetes Service (Amazon EKS) with AWS Fargate for compute and Amazon DocumentDB (with MongoDB compatibility) for data storage.
199. A telemarketing company is designing its customer call center functionality on AWS. The company needs a solution that provides multiple speaker recognition and generates transcript les. The company wants to query the transcript les to analyze the business patterns. The transcript les must be stored for 7 years for auditing purposes.
     Which solution will meet these requirements?
     A. Use Amazon Rekognition for multiple speaker recognition. Store the transcript les in Amazon S3. Use machine learning models for transcript le analysis.
     B. Use Amazon Transcribe for multiple speaker recognition. Use Amazon Athena for transcript le analysis.
     C. Use Amazon Translate for multiple speaker recognition. Store the transcript les in Amazon Redshift. Use SQL queries for transcript le analysis.
     D. Use Amazon Rekognition for multiple speaker recognition. Store the transcript les in Amazon S3. Use Amazon Textract for transcript le analysis.
200. A company hosts its application on AWS. The company uses Amazon Cognito to manage users. When users log in to the application, the application fetches required data from Amazon DynamoDB by using a REST API that is hosted in Amazon API Gateway. The company wants an AWS managed solution that will control access to the REST API to reduce development efforts.
     Which solution will meet these requirements with the LEAST operational overhead?
     A. Congure an AWS Lambda function to be an authorizer in API Gateway to validate which user made the request.
     B. For each user, create and assign an API key that must be sent with each request. Validate the key by using an AWS Lambda function.
     C. Send the user’s email address in the header with every request. Invoke an AWS Lambda function to validate that the user with that email address has proper access.
     D. Congure an Amazon Cognito user pool authorizer in API Gateway to allow Amazon Cognito to validate each request. 
201. A company is developing a marketing communications service that targets mobile app users. The company needs to send conrmation messages with Short Message Service (SMS) to its users. The users must be able to reply to the SMS messages. The company must store the responses for a year for analysis.
     What should a solutions architect do to meet these requirements?
     A. Create an Amazon Connect contact ow to send the SMS messages. Use AWS Lambda to process the responses.
     B. Build an Amazon Pinpoint journey. Congure Amazon Pinpoint to send events to an Amazon Kinesis data stream for analysis and archiving.
     C. Use Amazon Simple Queue Service (Amazon SQS) to distribute the SMS messages. Use AWS Lambda to process the responses.
     D. Create an Amazon Simple Notication Service (Amazon SNS) FIFO topic. Subscribe an Amazon Kinesis data stream to the SNS topic for analysis and archiving.
202. A company is planning to move its data to an Amazon S3 bucket. The data must be encrypted when it is stored in the S3 bucket. Additionally, the encryption key must be automatically rotated every year.
     Which solution will meet these requirements with the LEAST operational overhead?
     A. Move the data to the S3 bucket. Use server-side encryption with Amazon S3 managed encryption keys (SSE-S3). Use the built-in key rotation behavior of SSE-S3 encryption keys.
     B. Create an AWS Key Management Service (AWS KMS) customer managed key. Enable automatic key rotation. Set the S3 bucket’s default encryption behavior to use the customer managed KMS key. Move the data to the S3 bucket.
     C. Create an AWS Key Management Service (AWS KMS) customer managed key. Set the S3 bucket’s default encryption behavior to use the customer managed KMS key. Move the data to the S3 bucket. Manually rotate the KMS key every year.
     D. Encrypt the data with customer key material before moving the data to the S3 bucket. Create an AWS Key Management Service (AWS KMS) key without key material. Import the customer key material into the KMS key. Enable automatic key rotation.
203. The customers of a nance company request appointments with nancial advisors by sending text messages. A web application that runs on Amazon EC2 instances accepts the appointment requests. The text messages are published to an Amazon Simple Queue Service (Amazon SQS) queue through the web application. Another application that runs on EC2 instances then sends meeting invitations and meeting conrmation email messages to the customers. After successful scheduling, this application stores the meeting information in an Amazon DynamoDB database.
     As the company expands, customers report that their meeting invitations are taking longer to arrive. What should a solutions architect recommend to resolve this issue?
     A. Add a DynamoDB Accelerator (DAX) cluster in front of the DynamoDB database.
     B. Add an Amazon API Gateway API in front of the web application that accepts the appointment requests.
     C. Add an Amazon CloudFront distribution. Set the origin as the web application that accepts the appointment requests.
     D. Add an Auto Scaling group for the application that sends meeting invitations. Congure the Auto Scaling group to scale based on the depth of the SQS queue.
204. An online retail company has more than 50 million active customers and receives more than 25,000 orders each day. The company collects purchase data for customers and stores this data in Amazon S3. Additional customer data is stored in Amazon RDS.
     The company wants to make all the data available to various teams so that the teams can perform analytics. The solution must provide the ability to manage ne-grained permissions for the data and must minimize operational overhead.
     Which solution will meet these requirements?
     A. Migrate the purchase data to write directly to Amazon RDS. Use RDS access controls to limit access.
     B. Schedule an AWS Lambda function to periodically copy data from Amazon RDS to Amazon S3. Create an AWS Glue crawler. Use Amazon Athena to query the data. Use S3 policies to limit access.
     C. Create a data lake by using AWS Lake Formation. Create an AWS Glue JDBC connection to Amazon RDS. Register the S3 bucket in Lake Formation. Use Lake Formation access controls to limit access.
     D. Create an Amazon Redshift cluster. Schedule an AWS Lambda function to periodically copy data from Amazon S3 and Amazon RDS to Amazon Redshift. Use Amazon Redshift access controls to limit access.
205. A company hosts a marketing website in an on-premises data center. The website consists of static documents and runs on a single server. An administrator updates the website content infrequently and uses an SFTP client to upload new documents.
     The company decides to host its website on AWS and to use Amazon CloudFront. The company’s solutions architect creates a CloudFront distribution. The solutions architect must design the most cost-effective and resilient architecture for website hosting to serve as the CloudFront origin.
     Which solution will meet these requirements?
     A. Create a virtual server by using Amazon Lightsail. Congure the web server in the Lightsail instance. Upload website content by using an SFTP client.
     B. Create an AWS Auto Scaling group for Amazon EC2 instances. Use an Application Load Balancer. Upload website content by using an SFTP client.
     C. Create a private Amazon S3 bucket. Use an S3 bucket policy to allow access from a CloudFront origin access identity (OAI). Upload website content by using the AWS CLI.
     D. Create a public Amazon S3 bucket. Congure AWS Transfer for SFTP. Congure the S3 bucket for website hosting. Upload website content by using the SFTP client.
206. A company wants to manage Amazon Machine Images (AMIs). The company currently copies AMIs to the same AWS Region where the AMIs were created. The company needs to design an application that captures AWS API calls and sends alerts whenever the Amazon EC2 CreateImage API operation is called within the company’s account.
     Which solution will meet these requirements with the LEAST operational overhead?
     A. Create an AWS Lambda function to query AWS CloudTrail logs and to send an alert when a CreateImage API call is detected.
     B. Congure AWS CloudTrail with an Amazon Simple Notication Service (Amazon SNS) notication that occurs when updated logs are sent to Amazon S3. Use Amazon Athena to create a new table and to query on CreateImage when an API call is detected.
     C. Create an Amazon EventBridge (Amazon CloudWatch Events) rule for the CreateImage API call. Congure the target as an Amazon Simple Notication Service (Amazon SNS) topic to send an alert when a CreateImage API call is detected.
     D. Congure an Amazon Simple Queue Service (Amazon SQS) FIFO queue as a target for AWS CloudTrail logs. Create an AWS Lambda function to send an alert to an Amazon Simple Notication Service (Amazon SNS) topic when a CreateImage API call is detected.
207. A company owns an asynchronous API that is used to ingest user requests and, based on the request type, dispatch requests to the appropriate microservice for processing. The company is using Amazon API Gateway to deploy the API front end, and an AWS Lambda function that invokes Amazon DynamoDB to store user requests before dispatching them to the processing microservices.
     The company provisioned as much DynamoDB throughput as its budget allows, but the company is still experiencing availability issues and is losing user requests.
     What should a solutions architect do to address this issue without impacting existing users?
     A. Add throttling on the API Gateway with server-side throttling limits.
     B. Use DynamoDB Accelerator (DAX) and Lambda to buffer writes to DynamoDB.
     C. Create a secondary index in DynamoDB for the table with the user requests.
     D. Use the Amazon Simple Queue Service (Amazon SQS) queue and Lambda to buffer writes to DynamoDB.
208. A company needs to move data from an Amazon EC2 instance to an Amazon S3 bucket. The company must ensure that no API calls and no data are routed through public internet routes. Only the EC2 instance can have access to upload data to the S3 bucket.
     Which solution will meet these requirements?
     A. Create an interface VPC endpoint for Amazon S3 in the subnet where the EC2 instance is located. Attach a resource policy to the S3 bucket to only allow the EC2 instance’s IAM role for access.
     B. Create a gateway VPC endpoint for Amazon S3 in the Availability Zone where the EC2 instance is located. Attach appropriate security groups to the endpoint. Attach a resource policy to the S3 bucket to only allow the EC2 instance’s IAM role for access.
     C. Run the nslookup tool from inside the EC2 instance to obtain the private IP address of the S3 bucket’s service API endpoint. Create a route in the VPC route table to provide the EC2 instance with access to the S3 bucket. Attach a resource policy to the S3 bucket to only allow the EC2 instance’s IAM role for access.
     D. Use the AWS provided, publicly available ip-ranges.json le to obtain the private IP address of the S3 bucket’s service API endpoint. Create a route in the VPC route table to provide the EC2 instance with access to the S3 bucket. Attach a resource policy to the S3 bucket to only allow the EC2 instance’s IAM role for access.
209. A solutions architect is designing the architecture of a new application being deployed to the AWS Cloud. The application will run on Amazon EC2 On-Demand Instances and will automatically scale across multiple Availability Zones. The EC2 instances will scale up and down frequently throughout the day. An Application Load Balancer (ALB) will handle the load distribution. The architecture needs to support distributed session data management. The company is willing to make changes to code if needed.
     What should the solutions architect do to ensure that the architecture supports distributed session data management?
     A. Use Amazon ElastiCache to manage and store session data.
     B. Use session anity (sticky sessions) of the ALB to manage session data.
     C. Use Session Manager from AWS Systems Manager to manage the session.
     D. Use the GetSessionToken API operation in AWS Security Token Service (AWS STS) to manage the session
210. A company offers a food delivery service that is growing rapidly. Because of the growth, the company’s order processing system is experiencing scaling problems during peak trac hours. The current architecture includes the following:
     • A group of Amazon EC2 instances that run in an Amazon EC2 Auto Scaling group to collect orders from the application • Another group of EC2 instances that run in an Amazon EC2 Auto Scaling group to fulll orders
     The order collection process occurs quickly, but the order fulllment process can take longer. Data must not be lost because of a scaling event.
     A solutions architect must ensure that the order collection process and the order fulllment process can both scale properly during peak trac hours. The solution must optimize utilization of the company’s AWS resources.
     Which solution meets these requirements?
     A. Use Amazon CloudWatch metrics to monitor the CPU of each instance in the Auto Scaling groups. Congure each Auto Scaling group’s minimum capacity according to peak workload values.
     B. Use Amazon CloudWatch metrics to monitor the CPU of each instance in the Auto Scaling groups. Congure a CloudWatch alarm to invoke an Amazon Simple Notication Service (Amazon SNS) topic that creates additional Auto Scaling groups on demand.
     C. Provision two Amazon Simple Queue Service (Amazon SQS) queues: one for order collection and another for order fulllment. Congure the EC2 instances to poll their respective queue. Scale the Auto Scaling groups based on notications that the queues send.
     D. Provision two Amazon Simple Queue Service (Amazon SQS) queues: one for order collection and another for order fulllment. Congure the EC2 instances to poll their respective queue. Create a metric based on a backlog per instance calculation. Scale the Auto Scaling groups based on this metric.
211. A company hosts multiple production applications. One of the applications consists of resources from Amazon EC2, AWS Lambda, Amazon RDS, Amazon Simple Notication Service (Amazon SNS), and Amazon Simple Queue Service (Amazon SQS) across multiple AWS Regions. All company resources are tagged with a tag name of “application” and a value that corresponds to each application. A solutions architect must provide the quickest solution for identifying all of the tagged components.
     Which solution meets these requirements?
     A. Use AWS CloudTrail to generate a list of resources with the application tag.
     B. Use the AWS CLI to query each service across all Regions to report the tagged components.
     C. Run a query in Amazon CloudWatch Logs Insights to report on the components with the application tag.
     D. Run a query with the AWS Resource Groups Tag Editor to report on the resources globally with the application tag.
212. A company needs to export its database once a day to Amazon S3 for other teams to access. The exported object size varies between 2 GB and 5 GB. The S3 access pattern for the data is variable and changes rapidly. The data must be immediately available and must remain accessible for up to 3 months. The company needs the most cost-effective solution that will not increase retrieval time.
     Which S3 storage class should the company use to meet these requirements?
     A. S3 Intelligent-Tiering
     B. S3 Glacier Instant Retrieval
     C. S3 Standard
     D. S3 Standard-Infrequent Access (S3 Standard-IA)
213. A company is developing a new mobile app. The company must implement proper trac ltering to protect its Application Load Balancer (ALB) against common application-level attacks, such as cross-site scripting or SQL injection. The company has minimal infrastructure and operational staff. The company needs to reduce its share of the responsibility in managing, updating, and securing servers for its AWS environment.
     What should a solutions architect recommend to meet these requirements?
     A. Congure AWS WAF rules and associate them with the ALB.
     B. Deploy the application using Amazon S3 with public hosting enabled.
     C. Deploy AWS Shield Advanced and add the ALB as a protected resource.
     D. Create a new ALB that directs trac to an Amazon EC2 instance running a third-party rewall, which then passes the trac to the current ALB.
214. A company’s reporting system delivers hundreds of .csv les to an Amazon S3 bucket each day. The company must convert these les to Apache Parquet format and must store the les in a transformed data bucket.
     Which solution will meet these requirements with the LEAST development effort?
     A. Create an Amazon EMR cluster with Apache Spark installed. Write a Spark application to transform the data. Use EMR File System (EMRFS) to write les to the transformed data bucket.
     B. Create an AWS Glue crawler to discover the data. Create an AWS Glue extract, transform, and load (ETL) job to transform the data. Specify the transformed data bucket in the output step.
     C. Use AWS Batch to create a job denition with Bash syntax to transform the data and output the data to the transformed data bucket. Use the job denition to submit a job. Specify an array job as the job type.
     D. Create an AWS Lambda function to transform the data and output the data to the transformed data bucket. Congure an event notication for the S3 bucket. Specify the Lambda function as the destination for the event notication.
215. A company has 700 TB of backup data stored in network attached storage (NAS) in its data center. This backup data need to be accessible for infrequent regulatory requests and must be retained 7 years. The company has decided to migrate this backup data from its data center to AWS. The migration must be complete within 1 month. The company has 500 Mbps of dedicated bandwidth on its public internet connection available for data transfer.
     What should a solutions architect do to migrate and store the data at the LOWEST cost?
     A. Order AWS Snowball devices to transfer the data. Use a lifecycle policy to transition the les to Amazon S3 Glacier Deep Archive.
     B. Deploy a VPN connection between the data center and Amazon VPC. Use the AWS CLI to copy the data from on premises to Amazon S3 Glacier.
     C. Provision a 500 Mbps AWS Direct Connect connection and transfer the data to Amazon S3. Use a lifecycle policy to transition the les to Amazon S3 Glacier Deep Archive.
     D. Use AWS DataSync to transfer the data and deploy a DataSync agent on premises. Use the DataSync task to copy les from the on- premises NAS storage to Amazon S3 Glacier.
216. A company has a serverless website with millions of objects in an Amazon S3 bucket. The company uses the S3 bucket as the origin for an Amazon CloudFront distribution. The company did not set encryption on the S3 bucket before the objects were loaded. A solutions architect needs to enable encryption for all existing objects and for all objects that are added to the S3 bucket in the future.
     Which solution will meet these requirements with the LEAST amount of effort?
     A. Create a new S3 bucket. Turn on the default encryption settings for the new S3 bucket. Download all existing objects to temporary local storage. Upload the objects to the new S3 bucket.
     B. Turn on the default encryption settings for the S3 bucket. Use the S3 Inventory feature to create a .csv le that lists the unencrypted objects. Run an S3 Batch Operations job that uses the copy command to encrypt those objects.
     C. Create a new encryption key by using AWS Key Management Service (AWS KMS). Change the settings on the S3 bucket to use server- side encryption with AWS KMS managed encryption keys (SSE-KMS). Turn on versioning for the S3 bucket.
     D. Navigate to Amazon S3 in the AWS Management Console. Browse the S3 bucket’s objects. Sort by the encryption eld. Select each unencrypted object. Use the Modify button to apply default encryption settings to every unencrypted object in the S3 bucket.
217. A company runs a global web application on Amazon EC2 instances behind an Application Load Balancer. The application stores data in Amazon Aurora. The company needs to create a disaster recovery solution and can tolerate up to 30 minutes of downtime and potential data loss. The solution does not need to handle the load when the primary infrastructure is healthy.
     What should a solutions architect do to meet these requirements?
     A. Deploy the application with the required infrastructure elements in place. Use Amazon Route 53 to congure active-passive failover. Create an Aurora Replica in a second AWS Region.
     B. Host a scaled-down deployment of the application in a second AWS Region. Use Amazon Route 53 to congure active-active failover. Create an Aurora Replica in the second Region.
     C. Replicate the primary infrastructure in a second AWS Region. Use Amazon Route 53 to congure active-active failover. Create an Aurora database that is restored from the latest snapshot.
     D. Back up data with AWS Backup. Use the backup to create the required infrastructure in a second AWS Region. Use Amazon Route 53 to congure active-passive failover. Create an Aurora second primary instance in the second Region.
218. A company has a web server running on an Amazon EC2 instance in a public subnet with an Elastic IP address. The default security group is assigned to the EC2 instance. The default network ACL has been modied to block all trac. A solutions architect needs to make the web server accessible from everywhere on port 443.
     Which combination of steps will accomplish this task? (Choose two.)
     A. Create a security group with a rule to allow TCP port 443 from source 0.0.0.0/0.
     B. Create a security group with a rule to allow TCP port 443 to destination 0.0.0.0/0.
     C. Update the network ACL to allow TCP port 443 from source 0.0.0.0/0.
     D. Update the network ACL to allow inbound/outbound TCP port 443 from source 0.0.0.0/0 and to destination 0.0.0.0/0.
     E. Update the network ACL to allow inbound TCP port 443 from source 0.0.0.0/0 and outbound TCP port 32768-65535 to destination 0.0.0.0/0.
219. A company’s application is having performance issues. The application is stateful and needs to complete in-memory tasks on Amazon EC2 instances. The company used AWS CloudFormation to deploy infrastructure and used the M5 EC2 instance family. As trac increased, the application performance degraded. Users are reporting delays when the users attempt to access the application.
     Which solution will resolve these issues in the MOST operationally ecient way?
     A. Replace the EC2 instances with T3 EC2 instances that run in an Auto Scaling group. Make the changes by using the AWS Management Console.
     B. Modify the CloudFormation templates to run the EC2 instances in an Auto Scaling group. Increase the desired capacity and the maximum capacity of the Auto Scaling group manually when an increase is necessary.
     C. Modify the CloudFormation templates. Replace the EC2 instances with R5 EC2 instances. Use Amazon CloudWatch built-in EC2 memory metrics to track the application performance for future capacity planning.
     D. Modify the CloudFormation templates. Replace the EC2 instances with R5 EC2 instances. Deploy the Amazon CloudWatch agent on the EC2 instances to generate custom application latency metrics for future capacity planning.
220. A solutions architect is designing a new API using Amazon API Gateway that will receive requests from users. The volume of requests is highly variable; several hours can pass without receiving a single request. The data processing will take place asynchronously, but should be completed within a few seconds after a request is made.
     Which compute service should the solutions architect have the API invoke to deliver the requirements at the lowest cost?
     A. An AWS Glue job
     B. An AWS Lambda function
     C. A containerized service hosted in Amazon Elastic Kubernetes Service (Amazon EKS)
     D. A containerized service hosted in Amazon ECS with Amazon EC2
221. A company runs an application on a group of Amazon Linux EC2 instances. For compliance reasons, the company must retain all application log les for 7 years. The log les will be analyzed by a reporting tool that must be able to access all the les concurrently.
     Which storage solution meets these requirements MOST cost-effectively?
     A. Amazon Elastic Block Store (Amazon EBS) 
     B. Amazon Elastic File System (Amazon EFS)
     C. Amazon EC2 instance store
     D. Amazon S3
222. A company has hired an external vendor to perform work in the company’s AWS account. The vendor uses an automated tool that is hosted in an AWS account that the vendor owns. The vendor does not have IAM access to the company’s AWS account.
     How should a solutions architect grant this access to the vendor?
     A. Create an IAM role in the company’s account to delegate access to the vendor’s IAM role. Attach the appropriate IAM policies to the role for the permissions that the vendor requires.
     B. Create an IAM user in the company’s account with a password that meets the password complexity requirements. Attach the appropriate IAM policies to the user for the permissions that the vendor requires.
     C. Create an IAM group in the company’s account. Add the tool’s IAM user from the vendor account to the group. Attach the appropriate IAM policies to the group for the permissions that the vendor requires.
     D. Create a new identity provider by choosing “AWS account” as the provider type in the IAM console. Supply the vendor’s AWS account ID and user name. Attach the appropriate IAM policies to the new provider for the permissions that the vendor requires.
223. A company has deployed a Java Spring Boot application as a pod that runs on Amazon Elastic Kubernetes Service (Amazon EKS) in private subnets. The application needs to write data to an Amazon DynamoDB table. A solutions architect must ensure that the application can interact with the DynamoDB table without exposing trac to the internet.
     Which combination of steps should the solutions architect take to accomplish this goal? (Choose two.)
     A. Attach an IAM role that has sucient privileges to the EKS pod.
     B. Attach an IAM user that has sucient privileges to the EKS pod.
     C. Allow outbound connectivity to the DynamoDB table through the private subnets’ network ACLs.
     D. Create a VPC endpoint for DynamoDB.
     E. Embed the access keys in the Java Spring Boot code.
224. A company recently migrated its web application to AWS by rehosting the application on Amazon EC2 instances in a single AWS Region. The company wants to redesign its application architecture to be highly available and fault tolerant. Trac must reach all running EC2 instances randomly.
     Which combination of steps should the company take to meet these requirements? (Choose two.)
     A. Create an Amazon Route 53 failover routing policy.
     B. Create an Amazon Route 53 weighted routing policy.
     C. Create an Amazon Route 53 multivalue answer routing policy.
     D. Launch three EC2 instances: two instances in one Availability Zone and one instance in another Availability Zone.
     E. Launch four EC2 instances: two instances in one Availability Zone and two instances in another Availability Zone.
225. A media company collects and analyzes user activity data on premises. The company wants to migrate this capability to AWS. The user activity data store will continue to grow and will be petabytes in size. The company needs to build a highly available data ingestion solution that facilitates on-demand analytics of existing data and new data with SQL.
     Which solution will meet these requirements with the LEAST operational overhead?
     A. Send activity data to an Amazon Kinesis data stream. Congure the stream to deliver the data to an Amazon S3 bucket.
     B. Send activity data to an Amazon Kinesis Data Firehose delivery stream. Congure the stream to deliver the data to an Amazon Redshift cluster.
     C. Place activity data in an Amazon S3 bucket. Congure Amazon S3 to run an AWS Lambda function on the data as the data arrives in the S3 bucket.
     D. Create an ingestion service on Amazon EC2 instances that are spread across multiple Availability Zones. Congure the service to forward data to an Amazon RDS Multi-AZ database.
226. A company collects data from thousands of remote devices by using a RESTful web services application that runs on an Amazon EC2 instance. The EC2 instance receives the raw data, transforms the raw data, and stores all the data in an Amazon S3 bucket. The number of remote devices will increase into the millions soon. The company needs a highly scalable solution that minimizes operational overhead.
     Which combination of steps should a solutions architect take to meet these requirements? (Choose two.)
     A. Use AWS Glue to process the raw data in Amazon S3.
     B. Use Amazon Route 53 to route trac to different EC2 instances.
     C. Add more EC2 instances to accommodate the increasing amount of incoming data.
     D. Send the raw data to Amazon Simple Queue Service (Amazon SQS). Use EC2 instances to process the data.
     E. Use Amazon API Gateway to send the raw data to an Amazon Kinesis data stream. Congure Amazon Kinesis Data Firehose to use the data stream as a source to deliver the data to Amazon S3.
227. A company needs to retain its AWS CloudTrail logs for 3 years. The company is enforcing CloudTrail across a set of AWS accounts by using AWS Organizations from the parent account. The CloudTrail target S3 bucket is congured with S3 Versioning enabled. An S3 Lifecycle policy is in place to delete current objects after 3 years.
     After the fourth year of use of the S3 bucket, the S3 bucket metrics show that the number of objects has continued to rise. However, the number of new CloudTrail logs that are delivered to the S3 bucket has remained consistent.
     Which solution will delete objects that are older than 3 years in the MOST cost-effective manner?
     A. Congure the organization’s centralized CloudTrail trail to expire objects after 3 years.
     B. Congure the S3 Lifecycle policy to delete previous versions as well as current versions.
     C. Create an AWS Lambda function to enumerate and delete objects from Amazon S3 that are older than 3 years.
     D. Congure the parent account as the owner of all objects that are delivered to the S3 bucket.
228. A company has an API that receives real-time data from a eet of monitoring devices. The API stores this data in an Amazon RDS DB instance for later analysis. The amount of data that the monitoring devices send to the API uctuates. During periods of heavy trac, the API often returns timeout errors.
     After an inspection of the logs, the company determines that the database is not capable of processing the volume of write trac that comes from the API. A solutions architect must minimize the number of connections to the database and must ensure that data is not lost during periods of heavy trac.
     Which solution will meet these requirements?
     A. Increase the size of the DB instance to an instance type that has more available memory.
     B. Modify the DB instance to be a Multi-AZ DB instance. Congure the application to write to all active RDS DB instances.
     C. Modify the API to write incoming data to an Amazon Simple Queue Service (Amazon SQS) queue. Use an AWS Lambda function that Amazon SQS invokes to write data from the queue to the database.
     D. Modify the API to write incoming data to an Amazon Simple Notication Service (Amazon SNS) topic. Use an AWS Lambda function that Amazon SNS invokes to write data from the topic to the database.
229. A company manages its own Amazon EC2 instances that run MySQL databases. The company is manually managing replication and scaling as demand increases or decreases. The company needs a new solution that simplies the process of adding or removing compute capacity to or from its database tier as needed. The solution also must offer improved performance, scaling, and durability with minimal effort from operations.
     Which solution meets these requirements?
     A. Migrate the databases to Amazon Aurora Serverless for Aurora MySQL.
     B. Migrate the databases to Amazon Aurora Serverless for Aurora PostgreSQL.
     C. Combine the databases into one larger MySQL database. Run the larger database on larger EC2 instances.
     D. Create an EC2 Auto Scaling group for the database tier. Migrate the existing databases to the new environment.
230. A company is concerned that two NAT instances in use will no longer be able to support the trac needed for the company’s application. A solutions architect wants to implement a solution that is highly available, fault tolerant, and automatically scalable.
     What should the solutions architect recommend?
     A. Remove the two NAT instances and replace them with two NAT gateways in the same Availability Zone.
     B. Use Auto Scaling groups with Network Load Balancers for the NAT instances in different Availability Zones.
     C. Remove the two NAT instances and replace them with two NAT gateways in different Availability Zones.
     D. Replace the two NAT instances with Spot Instances in different Availability Zones and deploy a Network Load Balancer.
231. An application runs on an Amazon EC2 instance that has an Elastic IP address in VPC A. The application requires access to a database in VPC B. Both VPCs are in the same AWS account.
     Which solution will provide the required access MOST securely?
     A. Create a DB instance security group that allows all trac from the public IP address of the application server in VPC A.
     B. Congure a VPC peering connection between VPC A and VPC B.
     C. Make the DB instance publicly accessible. Assign a public IP address to the DB instance.
     D. Launch an EC2 instance with an Elastic IP address into VPC B. Proxy all requests through the new EC2 instance.
232. A company runs demonstration environments for its customers on Amazon EC2 instances. Each environment is isolated in its own VPC. The company’s operations team needs to be notied when RDP or SSH access to an environment has been established.
     A. Congure Amazon CloudWatch Application Insights to create AWS Systems Manager OpsItems when RDP or SSH access is detected.
     B. Congure the EC2 instances with an IAM instance prole that has an IAM role with the AmazonSSMManagedInstanceCore policy attached.
     C. Publish VPC ow logs to Amazon CloudWatch Logs. Create required metric lters. Create an Amazon CloudWatch metric alarm with a notication action for when the alarm is in the ALARM state.
     D. Congure an Amazon EventBridge rule to listen for events of type EC2 Instance State-change Notication. Congure an Amazon Simple Notication Service (Amazon SNS) topic as a target. Subscribe the operations team to the topic.
233. A solutions architect has created a new AWS account and must secure AWS account root user access. Which combination of actions will accomplish this? (Choose two.)
     A. Ensure the root user uses a strong password.
     B. Enable multi-factor authentication to the root user.
     C. Store root user access keys in an encrypted Amazon S3 bucket.
     D. Add the root user to a group containing administrative permissions.
     E. Apply the required permissions to the root user with an inline policy document.
234. A company is building a new web-based customer relationship management application. The application will use several Amazon EC2 instances that are backed by Amazon Elastic Block Store (Amazon EBS) volumes behind an Application Load Balancer (ALB). The application will also use an Amazon Aurora database. All data for the application must be encrypted at rest and in transit.
     Which solution will meet these requirements?
     A. Use AWS Key Management Service (AWS KMS) certicates on the ALB to encrypt data in transit. Use AWS Certicate Manager (ACM) to encrypt the EBS volumes and Aurora database storage at rest.
     B. Use the AWS root account to log in to the AWS Management Console. Upload the company’s encryption certicates. While in the root account, select the option to turn on encryption for all data at rest and in transit for the account.
     C. Use AWS Key Management Service (AWS KMS) to encrypt the EBS volumes and Aurora database storage at rest. Attach an AWS Certicate Manager (ACM) certicate to the ALB to encrypt data in transit.
     D. Use BitLocker to encrypt all data at rest. Import the company’s TLS certicate keys to AWS Key Management Service (AWS KMS) Attach the KMS keys to the ALB to encrypt data in transit.
235. A company is moving its on-premises Oracle database to Amazon Aurora PostgreSQL. The database has several applications that write to the same tables. The applications need to be migrated one by one with a month in between each migration. Management has expressed concerns that the database has a high number of reads and writes. The data must be kept in sync across both databases throughout the migration.
     What should a solutions architect recommend?
     A. Use AWS DataSync for the initial migration. Use AWS Database Migration Service (AWS DMS) to create a change data capture (CDC) replication task and a table mapping to select all tables.
     B. Use AWS DataSync for the initial migration. Use AWS Database Migration Service (AWS DMS) to create a full load plus change data capture (CDC) replication task and a table mapping to select all tables.
     C. Use the AWS Schema Conversion Tool with AWS Database Migration Service (AWS DMS) using a memory optimized replication instance. Create a full load plus change data capture (CDC) replication task and a table mapping to select all tables.
     D. Use the AWS Schema Conversion Tool with AWS Database Migration Service (AWS DMS) using a compute optimized replication instance. Create a full load plus change data capture (CDC) replication task and a table mapping to select the largest tables.
236. A company has a three-tier application for image sharing. The application uses an Amazon EC2 instance for the front-end layer, another EC2 instance for the application layer, and a third EC2 instance for a MySQL database. A solutions architect must design a scalable and highly available solution that requires the least amount of change to the application.
     Which solution meets these requirements?
     A. Use Amazon S3 to host the front-end layer. Use AWS Lambda functions for the application layer. Move the database to an Amazon DynamoDB table. Use Amazon S3 to store and serve users’ images.
     B. Use load-balanced Multi-AZ AWS Elastic Beanstalk environments for the front-end layer and the application layer. Move the database to an Amazon RDS DB instance with multiple read replicas to serve users’ images.
     C. Use Amazon S3 to host the front-end layer. Use a eet of EC2 instances in an Auto Scaling group for the application layer. Move the database to a memory optimized instance type to store and serve users’ images.
     D. Use load-balanced Multi-AZ AWS Elastic Beanstalk environments for the front-end layer and the application layer. Move the database to an Amazon RDS Multi-AZ DB instance. Use Amazon S3 to store and serve users’ images.
237. An application running on an Amazon EC2 instance in VPC-A needs to access les in another EC2 instance in VPC-B. Both VPCs are in separate AWS accounts. The network administrator needs to design a solution to congure secure access to EC2 instance in VPC-B from VPC- A. The connectivity should not have a single point of failure or bandwidth concerns.
     Which solution will meet these requirements?
     A. Set up a VPC peering connection between VPC-A and VPC-B.
     B. Set up VPC gateway endpoints for the EC2 instance running in VPC-B.
     C. Attach a virtual private gateway to VPC-B and set up routing from VPC-A.
     D. Create a private virtual interface (VIF) for the EC2 instance running in VPC-B and add appropriate routes from VPC-A.
238. A company wants to experiment with individual AWS accounts for its engineer team. The company wants to be notied as soon as the Amazon EC2 instance usage for a given month exceeds a specic threshold for each account.
     What should a solutions architect do to meet this requirement MOST cost-effectively?
     A. Use Cost Explorer to create a daily report of costs by service. Filter the report by EC2 instances. Congure Cost Explorer to send an Amazon Simple Email Service (Amazon SES) notication when a threshold is exceeded.
     B. Use Cost Explorer to create a monthly report of costs by service. Filter the report by EC2 instances. Congure Cost Explorer to send an Amazon Simple Email Service (Amazon SES) notication when a threshold is exceeded.
     C. Use AWS Budgets to create a cost budget for each account. Set the period to monthly. Set the scope to EC2 instances. Set an alert threshold for the budget. Congure an Amazon Simple Notication Service (Amazon SNS) topic to receive a notication when a threshold is exceeded.
     D. Use AWS Cost and Usage Reports to create a report with hourly granularity. Integrate the report data with Amazon Athena. Use Amazon EventBridge to schedule an Athena query. Congure an Amazon Simple Notication Service (Amazon SNS) topic to receive a notication when a threshold is exceeded.
239. A solutions architect needs to design a new microservice for a company’s application. Clients must be able to call an HTTPS endpoint to reach the microservice. The microservice also must use AWS Identity and Access Management (IAM) to authenticate calls. The solutions architect will write the logic for this microservice by using a single AWS Lambda function that is written in Go 1.x.
     Which solution will deploy the function in the MOST operationally ecient way?
     A. Create an Amazon API Gateway REST API. Congure the method to use the Lambda function. Enable IAM authentication on the API.
     B. Create a Lambda function URL for the function. Specify AWS_IAM as the authentication type.
     C. Create an Amazon CloudFront distribution. Deploy the function to Lambda@Edge. Integrate IAM authentication logic into the Lambda@Edge function.
     D. Create an Amazon CloudFront distribution. Deploy the function to CloudFront Functions. Specify AWS_IAM as the authentication type.
240. A company previously migrated its data warehouse solution to AWS. The company also has an AWS Direct Connect connection. Corporate oce users query the data warehouse using a visualization tool. The average size of a query returned by the data warehouse is 50 MB and each webpage sent by the visualization tool is approximately 500 KB. Result sets returned by the data warehouse are not cached.
     Which solution provides the LOWEST data transfer egress cost for the company?
     A. Host the visualization tool on premises and query the data warehouse directly over the internet.
     B. Host the visualization tool in the same AWS Region as the data warehouse. Access it over the internet.
     C. Host the visualization tool on premises and query the data warehouse directly over a Direct Connect connection at a location in the same AWS Region.
     D. Host the visualization tool in the same AWS Region as the data warehouse and access it over a Direct Connect connection at a location in the same Region.
241. An online learning company is migrating to the AWS Cloud. The company maintains its student records in a PostgreSQL database. The company needs a solution in which its data is available and online across multiple AWS Regions at all times.
     Which solution will meet these requirements with the LEAST amount of operational overhead?
     A. Migrate the PostgreSQL database to a PostgreSQL cluster on Amazon EC2 instances.
     B. Migrate the PostgreSQL database to an Amazon RDS for PostgreSQL DB instance with the Multi-AZ feature turned on.
     C. Migrate the PostgreSQL database to an Amazon RDS for PostgreSQL DB instance. Create a read replica in another Region.
     D. Migrate the PostgreSQL database to an Amazon RDS for PostgreSQL DB instance. Set up DB snapshots to be copied to another Region.
242. A company hosts its web application on AWS using seven Amazon EC2 instances. The company requires that the IP addresses of all healthy EC2 instances be returned in response to DNS queries.
     Which policy should be used to meet this requirement?
     A. Simple routing policy
     B. Latency routing policy
     C. Multivalue routing policy
     D. Geolocation routing policy
243. A medical research lab produces data that is related to a new study. The lab wants to make the data available with minimum latency to clinics across the country for their on-premises, le-based applications. The data les are stored in an Amazon S3 bucket that has read-only permissions for each clinic.
     What should a solutions architect recommend to meet these requirements?
     A. Deploy an AWS Storage Gateway file gateway as a virtual machine (VM) on premises at each clinic
     B. Migrate the les to each clinic’s on-premises applications by using AWS DataSync for processing.
     C. Deploy an AWS Storage Gateway volume gateway as a virtual machine (VM) on premises at each clinic.
     D. Attach an Amazon Elastic File System (Amazon EFS) le system to each clinic’s on-premises servers.
244. A company is using a content management system that runs on a single Amazon EC2 instance. The EC2 instance contains both the web server and the database software. The company must make its website platform highly available and must enable the website to scale to meet user demand.
     What should a solutions architect recommend to meet these requirements?
     A. Move the database to Amazon RDS, and enable automatic backups. Manually launch another EC2 instance in the same Availability Zone. Congure an Application Load Balancer in the Availability Zone, and set the two instances as targets.
     B. Migrate the database to an Amazon Aurora instance with a read replica in the same Availability Zone as the existing EC2 instance. Manually launch another EC2 instance in the same Availability Zone. Congure an Application Load Balancer, and set the two EC2 instances as targets.
     C. Move the database to Amazon Aurora with a read replica in another Availability Zone. Create an Amazon Machine Image (AMI) from the EC2 instance. Congure an Application Load Balancer in two Availability Zones. Attach an Auto Scaling group that uses the AMI across two Availability Zones.
     D. Move the database to a separate EC2 instance, and schedule backups to Amazon S3. Create an Amazon Machine Image (AMI) from the original EC2 instance. Congure an Application Load Balancer in two Availability Zones. Attach an Auto Scaling group that uses the AMI across two Availability Zones.
245. A company is launching an application on AWS. The application uses an Application Load Balancer (ALB) to direct trac to at least two Amazon EC2 instances in a single target group. The instances are in an Auto Scaling group for each environment. The company requires a development environment and a production environment. The production environment will have periods of high trac.
     Which solution will congure the development environment MOST cost-effectively?
     A. Recongure the target group in the development environment to have only one EC2 instance as a target.
     B. Change the ALB balancing algorithm to least outstanding requests.
     C. Reduce the size of the EC2 instances in both environments.
     D. Reduce the maximum number of EC2 instances in the development environment’s Auto Scaling group.
246. A company runs a web application on Amazon EC2 instances in multiple Availability Zones. The EC2 instances are in private subnets. A solutions architect implements an internet-facing Application Load Balancer (ALB) and species the EC2 instances as the target group. However, the internet trac is not reaching the EC2 instances.
     How should the solutions architect recongure the architecture to resolve this issue?
     A. Replace the ALB with a Network Load Balancer. Congure a NAT gateway in a public subnet to allow internet trac.
     B. Move the EC2 instances to public subnets. Add a rule to the EC2 instances’ security groups to allow outbound trac to 0.0.0.0/0.
     C. Update the route tables for the EC2 instances’ subnets to send 0.0.0.0/0 trac through the internet gateway route. Add a rule to the EC2 instances’ security groups to allow outbound trac to 0.0.0.0/0.
     D. Create public subnets in each Availability Zone. Associate the public subnets with the ALB. Update the route tables for the public subnets with a route to the private subnets.
247. A company has deployed a database in Amazon RDS for MySQL. Due to increased transactions, the database support team is reporting slow reads against the DB instance and recommends adding a read replica.
     Which combination of actions should a solutions architect take before implementing this change? (Choose two.)
     A. Enable binlog replication on the RDS primary node.
     B. Choose a failover priority for the source DB instance.
     C. Allow long-running transactions to complete on the source DB instance.
     D. Create a global table and specify the AWS Regions where the table will be available.
     E. Enable automatic backups on the source instance by setting the backup retention period to a value other than 0.
248. A company runs analytics software on Amazon EC2 instances. The software accepts job requests from users to process data that has been uploaded to Amazon S3. Users report that some submitted data is not being processed Amazon CloudWatch reveals that the EC2 instances have a consistent CPU utilization at or near 100%. The company wants to improve system performance and scale the system based on user load.
     What should a solutions architect do to meet these requirements?
     A. Create a copy of the instance. Place all instances behind an Application Load Balancer.
     B. Create an S3 VPC endpoint for Amazon S3. Update the software to reference the endpoint.
     C. Stop the EC2 instances. Modify the instance type to one with a more powerful CPU and more memory. Restart the instances.
     D. Route incoming requests to Amazon Simple Queue Service (Amazon SQS). Congure an EC2 Auto Scaling group based on queue size. Update the software to read from the queue.
249. A company is implementing a shared storage solution for a media application that is hosted in the AWS Cloud. The company needs the ability to use SMB clients to access data. The solution must be fully managed.
     Which AWS solution meets these requirements?
     A. Create an AWS Storage Gateway volume gateway. Create a le share that uses the required client protocol. Connect the application server to the le share.
     B. Create an AWS Storage Gateway tape gateway. Congure tapes to use Amazon S3. Connect the application server to the tape gateway.
     C. Create an Amazon EC2 Windows instance. Install and congure a Windows le share role on the instance. Connect the application server to the le share.
     D. Create an Amazon FSx for Windows File Server le system. Attach the le system to the origin server. Connect the application server to the le system.
250. A company’s security team requests that network trac be captured in VPC Flow Logs. The logs will be frequently accessed for 90 days and then accessed intermittently.
     What should a solutions architect do to meet these requirements when conguring the logs?
     A. Use Amazon CloudWatch as the target. Set the CloudWatch log group with an expiration of 90 days
     B. Use Amazon Kinesis as the target. Congure the Kinesis stream to always retain the logs for 90 days.
     C. Use AWS CloudTrail as the target. Congure CloudTrail to save to an Amazon S3 bucket, and enable S3 Intelligent-Tiering.
     D. Use Amazon S3 as the target. Enable an S3 Lifecycle policy to transition the logs to S3 Standard-Infrequent Access (S3 Standard-IA) after 90 days.
251. An Amazon EC2 instance is located in a private subnet in a new VPC. This subnet does not have outbound internet access, but the EC2 instance needs the ability to download monthly security updates from an outside vendor.
     What should a solutions architect do to meet these requirements?
     A. Create an internet gateway, and attach it to the VPC. Congure the private subnet route table to use the internet gateway as the default route.
     B. Create a NAT gateway, and place it in a public subnet. Congure the private subnet route table to use the NAT gateway as the default route.
     C. Create a NAT instance, and place it in the same subnet where the EC2 instance is located. Congure the private subnet route table to use the NAT instance as the default route.
     D. Create an internet gateway, and attach it to the VPC. Create a NAT instance, and place it in the same subnet where the EC2 instance is located. Congure the private subnet route table to use the internet gateway as the default route.
252. A solutions architect needs to design a system to store client case les. The les are core company assets and are important. The number of les will grow over time.
     The les must be simultaneously accessible from multiple application servers that run on Amazon EC2 instances. The solution must have built-in redundancy.
     Which solution meets these requirements?
     A. Amazon Elastic File System (Amazon EFS)
     B. Amazon Elastic Block Store (Amazon EBS)
     C. Amazon S3 Glacier Deep Archive
     D. AWS Backup
253. 看原文
254. A company is reviewing a recent migration of a three-tier application to a VPC. The security team discovers that the principle of least privilege is not being applied to Amazon EC2 security group ingress and egress rules between the application tiers.
     What should a solutions architect do to correct this issue?
     A. Create security group rules using the instance ID as the source or destination.
     B. Create security group rules using the security group ID as the source or destination.
     C. Create security group rules using the VPC CIDR blocks as the source or destination.
     D. Create security group rules using the subnet CIDR blocks as the source or destination.
255. A company has an ecommerce checkout workow that writes an order to a database and calls a service to process the payment. Users are experiencing timeouts during the checkout process. When users resubmit the checkout form, multiple unique orders are created for the same desired transaction.
     How should a solutions architect refactor this workow to prevent the creation of multiple orders?
     A. Congure the web application to send an order message to Amazon Kinesis Data Firehose. Set the payment service to retrieve the message from Kinesis Data Firehose and process the order.
     B. Create a rule in AWS CloudTrail to invoke an AWS Lambda function based on the logged application path request. Use Lambda to query the database, call the payment service, and pass in the order information.
     C. Store the order in the database. Send a message that includes the order number to Amazon Simple Notication Service (Amazon SNS). Set the payment service to poll Amazon SNS, retrieve the message, and process the order.
     D. Store the order in the database. Send a message that includes the order number to an Amazon Simple Queue Service (Amazon SQS) FIFO queue. Set the payment service to retrieve the message and process the order. Delete the message from the queue.
256. A solutions architect is implementing a document review application using an Amazon S3 bucket for storage. The solution must prevent accidental deletion of the documents and ensure that all versions of the documents are available. Users must be able to download, modify, and upload documents.
     Which combination of actions should be taken to meet these requirements? (Choose two.)
     A. Enable a read-only bucket ACL.
     B. Enable versioning on the bucket.
     C. Attach an IAM policy to the bucket.
     D. Enable MFA Delete on the bucket.
     E. Encrypt the bucket using AWS KMS
257. A company is building a solution that will report Amazon EC2 Auto Scaling events across all the applications in an AWS account. The company needs to use a serverless solution to store the EC2 Auto Scaling status data in Amazon S3. The company then will use the data in Amazon S3 to provide near-real-time updates in a dashboard. The solution must not affect the speed of EC2 instance launches.
     How should the company move the data to Amazon S3 to meet these requirements?
     A. Use an Amazon CloudWatch metric stream to send the EC2 Auto Scaling status data to Amazon Kinesis Data Firehose. Store the data in Amazon S3.
     B. Launch an Amazon EMR cluster to collect the EC2 Auto Scaling status data and send the data to Amazon Kinesis Data Firehose. Store the data in Amazon S3.
     C. Create an Amazon EventBridge rule to invoke an AWS Lambda function on a schedule. Congure the Lambda function to send the EC2 Auto Scaling status data directly to Amazon S3.
     D. Use a bootstrap script during the launch of an EC2 instance to install Amazon Kinesis Agent. Congure Kinesis Agent to collect the EC2 Auto Scaling status data and send the data to Amazon Kinesis Data Firehose. Store the data in Amazon S3.
258. A company has an application that places hundreds of .csv les into an Amazon S3 bucket every hour. The les are 1 GB in size. Each time a le is uploaded, the company needs to convert the le to Apache Parquet format and place the output le into an S3 bucket.
     Which solution will meet these requirements with the LEAST operational overhead?
     A. Create an AWS Lambda function to download the .csv les, convert the les to Parquet format, and place the output les in an S3 bucket. Invoke the Lambda function for each S3 PUT event.
     B. Create an Apache Spark job to read the .csv les, convert the les to Parquet format, and place the output les in an S3 bucket. Create an AWS Lambda function for each S3 PUT event to invoke the Spark job.
     C. Create an AWS Glue table and an AWS Glue crawler for the S3 bucket where the application places the .csv les. Schedule an AWS Lambda function to periodically use Amazon Athena to query the AWS Glue table, convert the query results into Parquet format, and place the output les into an S3 bucket.
     D. Create an AWS Glue extract, transform, and load (ETL) job to convert the .csv les to Parquet format and place the output les into an S3 bucket. Create an AWS Lambda function for each S3 PUT event to invoke the ETL job.
259. A company is implementing new data retention policies for all databases that run on Amazon RDS DB instances. The company must retain daily backups for a minimum period of 2 years. The backups must be consistent and restorable.
     Which solution should a solutions architect recommend to meet these requirements?
     A. Create a backup vault in AWS Backup to retain RDS backups. Create a new backup plan with a daily schedule and an expiration period of 2 years after creation. Assign the RDS DB instances to the backup plan.
     B. Congure a backup window for the RDS DB instances for daily snapshots. Assign a snapshot retention policy of 2 years to each RDS DB instance. Use Amazon Data Lifecycle Manager (Amazon DLM) to schedule snapshot deletions.
     C. Congure database transaction logs to be automatically backed up to Amazon CloudWatch Logs with an expiration period of 2 years.
     D. Congure an AWS Database Migration Service (AWS DMS) replication task. Deploy a replication instance, and congure a change data capture (CDC) task to stream database changes to Amazon S3 as the target. Congure S3 Lifecycle policies to delete the snapshots after 2 years.
260. A company’s compliance team needs to move its le shares to AWS. The shares run on a Windows Server SMB le share. A self-managed on- premises Active Directory controls access to the les and folders.
     The company wants to use Amazon FSx for Windows File Server as part of the solution. The company must ensure that the on-premises Active Directory groups restrict access to the FSx for Windows File Server SMB compliance shares, folders, and les after the move to AWS. The company has created an FSx for Windows File Server le system.
     Which solution will meet these requirements?
     A. Create an Active Directory Connector to connect to the Active Directory. Map the Active Directory groups to IAM groups to restrict access.
     B. Assign a tag with a Restrict tag key and a Compliance tag value. Map the Active Directory groups to IAM groups to restrict access.
     C. Create an IAM service-linked role that is linked directly to FSx for Windows File Server to restrict access.
     D. Join the le system to the Active Directory to restrict access.
261. A company recently announced the deployment of its retail website to a global audience. The website runs on multiple Amazon EC2 instances behind an Elastic Load Balancer. The instances run in an Auto Scaling group across multiple Availability Zones.
     The company wants to provide its customers with different versions of content based on the devices that the customers use to access the website.
     Which combination of actions should a solutions architect take to meet these requirements? (Choose two.)
     A. Congure Amazon CloudFront to cache multiple versions of the content.
     B. Congure a host header in a Network Load Balancer to forward trac to different instances.
     C. Congure a Lambda@Edge function to send specic objects to users based on the User-Agent header.
     D. Congure AWS Global Accelerator. Forward requests to a Network Load Balancer (NLB). Congure the NLB to set up host-based routing to different EC2 instances.
     E. Congure AWS Global Accelerator. Forward requests to a Network Load Balancer (NLB). Congure the NLB to set up path-based routing to different EC2 instances.     C. Congure a Lambda@Edge function to send specic objects to users based on the User-Agent header.
262. A company plans to use Amazon ElastiCache for its multi-tier web application. A solutions architect creates a Cache VPC for the ElastiCache cluster and an App VPC for the application’s Amazon EC2 instances. Both VPCs are in the us-east-1 Region.
     The solutions architect must implement a solution to provide the application’s EC2 instances with access to the ElastiCache cluster. Which solution will meet these requirements MOST cost-effectively?
     A. Create a peering connection between the VPCs. Add a route table entry for the peering connection in both VPCs. Congure an inbound rule for the ElastiCache cluster’s security group to allow inbound connection from the application’s security group.
     B. Create a Transit VPC. Update the VPC route tables in the Cache VPC and the App VPC to route trac through the Transit VPC. Congure an inbound rule for the ElastiCache cluster's security group to allow inbound connection from the application’s security group.
     C. Create a peering connection between the VPCs. Add a route table entry for the peering connection in both VPCs. Congure an inbound rule for the peering connection’s security group to allow inbound connection from the application’s security group.
     D. Create a Transit VPC. Update the VPC route tables in the Cache VPC and the App VPC to route trac through the Transit VPC. Congure an inbound rule for the Transit VPC’s security group to allow inbound connection from the application’s security group.
263. A company is building an application that consists of several microservices. The company has decided to use container technologies to deploy its software on AWS. The company needs a solution that minimizes the amount of ongoing effort for maintenance and scaling. The company cannot manage additional infrastructure.
     Which combination of actions should a solutions architect take to meet these requirements? (Choose two.)
     A. Deploy an Amazon Elastic Container Service (Amazon ECS) cluster.
     B. Deploy the Kubernetes control plane on Amazon EC2 instances that span multiple Availability Zones.
     C. Deploy an Amazon Elastic Container Service (Amazon ECS) service with an Amazon EC2 launch type. Specify a desired task number level of greater than or equal to 2.
     D. Deploy an Amazon Elastic Container Service (Amazon ECS) service with a Fargate launch type. Specify a desired task number level of greater than or equal to 2.
     E. Deploy Kubernetes worker nodes on Amazon EC2 instances that span multiple Availability Zones. Create a deployment that species two or more replicas for each microservice.
264. A company has a web application hosted over 10 Amazon EC2 instances with trac directed by Amazon Route 53. The company occasionally experiences a timeout error when attempting to browse the application. The networking team nds that some DNS queries return IP addresses of unhealthy instances, resulting in the timeout error.
     What should a solutions architect implement to overcome these timeout errors?
     A. Create a Route 53 simple routing policy record for each EC2 instance. Associate a health check with each record.
     B. Create a Route 53 failover routing policy record for each EC2 instance. Associate a health check with each record.
     C. Create an Amazon CloudFront distribution with EC2 instances as its origin. Associate a health check with the EC2 instances.
     D. Create an Application Load Balancer (ALB) with a health check in front of the EC2 instances. Route to the ALB from Route 53.
265. A solutions architect needs to design a highly available application consisting of web, application, and database tiers. HTTPS content delivery should be as close to the edge as possible, with the least delivery time.
     Which solution meets these requirements and is MOST secure?
     A. Congure a public Application Load Balancer (ALB) with multiple redundant Amazon EC2 instances in public subnets. Congure Amazon CloudFront to deliver HTTPS content using the public ALB as the origin.
     B. Congure a public Application Load Balancer with multiple redundant Amazon EC2 instances in private subnets. Congure Amazon CloudFront to deliver HTTPS content using the EC2 instances as the origin.
     C. Congure a public Application Load Balancer (ALB) with multiple redundant Amazon EC2 instances in private subnets. Congure Amazon CloudFront to deliver HTTPS content using the public ALB as the origin.
     D. Congure a public Application Load Balancer with multiple redundant Amazon EC2 instances in public subnets. Congure Amazon CloudFront to deliver HTTPS content using the EC2 instances as the origin.
266. A company has a popular gaming platform running on AWS. The application is sensitive to latency because latency can impact the user experience and introduce unfair advantages to some players. The application is deployed in every AWS Region. It runs on Amazon EC2 instances that are part of Auto Scaling groups congured behind Application Load Balancers (ALBs). A solutions architect needs to implement a mechanism to monitor the health of the application and redirect trac to healthy endpoints.
     Which solution meets these requirements?
     A. Congure an accelerator in AWS Global Accelerator. Add a listener for the port that the application listens on, and attach it to a Regional endpoint in each Region. Add the ALB as the endpoint.
     B. Create an Amazon CloudFront distribution and specify the ALB as the origin server. Congure the cache behavior to use origin cache headers. Use AWS Lambda functions to optimize the trac.
     C. Create an Amazon CloudFront distribution and specify Amazon S3 as the origin server. Congure the cache behavior to use origin cache headers. Use AWS Lambda functions to optimize the trac.
     D. Congure an Amazon DynamoDB database to serve as the data store for the application. Create a DynamoDB Accelerator (DAX) cluster to act as the in-memory cache for DynamoDB hosting the application data.
267. A company has one million users that use its mobile app. The company must analyze the data usage in near-real time. The company also must encrypt the data in near-real time and must store the data in a centralized location in Apache Parquet format for further processing.
     Which solution will meet these requirements with the LEAST operational overhead?
     A. Create an Amazon Kinesis data stream to store the data in Amazon S3. Create an Amazon Kinesis Data Analytics application to analyze the data. Invoke an AWS Lambda function to send the data to the Kinesis Data Analytics application.
     B. Create an Amazon Kinesis data stream to store the data in Amazon S3. Create an Amazon EMR cluster to analyze the data. Invoke an AWS Lambda function to send the data to the EMR cluster.
     C. Create an Amazon Kinesis Data Firehose delivery stream to store the data in Amazon S3. Create an Amazon EMR cluster to analyze the data.
     D. Create an Amazon Kinesis Data Firehose delivery stream to store the data in Amazon S3. Create an Amazon Kinesis Data Analytics application to analyze the data.
268. A gaming company has a web application that displays scores. The application runs on Amazon EC2 instances behind an Application Load Balancer. The application stores data in an Amazon RDS for MySQL database. Users are starting to experience long delays and interruptions that are caused by database read performance. The company wants to improve the user experience while minimizing changes to the application’s architecture.
     What should a solutions architect do to meet these requirements?
     A. Use Amazon ElastiCache in front of the database.
     B. Use RDS Proxy between the application and the database.
     C. Migrate the application from EC2 instances to AWS Lambda.
     D. Migrate the database from Amazon RDS for MySQL to Amazon DynamoDB.
269. An ecommerce company has noticed performance degradation of its Amazon RDS based web application. The performance degradation is attributed to an increase in the number of read-only SQL queries triggered by business analysts. A solutions architect needs to solve the problem with minimal changes to the existing web application.
     What should the solutions architect recommend?
     A. Export the data to Amazon DynamoDB and have the business analysts run their queries.
     B. Load the data into Amazon ElastiCache and have the business analysts run their queries.
     C. Create a read replica of the primary database and have the business analysts run their queries.
     D. Copy the data into an Amazon Redshift cluster and have the business analysts run their queries.
270. A company is using a centralized AWS account to store log data in various Amazon S3 buckets. A solutions architect needs to ensure that the data is encrypted at rest before the data is uploaded to the S3 buckets. The data also must be encrypted in transit.
     Which solution meets these requirements?
     A. Use client-side encryption to encrypt the data that is being uploaded to the S3 buckets.
     B. Use server-side encryption to encrypt the data that is being uploaded to the S3 buckets.
     C. Create bucket policies that require the use of server-side encryption with S3 managed encryption keys (SSE-S3) for S3 uploads.
     D. Enable the security option to encrypt the S3 buckets through the use of a default AWS Key Management Service (AWS KMS) key.
271. A solutions architect observes that a nightly batch processing job is automatically scaled up for 1 hour before the desired Amazon EC2 capacity is reached. The peak capacity is the ‘same every night and the batch jobs always start at 1 AM. The solutions architect needs to nd a cost-effective solution that will allow for the desired EC2 capacity to be reached quickly and allow the Auto Scaling group to scale down after the batch jobs are complete.
     What should the solutions architect do to meet these requirements?
     A. Increase the minimum capacity for the Auto Scaling group.
     B. Increase the maximum capacity for the Auto Scaling group.
     C. Congure scheduled scaling to scale up to the desired compute level.
     D. Change the scaling policy to add more EC2 instances during each scaling operation.
272. A company serves a dynamic website from a eet of Amazon EC2 instances behind an Application Load Balancer (ALB). The website needs to support multiple languages to serve customers around the world. The website’s architecture is running in the us-west-1 Region and is exhibiting high request latency for users that are located in other parts of the world.
     The website needs to serve requests quickly and eciently regardless of a user’s location. However, the company does not want to recreate the existing architecture across multiple Regions.
     What should a solutions architect do to meet these requirements?
     A. Replace the existing architecture with a website that is served from an Amazon S3 bucket. Congure an Amazon CloudFront distribution with the S3 bucket as the origin. Set the cache behavior settings to cache based on the Accept-Language request header.
     B. Congure an Amazon CloudFront distribution with the ALB as the origin. Set the cache behavior settings to cache based on the Accept- Language request header.
     C. Create an Amazon API Gateway API that is integrated with the ALB. Congure the API to use the HTTP integration type. Set up an API Gateway stage to enable the API cache based on the Accept-Language request header.
     D. Launch an EC2 instance in each additional Region and congure NGINX to act as a cache server for that Region. Put all the EC2 instances and the ALB behind an Amazon Route 53 record set with a geolocation routing policy.
273. A rapidly growing ecommerce company is running its workloads in a single AWS Region. A solutions architect must create a disaster recovery (DR) strategy that includes a different AWS Region. The company wants its database to be up to date in the DR Region with the least possible latency. The remaining infrastructure in the DR Region needs to run at reduced capacity and must be able to scale up if necessary.
     Which solution will meet these requirements with the LOWEST recovery time objective (RTO)?
     A. Use an Amazon Aurora global database with a pilot light deployment.
     B. Use an Amazon Aurora global database with a warm standby deployment.
     C. Use an Amazon RDS Multi-AZ DB instance with a pilot light deployment.
     D. Use an Amazon RDS Multi-AZ DB instance with a warm standby deployment.
274. A company runs an application on Amazon EC2 instances. The company needs to implement a disaster recovery (DR) solution for the application. The DR solution needs to have a recovery time objective (RTO) of less than 4 hours. The DR solution also needs to use the fewest possible AWS resources during normal operations.
     Which solution will meet these requirements in the MOST operationally ecient way?
     A. Create Amazon Machine Images (AMIs) to back up the EC2 instances. Copy the AMIs to a secondary AWS Region. Automate infrastructure deployment in the secondary Region by using AWS Lambda and custom scripts.
     B. Create Amazon Machine Images (AMIs) to back up the EC2 instances. Copy the AMIs to a secondary AWS Region. Automate infrastructure deployment in the secondary Region by using AWS CloudFormation.
     C. Launch EC2 instances in a secondary AWS Region. Keep the EC2 instances in the secondary Region active at all times.
     D. Launch EC2 instances in a secondary Availability Zone. Keep the EC2 instances in the secondary Availability Zone active at all times.
275. A company runs an internal browser-based application. The application runs on Amazon EC2 instances behind an Application Load Balancer. The instances run in an Amazon EC2 Auto Scaling group across multiple Availability Zones. The Auto Scaling group scales up to 20 instances during work hours, but scales down to 2 instances overnight. Staff are complaining that the application is very slow when the day begins, although it runs well by mid-morning.
     How should the scaling be changed to address the staff complaints and keep costs to a minimum?
     A. Implement a scheduled action that sets the desired capacity to 20 shortly before the oce opens.
     B. Implement a step scaling action triggered at a lower CPU threshold, and decrease the cooldown period.
     C. Implement a target tracking action triggered at a lower CPU threshold, and decrease the cooldown period.
     D. Implement a scheduled action that sets the minimum and maximum capacity to 20 shortly before the oce opens.
276. A company has a multi-tier application deployed on several Amazon EC2 instances in an Auto Scaling group. An Amazon RDS for Oracle instance is the application’ s data layer that uses Oracle-specic PL/SQL functions. Trac to the application has been steadily increasing. This is causing the EC2 instances to become overloaded and the RDS instance to run out of storage. The Auto Scaling group does not have any scaling metrics and denes the minimum healthy instance count only. The company predicts that trac will continue to increase at a steady but unpredictable rate before leveling off.
     What should a solutions architect do to ensure the system can automatically scale for the increased trac? (Choose two.)
     A. Congure storage Auto Scaling on the RDS for Oracle instance.
     B. Migrate the database to Amazon Aurora to use Auto Scaling storage.
     C. Congure an alarm on the RDS for Oracle instance for low free storage space.
     D. Congure the Auto Scaling group to use the average CPU as the scaling metric.
     E. Congure the Auto Scaling group to use the average free memory as the scaling metric.
277. A company provides an online service for posting video content and transcoding it for use by any mobile platform. The application architecture uses Amazon Elastic File System (Amazon EFS) Standard to collect and store the videos so that multiple Amazon EC2 Linux instances can access the video content for processing. As the popularity of the service has grown over time, the storage costs have become too expensive.
     Which storage solution is MOST cost-effective?
     A. Use AWS Storage Gateway for les to store and process the video content.
     B. Use AWS Storage Gateway for volumes to store and process the video content.
     C. Use Amazon EFS for storing the video content. Once processing is complete, transfer the les to Amazon Elastic Block Store (Amazon EBS).
     D. Use Amazon S3 for storing the video content. Move the les temporarily over to an Amazon Elastic Block Store (Amazon EBS) volume attached to the server for processing.
278. A company wants to create an application to store employee data in a hierarchical structured relationship. The company needs a minimum- latency response to high-trac queries for the employee data and must protect any sensitive data. The company also needs to receive monthly email messages if any nancial information is present in the employee data.
     Which combination of steps should a solutions architect take to meet these requirements? (Choose two.)
     A. Use Amazon Redshift to store the employee data in hierarchies. Unload the data to Amazon S3 every month.
     B. Use Amazon DynamoDB to store the employee data in hierarchies. Export the data to Amazon S3 every month.
     C. Congure Amazon Macie for the AWS account. Integrate Macie with Amazon EventBridge to send monthly events to AWS Lambda.
     D. Use Amazon Athena to analyze the employee data in Amazon S3. Integrate Athena with Amazon QuickSight to publish analysis dashboards and share the dashboards with users.
     E. Congure Amazon Macie for the AWS account. Integrate Macie with Amazon EventBridge to send monthly notications through an Amazon Simple Notication Service (Amazon SNS) subscription.
279. A company has an application that is backed by an Amazon DynamoDB table. The company’s compliance requirements specify that database backups must be taken every month, must be available for 6 months, and must be retained for 7 years.
     Which solution will meet these requirements?
     A. Create an AWS Backup plan to back up the DynamoDB table on the rst day of each month. Specify a lifecycle policy that transitions the backup to cold storage after 6 months. Set the retention period for each backup to 7 years.
     B. Create a DynamoDB on-demand backup of the DynamoDB table on the rst day of each month. Transition the backup to Amazon S3 Glacier Flexible Retrieval after 6 months. Create an S3 Lifecycle policy to delete backups that are older than 7 years.
     C. Use the AWS SDK to develop a script that creates an on-demand backup of the DynamoDB table. Set up an Amazon EventBridge rule that runs the script on the rst day of each month. Create a second script that will run on the second day of each month to transition DynamoDB backups that are older than 6 months to cold storage and to delete backups that are older than 7 years.
     D. Use the AWS CLI to create an on-demand backup of the DynamoDB table. Set up an Amazon EventBridge rule that runs the command on the rst day of each month with a cron expression. Specify in the command to transition the backups to cold storage after 6 months and to delete the backups after 7 years.
280. A company is using Amazon CloudFront with its website. The company has enabled logging on the CloudFront distribution, and logs are saved in one of the company’s Amazon S3 buckets. The company needs to perform advanced analyses on the logs and build visualizations.
     What should a solutions architect do to meet these requirements?
     A. Use standard SQL queries in Amazon Athena to analyze the CloudFront logs in the S3 bucket. Visualize the results with AWS Glue.
     B. Use standard SQL queries in Amazon Athena to analyze the CloudFront logs in the S3 bucket. Visualize the results with Amazon QuickSight.
     C. Use standard SQL queries in Amazon DynamoDB to analyze the CloudFront logs in the S3 bucket. Visualize the results with AWS Glue.
     D. Use standard SQL queries in Amazon DynamoDB to analyze the CloudFront logs in the S3 bucket. Visualize the results with Amazon QuickSight.
281. A company runs a eet of web servers using an Amazon RDS for PostgreSQL DB instance. After a routine compliance check, the company sets a standard that requires a recovery point objective (RPO) of less than 1 second for all its production databases.
     Which solution meets these requirements?
     A. Enable a Multi-AZ deployment for the DB instance.
     B. Enable auto scaling for the DB instance in one Availability Zone.
     C. Congure the DB instance in one Availability Zone, and create multiple read replicas in a separate Availability Zone.
     D. Congure the DB instance in one Availability Zone, and congure AWS Database Migration Service (AWS DMS) change data capture (CDC) tasks.
282. A company runs a web application that is deployed on Amazon EC2 instances in the private subnet of a VPC. An Application Load Balancer (ALB) that extends across the public subnets directs web trac to the EC2 instances. The company wants to implement new security measures to restrict inbound trac from the ALB to the EC2 instances while preventing access from any other source inside or outside the private subnet of the EC2 instances.
     Which solution will meet these requirements?
     A. Congure a route in a route table to direct trac from the internet to the private IP addresses of the EC2 instances.
     B. Congure the security group for the EC2 instances to only allow trac that comes from the security group for the ALB.
     C. Move the EC2 instances into the public subnet. Give the EC2 instances a set of Elastic IP addresses.
     D. Congure the security group for the ALB to allow any TCP trac on any port.
283. A research company runs experiments that are powered by a simulation application and a visualization application. The simulation application runs on Linux and outputs intermediate data to an NFS share every 5 minutes. The visualization application is a Windows desktop application that displays the simulation output and requires an SMB le system.
     The company maintains two synchronized le systems. This strategy is causing data duplication and inecient resource usage. The company needs to migrate the applications to AWS without making code changes to either application.
     Which solution will meet these requirements?
     A. Migrate both applications to AWS Lambda. Create an Amazon S3 bucket to exchange data between the applications.
     B. Migrate both applications to Amazon Elastic Container Service (Amazon ECS). Congure Amazon FSx File Gateway for storage.
     C. Migrate the simulation application to Linux Amazon EC2 instances. Migrate the visualization application to Windows EC2 instances. Congure Amazon Simple Queue Service (Amazon SQS) to exchange data between the applications.
     D. Migrate the simulation application to Linux Amazon EC2 instances. Migrate the visualization application to Windows EC2 instances. Congure Amazon FSx for NetApp ONTAP for storage.
284. As part of budget planning, management wants a report of AWS billed items listed by user. The data will be used to create department budgets. A solutions architect needs to determine the most ecient way to obtain this report information.
     Which solution meets these requirements?
     A. Run a query with Amazon Athena to generate the report.
     B. Create a report in Cost Explorer and download the report.
     C. Access the bill details from the billing dashboard and download the bill.
     D. Modify a cost budget in AWS Budgets to alert with Amazon Simple Email Service (Amazon SES).
285. A company hosts its static website by using Amazon S3. The company wants to add a contact form to its webpage. The contact form will have dynamic server-side components for users to input their name, email address, phone number, and user message. The company anticipates that there will be fewer than 100 site visits each month.
     Which solution will meet these requirements MOST cost-effectively?
     A. Host a dynamic contact form page in Amazon Elastic Container Service (Amazon ECS). Set up Amazon Simple Email Service (Amazon SES) to connect to any third-party email provider.
     B. Create an Amazon API Gateway endpoint with an AWS Lambda backend that makes a call to Amazon Simple Email Service (Amazon SES).
     C. Convert the static webpage to dynamic by deploying Amazon Lightsail. Use client-side scripting to build the contact form. Integrate the form with Amazon WorkMail.
     D. Create a t2.micro Amazon EC2 instance. Deploy a LAMP (Linux, Apache, MySQL, PHP/Perl/Python) stack to host the webpage. Use client-side scripting to build the contact form. Integrate the form with Amazon WorkMail.
286. A company has a static website that is hosted on Amazon CloudFront in front of Amazon S3. The static website uses a database backend. The company notices that the website does not reect updates that have been made in the website’s Git repository. The company checks the continuous integration and continuous delivery (CI/CD) pipeline between the Git repository and Amazon S3. The company veries that the webhooks are congured properly and that the CI/CD pipeline is sending messages that indicate successful deployments.
     A solutions architect needs to implement a solution that displays the updates on the website. Which solution will meet these requirements?
     A. Add an Application Load Balancer.
     B. Add Amazon ElastiCache for Redis or Memcached to the database layer of the web application.
     C. Invalidate the CloudFront cache.
     D. Use AWS Certicate Manager (ACM) to validate the website’s SSL certicate.
287. A company wants to migrate a Windows-based application from on premises to the AWS Cloud. The application has three tiers: an application tier, a business tier, and a database tier with Microsoft SQL Server. The company wants to use specic features of SQL Server such as native backups and Data Quality Services. The company also needs to share les for processing between the tiers.
     How should a solutions architect design the architecture to meet these requirements?
     A. Host all three tiers on Amazon EC2 instances. Use Amazon FSx File Gateway for le sharing between the tiers.
     B. Host all three tiers on Amazon EC2 instances. Use Amazon FSx for Windows File Server for le sharing between the tiers.
     C. Host the application tier and the business tier on Amazon EC2 instances. Host the database tier on Amazon RDS. Use Amazon Elastic File System (Amazon EFS) for le sharing between the tiers.
     D. Host the application tier and the business tier on Amazon EC2 instances. Host the database tier on Amazon RDS. Use a Provisioned IOPS SSD (io2) Amazon Elastic Block Store (Amazon EBS) volume for le sharing between the tiers.
288. A company is migrating a Linux-based web server group to AWS. The web servers must access les in a shared le store for some content. The company must not make any changes to the application.
     What should a solutions architect do to meet these requirements?
     A. Create an Amazon S3 Standard bucket with access to the web servers.
     B. Congure an Amazon CloudFront distribution with an Amazon S3 bucket as the origin.
     C. Create an Amazon Elastic File System (Amazon EFS) le system. Mount the EFS le system on all web servers.
     D. Congure a General Purpose SSD (gp3) Amazon Elastic Block Store (Amazon EBS) volume. Mount the EBS volume to all web servers.
289. A company has an AWS Lambda function that needs read access to an Amazon S3 bucket that is located in the same AWS account. Which solution will meet these requirements in the MOST secure manner?
     A. Apply an S3 bucket policy that grants read access to the S3 bucket.
     B. Apply an IAM role to the Lambda function. Apply an IAM policy to the role to grant read access to the S3 bucket.
     C. Embed an access key and a secret key in the Lambda function’s code to grant the required IAM permissions for read access to the S3 bucket.
     D. Apply an IAM role to the Lambda function. Apply an IAM policy to the role to grant read access to all S3 buckets in the account.
290. A company hosts a web application on multiple Amazon EC2 instances. The EC2 instances are in an Auto Scaling group that scales in response to user demand. The company wants to optimize cost savings without making a long-term commitment.
     Which EC2 instance purchasing option should a solutions architect recommend to meet these requirements?
     A. Dedicated Instances only
     B. On-Demand Instances only
     C. A mix of On-Demand Instances and Spot Instances
     D. A mix of On-Demand Instances and Reserved Instances
291. A media company uses Amazon CloudFront for its publicly available streaming video content. The company wants to secure the video content that is hosted in Amazon S3 by controlling who has access. Some of the company’s users are using a custom HTTP client that does not support cookies. Some of the company’s users are unable to change the hardcoded URLs that they are using for access.
     Which services or methods will meet these requirements with the LEAST impact to the users? (Choose two.)
     A. Signed cookies
     B. Signed URLs
     C. AWS AppSync
     D. JSON Web Token (JWT)
     E. AWS Secrets Manager
292. A company is preparing a new data platform that will ingest real-time streaming data from multiple sources. The company needs to transform the data before writing the data to Amazon S3. The company needs the ability to use SQL to query the transformed data.
     Which solutions will meet these requirements? (Choose two.)
     A. Use Amazon Kinesis Data Streams to stream the data. Use Amazon Kinesis Data Analytics to transform the data. Use Amazon Kinesis Data Firehose to write the data to Amazon S3. Use Amazon Athena to query the transformed data from Amazon S3.
     B. Use Amazon Managed Streaming for Apache Kafka (Amazon MSK) to stream the data. Use AWS Glue to transform the data and to write the data to Amazon S3. Use Amazon Athena to query the transformed data from Amazon S3.
     C. Use AWS Database Migration Service (AWS DMS) to ingest the data. Use Amazon EMR to transform the data and to write the data to Amazon S3. Use Amazon Athena to query the transformed data from Amazon S3.
     D. Use Amazon Managed Streaming for Apache Kafka (Amazon MSK) to stream the data. Use Amazon Kinesis Data Analytics to transform the data and to write the data to Amazon S3. Use the Amazon RDS query editor to query the transformed data from Amazon S3.
     E. Use Amazon Kinesis Data Streams to stream the data. Use AWS Glue to transform the data. Use Amazon Kinesis Data Firehose to write the data to Amazon S3. Use the Amazon RDS query editor to query the transformed data from Amazon S3.
293. A company has an on-premises volume backup solution that has reached its end of life. The company wants to use AWS as part of a new backup solution and wants to maintain local access to all the data while it is backed up on AWS. The company wants to ensure that the data backed up on AWS is automatically and securely transferred.
     Which solution meets these requirements?
     A. Use AWS Snowball to migrate data out of the on-premises solution to Amazon S3. Congure on-premises systems to mount the Snowball S3 endpoint to provide local access to the data.
     B. Use AWS Snowball Edge to migrate data out of the on-premises solution to Amazon S3. Use the Snowball Edge le interface to provide on-premises systems with local access to the data.
     C. Use AWS Storage Gateway and congure a cached volume gateway. Run the Storage Gateway software appliance on premises and congure a percentage of data to cache locally. Mount the gateway storage volumes to provide local access to the data.
     D. Use AWS Storage Gateway and congure a stored volume gateway. Run the Storage Gateway software appliance on premises and map the gateway storage volumes to on-premises storage. Mount the gateway storage volumes to provide local access to the data.
294. An application that is hosted on Amazon EC2 instances needs to access an Amazon S3 bucket. Trac must not traverse the internet. How should a solutions architect congure access to meet these requirements?
     A. Create a private hosted zone by using Amazon Route 53.
     B. Set up a gateway VPC endpoint for Amazon S3 in the VPC.
     C. Congure the EC2 instances to use a NAT gateway to access the S3 bucket.
     D. Establish an AWS Site-to-Site VPN connection between the VPC and the S3 bucket.
295. An ecommerce company stores terabytes of customer data in the AWS Cloud. The data contains personally identiable information (PII). The company wants to use the data in three applications. Only one of the applications needs to process the PII. The PII must be removed before the other two applications process the data.
    Which solution will meet these requirements with the LEAST operational overhead?
    A. Store the data in an Amazon DynamoDB table. Create a proxy application layer to intercept and process the data that each application requests.
    B. Store the data in an Amazon S3 bucket. Process and transform the data by using S3 Object Lambda before returning the data to the requesting application.
    C. Process the data and store the transformed data in three separate Amazon S3 buckets so that each application has its own custom dataset. Point each application to its respective S3 bucket.
    D. Process the data and store the transformed data in three separate Amazon DynamoDB tables so that each application has its own custom dataset. Point each application to its respective DynamoDB table.
296. A development team has launched a new application that is hosted on Amazon EC2 instances inside a development VPC. A solutions architect needs to create a new VPC in the same account. The new VPC will be peered with the development VPC. The VPC CIDR block for the development VPC is 192.168.0.0/24. The solutions architect needs to create a CIDR block for the new VPC. The CIDR block must be valid for a VPC peering connection to the development VPC.
     What is the SMALLEST CIDR block that meets these requirements?
     A. 10.0.1.0/32
     B. 192.168.0.0/24
     C. 192.168.1.0/32
     D. 10.0.1.0/24
297. A company deploys an application on ve Amazon EC2 instances. An Application Load Balancer (ALB) distributes trac to the instances by using a target group. The average CPU usage on each of the instances is below 10% most of the time, with occasional surges to 65%.
     A solutions architect needs to implement a solution to automate the scalability of the application. The solution must optimize the cost of the architecture and must ensure that the application has enough CPU resources when surges occur.
     Which solution will meet these requirements?
     A. Create an Amazon CloudWatch alarm that enters the ALARM state when the CPUUtilization metric is less than 20%. Create an AWS Lambda function that the CloudWatch alarm invokes to terminate one of the EC2 instances in the ALB target group.
     B. Create an EC2 Auto Scaling group. Select the existing ALB as the load balancer and the existing target group as the target group. Set a target tracking scaling policy that is based on the ASGAverageCPUUtilization metric. Set the minimum instances to 2, the desired capacity to 3, the maximum instances to 6, and the target value to 50%. Add the EC2 instances to the Auto Scaling group.
     C. Create an EC2 Auto Scaling group. Select the existing ALB as the load balancer and the existing target group as the target group. Set the minimum instances to 2, the desired capacity to 3, and the maximum instances to 6. Add the EC2 instances to the Auto Scaling group.
     D. Create two Amazon CloudWatch alarms. Congure the rst CloudWatch alarm to enter the ALARM state when the average CPUUtilization metric is below 20%. Congure the second CloudWatch alarm to enter the ALARM state when the average CPUUtilization matric is above 50%. Congure the alarms to publish to an Amazon Simple Notication Service (Amazon SNS) topic to send an email message. After receiving the message, log in to decrease or increase the number of EC2 instances that are running.
298. A company is running a critical business application on Amazon EC2 instances behind an Application Load Balancer. The EC2 instances run in an Auto Scaling group and access an Amazon RDS DB instance.
     The design did not pass an operational review because the EC2 instances and the DB instance are all located in a single Availability Zone. A solutions architect must update the design to use a second Availability Zone.
     Which solution will make the application highly available?
     A. Provision a subnet in each Availability Zone. Congure the Auto Scaling group to distribute the EC2 instances across both Availability Zones. Congure the DB instance with connections to each network.
     B. Provision two subnets that extend across both Availability Zones. Congure the Auto Scaling group to distribute the EC2 instances across both Availability Zones. Congure the DB instance with connections to each network.
     C. Provision a subnet in each Availability Zone. Congure the Auto Scaling group to distribute the EC2 instances across both Availability Zones. Congure the DB instance for Multi-AZ deployment.
     D. Provision a subnet that extends across both Availability Zones. Congure the Auto Scaling group to distribute the EC2 instances across both Availability Zones. Congure the DB instance for Multi-AZ deployment.
299. A research laboratory needs to process approximately 8 TB of data. The laboratory requires sub-millisecond latencies and a minimum throughput of 6 GBps for the storage subsystem. Hundreds of Amazon EC2 instances that run Amazon Linux will distribute and process the data.
     Which solution will meet the performance requirements?
     A. Create an Amazon FSx for NetApp ONTAP le system. Sat each volume’ tiering policy to ALL. Import the raw data into the le system. Mount the la system on the EC2 instances.
     B. Create an Amazon S3 bucket to store the raw data. Create an Amazon FSx for Lustre le system that uses persistent SSD storage. Select the option to import data from and export data to Amazon S3. Mount the le system on the EC2 instances.
     C. Create an Amazon S3 bucket to store the raw data. Create an Amazon FSx for Lustre le system that uses persistent HDD storage. Select the option to import data from and export data to Amazon S3. Mount the le system on the EC2 instances.
     D. Create an Amazon FSx for NetApp ONTAP le system. Set each volume’s tiering policy to NONE. Import the raw data into the le system. Mount the le system on the EC2 instances.
300.  A company needs to migrate a legacy application from an on-premises data center to the AWS Cloud because of hardware capacity constraints. The application runs 24 hours a day, 7 days a week. The application’s database storage continues to grow over time.
      What should a solutions architect do to meet these requirements MOST cost-effectively?
      A. Migrate the application layer to Amazon EC2 Spot Instances. Migrate the data storage layer to Amazon S3.
      B. Migrate the application layer to Amazon EC2 Reserved Instances. Migrate the data storage layer to Amazon RDS On-Demand Instances. 
      C. Migrate the application layer to Amazon EC2 Reserved Instances. Migrate the data storage layer to Amazon Aurora Reserved Instances. 
      D. Migrate the application layer to Amazon EC2 On-Demand Instances. Migrate the data storage layer to Amazon RDS Reserved Instances.
301. A university research laboratory needs to migrate 30 TB of data from an on-premises Windows le server to Amazon FSx for Windows File Server. The laboratory has a 1 Gbps network link that many other departments in the university share.
     The laboratory wants to implement a data migration service that will maximize the performance of the data transfer. However, the laboratory needs to be able to control the amount of bandwidth that the service uses to minimize the impact on other departments. The data migration must take place within the next 5 days.
     Which AWS solution will meet these requirements?
     A. AWS Snowcone
     B. Amazon FSx File Gateway
     C. AWS DataSync
     D. AWS Transfer Family
302. A company wants to create a mobile app that allows users to stream slow-motion video clips on their mobile devices. Currently, the app captures video clips and uploads the video clips in raw format into an Amazon S3 bucket. The app retrieves these video clips directly from the S3 bucket. However, the videos are large in their raw format.
     Users are experiencing issues with buffering and playback on mobile devices. The company wants to implement solutions to maximize the performance and scalability of the app while minimizing operational overhead.
     Which combination of solutions will meet these requirements? (Choose two.)
     A. Deploy Amazon CloudFront for content delivery and caching.
     B. Use AWS DataSync to replicate the video les across AW'S Regions in other S3 buckets.
     C. Use Amazon Elastic Transcoder to convert the video les to more appropriate formats.
     D. Deploy an Auto Sealing group of Amazon EC2 instances in Local Zones for content delivery and caching.
     E. Deploy an Auto Scaling group of Amazon EC2 instances to convert the video les to more appropriate formats.
303. A company is launching a new application deployed on an Amazon Elastic Container Service (Amazon ECS) cluster and is using the Fargate launch type for ECS tasks. The company is monitoring CPU and memory usage because it is expecting high trac to the application upon its launch. However, the company wants to reduce costs when utilization decreases.
     What should a solutions architect recommend?
     A. Use Amazon EC2 Auto Scaling to scale at certain periods based on previous trac patterns.
     B. Use an AWS Lambda function to scale Amazon ECS based on metric breaches that trigger an Amazon CloudWatch alarm.
     C. Use Amazon EC2 Auto Scaling with simple scaling policies to scale when ECS metric breaches trigger an Amazon CloudWatch alarm.
     D. Use AWS Application Auto Scaling with target tracking policies to scale when ECS metric breaches trigger an Amazon CloudWatch alarm.
304. A company recently created a disaster recovery site in a different AWS Region. The company needs to transfer large amounts of data back and forth between NFS le systems in the two Regions on a periodic basis.
     Which solution will meet these requirements with the LEAST operational overhead?
     A. Use AWS DataSync.
     B. Use AWS Snowball devices.
     C. Set up an SFTP server on Amazon EC2.
     D. Use AWS Database Migration Service (AWS DMS).
305. A company is designing a shared storage solution for a gaming application that is hosted in the AWS Cloud. The company needs the ability to use SMB clients to access data. The solution must be fully managed.
     Which AWS solution meets these requirements?
     A. Create an AWS DataSync task that shares the data as a mountable le system. Mount the le system to the application server.
     B. Create an Amazon EC2 Windows instance. Install and congure a Windows le share role on the instance. Connect the application server to the le share.
     C. Create an Amazon FSx for Windows File Server le system. Attach the le system to the origin server. Connect the application server to the le system.
     D. Create an Amazon S3 bucket. Assign an IAM role to the application to grant access to the S3 bucket. Mount the S3 bucket to the application server.
306. A company wants to run an in-memory database for a latency-sensitive application that runs on Amazon EC2 instances. The application processes more than 100,000 transactions each minute and requires high network throughput. A solutions architect needs to provide a cost- effective network design that minimizes data transfer charges.
     Which solution meets these requirements?
     A. Launch all EC2 instances in the same Availability Zone within the same AWS Region. Specify a placement group with cluster strategy when launching EC2 instances.
     B. Launch all EC2 instances in different Availability Zones within the same AWS Region. Specify a placement group with partition strategy when launching EC2 instances.
     C. Deploy an Auto Scaling group to launch EC2 instances in different Availability Zones based on a network utilization target.
     D. Deploy an Auto Scaling group with a step scaling policy to launch EC2 instances in different Availability Zones.
307. A company that primarily runs its application servers on premises has decided to migrate to AWS. The company wants to minimize its need to scale its Internet Small Computer Systems Interface (iSCSI) storage on premises. The company wants only its recently accessed data to remain stored locally.
     Which AWS solution should the company use to meet these requirements?
     A. Amazon S3 File Gateway
     B. AWS Storage Gateway Tape Gateway
     C. AWS Storage Gateway Volume Gateway stored volumes
     D. AWS Storage Gateway Volume Gateway cached volumes
308. A company has multiple AWS accounts that use consolidated billing. The company runs several active high performance Amazon RDS for Oracle On-Demand DB instances for 90 days. The company’s nance team has access to AWS Trusted Advisor in the consolidated billing account and all other AWS accounts.
     The nance team needs to use the appropriate AWS account to access the Trusted Advisor check recommendations for RDS. The nance team must review the appropriate Trusted Advisor check to reduce RDS costs.
     Which combination of steps should the nance team take to meet these requirements? (Choose two.)

A. Use the Trusted Advisor recommendations from the account where the RDS instances are running.
B. Use the Trusted Advisor recommendations from the consolidated billing account to see all RDS instance checks at the same time.
C. Review the Trusted Advisor check for Amazon RDS Reserved Instance Optimization.
D. Review the Trusted Advisor check for Amazon RDS Idle DB Instances.
E. Review the Trusted Advisor check for Amazon Redshift Reserved Node Optimization.

309. A solutions architect needs to optimize storage costs. The solutions architect must identify any Amazon S3 buckets that are no longer being accessed or are rarely accessed.
     Which solution will accomplish this goal with the LEAST operational overhead?

A. Analyze bucket access patterns by using the S3 Storage Lens dashboard for advanced activity metrics.
B. Analyze bucket access patterns by using the S3 dashboard in the AWS Management Console.
C. Turn on the Amazon CloudWatch BucketSizeBytes metric for buckets. Analyze bucket access patterns by using the metrics data with Amazon Athena.
D. Turn on AWS CloudTrail for S3 object monitoring. Analyze bucket access patterns by using CloudTrail logs that are integrated with Amazon CloudWatch Logs.

310. A company sells datasets to customers who do research in articial intelligence and machine learning (AI/ML). The datasets are large, formatted les that are stored in an Amazon S3 bucket in the us-east-1 Region. The company hosts a web application that the customers use to purchase access to a given dataset. The web application is deployed on multiple Amazon EC2 instances behind an Application Load Balancer. After a purchase is made, customers receive an S3 signed URL that allows access to the les.
     The customers are distributed across North America and Europe. The company wants to reduce the cost that is associated with data transfers and wants to maintain or improve performance.
     What should a solutions architect do to meet these requirements?
     A. Congure S3 Transfer Acceleration on the existing S3 bucket. Direct customer requests to the S3 Transfer Acceleration endpoint. Continue to use S3 signed URLs for access control.
     B. Deploy an Amazon CloudFront distribution with the existing S3 bucket as the origin. Direct customer requests to the CloudFront URL. Switch to CloudFront signed URLs for access control.
     C. Set up a second S3 bucket in the eu-central-1 Region with S3 Cross-Region Replication between the buckets. Direct customer requests to the closest Region. Continue to use S3 signed URLs for access control.
     D. Modify the web application to enable streaming of the datasets to end users. Congure the web application to read the data from the existing S3 bucket. Implement access control directly in the application.
311. A company is using AWS to design a web application that will process insurance quotes. Users will request quotes from the application. Quotes must be separated by quote type, must be responded to within 24 hours, and must not get lost. The solution must maximize operational eciency and must minimize maintenance.
     Which solution meets these requirements
     A. Create multiple Amazon Kinesis data streams based on the quote type. Congure the web application to send messages to the proper data stream. Congure each backend group of application servers to use the Kinesis Client Library (KCL) to pool messages from its own data stream.
     B. Create an AWS Lambda function and an Amazon Simple Notication Service (Amazon SNS) topic for each quote type. Subscribe the Lambda function to its associated SNS topic. Congure the application to publish requests for quotes to the appropriate SNS topic.
     C. Create a single Amazon Simple Notication Service (Amazon SNS) topic. Subscribe Amazon Simple Queue Service (Amazon SQS) queues to the SNS topic. Congure SNS message ltering to publish messages to the proper SQS queue based on the quote type. Congure each backend application server to use its own SQS queue.
     D. Create multiple Amazon Kinesis Data Firehose delivery streams based on the quote type to deliver data streams to an Amazon OpenSearch Service cluster. Congure the application to send messages to the proper delivery stream. Congure each backend group of application servers to search for the messages from OpenSearch Service and process them accordingly.
312. A company has an application that runs on several Amazon EC2 instances. Each EC2 instance has multiple Amazon Elastic Block Store (Amazon EBS) data volumes attached to it. The application’s EC2 instance conguration and data need to be backed up nightly. The application also needs to be recoverable in a different AWS Region.
     Which solution will meet these requirements in the MOST operationally ecient way?
     A. Write an AWS Lambda function that schedules nightly snapshots of the application’s EBS volumes and copies the snapshots to a different Region.
     B. Create a backup plan by using AWS Backup to perform nightly backups. Copy the backups to another Region. Add the application’s EC2 instances as resources.
     C. Create a backup plan by using AWS Backup to perform nightly backups. Copy the backups to another Region. Add the application’s EBS volumes as resources.
     D. Write an AWS Lambda function that schedules nightly snapshots of the application's EBS volumes and copies the snapshots to a different Availability Zone.
313. A company is building a mobile app on AWS. The company wants to expand its reach to millions of users. The company needs to build a platform so that authorized users can watch the company’s content on their mobile devices.
     What should a solutions architect recommend to meet these requirements?
     A. Publish content to a public Amazon S3 bucket. Use AWS Key Management Service (AWS KMS) keys to stream content.
     B. Set up IPsec VPN between the mobile app and the AWS environment to stream content.
     C. Use Amazon CloudFront. Provide signed URLs to stream content.
     D. Set up AWS Client VPN between the mobile app and the AWS environment to stream content.
314. A company has an on-premises MySQL database used by the global sales team with infrequent access patterns. The sales team requires the database to have minimal downtime. A database administrator wants to migrate this database to AWS without selecting a particular instance type in anticipation of more users in the future.
     Which service should a solutions architect recommend?
     A. Amazon Aurora MySQL
     B. Amazon Aurora Serverless for MySQL
     C. Amazon Redshift Spectrum
     D. Amazon RDS for MySQL
315. A company experienced a breach that affected several applications in its on-premises data center. The attacker took advantage of vulnerabilities in the custom applications that were running on the servers. The company is now migrating its applications to run on Amazon EC2 instances. The company wants to implement a solution that actively scans for vulnerabilities on the EC2 instances and sends a report that details the ndings.
     Which solution will meet these requirements?
     A. Deploy AWS Shield to scan the EC2 instances for vulnerabilities. Create an AWS Lambda function to log any ndings to AWS CloudTrail.
     B. Deploy Amazon Macie and AWS Lambda functions to scan the EC2 instances for vulnerabilities. Log any ndings to AWS CloudTrail.
     C. Turn on Amazon GuardDuty. Deploy the GuardDuty agents to the EC2 instances. Congure an AWS Lambda function to automate the generation and distribution of reports that detail the ndings.
     D. Turn on Amazon Inspector. Deploy the Amazon Inspector agent to the EC2 instances. Congure an AWS Lambda function to automate the generation and distribution of reports that detail the ndings
316. A company uses an Amazon EC2 instance to run a script to poll for and process messages in an Amazon Simple Queue Service (Amazon SQS) queue. The company wants to reduce operational costs while maintaining its ability to process a growing number of messages that are added to the queue.
     What should a solutions architect recommend to meet these requirements?
     A. Increase the size of the EC2 instance to process messages faster.
     B. Use Amazon EventBridge to turn off the EC2 instance when the instance is underutilized.
     C. Migrate the script on the EC2 instance to an AWS Lambda function with the appropriate runtime. 
     D. Use AWS Systems Manager Run Command to run the script on demand.      
317. A company uses a legacy application to produce data in CSV format. The legacy application stores the output data in Amazon S3. The company is deploying a new commercial off-the-shelf (COTS) application that can perform complex SQL queries to analyze data that is stored in Amazon Redshift and Amazon S3 only. However, the COTS application cannot process the .csv les that the legacy application produces.
     The company cannot update the legacy application to produce data in another format. The company needs to implement a solution so that the COTS application can use the data that the legacy application produces.
     Which solution will meet these requirements with the LEAST operational overhead?
     A. Create an AWS Glue extract, transform, and load (ETL) job that runs on a schedule. Congure the ETL job to process the .csv les and store the processed data in Amazon Redshift.
     B. Develop a Python script that runs on Amazon EC2 instances to convert the .csv les to .sql les. Invoke the Python script on a cron schedule to store the output les in Amazon S3.
     C. Create an AWS Lambda function and an Amazon DynamoDB table. Use an S3 event to invoke the Lambda function. Congure the Lambda function to perform an extract, transform, and load (ETL) job to process the .csv les and store the processed data in the DynamoDB table.
     D. Use Amazon EventBridge to launch an Amazon EMR cluster on a weekly schedule. Congure the EMR cluster to perform an extract, transform, and load (ETL) job to process the .csv les and store the processed data in an Amazon Redshift table
318. A company recently migrated its entire IT environment to the AWS Cloud. The company discovers that users are provisioning oversized Amazon EC2 instances and modifying security group rules without using the appropriate change control process. A solutions architect must devise a strategy to track and audit these inventory and conguration changes.
     Which actions should the solutions architect take to meet these requirements? (Choose two.)
     A. Enable AWS CloudTrail and use it for auditing.
     B. Use data lifecycle policies for the Amazon EC2 instances.
     C. Enable AWS Trusted Advisor and reference the security dashboard.
     D. Enable AWS Cong and create rules for auditing and compliance purposes.
     E. Restore previous resource congurations with an AWS CloudFormation template.
319. A company has hundreds of Amazon EC2 Linux-based instances in the AWS Cloud. Systems administrators have used shared SSH keys to manage the instances. After a recent audit, the company’s security team is mandating the removal of all shared keys. A solutions architect must design a solution that provides secure access to the EC2 instances.
     Which solution will meet this requirement with the LEAST amount of administrative overhead?
     A. Use AWS Systems Manager Session Manager to connect to the EC2 instances.
     B. Use AWS Security Token Service (AWS STS) to generate one-time SSH keys on demand.
     C. Allow shared SSH access to a set of bastion instances. Congure all other instances to allow only SSH access from the bastion instances.
     D. Use an Amazon Cognito custom authorizer to authenticate users. Invoke an AWS Lambda function to generate a temporary SSH key.
320. A company is using a eet of Amazon EC2 instances to ingest data from on-premises data sources. The data is in JSON format and ingestion rates can be as high as 1 MB/s. When an EC2 instance is rebooted, the data in-ight is lost. The company’s data science team wants to query ingested data in near-real time.
     Which solution provides near-real-time data querying that is scalable with minimal data loss?
     A. Publish data to Amazon Kinesis Data Streams, Use Kinesis Data Analytics to query the data.
     B. Publish data to Amazon Kinesis Data Firehose with Amazon Redshift as the destination. Use Amazon Redshift to query the data.
     C. Store ingested data in an EC2 instance store. Publish data to Amazon Kinesis Data Firehose with Amazon S3 as the destination. Use Amazon Athena to query the data.
     D. Store ingested data in an Amazon Elastic Block Store (Amazon EBS) volume. Publish data to Amazon ElastiCache for Redis. Subscribe to the Redis channel to query the data.
321. What should a solutions architect do to ensure that all objects uploaded to an Amazon S3 bucket are encrypted?
     A. Update the bucket policy to deny if the PutObject does not have an s3:x-amz-acl header set.
     B. Update the bucket policy to deny if the PutObject does not have an s3:x-amz-acl header set to private.
     C. Update the bucket policy to deny if the PutObject does not have an aws:SecureTransport header set to true.
     D. Update the bucket policy to deny if the PutObject does not have an x-amz-server-side-encryption header set.
322. A solutions architect is designing a multi-tier application for a company. The application's users upload images from a mobile device. The application generates a thumbnail of each image and returns a message to the user to conrm that the image was uploaded successfully.
     The thumbnail generation can take up to 60 seconds, but the company wants to provide a faster response time to its users to notify them that the original image was received. The solutions architect must design the application to asynchronously dispatch requests to the different application tiers.
     What should the solutions architect do to meet these requirements?

A. Write a custom AWS Lambda function to generate the thumbnail and alert the user. Use the image upload process as an event source to invoke the Lambda function.
B. Create an AWS Step Functions workow. Congure Step Functions to handle the orchestration between the application tiers and alert the user when thumbnail generation is complete.
C. Create an Amazon Simple Queue Service (Amazon SQS) message queue. As images are uploaded, place a message on the SQS queue for thumbnail generation. Alert the user through an application message that the image was received.
D. Create Amazon Simple Notication Service (Amazon SNS) notication topics and subscriptions. Use one subscription with the application to generate the thumbnail after the image upload is complete. Use a second subscription to message the user's mobile app by way of a push notication after thumbnail generation is complete.

323. A company’s facility has badge readers at every entrance throughout the building. When badges are scanned, the readers send a message over HTTPS to indicate who attempted to access that particular entrance.
     A solutions architect must design a system to process these messages from the sensors. The solution must be highly available, and the results must be made available for the company’s security team to analyze.
     Which system architecture should the solutions architect recommend?

A. Launch an Amazon EC2 instance to serve as the HTTPS endpoint and to process the messages. Congure the EC2 instance to save the results to an Amazon S3 bucket.
B. Create an HTTPS endpoint in Amazon API Gateway. Congure the API Gateway endpoint to invoke an AWS Lambda function to process the messages and save the results to an Amazon DynamoDB table.
C. Use Amazon Route 53 to direct incoming sensor messages to an AWS Lambda function. Congure the Lambda function to process the messages and save the results to an Amazon DynamoDB table.
D. Create a gateway VPC endpoint for Amazon S3. Congure a Site-to-Site VPN connection from the facility network to the VPC so that sensor data can be written directly to an S3 bucket by way of the VPC endpoint

324. A company wants to implement a disaster recovery plan for its primary on-premises le storage volume. The le storage volume is mounted from an Internet Small Computer Systems Interface (iSCSI) device on a local storage server. The le storage volume holds hundreds of terabytes (TB) of data.
     The company wants to ensure that end users retain immediate access to all le types from the on-premises systems without experiencing latency.
     Which solution will meet these requirements with the LEAST amount of change to the company's existing infrastructure?
     A. Provision an Amazon S3 File Gateway as a virtual machine (VM) that is hosted on premises. Set the local cache to 10 TB. Modify existing applications to access the les through the NFS protocol. To recover from a disaster, provision an Amazon EC2 instance and mount the S3 bucket that contains the les.
     B. Provision an AWS Storage Gateway tape gateway. Use a data backup solution to back up all existing data to a virtual tape library. Congure the data backup solution to run nightly after the initial backup is complete. To recover from a disaster, provision an Amazon EC2 instance and restore the data to an Amazon Elastic Block Store (Amazon EBS) volume from the volumes in the virtual tape library.
     C. Provision an AWS Storage Gateway Volume Gateway cached volume. Set the local cache to 10 TB. Mount the Volume Gateway cached volume to the existing le server by using iSCSI, and copy all les to the storage volume. Congure scheduled snapshots of the storage volume. To recover from a disaster, restore a snapshot to an Amazon Elastic Block Store (Amazon EBS) volume and attach the EBS volume to an Amazon EC2 instance.
     D. Provision an AWS Storage Gateway Volume Gateway stored volume with the same amount of disk space as the existing le storage volume. Mount the Volume Gateway stored volume to the existing le server by using iSCSI, and copy all les to the storage volume. Congure scheduled snapshots of the storage volume. To recover from a disaster, restore a snapshot to an Amazon Elastic Block Store (Amazon EBS) volume and attach the EBS volume to an Amazon EC2 instance.
325. 














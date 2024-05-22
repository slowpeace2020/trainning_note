1. A company collects data for temperature, humidity, and atmospheric pressure in cities across multiple continents. The average volume of data that the company collects from each site daily is 500 GB. Each site has a high-speed Internet connection.
The company wants to aggregate the data from all these global sites as quickly as possible in a single Amazon S3 bucket. The solution must minimize operational complexity.
Which solution meets these requirements?

> Turn on S3 Transfer Acceleration on the destination S3 bucket. Use multipart uploads to directly upload site data to the destination S3 bucket.


2. A company needs the ability to analyze the log files of its proprietary application. The logs are stored in JSON format in an Amazon S3 bucket. Queries will be simple and will run on-demand. A solutions architect needs to perform the analysis with minimal changes to the existing architecture.
   What should the solutions architect do to meet these requirements with the LEAST amount of operational overhead?  

> Use Amazon Athena directly with Amazon S3 to run the queries as needed.

3. A company uses AWS Organizations to manage multiple AWS accounts for different departments. The management account has an Amazon S3 bucket that contains project reports. The company wants to limit access to this S3 bucket to only users of accounts within the organization in AWS Organizations.
Which solution meets these requirements with the LEAST amount of operational overhead?

> Add the aws PrincipalOrgID global condition key with a reference to the organization ID to the S3 bucket policy.

4. An application runs on an Amazon EC2 instance in a VPC. The application processes logs that are stored in an Amazon S3 bucket. The EC2 instance needs to access the S3 bucket without connectivity to the internet.
Which solution will provide private network connectivity to Amazon S3?

> Create a gateway VPC endpoint to the S3 bucket.

5. A company is hosting a web application on AWS using a single Amazon EC2 instance that stores user-uploaded documents in an Amazon EBS volume. For better scalability and availability, the company duplicated the architecture and created a second EC2 instance and EBS volume in another Availability Zone, placing both behind an Application Load Balancer. After completing this change, users reported that, each time they refreshed the website, they could see one subset of their documents or the other, but never all of the documents at the same time.
What should a solutions architect propose to ensure users see all of their documents at once?

> Copy the data from both EBS volumes to Amazon EFS. Modify the application to save new documents to Amazon EFS


6. A company uses NFS to store large video les in on-premises network attached storage. Each video le ranges in size from 1 MB to 500 GB. The total storage is 70 TB and is no longer growing. The company decides to migrate the video les to Amazon S3. The company must migrate the video les as soon as possible while using the least possible network bandwidth.
Which solution will meet these requirements?

> Deploy an S3 File Gateway on premises. Create a public service endpoint to connect to the S3 File Gateway. Create an S3 bucket. Create a new NFS le share on the S3 File Gateway. Point the new le share to the S3 bucket. Transfer the data from the existing NFS le share to the S3 File Gateway.


7. A company has an application that ingests incoming messages. Dozens of other applications and microservices then quickly consume these messages. The number of messages varies drastically and sometimes increases suddenly to 100,000 each second. The company wants to decouple the solution and increase scalability.
Which solution meets these requirements?

> Persist the messages to Amazon Kinesis Data Analytics. Configure the consumer applications to read and process the messages.


8. A company is migrating a distributed application to AWS. The application serves variable workloads. The legacy platform consists of a primary server that coordinates jobs across multiple compute nodes. The company wants to modernize the application with a solution that maximizes resiliency and scalability.
How should a solutions architect design the architecture to meet these requirements?

> Implement the primary server and the compute nodes with Amazon EC2 instances that are managed in an Auto Scaling group. Configure AWS CloudTrail as a destination for the jobs. Configure EC2 Auto Scaling based on the load on the primary server.

9. A company is running an SMB file server in its data center. The file server stores large file that are accessed frequently for the first few days after the files are created. After 7 days the file are rarely accessed.
   The total data size is increasing and is close to the company's total storage capacity. A solutions architect must increase the company's available storage space without losing low-latency access to the most recently accessed files. The solutions architect must also provide file lifecycle management to avoid future storage issues.
   Which solution will meet these requirements?

> Install a utility on each user's computer to access Amazon S3. Create an S3 Lifecycle policy to transition the data to S3 Glacier Flexible Retrieval after 7 days.

10. A company is building an ecommerce web application on AWS. The application sends information about new orders to an Amazon API Gateway REST API to process. The company wants to ensure that orders are processed in the order that they are received.
Which solution will meet these requirements?

> Use an API Gateway integration to send a message to an Amazon Simple Queue Service (Amazon SQS) FIFO queue when the application receives an order. Configure the SQS FIFO queue to invoke an AWS Lambda function for processing.

11. A company has an application that runs on Amazon EC2 instances and uses an Amazon Aurora database. The EC2 instances connect to the database by using user names and passwords that are stored locally in a le. The company wants to minimize the operational overhead of credential management.
    What should a solutions architect do to accomplish this goal?

> Use AWS Systems Manager Parameter Store. Turn on automatic rotation.

12. A global company hosts its web application on Amazon EC2 instances behind an Application Load Balancer (ALB). The web application has static data and dynamic data. The company stores its static data in an Amazon S3 bucket. The company wants to improve performance and reduce latency for the static data and dynamic data. The company is using its own domain name registered with Amazon Route 53.
What should a solutions architect do to meet these requirements?
> Create an Amazon CloudFront distribution that has the S3 bucket as an origin. Create an AWS Global Accelerator standard accelerator that has the ALB and the CloudFront distribution as endpoints. Create a custom domain name that points to the accelerator DNS name. Use the custom domain name as an endpoint for the web application.

13. A company performs monthly maintenance on its AWS infrastructure. During these maintenance activities, the company needs to rotate the credentials for its Amazon RDS for MySQL databases across multiple AWS Regions.
    Which solution will meet these requirements with the LEAST operational overhead?
> Store the credentials as secrets in AWS Secrets Manager. Use multi-Region secret replication for the required Regions. Congure Secrets Manager to rotate the secrets on a schedule.

14. A company runs an ecommerce application on Amazon EC2 instances behind an Application Load Balancer. The instances run in an Amazon EC2 Auto Scaling group across multiple Availability Zones. The Auto Scaling group scales based on CPU utilization metrics. The ecommerce application stores the transaction data in a MySQL 8.0 database that is hosted on a large EC2 instance.
    The database's performance degrades quickly as application load increases. The application handles more read requests than write transactions. The company wants a solution that will automatically scale the database to meet the demand of unpredictable read workloads while maintaining high availability.
    Which solution will meet these requirements?
> Use Amazon Aurora with a Multi-AZ deployment. Congure Aurora Auto Scaling with Aurora Replicas.

15. A company recently migrated to AWS and wants to implement a solution to protect the trac that ows in and out of the production VPC. The company had an inspection server in its on-premises data center. The inspection server performed specic operations such as trac ow inspection and trac ltering. The company wants to have the same functionalities in the AWS Cloud.
    Which solution will meet these requirements?
> Use AWS Network Firewall to create the required rules for trac inspection and trac ltering for the production VPC.

16. A company hosts a data lake on AWS. The data lake consists of data in Amazon S3 and Amazon RDS for PostgreSQL. The company needs a reporting solution that provides data visualization and includes all the data sources within the data lake. Only the company's management team should have full access to all the visualizations. The rest of the company should have only limited access.
    Which solution will meet these requirements?
>   Create an AWS Glue table and crawler for the data in Amazon S3. Use Amazon Athena Federated Query to access data within Amazon RDS for PostgreSQL. Generate reports by using Amazon Athena. Publish the reports to Amazon S3. Use S3 bucket policies to limit access to the reports.
17. A company is implementing a new business application. The application runs on two Amazon EC2 instances and uses an Amazon S3 bucket for document storage. A solutions architect needs to ensure that the EC2 instances can access the S3 bucket.
    What should the solutions architect do to meet this requirement?
>  Create an IAM role that grants access to the S3 bucket. Attach the role to the EC2 instances.

18. An application development team is designing a microservice that will convert large images to smaller, compressed images. When a user uploads an image through the web interface, the microservice should store the image in an Amazon S3 bucket, process and compress the image with an AWS Lambda function, and store the image in its compressed form in a different S3 bucket.
    A solutions architect needs to design a solution that uses durable, stateless components to process the images automatically.
    Which combination of actions will meet these requirements? (Choose two.)
>   Create an Amazon Simple Queue Service (Amazon SQS) queue. Congure the S3 bucket to send a notication to the SQS queue when an image is uploaded to the S3 bucket.
    Congure the Lambda function to use the Amazon Simple Queue Service (Amazon SQS) queue as the invocation source. When the SQS message is successfully processed, delete the message in the queue.
19. A company has a three-tier web application that is deployed on AWS. The web servers are deployed in a public subnet in a VPC. The application servers and database servers are deployed in private subnets in the same VPC. The company has deployed a third-party virtual firewall appliance from AWS Marketplace in an inspection VPC. The appliance is configured with an IP interface that can accept IP packets. A solutions architect needs to integrate the web application with the appliance to inspect all traffic to the application before the traffic reaches the web server.
    Which solution will meet these requirements with the LEAST operational overhead?
> Deploy a Gateway Load Balancer in the inspection VPC. Create a Gateway Load Balancer endpoint to receive the incoming packets and forward the packets to the appliance.

20. A company wants to improve its ability to clone large amounts of production data into a test environment in the same AWS Region. The data is stored in Amazon EC2 instances on Amazon Elastic Block Store (Amazon EBS) volumes. Modications to the cloned data must not affect the production environment. The software that accesses this data requires consistently high I/O performance.
> Take EBS snapshots of the production EBS volumes. Turn on the EBS fast snapshot restore feature on the EBS snapshots. Restore the snapshots into new EBS volumes. Attach the new EBS volumes to EC2 instances in the test environment.

21. An ecommerce company wants to launch a one-deal-a-day website on AWS. Each day will feature exactly one product on sale for a period of 24 hours. The company wants to be able to handle millions of requests each hour with millisecond latency during peak hours.
    Which solution will meet these requirements with the LEAST operational overhead?
> Use an Amazon S3 bucket to host the website's static content. Deploy an Amazon CloudFront distribution. Set the S3 bucket as the origin. Use Amazon API Gateway and AWS Lambda functions for the backend APIs. Store the data in Amazon DynamoDB.

22. A solutions architect is using Amazon S3 to design the storage architecture of a new digital media application. The media les must be resilient to the loss of an Availability Zone. Some les are accessed frequently while other les are rarely accessed in an unpredictable pattern. The solutions architect must minimize the costs of storing and retrieving the media les.
    Which storage option meets these requirements?
> S3 Intelligent-Tiering

23. A company is storing backup les by using Amazon S3 Standard storage. The les are accessed frequently for 1 month. However, the les are not accessed after 1 month. The company must keep the les indenitely.
    Which storage solution will meet these requirements MOST cost-effectively?
> Create an S3 Lifecycle conguration to transition objects from S3 Standard to S3 Glacier Deep Archive after 1 month.

24. A  company observes an increase in Amazon EC2 costs in its most recent bill. The billing team notices unwanted vertical scaling of instance types for a couple of EC2 instances. A solutions architect needs to create a graph comparing the last 2 months of EC2 costs and perform an in-depth analysis to identify the root cause of the vertical scaling.
How should the solutions architect generate the information with the LEAST operational overhead?
> Use Cost Explorer's granular ltering feature to perform an in-depth analysis of EC2 costs based on instance types.

25. A company is designing an application. The application uses an AWS Lambda function to receive information through Amazon API Gateway and to store the information in an Amazon Aurora PostgreSQL database.
    During the proof-of-concept stage, the company has to increase the Lambda quotas signicantly to handle the high volumes of data that the company needs to load into the database. A solutions architect must recommend a new design to improve scalability and minimize the conguration effort.
    Which solution will meet these requirements?
> Set up two Lambda functions. Congure one function to receive the information. Congure the other function to load the information into the database. Integrate the Lambda functions by using an Amazon Simple Queue Service (Amazon SQS) queue.
26. A company needs to review its AWS Cloud deployment to ensure that its Amazon S3 buckets do not have unauthorized conguration changes. What should a solutions architect do to accomplish this goal?
> Turn on AWS Cong with the appropriate rules.

27. A company is launching a new application and will display application metrics on an Amazon CloudWatch dashboard. The company's product manager needs to access this dashboard periodically. The product manager does not have an AWS account. A solutions architect must provide access to the product manager by following the principle of least privilege.
    Which solution will meet these requirements?
> Share the dashboard from the CloudWatch console. Enter the product manager's email address, and complete the sharing steps. Provide a shareable link for the dashboard to the product manager.
28. A company is migrating applications to AWS. The applications are deployed in different accounts. The company manages the accounts centrally by using AWS Organizations. The company's security team needs a single sign-on (SSO) solution across all the company's accounts. The company must continue managing the users and groups in its on-premises self-managed Microsoft Active Directory.
    Which solution will meet these requirements?
> B. Enable AWS Single Sign-On (AWS SSO) from the AWS SSO console. Create a two-way forest trust to connect the company's self-managed Microsoft Active Directory with AWS SSO by using AWS Directory Service for Microsoft Active Directory.
29. A company provides a Voice over Internet Protocol (VoIP) service that uses UDP connections. The service consists of Amazon EC2 instances that run in an Auto Scaling group. The company has deployments across multiple AWS Regions.
    The company needs to route users to the Region with the lowest latency. The company also needs automated failover between Regions. Which solution will meet these requirements?
>    A. Deploy a Network Load Balancer (NLB) and an associated target group. Associate the target group with the Auto Scaling group. Use the NLB as an AWS Global Accelerator endpoint in each Region.
30. A development team runs monthly resource-intensive tests on its general purpose Amazon RDS for MySQL DB instance with Performance Insights enabled. The testing lasts for 48 hours once a month and is the only process that uses the database. The team wants to reduce the cost of running the tests without reducing the compute and memory attributes of the DB instance.
>    Create a snapshot when tests are completed. Terminate the DB instance and restore the snapshot when required.

31. A company that hosts its web application on AWS wants to ensure all Amazon EC2 instances. Amazon RDS DB instances. and Amazon Redshift clusters are congured with tags. The company wants to minimize the effort of conguring and operating this check.
    What should a solutions architect do to accomplish this?
> Use AWS Cong rules to dene and detect resources that are not properly tagged.

32. A development team needs to host a website that will be accessed by other teams. The website contents consist of HTML, CSS, client-side JavaScript, and images.
    Which method is the MOST cost-effective for hosting the website?
> Create an Amazon S3 bucket and host the website there.

33. A company runs an online marketplace web application on AWS. The application serves hundreds of thousands of users during peak hours. The company needs a scalable, near-real-time solution to share the details of millions of nancial transactions with several other internal applications. Transactions also need to be processed to remove sensitive data before being stored in a document database for low-latency retrieval.
    What should a solutions architect recommend to meet these requirements?
> Stream the transactions data into Amazon Kinesis Data Streams. Use AWS Lambda integration to remove sensitive data from every transaction and then store the transactions data in Amazon DynamoDB. Other applications can consume the transactions data off the Kinesis data stream.

34. A company runs an online marketplace web application on AWS. The application serves hundreds of thousands of users during peak hours. The company needs a scalable, near-real-time solution to share the details of millions of nancial transactions with several other internal applications. Transactions also need to be processed to remove sensitive data before being stored in a document database for low-latency retrieval.
    What should a solutions architect recommend to meet these requirements?
>  Stream the transactions data into Amazon Kinesis Data Streams. Use AWS Lambda integration to remove sensitive data from every transaction and then store the transactions data in Amazon DynamoDB. Other applications can consume the transactions data off the Kinesis data stream.

35. A company is preparing to launch a public-facing web application in the AWS Cloud. The architecture consists of Amazon EC2 instances within a VPC behind an Elastic Load Balancer (ELB). A third-party service is used for the DNS. The company's solutions architect must recommend a solution to detect and protect against large-scale DDoS attacks.
    Which solution meets these requirements?
> Enable AWS Shield Advanced and assign the ELB to it.

36. ? A company is building an application in the AWS Cloud. The application will store data in Amazon S3 buckets in two AWS Regions. The company must use an AWS Key Management Service (AWS KMS) customer managed key to encrypt all data that is stored in the S3 buckets. The data in both S3 buckets must be encrypted and decrypted with the same KMS key. The data and the key must be stored in each of the two Regions.
Which solution will meet these requirements with the LEAST operational overhead?
A. Create an S3 bucket in each Region. Congure the S3 buckets to use server-side encryption with Amazon S3 managed encryption keys (SSE-S3). Congure replication between the S3 buckets.
B. Create a customer managed multi-Region KMS key. Create an S3 bucket in each Region. Congure replication between the S3 buckets. Congure the application to use the KMS key with client-side encryption.
C. Create a customer managed KMS key and an S3 bucket in each Region. Congure the S3 buckets to use server-side encryption with Amazon S3 managed encryption keys (SSE-S3). Congure replication between the S3 buckets.
D. Create a customer managed KMS key and an S3 bucket in each Region. Congure the S3 buckets to use server-side encryption with AWS KMS keys (SSE-KMS). Congure replication between the S3 buckets.

37. A company recently launched a variety of new workloads on Amazon EC2 instances in its AWS account. The company needs to create a strategy to access and administer the instances remotely and securely. The company needs to implement a repeatable process that works with native AWS services and follows the AWS Well-Architected Framework.
    Which solution will meet these requirements with the LEAST operational overhead?
> Attach the appropriate IAM role to each existing instance and new instance. Use AWS Systems Manager Session Manager to establish a remote SSH session.

38. A company is hosting a static website on Amazon S3 and is using Amazon Route 53 for DNS. The website is experiencing increased demand from around the world. The company must decrease latency for users who access the website.
> Add an Amazon CloudFront distribution in front of the S3 bucket. Edit the Route 53 entries to point to the CloudFront distribution.

39. A company maintains a searchable repository of items on its website. The data is stored in an Amazon RDS for MySQL database table that contains more than 10 million rows. The database has 2 TB of General Purpose SSD storage. There are millions of updates against this data every day through the company's website.
The company has noticed that some insert operations are taking 10 seconds or longer. The company has determined that the database storage performance is the problem.
Which solution addresses this performance issue?
> Change the storage type to Provisioned IOPS SSD.

40. A company has thousands of edge devices that collectively generate 1 TB of status alerts each day. Each alert is approximately 2 KB in size. A solutions architect needs to implement a solution to ingest and store the alerts for future analysis.
    The company wants a highly available solution. However, the company needs to minimize costs and does not want to manage additional infrastructure. Additionally, the company wants to keep 14 days of data available for immediate analysis and archive any data older than 14 days.
    What is the MOST operationally ecient solution that meets these requirements?
> Create an Amazon Kinesis Data Firehose delivery stream to ingest the alerts. Congure the Kinesis Data Firehose stream to deliver the alerts to an Amazon S3 bucket. Set up an S3 Lifecycle conguration to transition data to Amazon S3 Glacier after 14 days.

41. A company's application integrates with multiple software-as-a-service (SaaS) sources for data collection. The company runs Amazon EC2 instances to receive the data and to upload the data to an Amazon S3 bucket for analysis. The same EC2 instance that receives and uploads the data also sends a notication to the user when an upload is complete. The company has noticed slow application performance and wants to improve the performance as much as possible.
    Which solution will meet these requirements with the LEAST operational overhead?
> Create an Amazon AppFlow ow to transfer data between each SaaS source and the S3 bucket. Congure an S3 event notication to send events to an Amazon Simple Notication Service (Amazon SNS) topic when the upload to the S3 bucket is complete.

42. A company runs a highly available image-processing application on Amazon EC2 instances in a single VPC. The EC2 instances run inside several subnets across multiple Availability Zones. The EC2 instances do not communicate with each other. However, the EC2 instances download images from Amazon S3 and upload images to Amazon S3 through a single NAT gateway. The company is concerned about data transfer charges.
    What is the MOST cost-effective way for the company to avoid Regional data transfer charges?
> Deploy a gateway VPC endpoint for Amazon S3.

43. A company has an on-premises application that generates a large amount of time-sensitive data that is backed up to Amazon S3. The application has grown and there are user complaints about internet bandwidth limitations. A solutions architect needs to design a long-term solution that allows for both timely backups to Amazon S3 and with minimal impact on internet connectivity for internal users.
    Which solution meets these requirements?
> Establish a new AWS Direct Connect connection and direct backup trac through this new connection.

44. A company has an Amazon S3 bucket that contains critical data. The company must protect the data from accidental deletion. Which combination of steps should a solutions architect take to meet these requirements? (Choose two.)
> Enable versioning on the S3 bucket.
  Enable MFA Delete on the S3 bucket.

45. A company has a data ingestion workflow that consists of the following:
    • An Amazon Simple Notication Service (Amazon SNS) topic for notications about new data deliveries
    • An AWS Lambda function to process the data and record metadata
    The company observes that the ingestion workow fails occasionally because of network connectivity issues. When such a failure occurs, the Lambda function does not ingest the corresponding data unless the company manually reruns the job.
    Which combination of actions should a solutions architect take to ensure that the Lambda function ingests all data in the future? (Choose two.)

> Create an Amazon Simple Queue Service (Amazon SQS) queue, and subscribe it to the SNS topic.
  Modify the Lambda function to read from an Amazon Simple Queue Service (Amazon SQS) queue.

46. A company has an application that provides marketing services to stores. The services are based on previous purchases by store customers. The stores upload transaction data to the company through SFTP, and the data is processed and analyzed to generate new marketing offers. Some of the les can exceed 200 GB in size.
    Recently, the company discovered that some of the stores have uploaded les that contain personally identiable information (PII) that should not have been included. The company wants administrators to be alerted if PII is shared again. The company also wants to automate remediation.
    What should a solutions architect do to meet these requirements with the LEAST development effort?
> Use an Amazon S3 bucket as a secure transfer point. Use Amazon Macie to scan the objects in the bucket. If objects contain PII, use Amazon Simple Notication Service (Amazon SNS) to trigger a notication to the administrators to remove the objects that contain PII.

47. A company needs guaranteed Amazon EC2 capacity in three specic Availability Zones in a specic AWS Region for an upcoming event that will last 1 week.
    What should the company do to guarantee the EC2 capacity?
> Create an On-Demand Capacity Reservation that species the Region and three Availability Zones needed.

48. A company's website uses an Amazon EC2 instance store for its catalog of items. The company wants to make sure that the catalog is highly available and that the catalog is stored in a durable location.
    What should a solutions architect do to meet these requirements?
> Move the catalog to Amazon ElastiCache for Redis.

49. A company stores call transcript les on a monthly basis. Users access the les randomly within 1 year of the call, but users access the les infrequently after 1 year. The company wants to optimize its solution by giving users the ability to query and retrieve les that are less than 1- year-old as quickly as possible. A delay in retrieving older les is acceptable.
    Which solution will meet these requirements MOST cost-effectively?
> Store individual les in Amazon S3 Intelligent-Tiering. Use S3 Lifecycle policies to move the les to S3 Glacier Flexible Retrieval after 1 year. Query and retrieve the les that are in Amazon S3 by using Amazon Athena. Query and retrieve the les that are in S3 Glacier by using S3 Glacier Select.

50. A company has a production workload that runs on 1,000 Amazon EC2 Linux instances. The workload is powered by third-party software. The company needs to patch the third-party software on all EC2 instances as quickly as possible to remediate a critical security vulnerability. What should a solutions architect do to meet these requirements?
> Use AWS Systems Manager Run Command to run a custom command that applies the patch to all EC2 instances.

51. A company is developing an application that provides order shipping statistics for retrieval by a REST API. The company wants to extract the shipping statistics, organize the data into an easy-to-read HTML format, and send the report to several email addresses at the same time every morning.
    Which combination of steps should a solutions architect take to meet these requirements? (Choose two.)
>    B. Use Amazon Simple Email Service (Amazon SES) to format the data and to send the report by email.
    D. Create an Amazon EventBridge (Amazon CloudWatch Events) scheduled event that invokes an AWS Lambda function to query the application's API for the data.

52. A company wants to migrate its on-premises application to AWS. The application produces output les that vary in size from tens of gigabytes to hundreds of terabytes. The application data must be stored in a standard le system structure. The company wants a solution that scales automatically. is highly available, and requires minimum operational overhead.
    Which solution will meet these requirements?
> Migrate the application to Amazon EC2 instances in a Multi-AZ Auto Scaling group. Use Amazon Elastic File System (Amazon EFS) for storage.

53. A company needs to store its accounting records in Amazon S3. The records must be immediately accessible for 1 year and then must be archived for an additional 9 years. No one at the company, including administrative users and root users, can be able to delete the records during the entire 10-year period. The records must be stored with maximum resiliency.
> Use an S3 Lifecycle policy to transition the records from S3 Standard to S3 Glacier Deep Archive after 1 year. Use S3 Object Lock in compliance mode for a period of 10 years.

54. A company runs multiple Windows workloads on AWS. The company's employees use Windows le shares that are hosted on two Amazon EC2 instances. The le shares synchronize data between themselves and maintain duplicate copies. The company wants a highly available and durable storage solution that preserves how users currently access the les.
    What should a solutions architect do to meet these requirements?
> Extend the le share environment to Amazon FSx for Windows File Server with a Multi-AZ conguration. Migrate all the data to FSx for Windows File Server.

55. A solutions architect is developing a VPC architecture that includes multiple subnets. The architecture will host applications that use Amazon EC2 instances and Amazon RDS DB instances. The architecture consists of six subnets in two Availability Zones. Each Availability Zone includes a public subnet, a private subnet, and a dedicated subnet for databases. Only EC2 instances that run in the private subnets can have access to the RDS databases.
    Which solution will meet these requirements?
> Create a security group that allows inbound trac from the security group that is assigned to instances in the private subnets. Attach the security group to the DB instances.

56. A company has registered its domain name with Amazon Route 53. The company uses Amazon API Gateway in the ca-central-1 Region as a public interface for its backend microservice APIs. Third-party services consume the APIs securely. The company wants to design its API Gateway URL with the company's domain name and corresponding certicate so that the third-party services can use HTTPS.
    Which solution will meet these requirements?
> Create a Regional API Gateway endpoint. Associate the API Gateway endpoint with the company's domain name. Import the public certicate associated with the company's domain name into AWS Certicate Manager (ACM) in the same Region. Attach the certicate to the API Gateway endpoint. Congure Route 53 to route trac to the API Gateway endpoint.

57. A company is running a popular social media website. The website gives users the ability to upload images to share with other users. The company wants to make sure that the images do not contain inappropriate content. The company needs a solution that minimizes development effort.
    What should a solutions architect do to meet these requirements?
> Use Amazon Rekognition to detect inappropriate content. Use human review for low-condence predictions.

58. A company wants to run its critical applications in containers to meet requirements for scalability and availability. The company prefers to focus on maintenance of the critical applications. The company does not want to be responsible for provisioning and managing the underlying infrastructure that runs the containerized workload.
    What should a solutions architect do to meet these requirements?
> Use Amazon Elastic Container Service (Amazon ECS) on AWS Fargate.

59. A company hosts more than 300 global websites and applications. The company requires a platform to analyze more than 30 TB of clickstream data each day.
    What should a solutions architect do to transmit and process the clickstream data?
>  Collect the data from Amazon Kinesis Data Streams. Use Amazon Kinesis Data Firehose to transmit the data to an Amazon S3 data lake. Load the data in Amazon Redshift for analysis.

60. A company has a website hosted on AWS. The website is behind an Application Load Balancer (ALB) that is congured to handle HTTP and HTTPS separately. The company wants to forward all requests to the website so that the requests will use HTTPS.
    What should a solutions architect do to meet this requirement?
>  Create a listener rule on the ALB to redirect HTTP trac to HTTPS.

61. A company is developing a two-tier web application on AWS. The company's developers have deployed the application on an Amazon EC2 instance that connects directly to a backend Amazon RDS database. The company must not hardcode database credentials in the application. The company must also implement a solution to automatically rotate the database credentials on a regular basis.
    Which solution will meet these requirements with the LEAST operational overhead?
> Store the database credentials as a secret in AWS Secrets Manager. Turn on automatic rotation for the secret. Attach the required permission to the EC2 role to grant access to the secret.

62. A company is deploying a new public web application to AWS. The application will run behind an Application Load Balancer (ALB). The application needs to be encrypted at the edge with an SSL/TLS certicate that is issued by an external certicate authority (CA). The certicate must be rotated each year before the certicate expires.
    What should a solutions architect do to meet these requirements?
> Use AWS Certicate Manager (ACM) to import an SSL/TLS certicate. Apply the certicate to the ALB. Use Amazon EventBridge (Amazon CloudWatch Events) to send a notication when the certicate is nearing expiration. Rotate the certicate manually.

63. A company runs its infrastructure on AWS and has a registered base of 700,000 users for its document management application. The company intends to create a product that converts large .pdf les to .jpg image les. The .pdf les average 5 MB in size. The company needs to store the original les and the converted les. A solutions architect must design a scalable solution to accommodate demand that will grow rapidly over time.
    Which solution meets these requirements MOST cost-effectively?
> Save the .pdf les to Amazon S3. Congure an S3 PUT event to invoke an AWS Lambda function to convert the les to .jpg format and store them back in Amazon S3.

64. A company has more than 5 TB of le data on Windows le servers that run on premises. Users and applications interact with the data each day.
    The company is moving its Windows workloads to AWS. As the company continues this process, the company requires access to AWS and on- premises le storage with minimum latency. The company needs a solution that minimizes operational overhead and requires no signicant changes to the existing le access patterns. The company uses an AWS Site-to-Site VPN connection for connectivity to AWS.
    What should a solutions architect do to meet these requirements?
> Deploy and congure Amazon FSx for Windows File Server on AWS. Deploy and congure an Amazon FSx File Gateway on premises. Move the on-premises le data to the FSx File Gateway. Congure the cloud workloads to use FSx for Windows File Server on AWS. Congure the on-premises workloads to use the FSx File Gateway.

65. A hospital recently deployed a RESTful API with Amazon API Gateway and AWS Lambda. The hospital uses API Gateway and Lambda to upload reports that are in PDF format and JPEG format. The hospital needs to modify the Lambda code to identify protected health information (PHI) in the reports.
    Which solution will meet these requirements with the LEAST operational overhead?
> Use Amazon Textract to extract the text from the reports. Use Amazon Comprehend Medical to identify the PHI from the extracted text.

66. A company has an application that generates a large number of les, each approximately 5 MB in size. The les are stored in Amazon S3. Company policy requires the les to be stored for 4 years before they can be deleted. Immediate accessibility is always required as the les contain critical business data that is not easy to reproduce. The les are frequently accessed in the rst 30 days of the object creation but are rarely accessed after the rst 30 days.
Which storage solution is MOST cost-effective?
> Create an S3 bucket lifecycle policy to move les from S3 Standard to S3 Standard-Infrequent Access (S3 Standard-IA) 30 days from object creation. Delete the les 4 years after object creation.
 
67. A company hosts an application on multiple Amazon EC2 instances. The application processes messages from an Amazon SQS queue, writes to an Amazon RDS table, and deletes the message from the queue. Occasional duplicate records are found in the RDS table. The SQS queue does not contain any duplicate messages.
    What should a solutions architect do to ensure messages are being processed once only?
> Use the ChangeMessageVisibility API call to increase the visibility timeout.

68. A solutions architect is designing a new hybrid architecture to extend a company's on-premises infrastructure to AWS. The company requires a highly available connection with consistent low latency to an AWS Region. The company needs to minimize costs and is willing to accept slower trac if the primary connection fails.
    What should the solutions architect do to meet these requirements?
> Provision an AWS Direct Connect connection to a Region. Provision a VPN connection as a backup if the primary Direct Connect connection fails.

69. A company is running a business-critical web application on Amazon EC2 instances behind an Application Load Balancer. The EC2 instances are in an Auto Scaling group. The application uses an Amazon Aurora PostgreSQL database that is deployed in a single Availability Zone. The company wants the application to be highly available with minimum downtime and minimum loss of data.
    Which solution will meet these requirements with the LEAST operational effort?
> Congure the Auto Scaling group to use multiple Availability Zones. Congure the database as Multi-AZ. Congure an Amazon RDS Proxy instance for the database.

70. A company's HTTP application is behind a Network Load Balancer (NLB). The NLB's target group is congured to use an Amazon EC2 Auto Scaling group with multiple EC2 instances that run the web service.
> Replace the NLB with an Application Load Balancer. Enable HTTP health checks by supplying the URL of the company's application. Congure an Auto Scaling action to replace unhealthy instances.

71. A company runs a shopping application that uses Amazon DynamoDB to store customer information. In case of data corruption, a solutions architect needs to design a solution that meets a recovery point objective (RPO) of 15 minutes and a recovery time objective (RTO) of 1 hour. What should the solutions architect recommend to meet these requirements?
> Congure DynamoDB point-in-time recovery. For RPO recovery, restore to the desired point in time.

72. A company runs a photo processing application that needs to frequently upload and download pictures from Amazon S3 buckets that are located in the same AWS Region. A solutions architect has noticed an increased cost in data transfer fees and needs to implement a solution to reduce these costs.
    How can the solutions architect meet this requirement?
> Deploy an S3 VPC gateway endpoint into the VPC and attach an endpoint policy that allows access to the S3 buckets.

73. A company recently launched Linux-based application instances on Amazon EC2 in a private subnet and launched a Linux-based bastion host on an Amazon EC2 instance in a public subnet of a VPC. A solutions architect needs to connect from the on-premises network, through the company's internet connection, to the bastion host, and to the application servers. The solutions architect must make sure that the security groups of all the EC2 instances will allow that access.
    Which combination of steps should the solutions architect take to meet these requirements? (Choose two.)
> Replace the current security group of the bastion host with one that only allows inbound access from the external IP range for the company.
  Replace the current security group of the application instances with one that allows inbound SSH access from only the private IP address of the bastion host.


74. A solutions architect is designing a two-tier web application. The application consists of a public-facing web tier hosted on Amazon EC2 in public subnets. The database tier consists of Microsoft SQL Server running on Amazon EC2 in a private subnet. Security is a high priority for the company.
    How should security groups be congured in this situation? (Choose two.)
> Congure the security group for the web tier to allow inbound trac on port 443 from 0.0.0.0/0.
  Congure the security group for the database tier to allow inbound trac on port 1433 from the security group for the web tier.

75. A company wants to move a multi-tiered application from on premises to the AWS Cloud to improve the application's performance. The application consists of application tiers that communicate with each other by way of RESTful services. Transactions are dropped when one tier becomes overloaded. A solutions architect must design a solution that resolves these issues and modernizes the application.
    Which solution meets these requirements and is the MOST operationally ecient?
> Use Amazon API Gateway and direct transactions to the AWS Lambda functions as the application layer. Use Amazon Simple Queue Service (Amazon SQS) as the communication layer between application services.

76. A company receives 10 TB of instrumentation data each day from several machines located at a single factory. The data consists of JSON les stored on a storage area network (SAN) in an on-premises data center located within the factory. The company wants to send this data to Amazon S3 where it can be accessed by several additional systems that provide critical near-real-time analytics. A secure transfer is important because the data is considered sensitive.
    Which solution offers the MOST reliable data transfer?
> AWS DataSync over AWS Direct Connect

77. A company needs to congure a real-time data ingestion architecture for its application. The company needs an API, a process that transforms data as the data is streamed, and a storage solution for the data.
    Which solution will meet these requirements with the LEAST operational overhead?
> Congure an Amazon API Gateway API to send data to an Amazon Kinesis data stream. Create an Amazon Kinesis Data Firehose delivery stream that uses the Kinesis data stream as a data source. Use AWS Lambda functions to transform the data. Use the Kinesis Data Firehose delivery stream to send the data to Amazon S3.

78. A company needs to keep user transaction data in an Amazon DynamoDB table. The company must retain the data for 7 years. What is the MOST operationally ecient solution that meets these requirements?
> Use AWS Backup to create backup schedules and retention policies for the table.

79. A company is planning to use an Amazon DynamoDB table for data storage. The company is concerned about cost optimization. The table will not be used on most mornings. In the evenings, the read and write trac will often be unpredictable. When trac spikes occur, they will happen very quickly.
    What should a solutions architect recommend?
> Create a DynamoDB table in on-demand capacity mode.

80. A company recently signed a contract with an AWS Managed Service Provider (MSP) Partner for help with an application migration initiative. A solutions architect needs ta share an Amazon Machine Image (AMI) from an existing AWS account with the MSP Partner's AWS account. The AMI is backed by Amazon Elastic Block Store (Amazon EBS) and uses an AWS Key Management Service (AWS KMS) customer managed key to encrypt EBS volume snapshots.
    What is the MOST secure way for the solutions architect to share the AMI with the MSP Partner's AWS account?
> Modify the launchPermission property of the AMI. Share the AMI with the MSP Partner's AWS account only. Modify the key policy to allow the MSP Partner's AWS account to use the key.

81. A solutions architect is designing the cloud architecture for a new application being deployed on AWS. The process should run in parallel while adding and removing application nodes as needed based on the number of jobs to be processed. The processor application is stateless. The solutions architect must ensure that the application is loosely coupled and the job items are durably stored.
    Which design should the solutions architect use?
> Create an Amazon SQS queue to hold the jobs that need to be processed. Create an Amazon Machine Image (AMI) that consists of the processor application. Create a launch template that uses the AMI. Create an Auto Scaling group using the launch template. Set the scaling policy for the Auto Scaling group to add and remove nodes based on the number of items in the SQS queue.

82. ? A company hosts its web applications in the AWS Cloud. The company congures Elastic Load Balancers to use certicates that are imported into AWS Certicate Manager (ACM). The company's security team must be notied 30 days before the expiration of each certicate.
    What should a solutions architect recommend to meet this requirement?
    A. Add a rule in ACM to publish a custom message to an Amazon Simple Notication Service (Amazon SNS) topic every day, beginning 30 days before any certicate will expire.
    B. Create an AWS Cong rule that checks for certicates that will expire within 30 days. Congure Amazon EventBridge (Amazon CloudWatch Events) to invoke a custom alert by way of Amazon Simple Notication Service (Amazon SNS) when AWS Cong reports a noncompliant resource.
    C. Use AWS Trusted Advisor to check for certicates that will expire within 30 days. Create an Amazon CloudWatch alarm that is based on Trusted Advisor metrics for check status changes. Congure the alarm to send a custom alert by way of Amazon Simple Notication Service (Amazon SNS).
    D. Create an Amazon EventBridge (Amazon CloudWatch Events) rule to detect any certicates that will expire within 30 days. Congure the rule to invoke an AWS Lambda function. Congure the Lambda function to send a custom alert by way of Amazon Simple Notication Service (Amazon SNS).
83. A company's dynamic website is hosted using on-premises servers in the United States. The company is launching its product in Europe, and it wants to optimize site loading times for new European users. The site's backend must remain in the United States. The product is being launched in a few days, and an immediate solution is needed.
    What should the solutions architect recommend?
> Use Amazon CloudFront with a custom origin pointing to the on-premises servers.

84. A company wants to reduce the cost of its existing three-tier web architecture. The web, application, and database servers are running on Amazon EC2 instances for the development, test, and production environments. The EC2 instances average 30% CPU utilization during peak hours and 10% CPU utilization during non-peak hours.
    The production EC2 instances run 24 hours a day. The development and test EC2 instances run for at least 8 hours each day. The company plans to implement automation to stop the development and test EC2 instances when they are not in use.
    Which EC2 instance purchasing solution will meet the company's requirements MOST cost-effectively?
> Use Reserved Instances for the production EC2 instances. Use On-Demand Instances for the development and test EC2 instances.

85. A company has a production web application in which users upload documents through a web interface or a mobile app. According to a new regulatory requirement. new documents cannot be modied or deleted after they are stored.
What should a solutions architect do to meet this requirement?
> Store the uploaded documents in an Amazon S3 bucket with S3 Versioning and S3 Object Lock enabled.
86. A company has several web servers that need to frequently access a common Amazon RDS MySQL Multi-AZ DB instance. The company wants a secure method for the web servers to connect to the database while meeting a security requirement to rotate user credentials frequently. Which solution meets these requirements?
> Store the database user credentials in AWS Secrets Manager. Grant the necessary IAM permissions to allow the web servers to access AWS Secrets Manager.

87. A company hosts an application on AWS Lambda functions that are invoked by an Amazon API Gateway API. The Lambda functions save customer data to an Amazon Aurora MySQL database. Whenever the company upgrades the database, the Lambda functions fail to establish database connections until the upgrade is complete. The result is that customer data is not recorded for some of the event.
    A solutions architect needs to design a solution that stores customer data that is created during database upgrades.
    Which solution will meet these requirements?
> Provision an Amazon RDS proxy to sit between the Lambda functions and the database. Congure the Lambda functions to connect to the RDS proxy.

88. ? A survey company has gathered data for several years from areas in the United States. The company hosts the data in an Amazon S3 bucket that is 3 TB in size and growing. The company has started to share the data with a European marketing rm that has S3 buckets. The company wants to ensure that its data transfer costs remain as low as possible.
    Which solution will meet these requirements?
    A. Congure the Requester Pays feature on the company's S3 bucket.
    B. Congure S3 Cross-Region Replication from the company's S3 bucket to one of the marketing rm's S3 buckets.
    C. Congure cross-account access for the marketing rm so that the marketing rm has access to the company's S3 bucket.
    D. Congure the company's S3 bucket to use S3 Intelligent-Tiering. Sync the S3 bucket to one of the marketing rm's S3 buckets.
89. A company uses Amazon S3 to store its condential audit documents. The S3 bucket uses bucket policies to restrict access to audit team IAM user credentials according to the principle of least privilege. Company managers are worried about accidental deletion of documents in the S3 bucket and want a more secure solution.
    What should a solutions architect do to secure the audit documents?
> Enable the versioning and MFA Delete features on the S3 bucket.

90. A company is using a SQL database to store movie data that is publicly accessible. The database runs on an Amazon RDS Single-AZ DB instance. A script runs queries at random intervals each day to record the number of new movies that have been added to the database. The script must report a final total during business hours.
    The company's development team notices that the database performance is inadequate for development tasks when the script is running. A solutions architect must recommend a solution to resolve this issue.
    Which solution will meet this requirement with the LEAST operational overhead?
> Create a read replica of the database. Congure the script to query only the read replica.

91. A company has applications that run on Amazon EC2 instances in a VPC. One of the applications needs to call the Amazon S3 API to store and read objects. According to the company's security regulations, no trac from the applications is allowed to travel across the internet. Which solution will meet these requirements?
> Congure an S3 gateway endpoint.

92. A company is storing sensitive user information in an Amazon S3 bucket. The company wants to provide secure access to this bucket from the application tier running on Amazon EC2 instances inside a VPC.
    Which combination of steps should a solutions architect take to accomplish this? (Choose two.) 
>   A. Congure a VPC gateway endpoint for Amazon S3 within the VPC.
    C. Create a bucket policy that limits access to only the application tier running in the VPC.
93. A company runs an on-premises application that is powered by a MySQL database. The company is migrating the application to AWS to increase the application's elasticity and availability.
    The current architecture shows heavy read activity on the database during times of normal operation. Every 4 hours, the company's development team pulls a full export of the production database to populate a database in the staging environment. During this period, users experience unacceptable application latency. The development team is unable to use the staging environment until the procedure completes. A solutions architect must recommend replacement architecture that alleviates the application latency issue. The replacement architecture also must give the development team the ability to continue using the staging environment without delay.
    Which solution meets these requirements?
>  Use Amazon Aurora MySQL with Multi-AZ Aurora Replicas for production. Use database cloning to create the staging database on- demand.

94. A company is designing an application where users upload small les into Amazon S3. After a user uploads a le, the le requires one-time simple processing to transform the data and save the data in JSON format for later analysis.
    Each le must be processed as quickly as possible after it is uploaded. Demand will vary. On some days, users will upload a high number of les. On other days, users will upload a few les or no les.
    Which solution meets these requirements with the LEAST operational overhead?
>  Congure Amazon S3 to send an event notication to an Amazon Simple Queue Service (Amazon SQS) queue. Use an AWS Lambda function to read from the queue and process the data. Store the resulting JSON le in Amazon DynamoDB.
95. An application allows users at a company's headquarters to access product data. The product data is stored in an Amazon RDS MySQL DB instance. The operations team has isolated an application performance slowdown and wants to separate read trac from write trac. A solutions architect needs to optimize the application's performance quickly.
    What should the solutions architect recommend?
> Create read replicas for the database. Congure the read replicas with the same compute and storage resources as the source database.

96. 看源文档
97. A  company has a large Microsoft SharePoint deployment running on-premises that requires Microsoft Windows shared le storage. The company wants to migrate this workload to the AWS Cloud and is considering various storage options. The storage solution must be highly available and integrated with Active Directory for access control.
    Which solution will satisfy these requirements?
>  Create an Amazon FSx for Windows File Server le system on AWS and set the Active Directory domain for authentication.

98. An image-processing company has a web application that users use to upload images. The application uploads the images into an Amazon S3 bucket. The company has set up S3 event notications to publish the object creation events to an Amazon Simple Queue Service (Amazon SQS) standard queue. The SQS queue serves as the event source for an AWS Lambda function that processes the images and sends the results to users through email.
    Users report that they are receiving multiple email messages for every uploaded image. A solutions architect determines that SQS messages are invoking the Lambda function more than once, resulting in multiple email messages.
    What should the solutions architect do to resolve this issue with the LEAST operational overhead?
> Increase the visibility timeout in the SQS queue to a value that is greater than the total of the function timeout and the batch window timeout.

99. A company is implementing a shared storage solution for a gaming application that is hosted in an on-premises data center. The company needs the ability to use Lustre clients to access data. The solution must be fully managed.
    Which solution meets these requirements?
> Create an Amazon FSx for Lustre le system. Attach the le system to the origin server. Connect the application server to the le system.

100. A company's containerized application runs on an Amazon EC2 instance. The application needs to download security certicates before it can communicate with other business applications. The company wants a highly secure solution to encrypt and decrypt the certicates in near real time. The solution also needs to store data in highly available storage after the data is encrypted.
     Which solution will meet these requirements with the LEAST operational overhead?
> Create an AWS Key Management Service (AWS KMS) customer managed key. Allow the EC2 role to use the KMS key for encryption operations. Store the encrypted data on Amazon S3.

101. A solutions architect is designing a VPC with public and private subnets. The VPC and subnets use IPv4 CIDR blocks. There is one public subnet and one private subnet in each of three Availability Zones (AZs) for high availability. An internet gateway is used to provide internet access for the public subnets. The private subnets require access to the internet to allow Amazon EC2 instances to download software updates.
     What should the solutions architect do to enable Internet access for the private subnets?
> Create three NAT gateways, one for each public subnet in each AZ. Create a private route table for each AZ that forwards non-VPC trac to the NAT gateway in its AZ.

102. A company wants to migrate an on-premises data center to AWS. The data center hosts an SFTP server that stores its data on an NFS-based le system. The server holds 200 GB of data that needs to be transferred. The server must be hosted on an Amazon EC2 instance that uses an Amazon Elastic File System (Amazon EFS) le system.
     Which combination of steps should a solutions architect take to automate this task? (Choose two.)
>  Launch the EC2 instance into the same Availability Zone as the EFS le system.
   Install an AWS DataSync agent in the on-premises data center.

103. A company has an AWS Glue extract, transform, and load (ETL) job that runs every day at the same time. The job processes XML data that is in an Amazon S3 bucket. New data is added to the S3 bucket every day. A solutions architect notices that AWS Glue is processing all the data during each run.
What should the solutions architect do to prevent AWS Glue from reprocessing old data?
> Edit the job to use job bookmarks.

104. A solutions architect must design a highly available infrastructure for a website. The website is powered by Windows web servers that run on Amazon EC2 instances. The solutions architect must implement a solution that can mitigate a large-scale DDoS attack that originates from thousands of IP addresses. Downtime is not acceptable for the website.
     Which actions should the solutions architect take to protect the website from such an attack? (Choose two.)
>    A. Use AWS Shield Advanced to stop the DDoS attack.
     C. Congure the website to use Amazon CloudFront for both static and dynamic content. CloudFront for HA

105. A company is preparing to deploy a new serverless workload. A solutions architect must use the principle of least privilege to congure permissions that will be used to run an AWS Lambda function. An Amazon EventBridge (Amazon CloudWatch Events) rule will invoke the function.
Which solution meets these requirements?
> Add a resource-based policy to the function with lambda:InvokeFunction as the action and Service: events.amazonaws.com as the principal.
106. A company is preparing to store condential data in Amazon S3. For compliance reasons, the data must be encrypted at rest. Encryption key usage must be logged for auditing purposes. Keys must be rotated every year.
     Which solution meets these requirements and is the MOST operationally ecient?
> Server-side encryption with AWS KMS keys (SSE-KMS) with automatic rotation

107. A bicycle sharing company is developing a multi-tier architecture to track the location of its bicycles during peak operating hours. The company wants to use these data points in its existing analytics platform. A solutions architect must determine the most viable multi-tier option to support this architecture. The data points must be accessible from the REST API.
     Which action meets these requirements for storing and retrieving location data?
> Use Amazon API Gateway with Amazon Kinesis Data Analytics.

108. A company has an automobile sales website that stores its listings in a database on Amazon RDS. When an automobile is sold, the listing needs to be removed from the website and the data must be sent to multiple target systems.
     Which design should a solutions architect recommend?
> Create an AWS Lambda function triggered when the database on Amazon RDS is updated to send the information to an Amazon Simple Queue Service (Amazon SQS) queue for the targets to consume.
109. A company needs to store data in Amazon S3 and must prevent the data from being changed. The company wants new objects that are uploaded to Amazon S3 to remain unchangeable for a nonspecic amount of time until the company decides to modify the objects. Only specic users in the company's AWS account can have the ability 10 delete the objects.
     What should a solutions architect do to meet these requirements?
> Create an S3 bucket with S3 Object Lock enabled. Enable versioning. Add a legal hold to the objects. Add the s3:PutObjectLegalHold permission to the IAM policies of users who need to delete the objects.

110. A social media company allows users to upload images to its website. The website runs on Amazon EC2 instances. During upload requests, the website resizes the images to a standard size and stores the resized images in Amazon S3. Users are experiencing slow upload requests to the website.
     The company needs to reduce coupling within the application and improve website performance. A solutions architect must design the most operationally ecient process for image uploads.
     Which combination of actions should the solutions architect take to meet these requirements? (Choose two.)
> Congure the web server to upload the original images to Amazon S3.
 Congure S3 Event Notications to invoke an AWS Lambda function when an image is uploaded. Use the function to resize the image.


111. A company recently migrated a message processing system to AWS. The system receives messages into an ActiveMQ queue running on an Amazon EC2 instance. Messages are processed by a consumer application running on Amazon EC2. The consumer application processes the messages and writes results to a MySQL database running on Amazon EC2. The company wants this application to be highly available with low operational complexity.
     Which architecture offers the HIGHEST availability?
> Use Amazon MQ with active/standby brokers congured across two Availability Zones. Add an Auto Scaling group for the consumer EC2 instances across two Availability Zones. Use Amazon RDS for MySQL with Multi-AZ enabled.

112. A company hosts a containerized web application on a eet of on-premises servers that process incoming requests. The number of requests is growing quickly. The on-premises servers cannot handle the increased number of requests. The company wants to move the application to AWS with minimum code changes and minimum development effort.
     Which solution will meet these requirements with the LEAST operational overhead?
> Use AWS Fargate on Amazon Elastic Container Service (Amazon ECS) to run the containerized web application with Service Auto Scaling. Use an Application Load Balancer to distribute the incoming requests.
113. ?? A company uses 50 TB of data for reporting. The company wants to move this data from on premises to AWS. A custom application in the company’s data center runs a weekly data transformation job. The company plans to pause the application until the data transfer is complete and needs to begin the transfer process as soon as possible.
     The data center does not have any available network bandwidth for additional workloads. A solutions architect must transfer the data and must congure the transformation job to continue to run in the AWS Cloud.
     Which solution will meet these requirements with the LEAST operational overhead?
> Order an AWS Snowball Edge Storage Optimized device. Copy the data to the device. Create a custom transformation job by using AWS Glue.

114. A company has created an image analysis application in which users can upload photos and add photo frames to their images. The users upload images and metadata to indicate which photo frames they want to add to their images. The application uses a single Amazon EC2 instance and Amazon DynamoDB to store the metadata.
     The application is becoming more popular, and the number of users is increasing. The company expects the number of concurrent users to vary signicantly depending on the time of day and day of week. The company must ensure that the application can scale to meet the needs of the growing user base.
     Which solution meats these requirements?
> Use AWS Lambda to process the photos. Store the photos in Amazon S3. Retain DynamoDB to store the metadata.
115. A medical records company is hosting an application on Amazon EC2 instances. The application processes customer data les that are stored on Amazon S3. The EC2 instances are hosted in public subnets. The EC2 instances access Amazon S3 over the internet, but they do not require any other network access.
     A new requirement mandates that the network trac for le transfers take a private route and not be sent over the internet.
     Which change to the network architecture should a solutions architect recommend to meet this requirement?
> Move the EC2 instances to private subnets. Create a VPC endpoint for Amazon S3, and link the endpoint to the route table for the private subnets.

116. A company uses a popular content management system (CMS) for its corporate website. However, the required patching and maintenance are burdensome. The company is redesigning its website and wants anew solution. The website will be updated four times a year and does not need to have any dynamic content available. The solution must provide high scalability and enhanced security.
     Which combination of changes will meet these requirements with the LEAST operational overhead? (Choose two.)
> Congure Amazon CloudFront in front of the website to use HTTPS functionality.
 Create the new website and an Amazon S3 bucket. Deploy the website on the S3 bucket with static website hosting enabled.

117. A company stores its application logs in an Amazon CloudWatch Logs log group. A new policy requires the company to store all application logs in Amazon OpenSearch Service (Amazon Elasticsearch Service) in near-real time.
     Which solution will meet this requirement with the LEAST operational overhead?
> Create an Amazon Kinesis Data Firehose delivery stream. Congure the log group as the delivery streams sources. Congure Amazon OpenSearch Service (Amazon Elasticsearch Service) as the delivery stream's destination.

118. A company is building a web-based application running on Amazon EC2 instances in multiple Availability Zones. The web application will provide access to a repository of text documents totaling about 900 TB in size. The company anticipates that the web application will experience periods of high demand. A solutions architect must ensure that the storage component for the text documents can scale to meet the demand of the application at all times. The company is concerned about the overall cost of the solution.
     Which storage solution meets these requirements MOST cost-effectively?
> Amazon S3

119. A global company is using Amazon API Gateway to design REST APIs for its loyalty club users in the us-east-1 Region and the ap-southeast-2 Region. A solutions architect must design a solution to protect these API Gateway managed REST APIs across multiple accounts from SQL injection and cross-site scripting attacks.
     Which solution will meet these requirements with the LEAST amount of administrative effort?
> Set up AWS WAF in both Regions. Associate Regional web ACLs with an API stage.

120. A company has implemented a self-managed DNS solution on three Amazon EC2 instances behind a Network Load Balancer (NLB) in the us- west-2 Region. Most of the company's users are located in the United States and Europe. The company wants to improve the performance and availability of the solution. The company launches and congures three EC2 instances in the eu-west-1 Region and adds the EC2 instances as targets for a new NLB.
     Which solution can the company use to route trac to all the EC2 instances?
> Create a standard accelerator in AWS Global Accelerator. Create endpoint groups in us-west-2 and eu-west-1. Add the two NLBs as endpoints for the endpoint groups.
AWS Global Accelerator is a network service that can provide a global traffic management solution. By creating a standard accelerator in AWS Global Accelerator, you can guide user traffic to the endpoint closest to them, thereby improving the performance and availability of the application. In this case, you can establish endpoint groups in the us-west-2 and eu-west-1 regions, and add two NLBs as endpoints. In this way, no matter where the user is located, their requests will be routed to the EC2 instance closest to them, thereby improving the performance and availability of DNS resolution. In addition, this design can also provide flexibility and scalability to handle a large amount of traffic. Therefore, this solution can meet your needs.

121. A company is running an online transaction processing (OLTP) workload on AWS. This workload uses an unencrypted Amazon RDS DB instance in a Multi-AZ deployment. Daily database snapshots are taken from this instance.
     What should a solutions architect do to ensure the database and snapshots are always encrypted moving forward?
> Encrypt a copy of the latest DB snapshot. Replace existing DB instance by restoring the encrypted snapshot.


122. A company wants to build a scalable key management infrastructure to support developers who need to encrypt data in their applications. What should a solutions architect do to reduce the operational burden?
> Use AWS Key Management Service (AWS KMS) to protect the encryption keys.

123. A company has a dynamic web application hosted on two Amazon EC2 instances. The company has its own SSL certicate, which is on each instance to perform SSL termination.
     There has been an increase in trac recently, and the operations team determined that SSL encryption and decryption is causing the compute capacity of the web servers to reach their maximum limit.
     What should a solutions architect do to increase the application's performance?
> Import the SSL certicate into AWS Certicate Manager (ACM). Create an Application Load Balancer with an HTTPS listener that uses the SSL certicate from ACM.

124. A company has a highly dynamic batch processing job that uses many Amazon EC2 instances to complete it. The job is stateless in nature, can be started and stopped at any given time with no negative impact, and typically takes upwards of 60 minutes total to complete. The company has asked a solutions architect to design a scalable and cost-effective solution that meets the requirements of the job.
     What should the solutions architect recommend?
> Implement EC2 Spot Instances.

125. A company runs its two-tier ecommerce website on AWS. The web tier consists of a load balancer that sends trac to Amazon EC2 instances. The database tier uses an Amazon RDS DB instance. The EC2 instances and the RDS DB instance should not be exposed to the public internet. The EC2 instances require internet access to complete payment processing of orders through a third-party web service. The application must be highly available.
     Which combination of conguration options will meet these requirements? (Choose two.)
     A. Use an Auto Scaling group to launch the EC2 instances in private subnets. Deploy an RDS Multi-AZ DB instance in private subnets.
     E. Congure a VPC with two public subnets, two private subnets, and two NAT gateways across two Availability Zones. Deploy an Application Load Balancer in the public subnets.
126. A solutions architect needs to implement a solution to reduce a company's storage costs. All the company's data is in the Amazon S3 Standard storage class. The company must keep all data for at least 25 years. Data from the most recent 2 years must be highly available and immediately retrievable.
     Which solution will meet these requirements?
> Set up an S3 Lifecycle policy to transition objects to S3 Glacier Deep Archive after 2 years.

127. A media company is evaluating the possibility of moving its systems to the AWS Cloud. The company needs at least 10 TB of storage with the maximum possible I/O performance for video processing, 300 TB of very durable storage for storing media content, and 900 TB of storage to meet requirements for archival media that is not in use anymore.
     Which set of services should a solutions architect recommend to meet these requirements?
> D. Amazon EC2 instance store for maximum performance, Amazon S3 for durable data storage, and Amazon S3 Glacier for archival storage
EC2 instance store provides the highest performance storage for I/O intensive video processing. S3 provides durable, scalable object storage for the media content library.
Glacier provides the lowest cost archival storage for media no longer in active use.
EBS volumes don't offer the IOPS needed for video processing.
EFS file storage isn't as durable or cost effective for large media libraries as S3.
By matching each storage need with the optimal storage service - EC2, S3, Glacier - this combination meets the performance, durability, and cost requirements for each storage use case.

128. A company wants to run applications in containers in the AWS Cloud. These applications are stateless and can tolerate disruptions within the underlying infrastructure. The company needs a solution that minimizes cost and operational overhead.
     What should a solutions architect do to meet these requirements?
> B. Use Spot Instances in an Amazon Elastic Kubernetes Service (Amazon EKS) managed node group.

129. A company is running a multi-tier web application on premises. The web application is containerized and runs on a number of Linux hosts connected to a PostgreSQL database that contains user records. The operational overhead of maintaining the infrastructure and capacity planning is limiting the company's growth. A solutions architect must improve the application's infrastructure.
     Which combination of actions should the solutions architect take to accomplish this? (Choose two.)
>   A. Migrate the PostgreSQL database to Amazon Aurora.
   E. Migrate the web application to be hosted on AWS Fargate with Amazon Elastic Container Service (Amazon ECS).

130. An application runs on Amazon EC2 instances across multiple Availability Zonas. The instances run in an Amazon EC2 Auto Scaling group behind an Application Load Balancer. The application performs best when the CPU utilization of the EC2 instances is at or near 40%. What should a solutions architect do to maintain the desired performance across all instances in the group?
>    B. Use a target tracking policy to dynamically scale the Auto Scaling group.

131. A company is developing a le-sharing application that will use an Amazon S3 bucket for storage. The company wants to serve all the les through an Amazon CloudFront distribution. The company does not want the les to be accessible through direct navigation to the S3 URL. What should a solutions architect do to meet these requirements?
>    D. Create an origin access identity (OAI). Assign the OAI to the CloudFront distribution. Congure the S3 bucket permissions so that only the OAI has read permission.
132. A company’s website provides users with downloadable historical performance reports. The website needs a solution that will scale to meet the company’s website demands globally. The solution should be cost-effective, limit the provisioning of infrastructure resources, and provide the fastest possible response time.
     Which combination should a solutions architect recommend to meet these requirements?
     A. Amazon CloudFront and Amazon S3

133. A company runs an Oracle database on premises. As part of the company’s migration to AWS, the company wants to upgrade the database to the most recent available version. The company also wants to set up disaster recovery (DR) for the database. The company needs to minimize the operational overhead for normal operations and DR setup. The company also needs to maintain access to the database's underlying operating system.
     Which solution will meet these requirements?
>   C. Migrate the Oracle database to Amazon RDS Custom for Oracle. Create a read replica for the database in another AWS Region.

134. A  company wants to move its application to a serverless solution. The serverless solution needs to analyze existing and new data by using SL. The company stores the data in an Amazon S3 bucket. The data requires encryption and must be replicated to a different AWS Region.
     Which solution will meet these requirements with the LEAST operational overhead?
>   C. Load the data into the existing S3 bucket. Use S3 Cross-Region Replication (CRR) to replicate encrypted objects to an S3 bucket in another Region. Use server-side encryption with Amazon S3 managed encryption keys (SSE-S3). Use Amazon Athena to query the data.
SSE-KMS vs SSE-S3 - The last seems to have less overhead (as the keys are automatically generated by S3 and applied on data at upload, and don't require further actions. KMS provides more flexibility, but in turn involves a different service, which finally is more "complex" than just managing one (S3). So A and B are excluded. If you are in doubt, you are having 2 buckets in A and B, while just keeping one in C and D. https://s3browser.com/server-side-encryption-types.aspx
Decide between C and D is deciding on Athena or RDS. RDS is a relational db, and we have documents on S3, which is the use case for Athena. Athena is also serverless, which eliminates the need of controlling the underlying infrastructure and capacity. So C is the answer. https://aws.amazon.com/athena/

135. A company runs workloads on AWS. The company needs to connect to a service from an external provider. The service is hosted in the provider's VPC. According to the company’s security team, the connectivity must be private and must be restricted to the target service. The connection must be initiated only from the company’s VPC.
     Which solution will mast these requirements?
> D. Ask the provider to create a VPC endpoint for the target service. Use AWS PrivateLink to connect to the target service.

136. A company is migrating its on-premises PostgreSQL database to Amazon Aurora PostgreSQL. The on-premises database must remain online and accessible during the migration. The Aurora database must remain synchronized with the on-premises database.
     Which combination of actions must a solutions architect take to meet these requirements? (Choose two.)
>    A. Create an ongoing replication task.
     C. Create an AWS Database Migration Service (AWS DMS) replication server.

137. A company uses AWS Organizations to create dedicated AWS accounts for each business unit to manage each business unit's account independently upon request. The root email recipient missed a notication that was sent to the root user email address of one account. The company wants to ensure that all future notications are not missed. Future notications must be limited to account administrators.
     Which solution will meet these requirements?
>     B. Congure all AWS account root user email addresses as distribution lists that go to a few administrators who can respond to alerts. Congure AWS account alternate contacts in the AWS Organizations console or programmatically.
138. A company runs its ecommerce application on AWS. Every new order is published as a massage in a RabbitMQ queue that runs on an Amazon EC2 instance in a single Availability Zone. These messages are processed by a different application that runs on a separate EC2 instance. This application stores the details in a PostgreSQL database on another EC2 instance. All the EC2 instances are in the same Availability Zone. The company needs to redesign its architecture to provide the highest availability with the least operational overhead.
     What should a solutions architect do to meet these requirements?
>     B. Migrate the queue to a redundant pair (active/standby) of RabbitMQ instances on Amazon MQ. Create a Multi-AZ Auto Scaling group for EC2 instances that host the application. Migrate the database to run on a Multi-AZ deployment of Amazon RDS for PostgreSQL.
139. A reporting team receives les each day in an Amazon S3 bucket. The reporting team manually reviews and copies the les from this initial S3 bucket to an analysis S3 bucket each day at the same time to use with Amazon QuickSight. Additional teams are starting to send more les in larger sizes to the initial S3 bucket.
     The reporting team wants to move the les automatically analysis S3 bucket as the les enter the initial S3 bucket. The reporting team also wants to use AWS Lambda functions to run pattern-matching code on the copied data. In addition, the reporting team wants to send the data les to a pipeline in Amazon SageMaker Pipelines.
     What should a solutions architect do to meet these requirements with the LEAST operational overhead?
>     D. Congure S3 replication between the S3 buckets. Congure the analysis S3 bucket to send event notications to Amazon EventBridge (Amazon CloudWatch Events). Congure an ObjectCreated rule in EventBridge (CloudWatch Events). Congure Lambda and SageMaker Pipelines as targets for the rule.
140. A solutions architect needs to help a company optimize the cost of running an application on AWS. The application will use Amazon EC2 instances, AWS Fargate, and AWS Lambda for compute within the architecture.
     The EC2 instances will run the data ingestion layer of the application. EC2 usage will be sporadic and unpredictable. Workloads that run on EC2 instances can be interrupted at any time. The application front end will run on Fargate, and Lambda will serve the API layer. The front-end utilization and API layer utilization will be predictable over the course of the next year.
     Which combination of purchasing options will provide the MOST cost-effective solution for hosting this application? (Choose two.)
>     A. Use Spot Instances for the data ingestion layer
     C. Purchase a 1-year Compute Savings Plan for the front end and API layer.
141. A company runs a web-based portal that provides users with global breaking news, local alerts, and weather updates. The portal delivers each user a personalized view by using mixture of static and dynamic content. Content is served over HTTPS through an API server running on an Amazon EC2 instance behind an Application Load Balancer (ALB). The company wants the portal to provide this content to its users across the world as quickly as possible.
     How should a solutions architect design the application to ensure the LEAST amount of latency for all users?
>   A. Deploy the application stack in a single AWS Region. Use Amazon CloudFront to serve all static and dynamic content by specifying the ALB as an origin.
142. A gaming company is designing a highly available architecture. The application runs on a modied Linux kernel and supports only UDP-based trac. The company needs the front-end tier to provide the best possible user experience. That tier must have low latency, route trac to the nearest edge location, and provide static IP addresses for entry into the application endpoints.
     What should a solutions architect do to meet these requirements?
>  C. Congure AWS Global Accelerator to forward requests to a Network Load Balancer. Use Amazon EC2 instances for the application in an EC2 Auto Scaling group.

143. A company wants to migrate its existing on-premises monolithic application to AWS. The company wants to keep as much of the front-end code and the backend code as possible. However, the company wants to break the application into smaller applications. A different team will manage each application. The company needs a highly scalable solution that minimizes operational overhead.
     Which solution will meet these requirements?
> D. Host the application on Amazon Elastic Container Service (Amazon ECS). Set up an Application Load Balancer with Amazon ECS as the target.

144. A company recently started using Amazon Aurora as the data store for its global ecommerce application. When large reports are run, developers report that the ecommerce application is performing poorly. After reviewing metrics in Amazon CloudWatch, a solutions architect nds that the ReadIOPS and CPUUtilizalion metrics are spiking when monthly reports run.
     What is the MOST cost-effective solution?
>    B. Migrate the monthly reporting to an Aurora Replica.
145. A company hosts a website analytics application on a single Amazon EC2 On-Demand Instance. The analytics software is written in PHP and uses a MySQL database. The analytics software, the web server that provides PHP, and the database server are all hosted on the EC2 instance. The application is showing signs of performance degradation during busy times and is presenting 5xx errors. The company needs to make the application scale seamlessly.
     Which solution will meet these requirements MOST cost-effectively?
> D. Migrate the database to an Amazon Aurora MySQL DB instance. Create an AMI of the web application. Apply the AMI to a launch template. Create an Auto Scaling group with the launch template Congure the launch template to use a Spot Fleet. Attach an Application Load Balancer to the Auto Scaling group.
146. A company runs a stateless web application in production on a group of Amazon EC2 On-Demand Instances behind an Application Load Balancer. The application experiences heavy usage during an 8-hour period each business day. Application usage is moderate and steady overnight. Application usage is low during weekends.
     The company wants to minimize its EC2 costs without affecting the availability of the application.
     Which solution will meet these requirements?
 >    B. Use Reserved Instances for the baseline level of usage. Use Spot instances for any additional capacity that the application needs.

147. A company needs to retain application log les for a critical application for 10 years. The application team regularly accesses logs from the past month for troubleshooting, but logs older than 1 month are rarely accessed. The application generates more than 10 TB of logs per month.
 >    B. Store the logs in Amazon S3. Use S3 Lifecycle policies to move logs more than 1 month old to S3 Glacier Deep Archive.
148. A company has a data ingestion workow that includes the following components:
     An Amazon Simple Notication Service (Amazon SNS) topic that receives notications about new data deliveries
     An AWS Lambda function that processes and stores the data
     The ingestion workow occasionally fails because of network connectivity issues. When failure occurs, the corresponding data is not ingested unless the company manually reruns the job.
     What should a solutions architect do to ensure that all notications are eventually processed?
 >    D. Congure an Amazon Simple Queue Service (Amazon SQS) queue as the on-failure destination. Modify the Lambda function to process messages in the queue.

149. A company has a service that produces event data. The company wants to use AWS to process the event data as it is received. The data is written in a specic order that must be maintained throughout processing. The company wants to implement a solution that minimizes operational overhead.
     How should a solutions architect accomplish this?
>     A. Create an Amazon Simple Queue Service (Amazon SQS) FIFO queue to hold messages. Set up an AWS Lambda function to process messages from the queue.

150. A company is migrating an application from on-premises servers to Amazon EC2 instances. As part of the migration design requirements, a solutions architect must implement infrastructure metric alarms. The company does not need to take action if CPU utilization increases to more than 50% for a short burst of time. However, if the CPU utilization increases to more than 50% and read IOPS on the disk are high at the same time, the company needs to act as soon as possible. The solutions architect also must reduce false alarms.
     What should the solutions architect do to meet these requirements?
>     A. Create Amazon CloudWatch composite alarms where possible.

151. A company wants to migrate its on-premises data center to AWS. According to the company's compliance requirements, the company can use only the ap-northeast-3 Region. Company administrators are not permitted to connect VPCs to the internet.
     Which solutions will meet these requirements? (Choose two.)
>     A. Use AWS Control Tower to implement data residency guardrails to deny internet access and deny access to all AWS Regions except ap- northeast-3.
     C. Use AWS Organizations to congure service control policies (SCPS) that prevent VPCs from gaining internet access. Deny access to all AWS Regions except ap-northeast-3.

152. A company uses a three-tier web application to provide training to new employees. The application is accessed for only 12 hours every day. The company is using an Amazon RDS for MySQL DB instance to store information and wants to minimize costs.
     What should a solutions architect do to meet these requirements?
>    D. Create AWS Lambda functions to start and stop the DB instance. Create Amazon EventBridge (Amazon CloudWatch Events) scheduled rules to invoke the Lambda functions. Congure the Lambda functions as event targets for the rules.
153. A company sells ringtones created from clips of popular songs. The les containing the ringtones are stored in Amazon S3 Standard and are at least 128 KB in size. The company has millions of les, but downloads are infrequent for ringtones older than 90 days. The company needs to save money on storage while keeping the most accessed les readily available for its users.
     Which action should the company take to meet these requirements MOST cost-effectively?
>    D. Implement an S3 Lifecycle policy that moves the objects from S3 Standard to S3 Standard-Infrequent Access (S3 Standard-1A) after 90 days.
154. A company needs to save the results from a medical trial to an Amazon S3 repository. The repository must allow a few scientists to add new les and must restrict all other users to read-only access. No users can have the ability to modify or delete any les in the repository. The company must keep every le in the repository for a minimum of 1 year after its creation date.
     Which solution will meet these requirements?
>     B. Use S3 Object Lock in compliance mode with a retention period of 365 days.
155. A large media company hosts a web application on AWS. The company wants to start caching condential media les so that users around the world will have reliable access to the les. The content is stored in Amazon S3 buckets. The company must deliver the content quickly, regardless of where the requests originate geographically.
     Which solution will meet these requirements?
>     C. Deploy Amazon CloudFront to connect the S3 buckets to CloudFront edge servers.

156. A company produces batch data that comes from different databases. The company also produces live stream data from network sensors and application APIs. The company needs to consolidate all the data into one place for business analytics. The company needs to process the incoming data and then stage the data in different Amazon S3 buckets. Teams will later run one-time queries and import the data into a business intelligence tool to show key performance indicators (KPIs).
     Which combination of steps will meet these requirements with the LEAST operational overhead? (Choose two.)
>     A. Use Amazon Athena for one-time queries. Use Amazon QuickSight to create dashboards for KPIs.
     E. Use blueprints in AWS Lake Formation to identify the data that can be ingested into a data lake. Use AWS Glue to crawl the source, extract the data, and load the data into Amazon S3 in Apache Parquet format.

157. A company stores data in an Amazon Aurora PostgreSQL DB cluster. The company must store all the data for 5 years and must delete all the data after 5 years. The company also must indenitely keep audit logs of actions that are performed within the database. Currently, the company has automated backups congured for Aurora.
     Which combination of steps should a solutions architect take to meet these requirements? (Choose two.)
>     D. Congure an Amazon CloudWatch Logs export for the DB cluster.
     E. Use AWS Backup to take the backups and to keep the backups for 5 years.
158. A solutions architect is optimizing a website for an upcoming musical event. Videos of the performances will be streamed in real time and then will be available on demand. The event is expected to attract a global online audience.
     Which service will improve the performance of both the real-time and on-demand streaming?
>    A. Amazon CloudFront

159. A company is running a publicly accessible serverless application that uses Amazon API Gateway and AWS Lambda. The application’s trac recently spiked due to fraudulent requests from botnets.
     Which steps should a solutions architect take to block requests from unauthorized users? (Choose two.)
>     C. Implement an AWS WAF rule to target malicious requests and trigger actions to lter them out.
     D. Convert the existing public API to a private API. Update the DNS records to redirect users to the new API endpoint.

160. An ecommerce company hosts its analytics application in the AWS Cloud. The application generates about 300 MB of data each month. The data is stored in JSON format. The company is evaluating a disaster recovery solution to back up the data. The data must be accessible in milliseconds if it is needed, and the data must be kept for 30 days.
     Which solution meets these requirements MOST cost-effectively?
>    C. Amazon S3 Standard. Cost-effective solution with milliseconds of retrieval -> it should be s3 standard
161. A company has a small Python application that processes JSON documents and outputs the results to an on-premises SQL database. The application runs thousands of times each day. The company wants to move the application to the AWS Cloud. The company needs a highly available solution that maximizes scalability and minimizes operational overhead.
     Which solution will meet these requirements?
>    B. Place the JSON documents in an Amazon S3 bucket. Create an AWS Lambda function that runs the Python code to process the documents as they arrive in the S3 bucket. Store the results in an Amazon Aurora DB cluster.

162. A company wants to use high performance computing (HPC) infrastructure on AWS for nancial risk modeling. The company’s HPC workloads run on Linux. Each HPC workow runs on hundreds of Amazon EC2 Spot Instances, is short-lived, and generates thousands of output les that are ultimately stored in persistent storage for analytics and long-term future use.
     The company seeks a cloud storage solution that permits the copying of on-premises data to long-term persistent storage to make data available for processing by all EC2 instances. The solution should also be a high performance le system that is integrated with persistent storage to read and write datasets and output les.
     Which combination of AWS services meets these requirements?
>    A. Amazon FSx for Lustre integrated with Amazon S3

163. A company is building a containerized application on premises and decides to move the application to AWS. The application will have thousands of users soon after it is deployed. The company is unsure how to manage the deployment of containers at scale. The company needs to deploy the containerized application in a highly available architecture that minimizes operational overhead.
     Which solution will meet these requirements?
     A. Store container images in an Amazon Elastic Container Registry (Amazon ECR) repository. Use an Amazon Elastic Container Service (Amazon ECS) cluster with the AWS Fargate launch type to run the containers. Use target tracking to scale automatically based on demand.
164. A company has two applications: a sender application that sends messages with payloads to be processed and a processing application intended to receive the messages with payloads. The company wants to implement an AWS service to handle messages between the two applications. The sender application can send about 1,000 messages each hour. The messages may take up to 2 days to be processed: If the messages fail to process, they must be retained so that they do not impact the processing of any remaining messages.
     Which solution meets these requirements and is the MOST operationally ecient?
> C. Integrate the sender and processor applications with an Amazon Simple Queue Service (Amazon SQS) queue. Congure a dead-letter queue to collect the messages that failed to process.
165. A solutions architect must design a solution that uses Amazon CloudFront with an Amazon S3 origin to store a static website. The company’s security policy requires that all website trac be inspected by AWS WAF.
     How should the solutions architect comply with these requirements?
>    D. Congure Amazon CloudFront and Amazon S3 to use an origin access identity (OAI) to restrict access to the S3 bucket. Enable AWS WAF on the distribution.
166. Organizers for a global event want to put daily reports online as static HTML pages. The pages are expected to generate millions of views from users around the world. The les are stored in an Amazon S3 bucket. A solutions architect has been asked to design an ecient and effective solution.
     Which action should the solutions architect take to accomplish this?
>     D. Use Amazon CloudFront with the S3 bucket as its origin.
167. A company runs a production application on a eet of Amazon EC2 instances. The application reads the data from an Amazon SQS queue and processes the messages in parallel. The message volume is unpredictable and often has intermittent trac. This application should continually process messages without any downtime.
     Which solution meets these requirements MOST cost-effectively?
>    D. Use Reserved Instances for the baseline capacity and use On-Demand Instances to handle additional capacity.
168. A security team wants to limit access to specic services or actions in all of the team’s AWS accounts. All accounts belong to a large organization in AWS Organizations. The solution must be scalable and there must be a single point where permissions can be maintained.
     What should a solutions architect do to accomplish this?
> D. Create a service control policy in the root organizational unit to deny access to the services or actions.
D. Service control policies (SCPs) are one type of policy that you can use to manage your organization. SCPs offer central control over the maximum available permissions for all accounts in your organization, allowing you to ensure your accounts stay within your organization's access control guidelines.

169. A company is concerned about the security of its public web application due to recent web attacks. The application uses an Application Load Balancer (ALB). A solutions architect must reduce the risk of DDoS attacks against the application.
     What should the solutions architect do to meet this requirement?
>    C. Enable AWS Shield Advanced to prevent attacks.
170. A company’s web application is running on Amazon EC2 instances behind an Application Load Balancer. The company recently changed its policy, which now requires the application to be accessed from one specic country only.
     Which conguration will meet this requirement?
>     C. Congure AWS WAF on the Application Load Balancer in a VPC.
171. A company provides an API to its users that automates inquiries for tax computations based on item prices. The company experiences a larger number of inquiries during the holiday season only that cause slower response times. A solutions architect needs to design a solution that is scalable and elastic.
     What should the solutions architect do to accomplish this?
>     B. Design a REST API using Amazon API Gateway that accepts the item names. API Gateway passes item names to AWS Lambda for tax computations.

172. A solutions architect is creating a new Amazon CloudFront distribution for an application. Some of the information submitted by users is sensitive. The application uses HTTPS but needs another layer of security. The sensitive information should be protected throughout the entire application stack, and access to the information should be restricted to certain applications.
     Which action should the solutions architect take?
>    C. Congure a CloudFront eld-level encryption prole.

173. A gaming company hosts a browser-based application on AWS. The users of the application consume a large number of videos and images that are stored in Amazon S3. This content is the same for all users.
     The application has increased in popularity, and millions of users worldwide accessing these media les. The company wants to provide the les to the users while reducing the load on the origin.
     Which solution meets these requirements MOST cost-effectively?
>     B. Deploy an Amazon CloudFront web distribution in front of the S3 bucket.
174. A company has a multi-tier application that runs six front-end web servers in an Amazon EC2 Auto Scaling group in a single Availability Zone behind an Application Load Balancer (ALB). A solutions architect needs to modify the infrastructure to be highly available without modifying the application.
     Which architecture should the solutions architect choose that provides high availability?
>     B. Modify the Auto Scaling group to use three instances across each of two Availability Zones.
175. An ecommerce company has an order-processing application that uses Amazon API Gateway and an AWS Lambda function. The application stores data in an Amazon Aurora PostgreSQL database. During a recent sales event, a sudden surge in customer orders occurred. Some customers experienced timeouts, and the application did not process the orders of those customers.
     A solutions architect determined that the CPU utilization and memory utilization were high on the database because of a large number of open connections. The solutions architect needs to prevent the timeout errors while making the least possible changes to the application.
     Which solution will meet these requirements?
>     B. Use Amazon RDS Proxy to create a proxy for the database. Modify the Lambda function to use the RDS Proxy endpoint instead of the database endpoint.
176. An application runs on Amazon EC2 instances in private subnets. The application needs to access an Amazon DynamoDB table. What is the MOST secure way to access the table while ensuring that the trac does not leave the AWS network?
>     A. Use a VPC endpoint for DynamoDB.

177. An entertainment company is using Amazon DynamoDB to store media metadata. The application is read intensive and experiencing delays. The company does not have staff to handle additional operational overhead and needs to improve the performance eciency of DynamoDB without reconguring the application.
     What should a solutions architect recommend to meet this requirement?
>    B. Use Amazon DynamoDB Accelerator (DAX).

178. A company’s infrastructure consists of Amazon EC2 instances and an Amazon RDS DB instance in a single AWS Region. The company wants to back up its data in a separate Region.
     Which solution will meet these requirements with the LEAST operational overhead?
>    A. Use AWS Backup to copy EC2 backups and RDS backups to the separate Region.

179. A solutions architect needs to securely store a database user name and password that an application uses to access an Amazon RDS DB instance. The application that accesses the database runs on an Amazon EC2 instance. The solutions architect wants to create a secure parameter in AWS Systems Manager Parameter Store.
     What should the solutions architect do to meet this requirement?
>   A. Create an IAM role that has read access to the Parameter Store parameter. Allow Decrypt access to an AWS Key Management Service (AWS KMS) key that is used to encrypt the parameter. Assign this IAM role to the EC2 instance.

180. A company is designing a cloud communications platform that is driven by APIs. The application is hosted on Amazon EC2 instances behind a Network Load Balancer (NLB). The company uses Amazon API Gateway to provide external users with access to the application through APIs. The company wants to protect the platform against web exploits like SQL injection and also wants to detect and mitigate large, sophisticated DDoS attacks.
     Which combination of solutions provides the MOST protection? (Choose two.)
>     B. Use AWS Shield Advanced with the NLB.
     C. Use AWS WAF to protect Amazon API Gateway.
181. A company has a legacy data processing application that runs on Amazon EC2 instances. Data is processed sequentially, but the order of results does not matter. The application uses a monolithic architecture. The only way that the company can scale the application to meet increased demand is to increase the size of the instances.
     The company’s developers have decided to rewrite the application to use a microservices architecture on Amazon Elastic Container Service (Amazon ECS).
     What should a solutions architect recommend for communication between the microservices?
>    A. Create an Amazon Simple Queue Service (Amazon SQS) queue. Add code to the data producers, and send data to the queue. Add code to the data consumers to process data from the queue.
182. A company wants to migrate its MySQL database from on premises to AWS. The company recently experienced a database outage that signicantly impacted the business. To ensure this does not happen again, the company wants a reliable database solution on AWS that minimizes data loss and stores every transaction on at least two nodes.
     Which solution meets these requirements?
>   B. Create an Amazon RDS MySQL DB instance with Multi-AZ functionality enabled to synchronously replicate the data.
183. A company is building a new dynamic ordering website. The company wants to minimize server maintenance and patching. The website must be highly available and must scale read and write capacity as quickly as possible to meet changes in user demand.
     Which solution will meet these requirements?
>    A. Host static content in Amazon S3. Host dynamic content by using Amazon API Gateway and AWS Lambda. Use Amazon DynamoDB with on-demand capacity for the database. Congure Amazon CloudFront to deliver the website content.
184. A company has an AWS account used for software engineering. The AWS account has access to the company’s on-premises data center through a pair of AWS Direct Connect connections. All non-VPC trac routes to the virtual private gateway.
     A development team recently created an AWS Lambda function through the console. The development team needs to allow the function to access a database that runs in a private subnet in the company’s data center.
     Which solution will meet these requirements?
>     A. Congure the Lambda function to run in the VPC with the appropriate security group.
185. A company runs an application using Amazon ECS. The application creates resized versions of an original image and then makes Amazon S3 API calls to store the resized images in Amazon S3.
     How can a solutions architect ensure that the application has permission to access Amazon S3?
>     B. Create an IAM role with S3 permissions, and then specify that role as the taskRoleArn in the task denition.
186. A company has a Windows-based application that must be migrated to AWS. The application requires the use of a shared Windows le system attached to multiple Amazon EC2 Windows instances that are deployed across multiple Availability Zone:
     What should a solutions architect do to meet this requirement?
>     B. Congure Amazon FSx for Windows File Server. Mount the Amazon FSx le system to each Windows instance.
187. A company is developing an ecommerce application that will consist of a load-balanced front end, a container-based application, and a relational database. A solutions architect needs to create a highly available solution that operates with as little manual intervention as possible.
     Which solutions meet these requirements? (Choose two.)
>     A. Create an Amazon RDS DB instance in Multi-AZ mode.
    D. Create an Amazon Elastic Container Service (Amazon ECS) cluster with a Fargate launch type to handle the dynamic application load.
188. A company uses Amazon S3 as its data lake. The company has a new partner that must use SFTP to upload data les. A solutions architect needs to implement a highly available SFTP solution that minimizes operational overhead.
     Which solution will meet these requirements?
>  A. Use AWS Transfer Family to congure an SFTP-enabled server with a publicly accessible endpoint. Choose the S3 data lake as the destination.

189. A company needs to store contract documents. A contract lasts for 5 years. During the 5-year period, the company must ensure that the documents cannot be overwritten or deleted. The company needs to encrypt the documents at rest and rotate the encryption keys automatically every year.
     Which combination of steps should a solutions architect take to meet these requirements with the LEAST operational overhead? (Choose two.)
>     B. Store the documents in Amazon S3. Use S3 Object Lock in compliance mode.
     D. Use server-side encryption with AWS Key Management Service (AWS KMS) customer managed keys. Congure key rotation.
190. A company has a web application that is based on Java and PHP. The company plans to move the application from on premises to AWS. The company needs the ability to test new site features frequently. The company also needs a highly available and managed solution that requires minimum operational overhead.
     Which solution will meet these requirements?
>    B. Deploy the web application to an AWS Elastic Beanstalk environment. Use URL swapping to switch between multiple Elastic Beanstalk environments for feature testing.
191. A company has an ordering application that stores customer information in Amazon RDS for MySQL. During regular business hours, employees run one-time queries for reporting purposes. Timeouts are occurring during order processing because the reporting queries are taking a long time to run. The company needs to eliminate the timeouts without preventing employees from performing queries.
     What should a solutions architect do to meet these requirements?
>    A. Create a read replica. Move reporting queries to the read replica.

192. A hospital wants to create digital copies for its large collection of historical written records. The hospital will continue to add hundreds of new documents each day. The hospital’s data team will scan the documents and will upload the documents to the AWS Cloud.
     A solutions architect must implement a solution to analyze the documents, extract the medical information, and store the documents so that an application can run SQL queries on the data. The solution must maximize scalability and operational eciency.
     Which combination of steps should the solutions architect take to meet these requirements? (Choose two.)
>     B. Write the document information to an Amazon S3 bucket. Use Amazon Athena to query the data.
     E. Create an AWS Lambda function that runs when new documents are uploaded. Use Amazon Textract to convert the documents to raw text. Use Amazon Comprehend Medical to detect and extract relevant medical information from the text.
193. ? A company is running a batch application on Amazon EC2 instances. The application consists of a backend with multiple Amazon RDS databases. The application is causing a high number of reads on the databases. A solutions architect must reduce the number of database reads while ensuring high availability.
     What should the solutions architect do to meet this requirement?
 >    A. Add Amazon RDS read replicas.

194. ?A company needs to run a critical application on AWS. The company needs to use Amazon EC2 for the application’s database. The database must be highly available and must fail over automatically if a disruptive event occurs.
     Which solution will meet these requirements?
>     A. Launch two EC2 instances, each in a different Availability Zone in the same AWS Region. Install the database on both EC2 instances. Congure the EC2 instances as a cluster. Set up database replication.
     C. Launch two EC2 instances, each in a different AWS Region. Install the database on both EC2 instances. Set up database replication. Fail over the database to a second Region.
195. A company’s order system sends requests from clients to Amazon EC2 instances. The EC2 instances process the orders and then store the orders in a database on Amazon RDS. Users report that they must reprocess orders when the system fails. The company wants a resilient solution that can process orders automatically if a system outage occurs.
     What should a solutions architect do to meet these requirements?
> C. Move the EC2 instances into an Auto Scaling group. Congure the order system to send messages to an Amazon Simple Queue Service (Amazon SQS) queue. Congure the EC2 instances to consume messages from the queue.

196. A company runs an application on a large eet of Amazon EC2 instances. The application reads and writes entries into an Amazon DynamoDB table. The size of the DynamoDB table continuously grows, but the application needs only data from the last 30 days. The company needs a solution that minimizes cost and development effort.
     Which solution meets these requirements?
>     D. Extend the application to add an attribute that has a value of the current timestamp plus 30 days to each new item that is created in the table. Congure DynamoDB to use the attribute as the TTL attribute.
197. A company has a Microsoft .NET application that runs on an on-premises Windows Server. The application stores data by using an Oracle Database Standard Edition server. The company is planning a migration to AWS and wants to minimize development changes while moving the application. The AWS application environment should be highly available.
     Which combination of actions should the company take to meet these requirements? (Choose two.)
>     B. Rehost the application in AWS Elastic Beanstalk with the .NET platform in a Multi-AZ deployment.
     E. Use AWS Database Migration Service (AWS DMS) to migrate from the Oracle database to Oracle on Amazon RDS in a Multi-AZ deployment.
198. A company runs a containerized application on a Kubernetes cluster in an on-premises data center. The company is using a MongoDB database for data storage. The company wants to migrate some of these environments to AWS, but no code changes or deployment method changes are possible at this time. The company needs a solution that minimizes operational overhead.
     Which solution meets these requirements?
>    D. Use Amazon Elastic Kubernetes Service (Amazon EKS) with AWS Fargate for compute and Amazon DocumentDB (with MongoDB compatibility) for data storage.
199. A telemarketing company is designing its customer call center functionality on AWS. The company needs a solution that provides multiple speaker recognition and generates transcript les. The company wants to query the transcript les to analyze the business patterns. The transcript les must be stored for 7 years for auditing purposes.
     Which solution will meet these requirements?
>  B. Use Amazon Transcribe for multiple speaker recognition. Use Amazon Athena for transcript le analysis.
200. A company hosts its application on AWS. The company uses Amazon Cognito to manage users. When users log in to the application, the application fetches required data from Amazon DynamoDB by using a REST API that is hosted in Amazon API Gateway. The company wants an AWS managed solution that will control access to the REST API to reduce development efforts.
     Which solution will meet these requirements with the LEAST operational overhead?
>  D. Congure an Amazon Cognito user pool authorizer in API Gateway to allow Amazon Cognito to validate each request. 
201. A company is developing a marketing communications service that targets mobile app users. The company needs to send conrmation messages with Short Message Service (SMS) to its users. The users must be able to reply to the SMS messages. The company must store the responses for a year for analysis.
     What should a solutions architect do to meet these requirements?
>    B. Build an Amazon Pinpoint journey. Congure Amazon Pinpoint to send events to an Amazon Kinesis data stream for analysis and archiving.
202. A company is planning to move its data to an Amazon S3 bucket. The data must be encrypted when it is stored in the S3 bucket. Additionally, the encryption key must be automatically rotated every year.
     Which solution will meet these requirements with the LEAST operational overhead?
>     B. Create an AWS Key Management Service (AWS KMS) customer managed key. Enable automatic key rotation. Set the S3 bucket’s default encryption behavior to use the customer managed KMS key. Move the data to the S3 bucket.
203. The customers of a nance company request appointments with nancial advisors by sending text messages. A web application that runs on Amazon EC2 instances accepts the appointment requests. The text messages are published to an Amazon Simple Queue Service (Amazon SQS) queue through the web application. Another application that runs on EC2 instances then sends meeting invitations and meeting conrmation email messages to the customers. After successful scheduling, this application stores the meeting information in an Amazon DynamoDB database.
     As the company expands, customers report that their meeting invitations are taking longer to arrive. What should a solutions architect recommend to resolve this issue?
>     D. Add an Auto Scaling group for the application that sends meeting invitations. Congure the Auto Scaling group to scale based on the depth of the SQS queue.
204. An online retail company has more than 50 million active customers and receives more than 25,000 orders each day. The company collects purchase data for customers and stores this data in Amazon S3. Additional customer data is stored in Amazon RDS.
     The company wants to make all the data available to various teams so that the teams can perform analytics. The solution must provide the ability to manage ne-grained permissions for the data and must minimize operational overhead.
     Which solution will meet these requirements?
>    C. Create a data lake by using AWS Lake Formation. Create an AWS Glue JDBC connection to Amazon RDS. Register the S3 bucket in Lake Formation. Use Lake Formation access controls to limit access.
205. A company hosts a marketing website in an on-premises data center. The website consists of static documents and runs on a single server. An administrator updates the website content infrequently and uses an SFTP client to upload new documents.
     The company decides to host its website on AWS and to use Amazon CloudFront. The company’s solutions architect creates a CloudFront distribution. The solutions architect must design the most cost-effective and resilient architecture for website hosting to serve as the CloudFront origin.
     Which solution will meet these requirements?
>    C. Create a private Amazon S3 bucket. Use an S3 bucket policy to allow access from a CloudFront origin access identity (OAI). Upload website content by using the AWS CLI.

206. A company wants to manage Amazon Machine Images (AMIs). The company currently copies AMIs to the same AWS Region where the AMIs were created. The company needs to design an application that captures AWS API calls and sends alerts whenever the Amazon EC2 CreateImage API operation is called within the company’s account.
     Which solution will meet these requirements with the LEAST operational overhead?
>    C. Create an Amazon EventBridge (Amazon CloudWatch Events) rule for the CreateImage API call. Congure the target as an Amazon Simple Notication Service (Amazon SNS) topic to send an alert when a CreateImage API call is detected.
207. A company owns an asynchronous API that is used to ingest user requests and, based on the request type, dispatch requests to the appropriate microservice for processing. The company is using Amazon API Gateway to deploy the API front end, and an AWS Lambda function that invokes Amazon DynamoDB to store user requests before dispatching them to the processing microservices.
     The company provisioned as much DynamoDB throughput as its budget allows, but the company is still experiencing availability issues and is losing user requests.
     What should a solutions architect do to address this issue without impacting existing users?
>     D. Use the Amazon Simple Queue Service (Amazon SQS) queue and Lambda to buffer writes to DynamoDB.
208. ? A company needs to move data from an Amazon EC2 instance to an Amazon S3 bucket. The company must ensure that no API calls and no data are routed through public internet routes. Only the EC2 instance can have access to upload data to the S3 bucket.
     Which solution will meet these requirements?
>    A. Create an interface VPC endpoint for Amazon S3 in the subnet where the EC2 instance is located. Attach a resource policy to the S3 bucket to only allow the EC2 instance’s IAM role for access.
     B. Create a gateway VPC endpoint for Amazon S3 in the Availability Zone where the EC2 instance is located. Attach appropriate security groups to the endpoint. Attach a resource policy to the S3 bucket to only allow the EC2 instance’s IAM role for access.
209. A solutions architect is designing the architecture of a new application being deployed to the AWS Cloud. The application will run on Amazon EC2 On-Demand Instances and will automatically scale across multiple Availability Zones. The EC2 instances will scale up and down frequently throughout the day. An Application Load Balancer (ALB) will handle the load distribution. The architecture needs to support distributed session data management. The company is willing to make changes to code if needed.
     What should the solutions architect do to ensure that the architecture supports distributed session data management?
210. A company offers a food delivery service that is growing rapidly. Because of the growth, the company’s order processing system is experiencing scaling problems during peak trac hours. The current architecture includes the following:
     • A group of Amazon EC2 instances that run in an Amazon EC2 Auto Scaling group to collect orders from the application • Another group of EC2 instances that run in an Amazon EC2 Auto Scaling group to fulll orders
     The order collection process occurs quickly, but the order fulllment process can take longer. Data must not be lost because of a scaling event.
     A solutions architect must ensure that the order collection process and the order fulllment process can both scale properly during peak trac hours. The solution must optimize utilization of the company’s AWS resources.
     Which solution meets these requirements?
>    D. Provision two Amazon Simple Queue Service (Amazon SQS) queues: one for order collection and another for order fulllment. Congure the EC2 instances to poll their respective queue. Create a metric based on a backlog per instance calculation. Scale the Auto Scaling groups based on this metric.

211. A company hosts multiple production applications. One of the applications consists of resources from Amazon EC2, AWS Lambda, Amazon RDS, Amazon Simple Notication Service (Amazon SNS), and Amazon Simple Queue Service (Amazon SQS) across multiple AWS Regions. All company resources are tagged with a tag name of “application” and a value that corresponds to each application. A solutions architect must provide the quickest solution for identifying all of the tagged components.
     Which solution meets these requirements?
>    D. Run a query with the AWS Resource Groups Tag Editor to report on the resources globally with the application tag.
CloudTrail primarily focuses on capturing and logging API activity. While it can provide information about resource changes, it may not provide a comprehensive and quick way to identify all the tagged components across multiple services and Regions.
212. A company needs to export its database once a day to Amazon S3 for other teams to access. The exported object size varies between 2 GB and 5 GB. The S3 access pattern for the data is variable and changes rapidly. The data must be immediately available and must remain accessible for up to 3 months. The company needs the most cost-effective solution that will not increase retrieval time.
     Which S3 storage class should the company use to meet these requirements?
>    A. S3 Intelligent-Tiering

213. A company is developing a new mobile app. The company must implement proper trac ltering to protect its Application Load Balancer (ALB) against common application-level attacks, such as cross-site scripting or SQL injection. The company has minimal infrastructure and operational staff. The company needs to reduce its share of the responsibility in managing, updating, and securing servers for its AWS environment.
     What should a solutions architect recommend to meet these requirements?
>  A. Congure AWS WAF rules and associate them with the ALB.
WAF = cross-site scripting or SQL injection Shield/Shield Advanced = DDoS

214. A company’s reporting system delivers hundreds of .csv les to an Amazon S3 bucket each day. The company must convert these les to Apache Parquet format and must store the les in a transformed data bucket.
Which solution will meet these requirements with the LEAST development effort?
>B. Create an AWS Glue crawler to discover the data. Create an AWS Glue extract, transform, and load (ETL) job to transform the data. Specify the transformed data bucket in the output step.
Parquet format ========> Amazon Glue
> AWS Glue Crawler is for ETL
215. A company has 700 TB of backup data stored in network attached storage (NAS) in its data center. This backup data need to be accessible for infrequent regulatory requests and must be retained 7 years. The company has decided to migrate this backup data from its data center to AWS. The migration must be complete within 1 month. The company has 500 Mbps of dedicated bandwidth on its public internet connection available for data transfer.
     What should a solutions architect do to migrate and store the data at the LOWEST cost?
>     A. Order AWS Snowball devices to transfer the data. Use a lifecycle policy to transition the les to Amazon S3 Glacier Deep Archive.
     Terabytes, low costs, limited time = AWS snowball devices
216. A company has a serverless website with millions of objects in an Amazon S3 bucket. The company uses the S3 bucket as the origin for an Amazon CloudFront distribution. The company did not set encryption on the S3 bucket before the objects were loaded. A solutions architect needs to enable encryption for all existing objects and for all objects that are added to the S3 bucket in the future.
     Which solution will meet these requirements with the LEAST amount of effort?
>   B. Turn on the default encryption settings for the S3 bucket. Use the S3 Inventory feature to create a .csv le that lists the unencrypted objects. Run an S3 Batch Operations job that uses the copy command to encrypt those objects.
While enabling SSE with AWS KMS is a valid approach to encrypt objects in an S3, it does not address the requirement of encrypting existing objects. It only applies encryption to new objects added to the bucket
>

217. A company runs a global web application on Amazon EC2 instances behind an Application Load Balancer. The application stores data in Amazon Aurora. The company needs to create a disaster recovery solution and can tolerate up to 30 minutes of downtime and potential data loss. The solution does not need to handle the load when the primary infrastructure is healthy.
What should a solutions architect do to meet these requirements?
> A. Deploy the application with the required infrastructure elements in place. Use Amazon Route 53 to congure active-passive failover. Create an Aurora Replica in a second AWS Region.
     "The solution does not need to handle the load when the primary infrastructure is healthy." => Should use Route 53 Active-Passive 
218. A company has a web server running on an Amazon EC2 instance in a public subnet with an Elastic IP address. The default security group is assigned to the EC2 instance. The default network ACL has been modied to block all trac. A solutions architect needs to make the web server accessible from everywhere on port 443.
     Which combination of steps will accomplish this task? (Choose two.)
>     A. Create a security group with a rule to allow TCP port 443 from source 0.0.0.0/0.
     E. Update the network ACL to allow inbound TCP port 443 from source 0.0.0.0/0 and outbound TCP port 32768-65535 to destination 0.0.0.0/0.
219. A company’s application is having performance issues. The application is stateful and needs to complete in-memory tasks on Amazon EC2 instances. The company used AWS CloudFormation to deploy infrastructure and used the M5 EC2 instance family. As trac increased, the application performance degraded. Users are reporting delays when the users attempt to access the application.
     Which solution will resolve these issues in the MOST operationally ecient way?
>     D. Modify the CloudFormation templates. Replace the EC2 instances with R5 EC2 instances. Deploy the Amazon CloudWatch agent on the EC2 instances to generate custom application latency metrics for future capacity planning. 
> "in-memory tasks" => need the "R" EC2 instance type to archive memory optimization. So we are concerned about C & D.
 Because EC2 instances don't have built-in memory metrics to CW by default. As a result, we have to install the CW agent to archive the purpose.

220. A solutions architect is designing a new API using Amazon API Gateway that will receive requests from users. The volume of requests is highly variable; several hours can pass without receiving a single request. The data processing will take place asynchronously, but should be completed within a few seconds after a request is made.
     Which compute service should the solutions architect have the API invoke to deliver the requirements at the lowest cost?
>     B. An AWS Lambda function
> Lambda is a serverless compute service that can be triggered by API Gateway to process requests asynchronously. It automatically scales based on the incoming request volume and allows for cost optimization by charging only for the actual compute time used to process the requests.
221. A company runs an application on a group of Amazon Linux EC2 instances. For compliance reasons, the company must retain all application log les for 7 years. The log les will be analyzed by a reporting tool that must be able to access all the les concurrently.
     Which storage solution meets these requirements MOST cost-effectively?
>     D. Amazon S3

222. A company has hired an external vendor to perform work in the company’s AWS account. The vendor uses an automated tool that is hosted in an AWS account that the vendor owns. The vendor does not have IAM access to the company’s AWS account.
     How should a solutions architect grant this access to the vendor?
>    A. Create an IAM role in the company’s account to delegate access to the vendor’s IAM role. Attach the appropriate IAM policies to the role for the permissions that the vendor requires.
223. A company has deployed a Java Spring Boot application as a pod that runs on Amazon Elastic Kubernetes Service (Amazon EKS) in private subnets. The application needs to write data to an Amazon DynamoDB table. A solutions architect must ensure that the application can interact with the DynamoDB table without exposing trac to the internet.
     Which combination of steps should the solutions architect take to accomplish this goal? (Choose two.)
>     A. Attach an IAM role that has sucient privileges to the EKS pod.
     D. Create a VPC endpoint for DynamoDB.
>The application needs to write data to an Amazon DynamoDB table = Attach an IAM role that has write privileges to the EKS pod
Without exposing traffic to the internet = VPC endpoint for DynamoDB
224. A company recently migrated its web application to AWS by rehosting the application on Amazon EC2 instances in a single AWS Region. The company wants to redesign its application architecture to be highly available and fault tolerant. Trac must reach all running EC2 instances randomly.
     Which combination of steps should the company take to meet these requirements? (Choose two.)
>  C. Create an Amazon Route 53 multivalue answer routing policy.
     E. Launch four EC2 instances: two instances in one Availability Zone and two instances in another Availability Zone.
> C. A multivalue answer routing policy in Route 53 allows you to configure multiple values for a DNS record, and Route 53 responds to DNS queries with multiple random values. This enables the distribution of traffic randomly among the available EC2 instances.
E. By launching EC2 instances in different AZs, you achieve high availability and fault tolerance. Launching four instances (two in each AZ) ensures that there are enough resources to handle the traffic load and maintain the desired level of availability.
A. Failover routing is designed to direct traffic to a backup resource or secondary location only when the primary resource or location is unavailable.
B. Although a weighted routing policy allows you to distribute traffic across multiple EC2 instances, it does not ensure random distribution.
D. While launching instances in multiple AZs is important for fault tolerance, having only three instances does not provide an even distribution of traffic. With only three instances, the traffic may not be evenly distributed, potentially leading to imbalanced resource utilization.

225. A media company collects and analyzes user activity data on premises. The company wants to migrate this capability to AWS. The user activity data store will continue to grow and will be petabytes in size. The company needs to build a highly available data ingestion solution that facilitates on-demand analytics of existing data and new data with SQL.
     Which solution will meet these requirements with the LEAST operational overhead?
>     B. Send activity data to an Amazon Kinesis Data Firehose delivery stream. Congure the stream to deliver the data to an Amazon Redshift cluster.
>1- Kinesis Data Stream provides a fully managed platform for custom data processing and analysis. Or we can say that used for custom data processing and analysis which required more manual intervention.
2- Kinesis Data Firehose simplifies the delivery of streaming data to various destinations without the need for complex transformations. Option B is more suitable for the given scenario.
> Petabyte scale- Redshift

226. A company collects data from thousands of remote devices by using a RESTful web services application that runs on an Amazon EC2 instance. The EC2 instance receives the raw data, transforms the raw data, and stores all the data in an Amazon S3 bucket. The number of remote devices will increase into the millions soon. The company needs a highly scalable solution that minimizes operational overhead.
     Which combination of steps should a solutions architect take to meet these requirements? (Choose two.)
>     A. Use AWS Glue to process the raw data in Amazon S3.
     E. Use Amazon API Gateway to send the raw data to an Amazon Kinesis data stream. Congure Amazon Kinesis Data Firehose to use the data stream as a source to deliver the data to Amazon S3.
>"RESTful web services" => API Gateway.
"EC2 instance receives the raw data, transforms the raw data, and stores all the data in an Amazon S3 bucket" => GLUE with (Extract - Transform - Load)
227. A company needs to retain its AWS CloudTrail logs for 3 years. The company is enforcing CloudTrail across a set of AWS accounts by using AWS Organizations from the parent account. The CloudTrail target S3 bucket is congured with S3 Versioning enabled. An S3 Lifecycle policy is in place to delete current objects after 3 years.
     After the fourth year of use of the S3 bucket, the S3 bucket metrics show that the number of objects has continued to rise. However, the number of new CloudTrail logs that are delivered to the S3 bucket has remained consistent.
     Which solution will delete objects that are older than 3 years in the MOST cost-effective manner?
>     B. Congure the S3 Lifecycle policy to delete previous versions as well as current versions.
228. A company has an API that receives real-time data from a eet of monitoring devices. The API stores this data in an Amazon RDS DB instance for later analysis. The amount of data that the monitoring devices send to the API uctuates. During periods of heavy trac, the API often returns timeout errors.
     After an inspection of the logs, the company determines that the database is not capable of processing the volume of write trac that comes from the API. A solutions architect must minimize the number of connections to the database and must ensure that data is not lost during periods of heavy trac.
     Which solution will meet these requirements?
>    C. Modify the API to write incoming data to an Amazon Simple Queue Service (Amazon SQS) queue. Use an AWS Lambda function that Amazon SQS invokes to write data from the queue to the database.
> By leveraging SQS as a buffer and using an Lambda to process and write data from the queue to the database, the solution provides scalability, decoupling, and reliability while minimizing the number of connections to the database. This approach handles fluctuations in traffic and ensures data integrity during high-traffic periods.
B. Modifying the DB instance to be a Multi-AZ instance and writing to all active instances can improve availability but does not address the issue of efficiently handling high write traffic and minimizing connections to the database.

229. A company manages its own Amazon EC2 instances that run MySQL databases. The company is manually managing replication and scaling as demand increases or decreases. The company needs a new solution that simplies the process of adding or removing compute capacity to or from its database tier as needed. The solution also must offer improved performance, scaling, and durability with minimal effort from operations.
     Which solution meets these requirements?
> A. Migrate the databases to Amazon Aurora Serverless for Aurora MySQL.
Migrating the databases to Aurora Serverless provides automated scaling and replication capabilities. Aurora Serverless automatically scales the capacity based on the workload, allowing for seamless addition or removal of compute capacity as needed. It also offers improved performance, durability, and high availability without requiring manual management of replication and scaling.

230. A company is concerned that two NAT instances in use will no longer be able to support the trac needed for the company’s application. A solutions architect wants to implement a solution that is highly available, fault tolerant, and automatically scalable.
     What should the solutions architect recommend?
>     C. Remove the two NAT instances and replace them with two NAT gateways in different Availability Zones.
> Highly available, fault tolerant, and automatically scalable = two NAT gateways in different Availability Zones
231. An application runs on an Amazon EC2 instance that has an Elastic IP address in VPC A. The application requires access to a database in VPC B. Both VPCs are in the same AWS account.
     Which solution will provide the required access MOST securely?
>     B. Congure a VPC peering connection between VPC A and VPC B.
232. A company runs demonstration environments for its customers on Amazon EC2 instances. Each environment is isolated in its own VPC. The company’s operations team needs to be notied when RDP or SSH access to an environment has been established.
> C. Publish VPC flow logs to Amazon CloudWatch Logs. Create required metric lters. Create an Amazon CloudWatch metric alarm with a notication action for when the alarm is in the ALARM state.
By publishing VPC flow logs to CloudWatch Logs and creating metric filters to detect RDP or SSH access, the operations team can configure an CloudWatch metric alarm to notify them when the alarm is triggered. This will provide the desired notification when RDP or SSH access to an environment is established.
PC Flow Logs is a feature that enables you to capture information about the IP traffic going to and from network interfaces in your VPC. Flow log data can be published to the following locations: Amazon CloudWatch Logs, Amazon S3, or Amazon Kinesis Data Firehose. After you create a flow log, you can retrieve and view the flow log records in the log group, bucket, or delivery stream that you configured.
Flow logs can help you with a number of tasks, such as:
Diagnosing overly restrictive security group rules
Monitoring the traffic that is reaching your instance

> Option A is incorrect because CloudWatch Application Insights is not designed for detecting RDP or SSH access.
Option B is also incorrect because configuring an IAM instance profile with the AmazonSSMManagedInstanceCore policy does not directly address the requirement of notifying the operations team when RDP or SSH access occurs.
Option D is wrong beacuse configuring an EventBridge rule to listen for EC2 Instance State-change Notification events and using an SNS topic as a target will notify the operations team about changes in the instance state, such as starting or stopping instances. However, it does not specifically detect or notify when RDP or SSH access is established, which is the requirement stated in the question.

233. A solutions architect has created a new AWS account and must secure AWS account root user access. Which combination of actions will accomplish this? (Choose two.)
>     A. Ensure the root user uses a strong password.
>    B. Enable multi-factor authentication to the root user.

234. A company is building a new web-based customer relationship management application. The application will use several Amazon EC2 instances that are backed by Amazon Elastic Block Store (Amazon EBS) volumes behind an Application Load Balancer (ALB). The application will also use an Amazon Aurora database. All data for the application must be encrypted at rest and in transit.
     Which solution will meet these requirements?
>  C. Use AWS Key Management Service (AWS KMS) to encrypt the EBS volumes and Aurora database storage at rest. Attach an AWS Certicate Manager (ACM) certicate to the ALB to encrypt data in transit.
> AWS KMS can be used to encrypt the EBS and Aurora database storage at rest.
ACM can be used to obtain an SSL/TLS certificate and attach it to the ALB. This encrypts the data in transit between the clients and the ALB.

235. A company is moving its on-premises Oracle database to Amazon Aurora PostgreSQL. The database has several applications that write to the same tables. The applications need to be migrated one by one with a month in between each migration. Management has expressed concerns that the database has a high number of reads and writes. The data must be kept in sync across both databases throughout the migration.
     What should a solutions architect recommend?
> C. Use the AWS Schema Conversion Tool with AWS Database Migration Service (AWS DMS) using a memory optimized replication instance. Create a full load plus change data capture (CDC) replication task and a table mapping to select all tables.
The AWS SCT is used to convert the schema and code of the Oracle database to be compatible with Aurora PostgreSQL. AWS DMS is utilized to migrate the data from the Oracle database to Aurora PostgreSQL. Using a memory-optimized replication instance is recommended to handle the high number of reads and writes during the migration process.
By creating a full load plus CDC replication task, the initial data migration is performed, and ongoing changes in the Oracle database are continuously captured and applied to the Aurora PostgreSQL database. Selecting all tables for table mapping ensures that all the applications writing to the same tables are migrated.
236. A company has a three-tier application for image sharing. The application uses an Amazon EC2 instance for the front-end layer, another EC2 instance for the application layer, and a third EC2 instance for a MySQL database. A solutions architect must design a scalable and highly available solution that requires the least amount of change to the application.
     Which solution meets these requirements?
> D. Use load-balanced Multi-AZ AWS Elastic Beanstalk environments for the front-end layer and the application layer. Move the database to an Amazon RDS Multi-AZ DB instance. Use Amazon S3 to store and serve users’ images.
237. An application running on an Amazon EC2 instance in VPC-A needs to access les in another EC2 instance in VPC-B. Both VPCs are in separate AWS accounts. The network administrator needs to design a solution to congure secure access to EC2 instance in VPC-B from VPC- A. The connectivity should not have a single point of failure or bandwidth concerns.
     Which solution will meet these requirements?
>     A. Set up a VPC peering connection between VPC-A and VPC-B.

238. A company wants to experiment with individual AWS accounts for its engineer team. The company wants to be notied as soon as the Amazon EC2 instance usage for a given month exceeds a specic threshold for each account.
     What should a solutions architect do to meet this requirement MOST cost-effectively?
>  C. Use AWS Budgets to create a cost budget for each account. Set the period to monthly. Set the scope to EC2 instances. Set an alert threshold for the budget. Congure an Amazon Simple Notication Service (Amazon SNS) topic to receive a notication when a threshold is exceeded.
AWS Budgets allows you to create budgets for your AWS accounts and set alerts when usage exceeds a certain threshold. By creating a budget for each account, specifying the period as monthly and the scope as EC2 instances, you can effectively track the EC2 usage for each account and be notified when a threshold is exceeded. This solution is the most cost-effective option as it does not require additional resources such as Amazon Athena or Amazon EventBridge.
While Cost Explorer is useful for analyzing costs, it does not provide the real-time alerting capability that AWS Budgets offers.

239. A solutions architect needs to design a new microservice for a company’s application. Clients must be able to call an HTTPS endpoint to reach the microservice. The microservice also must use AWS Identity and Access Management (IAM) to authenticate calls. The solutions architect will write the logic for this microservice by using a single AWS Lambda function that is written in Go 1.x.
     Which solution will deploy the function in the MOST operationally ecient way?
>    A. Create an Amazon API Gateway REST API. Congure the method to use the Lambda function. Enable IAM authentication on the API.
Create an Amazon API Gateway REST API. Configure the method to use the Lambda function. Enable IAM authentication on the API.
This option is the most operationally efficient as it allows you to use API Gateway to handle the HTTPS endpoint and also allows you to use IAM to authenticate the calls to the microservice. API Gateway also provides many additional features such as caching, throttling, and monitoring, which can be useful for a microservice.

240. A company previously migrated its data warehouse solution to AWS. The company also has an AWS Direct Connect connection. Corporate oce users query the data warehouse using a visualization tool. The average size of a query returned by the data warehouse is 50 MB and each webpage sent by the visualization tool is approximately 500 KB. Result sets returned by the data warehouse are not cached.
     Which solution provides the LOWEST data transfer egress cost for the company?
>    D. Host the visualization tool in the same AWS Region as the data warehouse and access it over a Direct Connect connection at a location in the same Region.
> C. -> Valid but in this case you send out of AWS 50MB if you query the DWH instead of the visualization tool, D removes this need since puts the visualization tools in AWS with the DWH so reduces data returned out of AWS from 50MB to 500KB

241. An online learning company is migrating to the AWS Cloud. The company maintains its student records in a PostgreSQL database. The company needs a solution in which its data is available and online across multiple AWS Regions at all times.
     Which solution will meet these requirements with the LEAST amount of operational overhead?
>   C. Migrate the PostgreSQL database to an Amazon RDS for PostgreSQL DB instance. Create a read replica in another Region.
B - Multi-AZ is multiple AZs in same region, does not meet "Multiple AWS Regions" requirement
242. A company hosts its web application on AWS using seven Amazon EC2 instances. The company requires that the IP addresses of all healthy EC2 instances be returned in response to DNS queries.
     Which policy should be used to meet this requirement?
>     C. Multivalue routing policy
> The Multivalue routing policy allows Route 53 to respond to DNS queries with multiple healthy IP addresses for the same resource. This is particularly useful in scenarios where multiple instances are serving the same purpose and need to be load balanced or failover capable. With the Multivalue routing policy, Route 53 returns multiple IP addresses in a random order to distribute the traffic across all healthy instances.
Option A (Simple routing policy) would only return a single IP address in response to DNS queries and does not support returning multiple addresses.
Option B (Latency routing policy) is used to route traffic based on the lowest latency to the resource and does not fulfill the requirement of returning all healthy IP addresses.
Option D (Geolocation routing policy) is used to route traffic based on the geographic location of the user and does not fulfill the requirement of returning all healthy IP addresses.

243. A medical research lab produces data that is related to a new study. The lab wants to make the data available with minimum latency to clinics across the country for their on-premises, le-based applications. The data les are stored in an Amazon S3 bucket that has read-only permissions for each clinic.
     What should a solutions architect recommend to meet these requirements?
>     A. Deploy an AWS Storage Gateway file gateway as a virtual machine (VM) on premises at each clinic
     AWS Storage Gateway is a service that connects an on-premises software appliance with cloud-based storage to provide seamless and secure integration between an organization's on-premises IT environment and AWS's storage infrastructure. By deploying a file gateway as a virtual machine on each clinic's premises, the medical research lab can provide low-latency access to the data stored in the S3 bucket while maintaining read-only permissions for each clinic. This solution allows the clinics to access the data files directly from their on-premises file-based applications without the need for data transfer or migration.

244. A company is using a content management system that runs on a single Amazon EC2 instance. The EC2 instance contains both the web server and the database software. The company must make its website platform highly available and must enable the website to scale to meet user demand.
     What should a solutions architect recommend to meet these requirements?
>   C. Move the database to Amazon Aurora with a read replica in another Availability Zone. Create an Amazon Machine Image (AMI) from the EC2 instance. Congure an Application Load Balancer in two Availability Zones. Attach an Auto Scaling group that uses the AMI across two Availability Zones.
C: This will allow the website platform to be highly available by using Aurora, which provides automatic failover and replication. Additionally, by creating an AMI from the original EC2 instance, the Auto Scaling group can automatically launch new instances in multiple availability zones and use the Application Load Balancer to distribute traffic across them. This way, the website will be able to handle the increased traffic, and will be less likely to go down due to a single point of failure.

245. A company is launching an application on AWS. The application uses an Application Load Balancer (ALB) to direct trac to at least two Amazon EC2 instances in a single target group. The instances are in an Auto Scaling group for each environment. The company requires a development environment and a production environment. The production environment will have periods of high trac.
     Which solution will congure the development environment MOST cost-effectively?
>     A. Recongure the target group in the development environment to have only one EC2 instance as a target.
246. A company runs a web application on Amazon EC2 instances in multiple Availability Zones. The EC2 instances are in private subnets. A solutions architect implements an internet-facing Application Load Balancer (ALB) and species the EC2 instances as the target group. However, the internet trac is not reaching the EC2 instances.
How should the solutions architect recongure the architecture to resolve this issue?
> D. Create public subnets in each Availability Zone. Associate the public subnets with the ALB. Update the route tables for the public subnets with a route to the private subnets.

247. A company has deployed a database in Amazon RDS for MySQL. Due to increased transactions, the database support team is reporting slow reads against the DB instance and recommends adding a read replica.
     Which combination of actions should a solutions architect take before implementing this change? (Choose two.)
>    C. Allow long-running transactions to complete on the source DB instance.
     E. Enable automatic backups on the source instance by setting the backup retention period to a value other than 0.
An active, long-running transaction can slow the process of creating the read replica. We recommend that you wait for long-running transactions to complete before creating a read replica. If you create multiple read replicas in parallel from the same source DB instance, Amazon RDS takes only one snapshot at the start of the first create action.
When creating a read replica, there are a few things to consider. First, you must enable automatic backups on the source DB instance by setting the backup retention period to a value other than 0. This requirement also applies to a read replica that is the source DB instance for another read replica

248. A company runs analytics software on Amazon EC2 instances. The software accepts job requests from users to process data that has been uploaded to Amazon S3. Users report that some submitted data is not being processed Amazon CloudWatch reveals that the EC2 instances have a consistent CPU utilization at or near 100%. The company wants to improve system performance and scale the system based on user load.
     What should a solutions architect do to meet these requirements?
 >    D. Route incoming requests to Amazon Simple Queue Service (Amazon SQS). Congure an EC2 Auto Scaling group based on queue size. Update the software to read from the queue.
249. A company is implementing a shared storage solution for a media application that is hosted in the AWS Cloud. The company needs the ability to use SMB clients to access data. The solution must be fully managed.
     Which AWS solution meets these requirements?
>     D. Create an Amazon FSx for Windows File Server le system. Attach the le system to the origin server. Connect the application server to the le system.
> SMB + fully managed = fsx for windows imo
> Amazon FSx has native support for Windows file system features and for the industry-standard Server Message Block (SMB) protocol to access file storage over a network.
250. A company’s security team requests that network trac be captured in VPC Flow Logs. The logs will be frequently accessed for 90 days and then accessed intermittently.
     What should a solutions architect do to meet these requirements when conguring the logs?
>     D. Use Amazon S3 as the target. Enable an S3 Lifecycle policy to transition the logs to S3 Standard-Infrequent Access (S3 Standard-IA) after 90 days.
>  CloudTrail is designed for auditing and monitoring API activity, not for capturing network traffic logs. It does not meet the requirement of capturing VPC Flow Logs.

251. An Amazon EC2 instance is located in a private subnet in a new VPC. This subnet does not have outbound internet access, but the EC2 instance needs the ability to download monthly security updates from an outside vendor.
     What should a solutions architect do to meet these requirements?
> B. Create a NAT gateway, and place it in a public subnet. Congure the private subnet route table to use the NAT gateway as the default route.
place NAT GW in a public subnet and add it to the private subnet's route table

252. A solutions architect needs to design a system to store client case les. The les are core company assets and are important. The number of les will grow over time.
     The les must be simultaneously accessible from multiple application servers that run on Amazon EC2 instances. The solution must have built-in redundancy.
     Which solution meets these requirements?
>     A. Amazon Elastic File System (Amazon EFS)

253. 看原文
254. A company is reviewing a recent migration of a three-tier application to a VPC. The security team discovers that the principle of least privilege is not being applied to Amazon EC2 security group ingress and egress rules between the application tiers.
     What should a solutions architect do to correct this issue?
>    B. Create security group rules using the security group ID as the source or destination.

255. A company has an ecommerce checkout workow that writes an order to a database and calls a service to process the payment. Users are experiencing timeouts during the checkout process. When users resubmit the checkout form, multiple unique orders are created for the same desired transaction.
     How should a solutions architect refactor this workow to prevent the creation of multiple orders?
>     D. Store the order in the database. Send a message that includes the order number to an Amazon Simple Queue Service (Amazon SQS) FIFO queue. Set the payment service to retrieve the message and process the order. Delete the message from the queue.
> Store the order in the database. Send a message that includes the order number to an Amazon Simple Queue Service (Amazon SQS) FIFO queue. Set the payment service to retrieve the message and process the order. Delete the message from the queue.
This approach ensures that the order creation and payment processing steps are separate and atomic. By sending the order information to an SQS FIFO queue, the payment service can process the order one at a time and in the order they were received. If the payment service is unable to process an order, it can be retried later, preventing the creation of multiple orders. The deletion of the message from the queue after it is processed will prevent the same message from being processed multiple times.
It's worth noting that FIFO queues guarantee that messages are processed in the order they are received, and prevent duplicates.

256. A solutions architect is implementing a document review application using an Amazon S3 bucket for storage. The solution must prevent accidental deletion of the documents and ensure that all versions of the documents are available. Users must be able to download, modify, and upload documents.
     Which combination of actions should be taken to meet these requirements? (Choose two.)
>     B. Enable versioning on the bucket.
     D. Enable MFA Delete on the bucket.
257. A company is building a solution that will report Amazon EC2 Auto Scaling events across all the applications in an AWS account. The company needs to use a serverless solution to store the EC2 Auto Scaling status data in Amazon S3. The company then will use the data in Amazon S3 to provide near-real-time updates in a dashboard. The solution must not affect the speed of EC2 instance launches.
     How should the company move the data to Amazon S3 to meet these requirements?
>     A. Use an Amazon CloudWatch metric stream to send the EC2 Auto Scaling status data to Amazon Kinesis Data Firehose. Store the data in Amazon S3.
     This solution meets the requirements because it is serverless and does not affect the speed of EC2 instance launches. Amazon CloudWatch metric streams can continuously stream CloudWatch metrics to destinations such as Amazon S3. Amazon Kinesis Data Firehose can capture, transform, and deliver streaming data into data lakes, data stores, and analytics services. It can directly put the data into Amazon S3, which can then be used for near-real-time updates in a dashboard.
258. A company has an application that places hundreds of .csv les into an Amazon S3 bucket every hour. The les are 1 GB in size. Each time a le is uploaded, the company needs to convert the le to Apache Parquet format and place the output le into an S3 bucket.
     Which solution will meet these requirements with the LEAST operational overhead?
> D. Create an AWS Glue extract, transform, and load (ETL) job to convert the .csv les to Parquet format and place the output les into an S3 bucket. Create an AWS Lambda function for each S3 PUT event to invoke the ETL job.
259. A company is implementing new data retention policies for all databases that run on Amazon RDS DB instances. The company must retain daily backups for a minimum period of 2 years. The backups must be consistent and restorable.
     Which solution should a solutions architect recommend to meet these requirements?
>     A. Create a backup vault in AWS Backup to retain RDS backups. Create a new backup plan with a daily schedule and an expiration period of 2 years after creation. Assign the RDS DB instances to the backup plan.

260. A company’s compliance team needs to move its le shares to AWS. The shares run on a Windows Server SMB le share. A self-managed on- premises Active Directory controls access to the les and folders.
     The company wants to use Amazon FSx for Windows File Server as part of the solution. The company must ensure that the on-premises Active Directory groups restrict access to the FSx for Windows File Server SMB compliance shares, folders, and les after the move to AWS. The company has created an FSx for Windows File Server le system.
     Which solution will meet these requirements?
>   D. Join the le system to the Active Directory to restrict access.

261. A company recently announced the deployment of its retail website to a global audience. The website runs on multiple Amazon EC2 instances behind an Elastic Load Balancer. The instances run in an Auto Scaling group across multiple Availability Zones.
     The company wants to provide its customers with different versions of content based on the devices that the customers use to access the website.
     Which combination of actions should a solutions architect take to meet these requirements? (Choose two.)
>     A. Congure Amazon CloudFront to cache multiple versions of the content.
     C. Congure a Lambda@Edge function to send specic objects to users based on the User-Agent header.
> NLB lister rule only supports Protocol & Port (Not host/based routing like ALB) => D, E is incorrect. NLB just works layer 4 (TCP/UDP) instead of Layer 7 (HTTP) => B is incorrect.

262. A company plans to use Amazon ElastiCache for its multi-tier web application. A solutions architect creates a Cache VPC for the ElastiCache cluster and an App VPC for the application’s Amazon EC2 instances. Both VPCs are in the us-east-1 Region.
     The solutions architect must implement a solution to provide the application’s EC2 instances with access to the ElastiCache cluster. Which solution will meet these requirements MOST cost-effectively?
>    A. Create a peering connection between the VPCs. Add a route table entry for the peering connection in both VPCs. Congure an inbound rule for the ElastiCache cluster’s security group to allow inbound connection from the application’s security group.
>1. VPC transit is used for more complex architecture and can do VPCs to VPCs connectivity. But for simple VPC 2 VPC can use peer connection. 
>2. To enable private IPv4 traffic between instances in peered VPCs, you must add a route to the route tables associated with the subnets for both instances.

263. A company is building an application that consists of several microservices. The company has decided to use container technologies to deploy its software on AWS. The company needs a solution that minimizes the amount of ongoing effort for maintenance and scaling. The company cannot manage additional infrastructure.
     Which combination of actions should a solutions architect take to meet these requirements? (Choose two.)
>     A. Deploy an Amazon Elastic Container Service (Amazon ECS) cluster.
     D. Deploy an Amazon Elastic Container Service (Amazon ECS) service with a Fargate launch type. Specify a desired task number level of greater than or equal to 2.

264. A company has a web application hosted over 10 Amazon EC2 instances with trac directed by Amazon Route 53. The company occasionally experiences a timeout error when attempting to browse the application. The networking team nds that some DNS queries return IP addresses of unhealthy instances, resulting in the timeout error.
     What should a solutions architect implement to overcome these timeout errors?
>     D. Create an Application Load Balancer (ALB) with a health check in front of the EC2 instances. Route to the ALB from Route 53.
> ALB performs health checks on the EC2 instances, so it will only route traffic to healthy instances. This avoids the timeout errors.
ALB provides load balancing across the instances, improving performance and availability.
Route 53 routes to the ALB DNS name, so you don't have to manage records for each EC2 instance.
This is a standard and robust architecture for public-facing web applications. The ALB acts as the entry point and handles health checks and scaling.

265. A solutions architect needs to design a highly available application consisting of web, application, and database tiers. HTTPS content delivery should be as close to the edge as possible, with the least delivery time.
     Which solution meets these requirements and is MOST secure?
>    C. Congure a public Application Load Balancer (ALB) with multiple redundant Amazon EC2 instances in private subnets. Congure Amazon CloudFront to deliver HTTPS content using the public ALB as the origin.
     This solution meets the requirements for a highly available application with web, application, and database tiers, as well as providing edge-based content delivery. Additionally, it maximizes security by having the ALB in a private subnet, which limits direct access to the web servers, while still being able to serve traffic over the Internet via the public ALB. This will ensure that the web servers are not exposed to the public Internet, which reduces the attack surface and provides a secure way to access the application.

266. A company has a popular gaming platform running on AWS. The application is sensitive to latency because latency can impact the user experience and introduce unfair advantages to some players. The application is deployed in every AWS Region. It runs on Amazon EC2 instances that are part of Auto Scaling groups congured behind Application Load Balancers (ALBs). A solutions architect needs to implement a mechanism to monitor the health of the application and redirect trac to healthy endpoints.
     Which solution meets these requirements?
>    A. Congure an accelerator in AWS Global Accelerator. Add a listener for the port that the application listens on, and attach it to a Regional endpoint in each Region. Add the ALB as the endpoint.
When you have an Application Load Balancer or Network Load Balancer that includes multiple target groups, Global Accelerator considers the load balancer endpoint to be healthy only if each target group behind the load balancer has at least one healthy target. If any single target group for the load balancer has only unhealthy targets, Global Accelerator considers the endpoint to be unhealthy.
AWS Global Accelerator directs traffic to the optimal healthy endpoint based on health checks, it can also route traffic to the closest healthy endpoint based on geographic location of the client. By configuring an accelerator and attaching it to a Regional endpoint in each Region, and adding the ALB as the endpoint, the solution will redirect traffic to healthy endpoints, improving the user experience by reducing latency and ensuring that the application is running optimally. This solution will ensure that traffic is directed to the closest healthy endpoint and will help to improve the overall user experience.

267. A company has one million users that use its mobile app. The company must analyze the data usage in near-real time. The company also must encrypt the data in near-real time and must store the data in a centralized location in Apache Parquet format for further processing.
     Which solution will meet these requirements with the LEAST operational overhead?
>     D. Create an Amazon Kinesis Data Firehose delivery stream to store the data in Amazon S3. Create an Amazon Kinesis Data Analytics application to analyze the data.

268. A gaming company has a web application that displays scores. The application runs on Amazon EC2 instances behind an Application Load Balancer. The application stores data in an Amazon RDS for MySQL database. Users are starting to experience long delays and interruptions that are caused by database read performance. The company wants to improve the user experience while minimizing changes to the application’s architecture.
     What should a solutions architect do to meet these requirements?
 >    B. Use RDS Proxy between the application and the database.
> Seems like RDS Proxy is used for too many connections, while ElastiCache is general performance improvement.
269. An ecommerce company has noticed performance degradation of its Amazon RDS based web application. The performance degradation is attributed to an increase in the number of read-only SQL queries triggered by business analysts. A solutions architect needs to solve the problem with minimal changes to the existing web application.
     What should the solutions architect recommend?
> C. Create a read replica of the primary database and have the business analysts run their queries.

270. A company is using a centralized AWS account to store log data in various Amazon S3 buckets. A solutions architect needs to ensure that the data is encrypted at rest before the data is uploaded to the S3 buckets. The data also must be encrypted in transit.
     Which solution meets these requirements?
>    A. Use client-side encryption to encrypt the data that is being uploaded to the S3 buckets.

271. A solutions architect observes that a nightly batch processing job is automatically scaled up for 1 hour before the desired Amazon EC2 capacity is reached. The peak capacity is the ‘same every night and the batch jobs always start at 1 AM. The solutions architect needs to nd a cost-effective solution that will allow for the desired EC2 capacity to be reached quickly and allow the Auto Scaling group to scale down after the batch jobs are complete.
     What should the solutions architect do to meet these requirements?
> C. Congure scheduled scaling to scale up to the desired compute level.
272. A company serves a dynamic website from a eet of Amazon EC2 instances behind an Application Load Balancer (ALB). The website needs to support multiple languages to serve customers around the world. The website’s architecture is running in the us-west-1 Region and is exhibiting high request latency for users that are located in other parts of the world.
     The website needs to serve requests quickly and eciently regardless of a user’s location. However, the company does not want to recreate the existing architecture across multiple Regions.
     What should a solutions architect do to meet these requirements?
>    B. Congure an Amazon CloudFront distribution with the ALB as the origin. Set the cache behavior settings to cache based on the Accept- Language request header.
273. A rapidly growing ecommerce company is running its workloads in a single AWS Region. A solutions architect must create a disaster recovery (DR) strategy that includes a different AWS Region. The company wants its database to be up to date in the DR Region with the least possible latency. The remaining infrastructure in the DR Region needs to run at reduced capacity and must be able to scale up if necessary.
     Which solution will meet these requirements with the LOWEST recovery time objective (RTO)?
>    B. Use an Amazon Aurora global database with a warm standby deployment.
>    Aurora global database is a good solution for disaster recovery, pilot light deployment provides only a minimalistic setup and would require manual intervention to make the DR Region fully operational, which increases the recovery time.
The pilot light approach requires you to “turn on” servers, possibly deploy additional (non-core) infrastructure, and scale up, whereas warm standby only requires you to scale up (everything is already deployed and running). Use your RTO and RPO needs to help you choose between these approaches.
274. A company runs an application on Amazon EC2 instances. The company needs to implement a disaster recovery (DR) solution for the application. The DR solution needs to have a recovery time objective (RTO) of less than 4 hours. The DR solution also needs to use the fewest possible AWS resources during normal operations.
     Which solution will meet these requirements in the MOST operationally ecient way?
>     B. Create Amazon Machine Images (AMIs) to back up the EC2 instances. Copy the AMIs to a secondary AWS Region. Automate infrastructure deployment in the secondary Region by using AWS CloudFormation.
> CloudFormation allows you to define and provision resources in a declarative manner, making it easier to maintain and update your infrastructure. This solution is more operationally efficient compared to Option A.

275. A company runs an internal browser-based application. The application runs on Amazon EC2 instances behind an Application Load Balancer. The instances run in an Amazon EC2 Auto Scaling group across multiple Availability Zones. The Auto Scaling group scales up to 20 instances during work hours, but scales down to 2 instances overnight. Staff are complaining that the application is very slow when the day begins, although it runs well by mid-morning.
     How should the scaling be changed to address the staff complaints and keep costs to a minimum?
>     C. Implement a target tracking action triggered at a lower CPU threshold, and decrease the cooldown period.
 
276. A company has a multi-tier application deployed on several Amazon EC2 instances in an Auto Scaling group. An Amazon RDS for Oracle instance is the application’ s data layer that uses Oracle-specic PL/SQL functions. Trac to the application has been steadily increasing. This is causing the EC2 instances to become overloaded and the RDS instance to run out of storage. The Auto Scaling group does not have any scaling metrics and denes the minimum healthy instance count only. The company predicts that trac will continue to increase at a steady but unpredictable rate before leveling off.
     What should a solutions architect do to ensure the system can automatically scale for the increased trac? (Choose two.)
>     A. Congure storage Auto Scaling on the RDS for Oracle instance.
     D. Congure the Auto Scaling group to use the average CPU as the scaling metric.

277. A company provides an online service for posting video content and transcoding it for use by any mobile platform. The application architecture uses Amazon Elastic File System (Amazon EFS) Standard to collect and store the videos so that multiple Amazon EC2 Linux instances can access the video content for processing. As the popularity of the service has grown over time, the storage costs have become too expensive.
     Which storage solution is MOST cost-effective?
>   D. Use Amazon S3 for storing the video content. Move the les temporarily over to an Amazon Elastic Block Store (Amazon EBS) volume attached to the server for processing.
278. A company wants to create an application to store employee data in a hierarchical structured relationship. The company needs a minimum- latency response to high-trac queries for the employee data and must protect any sensitive data. The company also needs to receive monthly email messages if any nancial information is present in the employee data.
     Which combination of steps should a solutions architect take to meet these requirements? (Choose two.)
>     B. Use Amazon DynamoDB to store the employee data in hierarchies. Export the data to Amazon S3 every month.
     E. Congure Amazon Macie for the AWS account. Integrate Macie with Amazon EventBridge to send monthly notications through an Amazon Simple Notication Service (Amazon SNS) subscription.
>B meets the need to store hierarchical employee data in DynamoDB for low latency queries at high traffic. DynamoDB can handle the access patterns for hierarchical data. Exporting to S3 monthly provides an audit trail.
E sets up Macie to analyze sensitive data and integrate with EventBridge to trigger monthly SNS notifications when financial data is present.
279. A company has an application that is backed by an Amazon DynamoDB table. The company’s compliance requirements specify that database backups must be taken every month, must be available for 6 months, and must be retained for 7 years.
     Which solution will meet these requirements?
     A. Create an AWS Backup plan to back up the DynamoDB table on the rst day of each month. Specify a lifecycle policy that transitions the backup to cold storage after 6 months. Set the retention period for each backup to 7 years.
280. A company is using Amazon CloudFront with its website. The company has enabled logging on the CloudFront distribution, and logs are saved in one of the company’s Amazon S3 buckets. The company needs to perform advanced analyses on the logs and build visualizations.
     What should a solutions architect do to meet these requirements?
>     B. Use standard SQL queries in Amazon Athena to analyze the CloudFront logs in the S3 bucket. Visualize the results with Amazon QuickSight.
>Amazon Athena allows you to run standard SQL queries directly on the data stored in the S3 bucket.
> Analysis on S3 = Athena 
> Visualizations = Quicksight
281. A company runs a eet of web servers using an Amazon RDS for PostgreSQL DB instance. After a routine compliance check, the company sets a standard that requires a recovery point objective (RPO) of less than 1 second for all its production databases.
     Which solution meets these requirements?
>   A. Enable a Multi-AZ deployment for the DB instance.
282. A company runs a web application that is deployed on Amazon EC2 instances in the private subnet of a VPC. An Application Load Balancer (ALB) that extends across the public subnets directs web trac to the EC2 instances. The company wants to implement new security measures to restrict inbound trac from the ALB to the EC2 instances while preventing access from any other source inside or outside the private subnet of the EC2 instances.
     Which solution will meet these requirements?
>    B. Congure the security group for the EC2 instances to only allow trac that comes from the security group for the ALB.
283. A research company runs experiments that are powered by a simulation application and a visualization application. The simulation application runs on Linux and outputs intermediate data to an NFS share every 5 minutes. The visualization application is a Windows desktop application that displays the simulation output and requires an SMB le system.
     The company maintains two synchronized le systems. This strategy is causing data duplication and inecient resource usage. The company needs to migrate the applications to AWS without making code changes to either application.
     Which solution will meet these requirements?
>     D. Migrate the simulation application to Linux Amazon EC2 instances. Migrate the visualization application to Windows EC2 instances. Congure Amazon FSx for NetApp ONTAP for storage.
284. As part of budget planning, management wants a report of AWS billed items listed by user. The data will be used to create department budgets. A solutions architect needs to determine the most ecient way to obtain this report information.
     Which solution meets these requirements?
>     B. Create a report in Cost Explorer and download the report.
285. A company hosts its static website by using Amazon S3. The company wants to add a contact form to its webpage. The contact form will have dynamic server-side components for users to input their name, email address, phone number, and user message. The company anticipates that there will be fewer than 100 site visits each month.
     Which solution will meet these requirements MOST cost-effectively?
>     B. Create an Amazon API Gateway endpoint with an AWS Lambda backend that makes a call to Amazon Simple Email Service (Amazon SES).
286. A company has a static website that is hosted on Amazon CloudFront in front of Amazon S3. The static website uses a database backend. The company notices that the website does not reect updates that have been made in the website’s Git repository. The company checks the continuous integration and continuous delivery (CI/CD) pipeline between the Git repository and Amazon S3. The company veries that the webhooks are congured properly and that the CI/CD pipeline is sending messages that indicate successful deployments.
     A solutions architect needs to implement a solution that displays the updates on the website. Which solution will meet these requirements?
>   C. Invalidate the CloudFront cache.
287. A company wants to migrate a Windows-based application from on premises to the AWS Cloud. The application has three tiers: an application tier, a business tier, and a database tier with Microsoft SQL Server. The company wants to use specic features of SQL Server such as native backups and Data Quality Services. The company also needs to share les for processing between the tiers.
     How should a solutions architect design the architecture to meet these requirements?
>     B. Host all three tiers on Amazon EC2 instances. Use Amazon FSx for Windows File Server for le sharing between the tiers.
288. A company is migrating a Linux-based web server group to AWS. The web servers must access les in a shared le store for some content. The company must not make any changes to the application.
     What should a solutions architect do to meet these requirements?
>     C. Create an Amazon Elastic File System (Amazon EFS) le system. Mount the EFS le system on all web servers.
> To meet the requirements of providing a shared file store for Linux-based web servers without making changes to the application, using an Amazon EFS file system is the best solution.
Amazon EFS is a managed NFS file system service that provides shared access to files across multiple Linux-based instances, which makes it suitable for this use case.

289. A company has an AWS Lambda function that needs read access to an Amazon S3 bucket that is located in the same AWS account. Which solution will meet these requirements in the MOST secure manner?
>     B. Apply an IAM role to the Lambda function. Apply an IAM policy to the role to grant read access to the S3 bucket.
290. A company hosts a web application on multiple Amazon EC2 instances. The EC2 instances are in an Auto Scaling group that scales in response to user demand. The company wants to optimize cost savings without making a long-term commitment.
     Which EC2 instance purchasing option should a solutions architect recommend to meet these requirements?
>     C. A mix of On-Demand Instances and Spot Instances
> By combining On-Demand Instances for steady-state workloads or critical components and Spot Instances for less critical or burstable workloads, you can achieve a balance between cost savings and performance. This strategy allows you to optimize costs without making a long-term commitment, as Spot Instances provide cost savings without the need for upfront payments or long-term contracts.

291. A media company uses Amazon CloudFront for its publicly available streaming video content. The company wants to secure the video content that is hosted in Amazon S3 by controlling who has access. Some of the company’s users are using a custom HTTP client that does not support cookies. Some of the company’s users are unable to change the hardcoded URLs that they are using for access.
     Which services or methods will meet these requirements with the LEAST impact to the users? (Choose two.)
>     A. Signed cookies
     B. Signed URLs

292. A company is preparing a new data platform that will ingest real-time streaming data from multiple sources. The company needs to transform the data before writing the data to Amazon S3. The company needs the ability to use SQL to query the transformed data.
     Which solutions will meet these requirements? (Choose two.)
>     A. Use Amazon Kinesis Data Streams to stream the data. Use Amazon Kinesis Data Analytics to transform the data. Use Amazon Kinesis Data Firehose to write the data to Amazon S3. Use Amazon Athena to query the transformed data from Amazon S3.
     B. Use Amazon Managed Streaming for Apache Kafka (Amazon MSK) to stream the data. Use AWS Glue to transform the data and to write the data to Amazon S3. Use Amazon Athena to query the transformed data from Amazon S3.
> You can create streaming extract, transform, and load (ETL) jobs that run continuously, consume data from streaming sources like Amazon Kinesis Data Streams, Apache Kafka, and Amazon Managed Streaming for Apache Kafka (Amazon MSK). The jobs cleanse and transform the data, and then load the results into Amazon S3 data lakes or JDBC data stores.
 Amazon Kinesis Data Analytics provides built-in functions to filter, aggregate, and transform streaming data for advanced analytics. It processes streaming data with sub-second latencies, enabling you to analyze and respond to incoming data and streaming events in real time.

293. A company has an on-premises volume backup solution that has reached its end of life. The company wants to use AWS as part of a new backup solution and wants to maintain local access to all the data while it is backed up on AWS. The company wants to ensure that the data backed up on AWS is automatically and securely transferred.
     Which solution meets these requirements?
>     D. Use AWS Storage Gateway and congure a stored volume gateway. Run the Storage Gateway software appliance on premises and map the gateway storage volumes to on-premises storage. Mount the gateway storage volumes to provide local access to the data.
294. An application that is hosted on Amazon EC2 instances needs to access an Amazon S3 bucket. Trac must not traverse the internet. How should a solutions architect congure access to meet these requirements?
>     B. Set up a gateway VPC endpoint for Amazon S3 in the VPC.

295. An ecommerce company stores terabytes of customer data in the AWS Cloud. The data contains personally identiable information (PII). The company wants to use the data in three applications. Only one of the applications needs to process the PII. The PII must be removed before the other two applications process the data.
     Which solution will meet these requirements with the LEAST operational overhead?
     B. Store the data in an Amazon S3 bucket. Process and transform the data by using S3 Object Lambda before returning the data to the requesting application.
296. A development team has launched a new application that is hosted on Amazon EC2 instances inside a development VPC. A solutions architect needs to create a new VPC in the same account. The new VPC will be peered with the development VPC. The VPC CIDR block for the development VPC is 192.168.0.0/24. The solutions architect needs to create a CIDR block for the new VPC. The CIDR block must be valid for a VPC peering connection to the development VPC.
     What is the SMALLEST CIDR block that meets these requirements?
>     D. 10.0.1.0/24
> CIDR表示法：定义了IP地址范围。例如，/24表示256个IP地址，/32表示1个IP地址。
> VPC对等连接：要求两个VPC的CIDR块不重叠。

297. A company deploys an application on ve Amazon EC2 instances. An Application Load Balancer (ALB) distributes trac to the instances by using a target group. The average CPU usage on each of the instances is below 10% most of the time, with occasional surges to 65%.
     A solutions architect needs to implement a solution to automate the scalability of the application. The solution must optimize the cost of the architecture and must ensure that the application has enough CPU resources when surges occur.
     Which solution will meet these requirements?
> B. Create an EC2 Auto Scaling group. Select the existing ALB as the load balancer and the existing target group as the target group. Set a target tracking scaling policy that is based on the ASGAverageCPUUtilization metric. Set the minimum instances to 2, the desired capacity to 3, the maximum instances to 6, and the target value to 50%. Add the EC2 instances to the Auto Scaling group.

298. A company is running a critical business application on Amazon EC2 instances behind an Application Load Balancer. The EC2 instances run in an Auto Scaling group and access an Amazon RDS DB instance.
     The design did not pass an operational review because the EC2 instances and the DB instance are all located in a single Availability Zone. A solutions architect must update the design to use a second Availability Zone.
     Which solution will make the application highly available?
> C. Provision a subnet in each Availability Zone. Congure the Auto Scaling group to distribute the EC2 instances across both Availability Zones. Congure the DB instance for Multi-AZ deployment.
a subnet only resides on a one AZ, it does not span to another AZ.
This solution will ensure that the EC2 instances and the DB instance are not located in the same Availability Zone, which will improve the availability of the application.

299. A research laboratory needs to process approximately 8 TB of data. The laboratory requires sub-millisecond latencies and a minimum throughput of 6 GBps for the storage subsystem. Hundreds of Amazon EC2 instances that run Amazon Linux will distribute and process the data.
     Which solution will meet the performance requirements?
>     B. Create an Amazon S3 bucket to store the raw data. Create an Amazon FSx for Lustre le system that uses persistent SSD storage. Select the option to import data from and export data to Amazon S3. Mount the le system on the EC2 instances.
>Keyword here is a minimum throughput of 6 GBps. Only the FSx for Lustre with SSD option gives the sub-milli response and throughput of 6 GBps or more.
B. Create an Amazon S3 bucket to store the raw data. Create an Amazon FSx for Lustre file system that uses persistent SSD storage. Select the option to import data from and export data to Amazon S3. Mount the file system on the EC2 instances.

300.  A company needs to migrate a legacy application from an on-premises data center to the AWS Cloud because of hardware capacity constraints. The application runs 24 hours a day, 7 days a week. The application’s database storage continues to grow over time.
      What should a solutions architect do to meet these requirements MOST cost-effectively?
 > C. Migrate the application layer to Amazon EC2 Reserved Instances. Migrate the data storage layer to Amazon Aurora Reserved Instances. 
> Amazon EC2 Reserved Instances allow for significant cost savings compared to On-Demand instances for long-running, steady-state workloads like this one. Reserved Instances provide a capacity reservation, so the instances are guaranteed to be available for the duration of the reservation period.
 Amazon Aurora is a highly scalable, cloud-native relational database service that is designed to be compatible with MySQL and PostgreSQL. It can automatically scale up to meet growing storage requirements, so it can accommodate the application's database storage needs over time. By using Reserved Instances for Aurora, the cost savings will be significant over the long term.
 
301. A university research laboratory needs to migrate 30 TB of data from an on-premises Windows le server to Amazon FSx for Windows File Server. The laboratory has a 1 Gbps network link that many other departments in the university share.
     The laboratory wants to implement a data migration service that will maximize the performance of the data transfer. However, the laboratory needs to be able to control the amount of bandwidth that the service uses to minimize the impact on other departments. The data migration must take place within the next 5 days.
     Which AWS solution will meet these requirements?
> C. AWS DataSync
> AWS DataSync is a data transfer service that can copy large amounts of data between on-premises storage and Amazon FSx for Windows File Server at high speeds. It allows you to control the amount of bandwidth used during data transfer.
• DataSync uses agents at the source and destination to automatically copy files and file metadata over the network. This optimizes the data transfer and minimizes the impact on your network bandwidth.
• DataSync allows you to schedule data transfers and configure transfer rates to suit your needs. You can transfer 30 TB within 5 days while controlling bandwidth usage.
• DataSync can resume interrupted transfers and validate data to ensure integrity. It provides detailed monitoring and reporting on the progress and performance of data transfers.
> Option A - AWS Snowcone is more suitable for physically transporting data when network bandwidth is limited. It would not complete the transfer within 5 days.
Option B - Amazon FSx File Gateway only provides access to files stored in Amazon FSx and does not perform the actual data migration from on-premises to FSx.
Option D - AWS Transfer Family is for transferring files over FTP, FTPS and SFTP. It may require scripting to transfer 30 TB and monitor progress, and lacks bandwidth controls.

302. A company wants to create a mobile app that allows users to stream slow-motion video clips on their mobile devices. Currently, the app captures video clips and uploads the video clips in raw format into an Amazon S3 bucket. The app retrieves these video clips directly from the S3 bucket. However, the videos are large in their raw format.
     Users are experiencing issues with buffering and playback on mobile devices. The company wants to implement solutions to maximize the performance and scalability of the app while minimizing operational overhead.
     Which combination of solutions will meet these requirements? (Choose two.)
>     A. Deploy Amazon CloudFront for content delivery and caching.
     C. Use Amazon Elastic Transcoder to convert the video les to more appropriate formats.
303. A company is launching a new application deployed on an Amazon Elastic Container Service (Amazon ECS) cluster and is using the Fargate launch type for ECS tasks. The company is monitoring CPU and memory usage because it is expecting high trac to the application upon its launch. However, the company wants to reduce costs when utilization decreases.
     What should a solutions architect recommend?
>    D. Use AWS Application Auto Scaling with target tracking policies to scale when ECS metric breaches trigger an Amazon CloudWatch alarm.
This is running on Fargate, so EC2 scaling (A and C) is out. Lambda (B) is too complex.
> Answer is D - Auto-scaling with target tracking
304. A company recently created a disaster recovery site in a different AWS Region. The company needs to transfer large amounts of data back and forth between NFS le systems in the two Regions on a periodic basis.
     Which solution will meet these requirements with the LEAST operational overhead?
>    A. Use AWS DataSync.
305. A company is designing a shared storage solution for a gaming application that is hosted in the AWS Cloud. The company needs the ability to use SMB clients to access data. The solution must be fully managed.
     Which AWS solution meets these requirements?
>     C. Create an Amazon FSx for Windows File Server le system. Attach the le system to the origin server. Connect the application server to the le system.
> C L: Amazon FSx for Windows File Server file system

306. A company wants to run an in-memory database for a latency-sensitive application that runs on Amazon EC2 instances. The application processes more than 100,000 transactions each minute and requires high network throughput. A solutions architect needs to provide a cost- effective network design that minimizes data transfer charges.
     Which solution meets these requirements?
>     A. Launch all EC2 instances in the same Availability Zone within the same AWS Region. Specify a placement group with cluster strategy when launching EC2 instances.
     • Launching instances within a single AZ and using a cluster placement group provides the lowest network latency and highest bandwidth between instances. This maximizes performance for an in-memory database and high-throughput application.
     • Communications between instances in the same AZ and placement group are free, minimizing data transfer charges. Inter-AZ and public IP traffic can incur charges.
     • A cluster placement group enables the instances to be placed close together within the AZ, allowing the high network throughput required. Partition groups span AZs, reducing bandwidth.
     • Auto Scaling across zones could launch instances in AZs that increase data transfer charges. It may reduce network throughput, impacting performance.
307. A company that primarily runs its application servers on premises has decided to migrate to AWS. The company wants to minimize its need to scale its Internet Small Computer Systems Interface (iSCSI) storage on premises. The company wants only its recently accessed data to remain stored locally.
     Which AWS solution should the company use to meet these requirements?
>  D. AWS Storage Gateway Volume Gateway cached volumes
> AWS Storage Gateway Volume Gateway provides two configurations for connecting to iSCSI storage, namely, stored volumes and cached volumes. The stored volume configuration stores the entire data set on-premises and asynchronously backs up the data to AWS. The cached volume configuration stores recently accessed data on-premises, and the remaining data is stored in Amazon S3.
Since the company wants only its recently accessed data to remain stored locally, the cached volume configuration would be the most appropriate. It allows the company to keep frequently accessed data on-premises and reduce the need for scaling its iSCSI storage while still providing access to all data through the AWS cloud. This configuration also provides low-latency access to frequently accessed data and cost- effective off-site backups for less frequently accessed data.
308. ? A company has multiple AWS accounts that use consolidated billing. The company runs several active high performance Amazon RDS for Oracle On-Demand DB instances for 90 days. The company’s nance team has access to AWS Trusted Advisor in the consolidated billing account and all other AWS accounts.
     The nance team needs to use the appropriate AWS account to access the Trusted Advisor check recommendations for RDS. The nance team must review the appropriate Trusted Advisor check to reduce RDS costs.
     Which combination of steps should the nance team take to meet these requirements? (Choose two.)

B. Use the Trusted Advisor recommendations from the consolidated billing account to see all RDS instance checks at the same time.
C. Review the Trusted Advisor check for Amazon RDS Reserved Instance Optimization.
D. Review the Trusted Advisor check for Amazon RDS Idle DB Instances.

309. A solutions architect needs to optimize storage costs. The solutions architect must identify any Amazon S3 buckets that are no longer being accessed or are rarely accessed.
     Which solution will accomplish this goal with the LEAST operational overhead?

A. Analyze bucket access patterns by using the S3 Storage Lens dashboard for advanced activity metrics.

310. A company sells datasets to customers who do research in articial intelligence and machine learning (AI/ML). The datasets are large, formatted les that are stored in an Amazon S3 bucket in the us-east-1 Region. The company hosts a web application that the customers use to purchase access to a given dataset. The web application is deployed on multiple Amazon EC2 instances behind an Application Load Balancer. After a purchase is made, customers receive an S3 signed URL that allows access to the les.
     The customers are distributed across North America and Europe. The company wants to reduce the cost that is associated with data transfers and wants to maintain or improve performance.
     What should a solutions architect do to meet these requirements?
>     B. Deploy an Amazon CloudFront distribution with the existing S3 bucket as the origin. Direct customer requests to the CloudFront URL. Switch to CloudFront signed URLs for access control.

311. A company is using AWS to design a web application that will process insurance quotes. Users will request quotes from the application. Quotes must be separated by quote type, must be responded to within 24 hours, and must not get lost. The solution must maximize operational eciency and must minimize maintenance.
     Which solution meets these requirements
>  C. Create a single Amazon Simple Notication Service (Amazon SNS) topic. Subscribe Amazon Simple Queue Service (Amazon SQS) queues to the SNS topic. Congure SNS message ltering to publish messages to the proper SQS queue based on the quote type. Congure each backend application server to use its own SQS queue.

312. A company has an application that runs on several Amazon EC2 instances. Each EC2 instance has multiple Amazon Elastic Block Store (Amazon EBS) data volumes attached to it. The application’s EC2 instance conguration and data need to be backed up nightly. The application also needs to be recoverable in a different AWS Region.
     Which solution will meet these requirements in the MOST operationally ecient way?
>     B. Create a backup plan by using AWS Backup to perform nightly backups. Copy the backups to another Region. Add the application’s EC2 instances as resources.
313. A company is building a mobile app on AWS. The company wants to expand its reach to millions of users. The company needs to build a platform so that authorized users can watch the company’s content on their mobile devices.
     What should a solutions architect recommend to meet these requirements?
>  C. Use Amazon CloudFront. Provide signed URLs to stream content.
314. A company has an on-premises MySQL database used by the global sales team with infrequent access patterns. The sales team requires the database to have minimal downtime. A database administrator wants to migrate this database to AWS without selecting a particular instance type in anticipation of more users in the future.
     Which service should a solutions architect recommend?
>     B. Amazon Aurora Serverless for MySQL
>     "without selecting a particular instance type" = serverless
315. A company experienced a breach that affected several applications in its on-premises data center. The attacker took advantage of vulnerabilities in the custom applications that were running on the servers. The company is now migrating its applications to run on Amazon EC2 instances. The company wants to implement a solution that actively scans for vulnerabilities on the EC2 instances and sends a report that details the ndings.
     Which solution will meet these requirements?
>   D. Turn on Amazon Inspector. Deploy the Amazon Inspector agent to the EC2 instances. Congure an AWS Lambda function to automate the generation and distribution of reports that detail the ndings.  AWS Shield for DDOS
     Amazon Macie for discover and protect sensitive date
     Amazon GuardDuty for intelligent thread discovery to protect AWS account Amazon Inspector for automated security assessment. like known Vulnerability
316. A company uses an Amazon EC2 instance to run a script to poll for and process messages in an Amazon Simple Queue Service (Amazon SQS) queue. The company wants to reduce operational costs while maintaining its ability to process a growing number of messages that are added to the queue.
     What should a solutions architect recommend to meet these requirements?
>   C. Migrate the script on the EC2 instance to an AWS Lambda function with the appropriate runtime. D. Use AWS Systems Manager Run Command to run the script on demand.
317. A company uses a legacy application to produce data in CSV format. The legacy application stores the output data in Amazon S3. The company is deploying a new commercial off-the-shelf (COTS) application that can perform complex SQL queries to analyze data that is stored in Amazon Redshift and Amazon S3 only. However, the COTS application cannot process the .csv les that the legacy application produces.
     The company cannot update the legacy application to produce data in another format. The company needs to implement a solution so that the COTS application can use the data that the legacy application produces.
     Which solution will meet these requirements with the LEAST operational overhead?
>     A. Create an AWS Glue extract, transform, and load (ETL) job that runs on a schedule. Congure the ETL job to process the .csv les and store the processed data in Amazon Redshift.
     AWS Glue is a fully managed ETL service that can extract data from various sources, transform it into the required format, and load it into a target data store. In this case, the ETL job can be configured to read the CSV files from Amazon S3, transform the data into a format that can be loaded into Amazon Redshift, and load it into an Amazon Redshift table.
318. A company recently migrated its entire IT environment to the AWS Cloud. The company discovers that users are provisioning oversized Amazon EC2 instances and modifying security group rules without using the appropriate change control process. A solutions architect must devise a strategy to track and audit these inventory and conguration changes.
     Which actions should the solutions architect take to meet these requirements? (Choose two.)
>     A. Enable AWS CloudTrail and use it for auditing.
     D. Enable AWS Config and create rules for auditing and compliance purposes.
>A. Enable AWS CloudTrail and use it for auditing. CloudTrail provides event history of your AWS account activity, including actions taken through the AWS Management Console, AWS Command Line Interface (CLI), and AWS SDKs and APIs. By enabling CloudTrail, the company can track user activity and changes to AWS resources, and monitor compliance with internal policies and external regulations.
D. Enable AWS Config and create rules for auditing and compliance purposes. AWS Config provides a detailed inventory of the AWS resources in your account, and continuously records changes to the configurations of those resources. By creating rules in AWS Config, the company can automate the evaluation of resource configurations against desired state, and receive alerts when configurations drift from compliance.

319. A company has hundreds of Amazon EC2 Linux-based instances in the AWS Cloud. Systems administrators have used shared SSH keys to manage the instances. After a recent audit, the company’s security team is mandating the removal of all shared keys. A solutions architect must design a solution that provides secure access to the EC2 instances.
     Which solution will meet this requirement with the LEAST amount of administrative overhead?
>     A. Use AWS Systems Manager Session Manager to connect to the EC2 instances.

320. A company is using a eet of Amazon EC2 instances to ingest data from on-premises data sources. The data is in JSON format and ingestion rates can be as high as 1 MB/s. When an EC2 instance is rebooted, the data in-ight is lost. The company’s data science team wants to query ingested data in near-real time.
     Which solution provides near-real-time data querying that is scalable with minimal data loss?
>     A. Publish data to Amazon Kinesis Data Streams, Use Kinesis Data Analytics to query the data.
321. What should a solutions architect do to ensure that all objects uploaded to an Amazon S3 bucket are encrypted?
> D. Update the bucket policy to deny if the PutObject does not have an x-amz-server-side-encryption header set.
To encrypt an object at the time of upload, you need to add a header called x-amz-server-side-encryption to the request to tell S3 to encrypt the object using SSE-C, SSE-S3, or SSE-KMS. The following code example shows a Put request using SSE-S3.
322. A solutions architect is designing a multi-tier application for a company. The application's users upload images from a mobile device. The application generates a thumbnail of each image and returns a message to the user to conrm that the image was uploaded successfully.
     The thumbnail generation can take up to 60 seconds, but the company wants to provide a faster response time to its users to notify them that the original image was received. The solutions architect must design the application to asynchronously dispatch requests to the different application tiers.
     What should the solutions architect do to meet these requirements?
> C. Create an Amazon Simple Queue Service (Amazon SQS) message queue. As images are uploaded, place a message on the SQS queue for thumbnail generation. Alert the user through an application message that the image was received.
Asynchronous, Decoupling = Amazon Simple Queue Service

323. A company’s facility has badge readers at every entrance throughout the building. When badges are scanned, the readers send a message over HTTPS to indicate who attempted to access that particular entrance.
     A solutions architect must design a system to process these messages from the sensors. The solution must be highly available, and the results must be made available for the company’s security team to analyze.
     Which system architecture should the solutions architect recommend?

> B. Create an HTTPS endpoint in Amazon API Gateway. Congure the API Gateway endpoint to invoke an AWS Lambda function to process the messages and save the results to an Amazon DynamoDB table.

324. A company wants to implement a disaster recovery plan for its primary on-premises le storage volume. The le storage volume is mounted from an Internet Small Computer Systems Interface (iSCSI) device on a local storage server. The le storage volume holds hundreds of terabytes (TB) of data.
     The company wants to ensure that end users retain immediate access to all le types from the on-premises systems without experiencing latency.
     Which solution will meet these requirements with the LEAST amount of change to the company's existing infrastructure?
> D. Provision an AWS Storage Gateway Volume Gateway stored volume with the same amount of disk space as the existing le storage volume. Mount the Volume Gateway stored volume to the existing le server by using iSCSI, and copy all les to the storage volume. Congure scheduled snapshots of the storage volume. To recover from a disaster, restore a snapshot to an Amazon Elastic Block Store (Amazon EBS) volume and attach the EBS volume to an Amazon EC2 instance.
Volume Gateway CACHED Vs STORED
Cached = stores a subset of frequently accessed data locally
Stored = Retains the ENTIRE ("all file types") in on prem data centre

325. 



# Without Classification
**OpsWorks** Configuration management service, chef-puppet, managed instances
**Amazon Resource Names (ARN)** uniquely identify AWS resources.

**AWS Global Accelerator**: A service that uses the AWS global network to optimize the routing of traffic to applications. It improves the availability and performance of applications by utilizing anycast IP addresses. It specifically improves network performance globally. 

**Amazon Polly**: Deploy high-quality, natural-sounding human voices in dozens of languages.

**Amazon Personalize** Enhance your digital transformation with ML, seamlessly integrating personalized recommendations into websites, applications, email systems.

**Amazon Comprehend:** Derive and understand valuable insights from text within document. -Amazon Rekognition : Automate and lower the cost of your image recognition and video analysis with machine learning.

A service that uses static IP addresses to route traffic over the AWS global network to optimal AWS endpoints based on health, geography, and routing policies. It provides highly available and performant applications with features like fast failover for multi-Region and Multi-A.

**AWS Certificate Manager (ACM):** Primarily used for managing SSL/TLS certificates used in conjunction with AWS services like Elastic Load Balancer (ELB) or Amazon CloudFront to enable secure communication over HTTPS. It is not directly related to encrypting Amazon EBS volumes.

**AWS Systems Manager:** Allows you to automate operational tasks across your AWS resources. While it provides features for managing system configurations, patching, and automation, it is not specifically designed for encrypting Amazon EBS volumes.

**AWS Key Management Service (AWS KMS):** A fully managed service that makes it easy for you to create, control, and manage encryption keys used to encrypt your data. It integrates seamlessly with other AWS services, including Amazon EBS, for encryption purposes. D. AWS Config: Enables you to assess, audit, and evaluate the configurations of your AWS resources. It does not directly provide encryption for Amazon EBS volumes.



[[ IAM ]] (Root account, Users, Groups, Politics, Roles).

[[ Amazon MQ ]]
[[ Amazon Simple Queue Service (Amazon SQS)]]
[[ Amazon Simple Notification Service (Amazon SNS)]]
[[ Amazon Kinesis Data Streams ]]

**AWS Service Catalog** lets you centrally manage your cloud resources to achieve governance at scale of your infrastructure as code (IaC).
**AWS Glue** is a serverless data integration service that makes it easier to discover, prepare, move, and integrate data from multiple sources for analytics, machine learning (ML), and application development.
**Amazon QuickSight** powers data-driven organizations with unified business intelligence (BI) at hyperscale. With QuickSight, all users can meet varying analytic needs from the same source of truth through modern interactive dashboards, paginated reports, embedded analytics, and natural language queries.
**Elastic Beanstalk**, you can quickly deploy and manage applications in the AWS Cloud without having to learn about the infrastructure that runs those applications.
[[API Gateway]] handles all the tasks involved in accepting and processing up to hundreds of thousands of concurrent API calls, including traffic management.
**AWS X-Ray**: Helps trace requests as they travel through applications, providing insights into application performance. It is not primarily designed for auditing API calls but for understanding and debugging distributed applications.
**Amazon Athena** is a serverless query service that allows you to analyze data directly in Amazon S3 using standard SQL queries.

# Computing

[[ EC2 (Elastic Compute Cloud)]] (Virtual Server, Security Group).

**Amazon LightSaIl** Friendly version of EC2, eg, launch wordpress.

**Elastic Container Service (ECS)** Container orchestration service.

**Elastic Container Registry (ECR)** Repository for container images.

**ECS Fargate** Serverless orchestration, do not have to upgrade/scale always run ECS.

**Elastic Kubernetes Services (EKS)** Kubernetes as a Service.

**AWS Lambda** Serverless function service.

**AWS Nitro System** A combination of dedicated hardware and lightweight hypervisor enabling faster innovation and enhanced security.

**Bottlerocket** Linux OS by AWS for running containers on VMs or bare metal hosts.

**AWS Parallel cluster** High Performance Computing (HPC) Cluster

**Step Functions**  
# Security
**AWS KMS** Manage encryption key for DBs (DynamoDB).

**AWS WAF** Checks from the **ACL** requests received, uses machine learning and denies malicious requests.

**AWS Inspector** Gives a list of security findings, such as open access to EC2.

**AWS CloudHSM:** AWS CloudHSM (Hardware Security Module) is a service that provides hardware-based key storage for sensitive data and cryptographic operations. It is not designed for providing command line access to AWS tools and resources from a web browser.

**IAM Access Analyzer** helps identify resources in your organization and accounts that are shared with an external entity.

**Amazon Macie**: A security service that uses machine learning to automatically discover, classify, and protect sensitive data, such as personally identifiable information (PII), in Amazon S3.

**Amazon Detective:** A security service that helps users investigate and identify the root cause of potential security issues or suspicious activities.

**Amazon GuardDuty:** A threat detection service that continuously monitors for malicious activity and unauthorized behavior to protect AWS accounts and workloads.
**AWS Artifact** AWS and (ISV) Independant Software Vendor compliance reports.
Inspector Security and Complience, EC2 exposure, vulnerabilities
# Monitoring
Observing systems, collecting metrics , and then using the data to make decisions.
*Metrics: Variables tied to your resources*

**CloudWatch** is a monitoring service that can be used to collect and track metrics, logs, and events from various AWS resources. It supports setting up alarms based on cost metrics.

**AWS CloudTrai**l: audit API calls in their AWS by capturing and logging those calls. It provides visibility into user and resource activity and can be used for security analysis, compliance checking, and troubleshooting.

**AWS Trusted Advisor** Gives recommendations for (Cost optimization, Performance, Security, Fault tolerance, Service limits) in real time. Some checks are free.
# Pricing
[[ AWS Budgets ]]
[[ AWS Cost Explorer ]]
[[ AWS Organizations ]]
[[ AWS Pricing Calculator ]]
# Infrastructure
[[ AWS CloudFront]] Content delivery service (edge locations) 
[[ AWS Outposts]] Run AWS in your own Data Center (Hybrid Approach)
[[ AWS CloudFrormation ]] Infrastructure as code
[[ AWS Elastic Beanstalk ]] Deploy resources with code and config provided
# Network
**AWS PrivateLink** enables private connectivity between VPCs (Virtual Private Clouds) and services.

**AWS Transit Gateway** connects your Amazon Virtual Private Clouds (VPCs) and on-premises networks through a central hub. This connection simplifies your network and puts an end to complex peering relationships. Transit Gateway acts as a highly scalable cloud router—each new connection is made only once.

**AWS Cloud Map**: AWS Cloud Map is a service for dynamic, highly available DNS-based service discovery. It is not designed for providing command line access to AWS tools and resources from a web browser.

[[ AWS VPC (Virtual Private Cloud)]] 
**ACL** It is stateless and allows all inbound and outbound traffic (Network access list), checks if a package can go through the subnet (aproved list)

**Security Group** Stateful, *in request* all blocked by default, and *out reques* all allowed, ACL Stateless (between subnets)

[[ AWS Direct Connect ]] Data Center to AWS VPC

[[ Amazon Route 53]] DNS
# Storage

**Amazon FSx**: A fully managed file storage service that is compatible with Windows file servers.

**AWS Storage Gateway**: This service allows on-premises users to access virtually unlimited cloud storage while maintaining a hybrid storage infrastructure.

**AWS DataSync**: A data transfer service that simplifies, automates, and accelerates moving large amounts of data between on-premises storage systems and AWS Cloud storage. It is focused on efficient data transfer.

**EC2 Amazon Machine Images (AMIs)**: AMIs are used to create backups of EC2 instances, and they can be used to launch replacement instances in the event of a disaster or data loss. AMIs are essential for creating recovery points for your EC2 instances.

[[ S3 (Simple Storage Service)]] Is not a DB service, object storage

[[ EBS (Elastic Block Store]] Persistent block storage Virtual hard drive, attachable to EC2 instances SSD, IOPS SSD, Throughput HHD, Cold HHD **only one AZ**.

[[ EFS (Elastic File System)]] Cloud native NFS file system regional Service, **multiple AZs**, can use AWS Direct Connect.

**File Gateway** Extends your local storage to AWS S3.

**Volume Gateway** Caches your local drives to S3 to backup files in the cloud.

**Tape Gateway** Store files onto virtual tapes, cost effective long term storage.

**AWS RDS** Relational DB 

**Amazon Aurora** Mysql Postgress - 6 copies - 1/10 price - Recovery - 5 Times Faster

**Dynamon DB** NoSQL

**Aamazon Redshift** Data Warehouse, Single SQL against hexabytes, larger-sets, 10 times higher performance than regular DBs

**DMS Amazon Database Migration Service**  Remains operational during migration - Can be of diff type (Homogenous same type) (Heterogenous diff type) - DB Consolidation (many to one DB), on premise to AWS.

**Amazon DocumentDB** MongoDB

**Amazon Neptune** is a graph database service, work with highly connected datasets, such as recommendation engines, fraud detection, and knowledge graphs.

**Amazon Managed Blockchain** is a service that you can use to create and manage blockchain networks with open-source frameworks. Blockchain is a distributed ledger system that lets multiple parties run transactions and share data without a central authority.

**Amazon Quantum Ledger DB (QLDB)** Ledger database service, you can use Amazon QLDB to review a complete history of all the changes that have been made to your application data, when you need to record history or financial activities that can be trusted.

**Amazon ElastiCache** is a service that adds caching layers on top of databases to help improve the read times of common requests (redis, memcached).

**Amazon KeySpaces** Cassandra DB, open-source NoSQL Key/Value (additional functions than DynamoDB).

**Timestreams** Fully managed time series db, to measure how things change overtime (IoT).

# Machine Learning
**Amazon Sage Maker** quickly build, train, and deploy machine learning models.

**Amazon A2I** provides built-in human review workflows for common machine learning use cases, such as content moderation and text extraction from documents.

**Amazon Lex** build conversational interfaces using voice and text.

**Amazon Textract** extracts text and data from scanned documents.

**AWS DeepRacer** 1/18 scale race car that you can use to test reinforcement learning models.

**Amazon Q Developer** is a machine learning-powered code generator that provides you with code recommendations in real time.

**Amazon Bedrock Guardrails** configurable safeguards to help safely build generative AI applications at scale, responsible AI policies.
# IoT
**Aws Ground Station** control satellite communication
# Migration

**AWS Data Sync** Migrate data, S3 storage class, hybrid data workflows, archive cold data.

**Mainframe-Moderization** Refactor applications, replatform, data replication ad file transfer. application testing.

**AWS Backup** Across EC2, EBS, RDS, DynamoDB, EFS, Storage Gateway, create backup plans.
## Snow Family

**AWS Snowmobile** is an exabyte-scale data transfer service used to move large amounts of data to AWS. 
You can transfer up to **100 petabytes** of data per Snowmobile, a 45-foot long ruggedized shipping container, pulled by a semi trailer truck.

**Snowcone** is a small, rugged, and secure edge computing and data transfer device. 
It features 2 CPUs, 4 GB of memory, and up to **14 TB** of usable storage.

[**AWS Snowball**(opens in a new tab)](https://aws.amazon.com/snowball/) offers two types of devices:

- **Snowball Edge Storage Optimized** devices are well suited for large-scale data migrations and recurring transfer workflows, in addition to local computing with higher capacity needs. 
    - Storage: **80 TB** of hard disk drive (HDD) capacity for block volumes and Amazon S3 compatible object storage, and 1 TB of SATA solid state drive (SSD) for block volumes. 
    - Compute: 40 vCPUs, and 80 GiB of memory to support Amazon EC2 sbe1 instances (equivalent to C5).
- **Snowball Edge Compute Optimized** provides powerful computing resources for use cases such as machine learning, full motion video analysis, analytics, and local computing stacks. 
    - Storage: 80-TB usable HDD capacity for Amazon S3 compatible object storage or Amazon EBS compatible block volumes and 28 TB of usable NVMe SSD capacity for Amazon EBS compatible block volumes. 
    - Compute: 104 vCPUs, 416 GiB of memory, and an optional NVIDIA Tesla V100 GPU. Devices run Amazon EC2 sbe-c and sbe-g instances, which are equivalent to C5, M5a, G3, and P3 instances.




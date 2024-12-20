# Links
Exam : [AWS Certification Account](https://www.aws.training/certification)
# Concepts
-Amazon Polly: Deploy high-quality, natural-sounding human voices in dozens of languages. -Amazon Personalize: Enhance your digital transformation with ML, seamlessly integrating personalized recommendations into websites, applications, email systems,... . -Amazon Comprehend: Derive and understand valuable insights from text within document. -Amazon Rekognition : Automate and lower the cost of your image recognition and video analysis with machine learning.
review 110 question 112
Cloud Adoption Framework: 
1) Business capabilities 
2) 1.1) Business 
3) 1.2) People 
4) 1.3) Governance 
5) ) Technical capabilities
6) 2.1) Platform 2.2) 
7) Security 2.3) Operations
A. Loose coupling: This is a design principle that promotes independence between components in a system. It enhances flexibility and scalability by reducing dependencies. While beneficial for system architecture, it doesn't directly target cost optimization. B. Rightsizing: Involves selecting the appropriate size and type of AWS resources to match the workload's actual needs. The focus is on optimizing costs by avoiding overprovisioning and ensuring resources are efficiently utilized. Regular reviews and adjustments contribute to ongoing cost-effectiveness. C. Caching: Involves storing frequently accessed data to reduce the need to fetch it repeatedly from the original source. It improves performance and can indirectly contribute to cost savings by reducing the load on backend resources. The primary focus, however, is on enhancing application performance rather than direct cost optimization. D. Redundancy: Involves having duplicate components to ensure high availability and fault tolerance. While crucial for reliability and minimizing downtime, redundancy's primary goal is not direct cost optimization. It can prevent costs associated with disruptions and
# Services
**AWS Global Accelerator**: A service that uses the AWS global network to optimize the routing of traffic to applications. It improves the availability and performance of applications by utilizing anycast IP addresses. It specifically improves network performance globally. 

A service that uses static IP addresses to route traffic over the AWS global network to optimal AWS endpoints based on health, geography, and routing policies. It provides highly available and performant applications with features like fast failover for multi-Region and Multi-A
. **AWS Certificate Manager (ACM):** Primarily used for managing SSL/TLS certificates used in conjunction with AWS services like Elastic Load Balancer (ELB) or Amazon CloudFront to enable secure communication over HTTPS. It is not directly related to encrypting Amazon EBS volumes. B. **AWS Systems Manager:** Allows you to automate operational tasks across your AWS resources. While it provides features for managing system configurations, patching, and automation, it is not specifically designed for encrypting Amazon EBS volumes.
**AWS Key Management Service (AWS KMS):** A fully managed service that makes it easy for you to create, control, and manage encryption keys used to encrypt your data. It integrates seamlessly with other AWS services, including Amazon EBS, for encryption purposes. D. AWS Config: Enables you to assess, audit, and evaluate the configurations of your AWS resources. It does not directly provide encryption for Amazon EBS volumes.
[[ EC2 (Elastic Compute Cloud)]] (Virtual Server, Security Group)
**Amazon LightSaIl** Friendly version of EC2, eg, launch wordpress
**Elastic Container Service (ECS)** Container orchestration service
**Elastic Container Registry (ECR)** Repository for container images
**ECS Fargate** Serverless orchestration, do not have to upgrade/scale always run ECS
**Elastic Kubernetes Services (EKS)** Kubernetes as a Service
**AWS Lambda** Serverless function service
[[ IAM ]] (Root account, Users, Groups, Politics, Roles)
[[ Amazon MQ ]]
[[ Amazon Simple Queue Service (Amazon SQS)]]
[[ Amazon Simple Notification Service (Amazon SNS)]]
[[ Amazon Kinesis Data Streams ]]
**AWS Service Catalog** lets you centrally manage your cloud resources to achieve governance at scale of your infrastructure as code (IaC)
**AWS Glue** is a serverless data integration service that makes it easier to discover, prepare, move, and integrate data from multiple sources for analytics, machine learning (ML), and application development.
**Amazon QuickSight** powers data-driven organizations with unified business intelligence (BI) at hyperscale. With QuickSight, all users can meet varying analytic needs from the same source of truth through modern interactive dashboards, paginated reports, embedded analytics, and natural language queries.
**Elastic Beanstalk**, you can quickly deploy and manage applications in the AWS Cloud without having to learn about the infrastructure that runs those applications.

**CloudWatch** Amazon CloudWatch: Amazon CloudWatch is a monitoring service that can be used to collect and track metrics, logs, and events from various AWS resources. It supports setting up alarms based on cost metrics, so you can create an alarm for a specific cost threshold and configure it to send notifications when the threshold is breached.
**AWS CloudTrai**l: Enables customers to audit API calls in their AWS accounts by capturing and logging those calls. It provides visibility into user and resource activity and can be used for security analysis, compliance checking, and troubleshooting.
**AWS X-Ray**: Helps trace requests as they travel through applications, providing insights into application performance. It is not primarily designed for auditing API calls but for understanding and debugging distributed applications.
**Amazon Athena** is a serverless query service that allows you to analyze data directly in Amazon S3 using standard SQL queries.
**AWS PrivateLink** enables private connectivity between VPCs (Virtual Private Clouds) and services.
## Security
**AWS CloudHSM:** AWS CloudHSM (Hardware Security Module) is a service that provides hardware-based key storage for sensitive data and cryptographic operations. It is not designed for providing command line access to AWS tools and resources from a web browser.
**IAM Access Analyzer** helps identify resources in your organization and accounts that are shared with an external entity.
**Amazon Macie**: A security service that uses machine learning to automatically discover, classify, and protect sensitive data, such as personally identifiable information (PII), in Amazon S3.
**Amazon Detective:** A security service that helps users investigate and identify the root cause of potential security issues or suspicious activities.
**Amazon GuardDuty:** A threat detection service that continuously monitors for malicious activity and unauthorized behavior to protect AWS accounts and workloads.
**AWS Artifact** Security, complience, 
## Pricing
[[ AWS Budgets ]]
[[ AWS Cost Explorer ]]
[[ AWS Organizations ]]
[[ AWS Pricing Calculator ]]
## Infrastructure
[[ AWS CloudFront]] Content delivery service (edge locations) 
[[ AWS Outposts]] Run AWS in your own Data Center (Hybrid Approach)
[[ AWS CloudFrormation ]] Infrastructure as code
[[ AWS Elastic Beanstalk ]] Deploy resources with code and config provided
## Network
**AWS Transit Gateway** connects your Amazon Virtual Private Clouds (VPCs) and on-premises networks through a central hub. This connection simplifies your network and puts an end to complex peering relationships. Transit Gateway acts as a highly scalable cloud router—each new connection is made only once.
**AWS Cloud Map**: AWS Cloud Map is a service for dynamic, highly available DNS-based service discovery. It is not designed for providing command line access to AWS tools and resources from a web browser.
[[ AWS VPC (Virtual Private Cloud)]] 
**ACL** It is stateless and allows all inbound and outbound traffic (Network access list), checks if a package can go through the subnet (aproved list)
**Security Group** Stateful, *in request* all blocked by default, and *out reques* all allowed, ACL Stateless (between subnets)
[[ AWS Direct Connect ]] Data Center to AWS VPC
[[ Amazon Route 53]] DNS
## Storage
**Amazon FSx**: A fully managed file storage service that is compatible with Windows file servers. It is designed to provide shared file storage for Windows-based applications, making it a suitable choice for the company's requirement of a fully managed Windows file server.
**AWS Storage Gateway**: A hybrid cloud storage service that enables on-premises applications to use cloud storage seamlessly. It provides file, volume, and tape gateway interfaces to integrate on-premises environments with AWS Cloud storage. This service allows on-premises users to access virtually unlimited cloud storage while maintaining a hybrid storage infrastructure.
**AWS DataSync**: A data transfer service that simplifies, automates, and accelerates moving large amounts of data between on-premises storage systems and AWS Cloud storage. It is focused on efficient data transfer.
B. **EC2 Amazon Machine Images (AMIs)**: AMIs are used to create backups of EC2 instances, and they can be used to launch replacement instances in the event of a disaster or data loss. AMIs are essential for creating recovery points for your EC2 instances. C. 
**Amazon Elastic Block Store (Amazon EBS) snapshots**: EBS snapshots allow you to create point-in-time backups of your EBS volumes. These snapshots can be used to restore data or create new EBS volumes, making them a key component of disaster recovery for EC2
[[ S3 (Simple Storage Service)]]
[[ EBS (Elastic Block Store]]
[[ EFS (Elastic File System)]]
EBS Single AZ, EC2 and EB2 must be on the same AZ
EFS Regional Service, multiple AZs, can use AWS Direct Connect.
**AWS RDS** Relational DB 
**Amazon Aurora** Mysql Postgress - 6 copies - 1/10 price - Recovery - 5 Times Faster
**Dynamon DB** 
**Aamazon Redshift** Data Warehouse, Single SQL against hexabytes, larger-sets, 10 times higher performance than regular DBs
**Amazon DMS** Amazon Database Migration Service - Remains operational during migration - Can be of diff type (Homogenous same type) (Heterogenous diff type) - DB Consolidation (many to one DB)
**Amazon DocumentDB** MongoDB
**Amazon Neptune** is a graph database service, work with highly connected datasets, such as recommendation engines, fraud detection, and knowledge graphs.
**Amazon Managed Blockchain** is a service that you can use to create and manage blockchain networks with open-source frameworks. Blockchain is a distributed ledger system that lets multiple parties run transactions and share data without a central authority.
**Amazon Quantum Ledger DB (QLDB)** Ledger database service, you can use Amazon QLDB to review a complete history of all the changes that have been made to your application data.
**Amazon ElastiCache** Improve lifting - DAX for DynamoDB
# Pricing
**Consolidated billing has the following benefits:** - ONE BILL – You get one bill for multiple accounts. - Combined usage – You can combine the usage across all accounts in the organization to share the VOLUME PRICING DISCOUNTS, Reserved Instance discounts, and Savings Plans. This can result in a lower charge for your project, department, or company than with individual standalone accounts.

AWS Developer Support, AWS Business Support, AWS Enterprise On-Ramp Support y AWS Enterprise Support. Todos los clientes de AWS disponen de un plan de soporte básico.

**AWS Business Support** - Deberías utilizar el plan AWS Business Support si tienes cargas de trabajo de producción en AWS y quieres acceso telefónico, por correo electrónico y por chat 24/7 a soporte técnico y orientación sobre arquitectura en el contexto de tus casos de uso específicos. El plan AWS Business Support es la opción MÁS rentable para el caso de uso concreto.

**AWS Enterprise On-Ramp Support** - Deberías utilizar el plan AWS Enterprise On-Ramp Support si tienes cargas de trabajo de producción/negocio críticas en AWS y quieres acceso 24/7 a soporte técnico y necesitas orientación experta para crecer y optimizar en el Cloud. El plan AWS Enterprise On-Ramp Support proporciona acceso 24/7 a soporte técnico por teléfono, correo electrónico y chat, pero es más caro que el plan AWS Business Support.

**AWS Developer Support** - Deberías utilizar el plan AWS Developer Support si estás probando o realizando desarrollos iniciales en AWS y quieres tener la posibilidad de obtener soporte técnico por correo electrónico durante el horario laboral, así como orientación general sobre la arquitectura a medida que construyes y pruebas. Este plan no ofrece soporte técnico telefónico 24/7.

**AWS Enterprise Support** - Deberías utilizar el plan AWS Enterprise Support para proporcionar a los clientes un servicio similar al de un conserje, en el que el objetivo principal sea ayudar al cliente a conseguir sus resultados y a encontrar el éxito en el Cloud. Con el plan AWS Enterprise Support, obtienes soporte técnico ininterrumpido de ingenieros de alta calidad, herramientas y tecnología para administrar automáticamente la salud de tu entorno, orientación arquitectónica consultiva proporcionada en el contexto de tus aplicaciones y casos de uso, y un administrador técnico de cuentas (TAM) designado para coordinar el acceso a programas pro-activos/preventivos y a expertos en la materia de AWS. El plan AWS Enterprise Support proporciona acceso a soporte técnico 24/7 por teléfono, correo electrónico y chat, pero es más caro que el plan AWS Business Support.

AWS Enterprise Support proporciona a los clientes un servicio similar al de un conserje, en el que el objetivo principal es ayudar al cliente a lograr sus resultados y alcanzar el éxito en el Cloud. Con AWS Enterprise Support, obtienes soporte técnico 24/7 de ingenieros de alta calidad, herramientas y tecnología para administrar automáticamente el estado de tu entorno, orientación arquitectónica consultiva en el contexto de tus aplicaciones y casos de uso, y un administrador técnico de cuentas (TAM) designado para coordinar el acceso a programas pro-activos/preventivos y a expertos en la materia de AWS.

Servicios de Ámbito Global:
AWS Identity and Access Management (AWS IAM), Amazon Cloud Front, Amazon Route 53 y AWS Web Application Firewall (AWS WAF) son algunos de los servicios globales.


# Infrastructure
AWS Regions are clusters of data centers, they are named like us-east-1, and each has at least 3 AZ (Availability zones)
### How to choose a Region
- **Compliance** with data governance and legal requirements: data never leaves a region without your explicit permission
- **Proximity** to customers: reduced latency
- **Available** services within a Region: new services and new features aren-t available in every Region
- **Pricing**: pricing varies region to region and is transparent in te service pricing page
### Edge 

# Cloud Computing General
Cloud Computing is the **on-demand delivery** of compute power, database storage, applications and other IT resources. This was born due to the problem of [[1 - IT Overview|Traditional Data Centers Approach]] when speaking of big an scalable companies, where more customers imply more resources. 

Cloud Computing has a lot of advantages:
- Cloud Services with **pay-as-you-go**
- Provision exactly the **right type and size of computing resources** you need
- Access as many resources as you need, **almost instantly**
- Simple way to access **servers, storage, databases** and a set of application services
## Deployment Models of the Cloud

## Private Cloud
e.g. Rackspace

- Cloud services used by a single organization, not exposed to the public 
- Complete control
- Security for sensitive applications
- Meet specific business needs
## Public Cloud
e.g. Azure, Google, AWS

- Cloud resources owned and operated by a third-party cloud service provider delivered over the internet
- [[#Six Advantages of Cloud Computing]]
## Hybrid Cloud
e.g. Your own Infra with Cloud, like AWS

- Keep some servers on premises and extend some capabilities to the Cloud
- Control over sensitive assets in your private infrastructure
- Flexibility and cost-effectiveness of the public cloud
## The Five Characteristics of Cloud Computing

**On-demand self service:**
- Users can provision resources and use them without human interaction from the service provider
**Broad network access:**
- Resources available over the network and can be accessed by diverse client platforms
**Multi-tenancy and resource pooling:**
- Multiple customer can share the same infrastructure and applications with security and privacy
- Multiple customer are serviced from the same physical resources
**Rapid elasticity and scalability:**
- Automatically and quickly acquire and dispose resources when needed
- Quickly and easily scale based on demand
**Measured service:**
- Usage is measured, users pay correctly for what the have used

## Six Advantages of Cloud Computing

**Trade capital expense (CAPEX) for operational expense (OPEX)**
- Pay On-Demand: don't own hardware
- Reduced Total Cost of Ownership (TCO) & Operational Expense (OPEX)
**Benefit from massive economies of scale**
- Prices are reduced as AWS is more efficient due to large scale
**Stop guessing capacity**
- Scale based on actual measured usage
**Increase speed and agility**
- Due to its infrastructure is easy to build and deploy
**Stop spending money running and maintaining data centers**
- No costs of maintaining
**Go global in minutes**
- Leverage the AWS global infrastructure
## Problems solved by the Cloud

- **Flexibility:** Change resource types when needed
- **Cost-Effectiveness:** Pay as you go, for what you use
- **Scalability:** Accommodate larger loads by making hardware stronger or adding additional nodes
- **Elasticity:** Ability to scale out and scale-in when needed
- **High-availability and fault-tolerance:** Build across data centers
- **Agility:** Rapidly develop, test and launch software applications


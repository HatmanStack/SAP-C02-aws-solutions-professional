# Networking

**Amazon VPC** - Virtual private cloud to launch AWS resources in a private virtual network. Allows control over virtual networking environment.

- Works with Direct Connect, VPN, VPC endpoints, VPC peering
- Use flow logs, ACLs, security groups to control network traffic
- Support for IPv6 addressing
- Create public and private subnets

**AWS Direct Connect** - Dedicated network connection from on-premises to AWS. Provides private connectivity without using internet. Useful for large data transfers.

- Creates a connection between your router and a Direct Connect location
- Lower cost for data transfer compared to VPN or internet  
- Supports bandwidths up to 100 Gbps
- Use virtual interfaces (VIFs) to connect to VPCs
- On-premises must use BGP with Autonomous System Numbers

**AWS Client VPN** - Managed client-based VPN service for secure connections from client devices to AWS or on-premises networks.

- Endpoint is elastic, can handle bursts in connections
- Integrates with AWS IAM for access controls
- Cannot accept connections from 0.0.0.0/0 CIDR range

**AWS Site-to-Site VPN** - Connects on-premises network or branch office site to Amazon VPC. Goes over public internet.

- Can be set up in minutes
- Higher data transfer costs compared to Direct Connect
- On-premises side must use dynamic routing VPN  

**AWS Transit Gateway** - Service to connect VPCs and on-premises networks. Simplifies network topology and minimizes VPC peering connections.

- Attach on-premises and up to 5000 VPCs per Region
- Use route tables to limit access between VPCs
- Charged per hour and amount of data transferred

**Internet Gateway** - Horizontal scaled, redundant, highly available component that allows communication between VPCs and internet.

**NAT Gateway** - Allow private subnets to connect to internet for downloads while preventing internet accessing resources in private subnets.

- Not available by default, must be created
- Highly available using multi-AZ redundancy
- No way to associate security groups

**AWS PrivateLink** - Access AWS services over private VPC endpoint without internet gateway, NAT device, VPN, etc.

- Provides private connectivity between VPCs, AWS services, and on-premises  
- Use interface endpoints for AWS services using PrivateLink
- Reduces exposure through internet gateway

**Amazon Route 53** - Highly available and scalable DNS web service. Translates friendly domain names to IP addresses.

- Simple routing, weighted routing, latency-based routing, failover routing
- Alias records to map resource record sets in your hosted zone to AWS resources
- Private DNS to configure a private namespace that can be accessed from your VPCs

# Security

**AWS KMS** - Create, manage, and use encryption keys. Integrates with other AWS services.

- Use for encryption at rest and in transit
- FIPS 140-2 Level 2 compliant
- CloudTrail can audit key usage  
- Import key material or use AWS managed keys
- Use grants to allow access to keys

**AWS WAF** - Filter malicious web traffic based on rules. Protects apps from common exploits. 

- Protect ALBs, API Gateway, CloudFront distributions, AppSync APIs
- Block common exploits like SQL injection, cross-site scripting 
- Rate limiting and CAPTCHA challenges

**AWS Shield** - DDoS protection service that safeguards web apps running on AWS.

- Shield Standard: Automatic protections for all AWS customers 
- Shield Advanced: Additional protections for high risk apps and 24x7 support

**AWS Security Hub** - Unified security and compliance center. Aggregates alerts and findings from multiple AWS services.

- Integrates with GuardDuty, Inspector, Macie, and 3rd party security tools
- Applies compliance checks using AWS Config rules
- Aggregates findings and alerts across accounts

**Amazon GuardDuty** - Threat detection service that analyzes VPC, DNS, and CloudTrail data to identify threats. 

- Uses machine learning to detect anomalies and threats
- Analyzes CloudTrail, VPC Flow Logs, DNS Logs
- Integrates with Security Hub  

**Amazon Inspector** - Automated security assessment service that helps improve security and compliance of applications deployed on AWS.

- Scans for vulnerabilities and deviations from best practices
- Analyzes network, file system, and process activity
- Integrates with Security Hub to aggregate findings

**Amazon CloudWatch** - Monitoring service for AWS resources and applications.

- Metrics, logs, and events to monitor systems
- Alarms and notifications based on defined thresholds
- Dashboards for visualizing metrics

CloudWatch provides real-time visibility into resource utilization, application performance, operational health, and more. Integrates with AWS services to collect metrics and logs.

**AWS CloudTrail** - Tracks user activity and API usage in AWS accounts. 

- Logs deliver events related to resource provisioning and configuration
- Integrates with CloudWatch Logs and EventBridge
- Analyze events with CloudTrail Lake, CloudTrail Insights
- Can aggregate logs from multiple accounts and regions

CloudTrail provides audit history of account activity across AWS. It records actions taken through the CLI, SDKs, console, and services. Enables security analysis, resource change tracking, and compliance.

# Storage

**Amazon S3** - Highly scalable object storage. Offers different storage classes and lifecycle policies. 

- Provides 99.999999999% durability and 99.99% availability
- Can be used for archiving, big data analytics, disaster recovery
- Storage classes optimized for different access patterns  

**Amazon EBS** - Block level storage volumes for EC2 instances. Persistent storage independent of instance lifecycle.

- Offered in HDD, SSD, and provisioned IOPS types 
- Snapshots can be taken for backups and copied across AZs/regions
- Multi-attach for shared block storage between EC2 instances

**Amazon EFS** - Managed elastic NFS file system for EC2 instances. Supports thousands of concurrent connections.

- Fully managed service, handles provisioning and scaling
- Storage classes for frequency of access patterns
- Encryption at rest capability

**Amazon FSx** - Managed file storage built on Windows, Lustre, and NetApp ONTAP. High performance for workloads.

- Seamlessly uses native file systems, for Windows or HPC workloads
- Integrates with Active Directory, backups, encryption
- Options for on-premises access to data in AWS

**Amazon S3 Glacier** - Secure, durable, low-cost cloud storage for data archiving and long-term backup. Retrieval times from minutes to hours.  

- Integrates lifecycle policies to transition objects to Glacier for archiving
- Cost optimized for infrequently accessed data 
- Can be accessed through S3 APIs

# Databases

**Amazon RDS** - Managed relational database service for popular databases. Handles provisioning, patching, backups, etc.

- Automated backups to S3, point-in-time restore, read replicas
- Multi-AZ for high availability, failover in case of outage
- 6 database engines supported: MySQL, MariaDB, PostgreSQL, Oracle, SQL Server

**Amazon Aurora** - MySQL and PostgreSQL compatible relational database. Start at 10 GB, scales to 64 TB. High performance and availability.

- 5x performance of MySQL, 3x PostgreSQL at lower cost 
- Storage scales to 128 TB, autoscaling based on usage
- Automated failover capability

**Amazon DynamoDB** - Managed NoSQL database. Single-digit millisecond response times at any scale. For key-value and document data models.  

- Built-in security, backup/restore, in-memory caching
- Integrates with IAM for access control
- On-demand or provisioned capacity modes

**Amazon ElastiCache** - In-memory caching service to speed up data retrieval from databases. Supports Memcached and Redis.

- Sub-millisecond latency retrieving data from cache
- Reduces load off databases for read intensive workloads
- Node types optimized for memory or compute  

**Amazon Redshift** - Petabyte-scale data warehousing service. Query and analyze structured and semi-structured data. Columnar storage optimized for analytics.

- 10x better performance than other data warehouses 
- Integrates with common BI tools like Quicksight
- Advanced compression to minimize storage

# Migration

**AWS Migration Hub** - Tracks progress of application migrations across multiple AWS and partner solutions. Provides portfolio view of migrations.

- Aggregates data using Discovery Connector or Discovery Agent
- Integrates with Migration Evaluator for planning  
- Monitor progress of migrations to AWS

**AWS Database Migration Service (DMS)** - Migrates databases to AWS quickly with minimal downtime. Source and target databases remain fully operational during migration.

- Replicate data changes during migration using change data capture
- Supports homogenous and heterogeneous migrations
- Replicate data continuously after migration

**AWS Server Migration Service (SMS)** - Migrates on-premises servers to AWS. Minimizes downtime. Agentless works for VMware vSphere vms.  

- Integrates with vCenter for agentless migration
- Does not support migration of physical servers
- Orchestrates replication of server volumes to AWS

**AWS Application Discovery Service** - Discovers on-premises servers, collects server configuration data, tracks server dependencies, and maps data to migrating servers to AWS.

- Agent-based and agentless discovery options  
- Integrates with Migration Hub for tracking
- Gather data about servers, dependencies, processes

**AWS Database Migration Service (DMS) Fleet Advisor** - Provides recommendations to simplify and optimize database migration planning for heterogeneous migrations.

- Analyzes source database and provides migration assessment
- Integrates with AWS Schema Conversion Tool
- Recommends optimal database engine, instance class for target

# Identity

**AWS Organizations** - Centrally manage multiple AWS accounts. 

- Consolidated billing, sharing resources, grouping accounts
- Service Control Policies (SCPs) to restrict permissions

**AWS Control Tower** - Set up and govern secure, compliant multi-account AWS environment.

- Create landing zones with central security controls
- Monitor accounts and OUs using guardrails 
- Dashboard to view alerts and compliance

**AWS IAM** - Manage access to AWS services and resources.

- Users, groups, roles, policies to grant permissions 
- Integrates with on-prem identity providers
- Temporary credentials for federated access

**Security Groups** - Act as virtual firewalls for EC2 instances to control inbound and outbound traffic.

- Stateful - outbound traffic automatically allowed
- Assigned at the instance level, not subnet
- Must explicitly allow access to DNS, DHCP, instance metadata
- Create audit rules to allow or disallow within your Organization and to check for unused or redudndant security groups

**Access Control Lists (ACLs)** - Resource-based permissions policy that controls cross-account access to AWS resources.

- ACLs grant permissions to AWS accounts and principals
- Used to control access to S3 buckets, SNS topics, SQS queues
- Cannot grant permissions to IAM entities in the same account
- Specify individual accounts or predefined groups (Authenticated Users, All Users)

**IAM Access Advisor** - Gives two types of last accessed information for IAM entities
					
- allowed AWS services information
- allowed AWS action information
- Does not generate policies

**IAM Access Analyzer** - Analyzes resource policies and generates IAM policies based on actual access patterns.

- IAM Access Analyzer policy generation analyzes CloudTrail logs to identify the specific actions and services that have been used by an IAM entity like a user, group, or role.
- It generates an IAM policy that grants permissions tailored to those observed actions and services. This helps apply the principle of least privilege access by right-sizing permissions based on actual usage analysis.
- Access Analyzer evaluates resources shared externally and validates IAM policies against best practices. It provides actionable findings to refine broad policies with minimal needed permissions.
  
# Compute 

**Amazon EC2** - Resizable compute capacity in the cloud. Allows configuration of CPU, memory, storage, network.

- Multiple pricing models (on-demand, spot, reserved)
- Instance types optimized for different use cases
- Integrates with other AWS services and features

**AWS Lambda** - Serverless compute service that runs code in response to events. 

- Automated scaling, built-in high availability
- Multiple languages supported (Node.js, Python, Java, etc)
- Sub-second startup and billing increments 

**Amazon ECS** - Highly scalable container orchestration service that supports Docker containers.

- Task definitions specify CPU, memory, containers
- Integrates with ALB and service discovery features 

**Amazon EKS** - Managed Kubernetes service for running containerized applications.

- Simplifies Kubernetes operations and maintenance
- Integrates VPC networking, IAM, Security groups
- Runs upstream Kubernetes and is certified Kubernetes conformant

**AWS Fargate** - Serverless container engine for ECS and EKS.

- No need to provision underlying EC2 instances
- Pay per task duration and resources consumed
- Integrates with Elastic Load Balancing, service discovery, security groups
  
**AWS Batch** - Fully managed batch processing at any scale. Optimizes workload distribution.

- Multi-AZ in one Region, automatic scaling of compute 
- Schedule batch jobs or process data streams
- Integrates with AWS services for processing batch data  

**Amazon SageMaker** - Build, train, and deploy machine learning models at scale.

- notebooks, automatic model tuning, A/B testing, model hosting 
- Managed service, pay-as-you-use pricing
- Tightly integrated with other AWS services

# AWS IoT

AWS IoT provides services to connect IoT devices to the AWS cloud, ingest data streams, apply analytics, and create applications.

**AWS IoT Core** - Managed cloud service to securely connect IoT devices and applications. 

- Communication protocols: MQTT, MQTT over WebSocket, HTTPS, LoRaWAN
- Integrates with AWS IoT Device SDK, AWS IoT Greengrass, Amazon FreeRTOS
- Rules engine to process data and trigger actions
- Device Shadows maintain state when devices go offline

**AWS IoT Analytics** - Filters, transforms, and stores IoT data for analysis.

- Automates data collection from multiple IoT sources
- Performs ETL on IoT data using SQL queries 
- Stores processed data in time-series optimized format

**AWS IoT Events** - Detect events from IoT sensors and applications.

- Continuously monitor data sources like sensors
- Define rules to match event patterns and trigger actions
- Integrates with IoT Core, SiteWise, and other AWS services

**AWS IoT Greengrass** - Extends AWS IoT to edge devices to enable local processing and AI inferencing. 

- Run Lambda functions on edge devices
- Operate offline and sync data when connected 
- Deploy ML models trained in SageMaker to edge devices

**AWS IoT Device Management** - Onboard, organize, monitor, and remotely manage IoT devices at scale.

- Secure device provisioning and authentication
- Group devices and manage as fleets 
- Monitor fleet health, apply updates, troubleshoot

**AWS IoT 1-Click** - Enable simple devices to trigger AWS Lambda functions. 

- Devices can be triggered with a single click
- No coding required to attach Lambda triggers
- Built-in libraries for hardware modules and devices

**AWS IoT Things Graph** - Easily connect devices and web services without writing code.

- Visual drag-and-drop interface
- Build flows using prebuilt models of IoT devices  
- Generate AWS CloudFormation templates for deployment

Other capabilities:

- Connect vehicles, industrial equipment, home devices 
- Build custom voice assistants using Alexa Voice Service
- Embed real-time video analytics into apps with Amazon Rekognition
- Develop smart utility meters, asset trackers, remote sensors

IoT enables predictive maintenance, remote monitoring, asset tracking, and smart environments across industries.

# Provisioning

**AWS CloudFormation** - Service for modeling and provisioning AWS and third party resources using templates.

- Templates describe the desired resources and their dependencies 
- Control and automate resource provisioning for applications
- Reuse templates to replicate stacks across accounts, regions
- Rollback and drift detection features

CloudFormation is infrastructure as code and allows consistent, automated resource provisioning for applications built on AWS. Templates can be version controlled and updated to push changes.

# Content Delivery

**Amazon CloudFront** - Content delivery network (CDN) to distribute content to customers globally with low latency. 

- Improves performance by caching content at edge locations
- Integrates with AWS shield for DDoS mitigation
- Origin failover capability if primary origin is unavailable
- Lambda@Edge to run functions at edge locations 

CloudFront works seamlessly with services like S3, EC2, and Elastic Load Balancing to deliver static, media, and dynamic web content. Reduces traffic on origin servers.

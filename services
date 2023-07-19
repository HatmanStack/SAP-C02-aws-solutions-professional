# Networking

**Amazon VPC** - Virtual private cloud to launch AWS resources in a private virtual network. Allows control over virtual networking environment.

- Works with Direct Connect, VPN, VPC endpoints, VPC peering
- Use flow logs, ACLs, security groups to control network traffic

**AWS Direct Connect** - Dedicated network connection from on-premises to AWS. Provides private connectivity without using internet. Useful for large data transfers.

- Creates a connection between your router and a Direct Connect location
- Lower cost for data transfer compared to VPN or internet
- Supports bandwidths up to 100 Gbps

**AWS Client VPN** - Managed client-based VPN service for secure connections from client devices to AWS or on-premises networks.

- Endpoint is elastic, can handle bursts in connections
- Integrates with AWS IAM for access controls

**AWS Site-to-Site VPN** - Connects on-premises network or branch office site to Amazon VPC. Goes over public internet.

- Can be set up in minutes
- Higher data transfer costs compared to Direct Connect

**AWS Transit Gateway** - Service to connect VPCs and on-premises networks. Simplifies network topology and minimizes VPC peering connections.

- Attach on-premises and up to 5000 VPCs per Region
- Use route tables to limit access between VPCs

**Internet Gateway** - Horizontal scaled, redundant, highly available component that allows communication between VPCs and internet.

**NAT Gateway** - Allow private subnets to connect to internet for downloads while preventing internet accessing resources in private subnets. 

- Not available by default, must be created
- Highly available using multi-AZ redundancy

**AWS PrivateLink** - Access AWS services over private VPC endpoint without internet gateway, NAT device, VPN, etc.

- Provides private connectivity between VPCs, AWS services, and on-premises networks
- Use interface endpoints for services powered by PrivateLink

# Security

**AWS KMS** - Create, manage, and use encryption keys. Integrates with other AWS services.

- Use for encryption at rest and in transit
- FIPS 140-2 Level 2 compliant
- CloudTrail can audit key usage

**AWS WAF** - Filter malicious web traffic based on rules. Protects apps from common exploits.

- Protect ALBs, API Gateway, CloudFront distributions, AppSync APIs 
- Block common exploits like SQL injection, cross-site scripting

**AWS Shield** - DDoS protection service that safeguards web apps running on AWS. 

- Shield Standard: Automatic protections for all AWS customers
- Shield Advanced: Additional protections for high risk apps

**AWS Security Hub** - Unified security and compliance center. Aggregates alerts and findings from multiple AWS services.

- Integrates with GuardDuty, Inspector, Macie, and 3rd party security tools
- Applies compliance checks using AWS Config rules 

**Amazon GuardDuty** - Threat detection service that analyzes VPC, DNS, and CloudTrail data to identify threats.

- Uses machine learning to detect anomalies and threats
- Analyzes CloudTrail, VPC Flow Logs, DNS Logs

# Storage 

**Amazon S3** - Highly scalable object storage. Offers different storage classes and lifecycle policies.

- Provides 99.999999999% durability and 99.99% availability
- Can be used for archiving, big data analytics, disaster recovery

**Amazon EBS** - Block level storage volumes for EC2 instances. Persistent storage independent of instance lifecycle.

- Offered in HDD, SSD, and provisioned IOPS types
- Snapshots can be taken for backups and copied across AZs/regions

**Amazon EFS** - Managed elastic NFS file system for EC2 instances. Supports thousands of concurrent connections.

- Fully managed service, handles provisioning and scaling
- Storage classes for frequency of access patterns

**Amazon FSx** - Managed file storage built on Windows, Lustre, and NetApp ONTAP. High performance for workloads.

- Seamlessly uses native file systems, for Windows or HPC workloads
- Integrates with Active Directory, backups, encryption

**Amazon S3 Glacier** - Secure, durable, low-cost cloud storage for data archiving and long-term backup. Retrieval times from minutes to hours. 

- Integrates lifecycle policies to transition objects to Glacier for archiving
- Cost optimized for infrequently accessed data

# Databases

**Amazon RDS** - Managed relational database service for popular databases. Handles provisioning, patching, backups, etc.

- Automated backups to S3, point-in-time restore, read replicas
- Multi-AZ for high availability, failover in case of outage

**Amazon Aurora** - MySQL and PostgreSQL compatible relational database. Start at 10 GB, scales to 64 TB. High performance and availability.

- 5x performance of MySQL, 3x PostgreSQL at a lower cost
- Storage scales up to 128 TB, autoscaling based on usage

**Amazon DynamoDB** - Managed NoSQL database. Single-digit millisecond response times at any scale. For key-value and document data models.

- Built-in security, backup/restore, in-memory caching
- Integrates with IAM for access control

**Amazon ElastiCache** - In-memory caching service to speed up data retrieval from databases. Supports Memcached and Redis.

- Sub-millisecond latency retrieving data from cache
- Reduces load off databases for read intensive workloads

**Amazon Redshift** - Petabyte-scale data warehousing service. Query and analyze structured and semi-structured data. Columnar storage optimized for analytics.

- 10x better performance than other data warehouses
- Integrates with common BI tools like Quicksight

# Migration

**AWS Migration Hub** - Tracks progress of application migrations across multiple AWS and partner solutions. Provides portfolio view of migrations.

- Aggregates data using Discovery Connector or Discovery Agent
- Integrates with Migration Evaluator for planning

**AWS Database Migration Service (DMS)** - Migrates databases to AWS quickly with minimal downtime. Source and target databases remain fully operational during migration.

- Replicate data changes during migration using change data capture
- Supports homogenous and heterogeneous migrations

**AWS Server Migration Service (SMS)** - Migrates on-premises servers to AWS. Minimizes downtime. Works for both VMware vSphere and physical servers.

- Integrates with vCenter for agentless migration
- Does not support migration of physical servers

**AWS Application Discovery Service** - Discovers on-premises servers, collects server configuration data, tracks server dependencies, and maps data to migrating servers to AWS.

- Agent-based and agentless discovery options
- Integrates with Migration Hub for tracking

**AWS Database Migration Service (DMS) Fleet Advisor** - Provides recommendations to simplify and optimize database migration planning for heterogeneous migrations.

- Analyzes source database and provides migration assessment
- Integrates with AWS Schema Conversion Tool

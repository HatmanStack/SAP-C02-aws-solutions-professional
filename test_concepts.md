# Domain 1: Design Solutions for Organizational Complexity

## Network Connectivity Strategies
- Regions, Availability Zones, Local Zones, Edge Locations, Outposts
- VPC, Direct Connect, Client VPN, Site-to-Site VPN, Transit Gateway
- Know capabilities and best practices for key AWS network services 

## Prescribe Security Controls
- Foundations: IAM, SCPs, Access Control Lists 
- Encryption: KMS, SSL/TLS certificates
- Monitoring: CloudTrail, CloudWatch, Config, Security Hub
- Shared responsibility model for compliance

## Design Multi-Account AWS Environments
- AWS Organizations: Consolidated billing, sharing resources, SCPs
- AWS Control Tower: Multi-account structure, controls, compliance monitoring
- Central logging strategies: CloudTrail, CloudWatch, S3

# Domain 2: Design New Solutions 

## Deployment Strategy
- Automation with CloudFormation, Systems Manager
- Immutable infrastructure
- Adopt managed services to reduce infrastructure overhead

## Ensure Business Continuity
- Meet RTO/RPO with multi-AZ, read replicas, backups
- Disaster recovery: Elastic Disaster Recovery, Route 53
- Monitoring: CloudWatch, EventBridge 

## Determine Security Controls
- Defense in depth with IAM, VPC endpoints, WAF, Shield
- Shared responsibility model
- Compliance: Security Hub, Audit Manager, Access Analyzer

## Design Reliable Architectures
- Availability: Auto Scaling, load balancing, decoupling
- Resiliency: data replication, failover
- Performance: caching, CDNs, scaling controls
  
## Determine Cost Optimization  
- Savings Plans, RI utilization
- Tagging strategy for cost allocation 
- Tools: Cost Explorer, Budgets, Trusted Advisor

# Domain 3: Continuous Improvement

## Improve Operational Excellence
- Automate with SSM, CloudFormation
- Central logging with CloudTrail, CloudWatch  
- CI/CD with CodePipeline, CodeDeploy

## Improve Security
- Layered controls with WAF, Shield, VPCs  
- Auditing with CloudTrail, Config, Security Hub
- Remediation with Config, EventBridge

## Improve Performance
- Scaling: Auto Scaling, load balancing
- Caching: CloudFront, ElastiCache
- Metrics and monitoring with CloudWatch 

## Improve Reliability
- Resiliency: Multi-AZ, replication, failover
- Recovery: Backups, disaster recovery 
- Monitoring: CloudWatch, Route 53

## Optimize Costs
- Right-sizing, Savings Plans, RI utilization
- Tagging and allocation 
- Tools: Cost Explorer, Budgets
  
# Domain 4: Workload Migration

## Select Workloads for Migration
- Portfolio analysis and prioritization 
- Migration waves based on dependencies
- Migration strategies: rehost, replatform, refactor

## Determine Migration Approach  
- Connectivity: Direct Connect, VPN, DataSync
- Tools: DMS, SMS, MGN, Server Migration Service

## Define New Architecture
- Select compute, storage, databases
- Decompose monoliths into microservices 

## Identify Modernization Opportunities
- Serverless, containers, purpose-built databases
- Decouple storage and compute
- CI/CD pipelines, DevOps



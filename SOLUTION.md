# Exploring AWS Services Lab - Solution

**Student Name:** [Balint Lojt]  
**Date Completed:** [06/07/2026]

---

## Exercise 1: Console Navigation

### Part A: Service Discovery

**EC2 (Compute):**
- Purpose: Hosting and running virtual servers to deploy applications. 
- Screenshot: <img width="1894" height="707" alt="EC2-dashboard" src="https://github.com/user-attachments/assets/ed941372-492d-4b2d-abbe-2657013df007" />


**S3 (Storage):**
- Purpose: Storing and retrieving files and data such as images, videos, backups, logs, and static website files.
- Screenshot: <img width="1502" height="785" alt="s3-dashboard" src="https://github.com/user-attachments/assets/13edf7a6-e935-4e47-a9a2-b052ff28aa45" />


**RDS (Database):**
- Purpose: Setting up, operating, and scaling relational databases (like MySQL, PostgreSQL, or SQL Server)and also automating time-consuming management tasks like hardware provisioning, database setups, patching, and backups.
- Screenshot: <img width="1850" height="585" alt="RDS-dashboard" src="https://github.com/user-attachments/assets/5178e3f3-729b-406e-98af-077930af740b" />


**VPC (Networking):**
- Purpose: Provisioning a private, isolated virtual network within AWS. It gives total control over the networking environment, including IP address ranges, subnets, and security firewalls.
- Screenshot: <img width="1859" height="732" alt="VPC-dashboard" src="https://github.com/user-attachments/assets/6cde631a-ade7-42c0-9078-7a34a6bde32e" />


**IAM (Security):**
- Purpose: Managing security, access control, and permissions. It determines exactly who (users) or what (applications) can log into your AWS account and what specific resources they are allowed to interact with.
- Screenshot:<img width="1854" height="698" alt="IAM-dashboard" src="https://github.com/user-attachments/assets/53424e5f-a58f-4e73-a477-652f171bfb3b" />


### Part B: Console Features

**Lambda Category:** [Which category?]

**Pinned Services:**
![S3 Pinned](screenshots/console-navigation/s3-pinned.png)

**Recently Visited:**
![Recently Visited](screenshots/console-navigation/recently-visited.png)

**Region Selector:**
![Region Changed](screenshots/console-navigation/region-selector.png)
- Original region: [region]
- Changed to: [region]
- Changed back: [Yes/No]

---

## Exercise 2: Service Categorization

### Completed Service Matrix:

| Category | Services | Primary Use Case |
|----------|----------|------------------|
| Compute | EC2, Lambda, Elastic Beanstalk, ECS | EC2 is a virtual server for running custom applications and workloads. Lambda	is a serverless function that runs code automatically in response to events. Elastic Beanstalk is a Platform-as-a-Service (PaaS) to deploy web apps without managing underlying hardware. ECS (Elastic Container Service) is a	running and scaling Docker containers.|

| Storage | S3, EBS, EFS, S3 glacier | S3 is an	object storage for files, backups, and static web hosting.
EBS (Elastic Block Store)	is a dedicated, persistent block storage volume for EC2 instances (like a hard drive).
EFS (Elastic File System)is a	scalable file storage that can be shared across multiple EC2 instances simultaneously.
S3 Glacier is a low-cost archive storage for data that is rarely accessed.|

| Database | RDS,DynamoDB,ElastiCache | RDS is a	managed relational database (SQL) like MySQL, PostgreSQL, and Oracle.
DynamoDB is an ultra-fast, fully managed NoSQL database for key-value and document data.
ElastiCache is an in-memory data store used to cache frequent database queries and speed up apps.|

| Networking | VPC, CloudFront, Route53 |VPC is an isolated, secure virtual network inside the cloud.
CloudFront is a global Content Delivery Network (CDN) that caches data closer to users.
Route 53	is a highly available Domain Name System (DNS) service to route user traffic to apps. |

| Security | [List 3-5 services] | IAM	is a Controlling who can log in and what permissions they have to AWS resources.
KMS (Key Management Service) is used to create and manage cryptographic keys to encrypt data.
CloudTrail is for	recording and auditing all API calls and user actions across the account.
Secrets Manager	is used for safely storing and automatically rotating database credentials and API keys. |

| Management | CloudWatch, CloudFormation, Systems Manager | CloudWatch is a	Monitoring system for metrics, gathering logs, and setting performance alarms.
CloudFormation is used for code (JSON/YAML) to automatically deploy and manage AWS infrastructure.
Systems Manager is a central dashboard to patch, configure, and manage cloud resources at scale. |

### Research Question Answers:

**1. What's the difference between EC2 and Lambda?**

EC2 is server-based. For example, rent a virtual machine, choose the operating system, and keep it running 24/7. You have to pay for the time the server is on, whether it's processing traffic or sitting idle. Also responsible for patching the OS and scaling, the provider does not do it.
Lambda is serverless. You upload your raw code, and AWS handles the underlying infrastructure entirely. It only runs (and you only pay) when triggered by an event (like an uploaded file or an API call), scaling down to zero when inactive.

Short answer: C2 is a virtual server that runs continuously and requires you to manage it; Lambda is serverless code that only runs and charges when triggered by an event.

---

**2. When would you use S3 vs EBS?**

 Choose S3 when you need to store standalone files (images, videos, backups, logs) that need to be accessed directly from the web or shared globally. It is infinite, independent storage accessible via an API/URL.

 Choose EBS when you need a local, high-speed hard drive plugged directly into a specific EC2 instance to run an operating system, install software, or host a traditional database. It cannot be accessed over the internet on its own.

Short answer: S3 is a global, infinite storage locker for files (accessible via URLs); EBS is a virtual hard drive attached directly to a specific EC2 instance to run its operating system and apps.


**3. What's the difference between RDS and DynamoDB?**

RDS is handling Relational (SQL) databases. It is built for structured data with strict schemas, complex relationships, and deep analytical queries requiring table joins (e.g., financial ledger apps).

DynamoDB is handling Non-Relational (NoSQL) databases. It uses a flexible key-value format and is built for massive scale, offering consistent, single-digit millisecond performance even with billions of rows (e.g., gaming leaderboards, shopping carts).

Short answer: RDS is for structured, traditional relational databases (SQL) using tables and relationships; DynamoDB is a massive-scale, flexible key-value database (NoSQL) designed for fast speeds.

---

**4. Why do you need a VPC?**

A VPC functions as a digital security perimeter for your cloud infrastructure. Without it, your servers and databases would be directly exposed to the public internet. A VPC allows you to isolate sensitive data in a private subnet, control incoming and outgoing traffic via firewalls (Security Groups), and dictate exactly how your resources communicate with the outside world.

---

**5. What does CloudWatch monitor?**

CloudWatch monitors the health, performance, and behaviour of your AWS resources and applications. 
It tracks:
Metrics: CPU utilisation, network traffic, disk read/writes.
Logs: Application logs, system crash dumps, and custom text logs.
Alarms: It can send notifications (or trigger automatic scaling events) if a metric crosses a certain threshold—such as the EC2 CPU staying above 80% for too long.

---

## Exercise 3: AWS CLI

### CLI Version:
```
[Paste output of: aws --version]
```

### Configuration:
```
[Paste output of: aws configure list]
```

### CLI Outputs:

See attached `cli-outputs.txt` file for all command outputs.

**Key findings:**
- My AWS Account ID: [account-id]
- Default region: [region]
- Number of regions available: [number]

---

## Exercise 4: Pricing Research

### Pricing Worksheet:

**1. EC2 t3.micro (Linux, us-east-1):**
- On-Demand: $______ per hour
- Monthly (730 hours): $______
- Free Tier eligible: [Yes/No]
- Free Tier details: [hours/month free]

**2. S3 Standard Storage:**
- 100 GB monthly cost: $______
- Free Tier: First ___ GB free for 12 months
- Cost per GB: $______

**3. RDS db.t3.micro (MySQL):**
- Monthly cost: $______
- Storage (20 GB): $______
- Total: $______
- Free Tier eligible: [Yes/No]

**4. Data Transfer OUT:**
- 100 GB cost: $______
- First ___ GB free per month

### AWS Pricing Calculator Estimate:

![Pricing Calculator](screenshots/pricing-calculator.png)

**Estimate Link:** [Paste your estimate link here]

**Total Estimated Monthly Cost:** $______

---

## Exercise 5: Documentation Hunt

### EC2 Instance Types:
- Documentation URL: [URL]
- t3.medium vCPUs: ______
- t3.medium memory: ______ GB

### S3 Storage Classes:
- Documentation URL: [URL]
- All storage classes:
  1. [Class name]
  2. [Class name]
  3. [Class name]
  4. [Etc...]
- Cheapest for archive: [Class name]

### IAM Best Practices:
- Documentation URL: [URL]
- Three best practices:
  1. [Practice]
  2. [Practice]
  3. [Practice]

### Free Tier Limits:
- Documentation URL: [URL]
- EC2 t2.micro hours/month: ______
- S3 storage free: ______ GB

---

## Exercise 6: Regions and Availability Zones

### Your Current Region:
- Region Name: [e.g., US East (N. Virginia)]
- Region Code: [e.g., us-east-1]
- Number of AZs: ______

### Concept Questions:

**What is the difference between a Region and an Availability Zone?**

[Your answer]

---

**Why does AWS have multiple regions?**

[Your answer]

---

**How many Availability Zones does each region typically have?**

[Your answer]

---

**Can you deploy resources in multiple regions simultaneously?**

[Your answer]

---

### Region Selection Analysis:

| Scenario | Best Region | Reasoning |
|----------|-------------|-----------|
| Serving users primarily in Europe | [region] | [Your reasoning] |
| Lowest cost for non-critical workloads | [region] | [Your reasoning] |
| GDPR compliance required | [region] | [Your reasoning] |
| Serving users in Asia-Pacific | [region] | [Your reasoning] |
| Need newest AWS services | [region] | [Your reasoning] |

---

## Bonus Challenges

### Challenge 1: Cost Estimate

**Architecture:**
- 1x t3.medium EC2 (24/7)
- 1x db.t3.micro RDS (24/7)
- 50 GB S3
- 100 GB data transfer

**Estimated Monthly Cost:** $______

**Calculator Link:** [URL]

---

### Challenge 2: Service Comparison

| AWS | Azure | GCP |
|-----|-------|-----|
| EC2 | [Azure service] | [GCP service] |
| S3 | [Azure service] | [GCP service] |
| RDS | [Azure service] | [GCP service] |
| Lambda | [Azure service] | [GCP service] |

---

### Challenge 3: CLI Advanced

[Paste outputs of advanced commands here]

---

## Reflection

**What surprised you most about AWS services?**

[Your answer]

---

**Which AWS service are you most excited to learn about?**

[Your answer]

---

**How comfortable do you feel navigating the AWS Console now?**

[Your answer: Scale 1-10 and why]

---

## Checklist

- [ ] All service dashboards visited and documented
- [ ] All CLI commands executed successfully
- [ ] All pricing research completed
- [ ] All documentation URLs found
- [ ] Region analysis completed
- [ ] All screenshots captured
- [ ] All questions answered
- [ ] Work committed to Git
- [ ] Pull request created

---

**Completed By:** [Your Name]  
**Date:** [Date]

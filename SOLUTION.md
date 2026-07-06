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
- Original region: United States (N. Virginia)
- Changed to: Europe (Stockholm)
- Changed back: [Yes]

---

## Exercise 2: Service Categorization

### Completed Service Matrix:

| Category | Services | Primary Use Case |

| Compute | EC2, Lambda, Elastic Beanstalk, ECS | EC2 is a virtual server for running custom applications and workloads. Lambda	is a serverless function that runs code automatically in response to events. Elastic Beanstalk is a Platform-as-a-Service (PaaS) to deploy web apps without managing underlying hardware. ECS (Elastic Container Service) is a	running and scaling Docker containers.|

| Storage | S3, EBS, EFS, S3 glacier | S3 is an	object storage for files, backups, and static web hosting.
EBS (Elastic Block Store)	is a dedicated, persistent block storage volume for EC2 instances (like a hard drive).
EFS (Elastic File System)is a	scalable file storage that can be shared across multiple EC2 instances simultaneously.
S3 Glacier is a low-cost archive storage for data that is rarely accessed.|

| Database | RDS, DynamoDB, ElastiCache | RDS is a	managed relational database (SQL) like MySQL, PostgreSQL, and Oracle.
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
aws-cli/2.31.35 Python/3.14.4 Linux/6.6.114.1-microsoft-standard-WSL2 source/x86_64.ubuntu.26aws configure list

```

### Configuration:
```
NAME       : VALUE                    : TYPE             : LOCATION
profile    : <not set>                : None             : None
access_key : ****************UA73     : shared-credentials-file :
secret_key : ****************5CXA     : shared-credentials-file :
region     : eu-west-2                : config-file      : ~/.aws/config
```

### CLI Outputs:

See attached `cli-outputs.txt` file for all command outputs.

**Key findings:**
- My AWS Account ID: 436-3183-6010
- Default region: eu-west-2
- Number of regions available: 17

---

## Exercise 4: Pricing Research

### Pricing Worksheet:

**1. EC2 t3.micro (Linux, us-east-1):**
- On-Demand: $_$0.0104 per hour
- Monthly (730 hours): $_$7.59
- Free Tier eligible: Yes
- Free Tier details: 750 hours/month free for the first 12 months

**2. S3 Standard Storage:**
- 100 GB monthly cost: $_$2.30_
- Free Tier: First _5__ GB free for 12 months
- Cost per GB: $_$0.023

**3. RDS db.t3.micro (MySQL):**
- Monthly cost: $21.90
- Storage (20 GB): $$2.30
- Total: $24.20
- Free Tier eligible: Yes

**4. Data Transfer OUT:**
- 100 GB cost: $_$0.00_
- First 100 GB free per month

### AWS Pricing Calculator Estimate:

<img width="2453" height="685" alt="pricing-calculator" src="https://github.com/user-attachments/assets/f9c83ab8-0fde-4fdf-8233-d047e43356fd" />


**Estimate Link:** (https://calculator.aws/#/estimate?id=18eda9eb066d5967db3d2afe2fe7ce43285aa650)

**Total Estimated Monthly Cost:** $44.61  / month  (without free tier)

---

## Exercise 5: Documentation Hunt

### EC2 Instance Types:
- Documentation URL:(https://aws.amazon.com/ec2/instance-types/t3/)
- t3.medium vCPUs: __2____
- t3.medium memory: __4____ GB

### S3 Storage Classes:
- Documentation URL: (https://aws.amazon.com/s3/storage-classes/)
- All storage classes:
  1. S3 Standard (General-purpose storage for frequently accessed data)
  2. S3 Intelligent-Tiering (Automatic cost savings for data with unknown access patterns)
  3. S3 Standard-Infrequent Access (S3 Standard-IA) (For long-lived, less frequently accessed data)
  4. S3 One Zone-Infrequent Access (S3 One Zone-IA) (Lower cost option for less frequent data, stored in 1 AZ)
  5. S3 Glacier Deep Archive (Lowest-cost storage for long-term data retention)
- Cheapest for archive: S3 Glacier Deep Archive
### IAM Best Practices:
- Documentation URL:(https://aws.amazon.com/iam/resources/best-practices/)
- Three best practices:
  1. Require human users to use federation with an identity provider to access AWS using temporary credentials (avoid long-term access keys).
  2. Require Multi-Factor Authentication (MFA) for all accounts, especially privileged users and the root user.
  3. Apply the Principle of Least Privilege (grant identities the minimum permissions required to perform their specific task, and nothing more).

### Free Tier Limits:
- Documentation URL: https://aws.amazon.com/free/
- EC2 t2.micro hours/month: __750____
- S3 storage free: ___5___ GB

---


### Region Selection Analysis:

| Scenario | Best Region | Reasoning |
|----------|-------------|-----------|
| Serving users primarily in Europe | eu-west-1 (Ireland) or eu-west-2 (London) | Geographically placing infrastructure near your users dramatically cuts network round-trip times (latency), ensuring the app loads quickly and smoothly for them.|
| Lowest cost for non-critical workloads | us-east-1 (N. Virginia) or us-east-2 (Ohio)| These are AWS's massive, high-volume flagship hubs. Due to economies of scale, they consistently offer the lowest baseline pricing for compute, storage, and databases globally. |
| GDPR compliance required | eu-central-1 (Frankfurt) or eu-west-1 (Ireland) | To comply with strict EU data privacy laws (GDPR), sensitive user data must physically reside within the borders of the European Union / EEA. (Note: eu-west-2 London covers UK-GDPR).|
| Serving users in Asia-Pacific |ap-southeast-1 (Singapore) or ap-northeast-1 (Tokyo)| Cuts transit times across undersea fiber-optic cables by establishing a localized regional endpoint for users located throughout Asia and Oceania.|
| Need newest AWS services | us-east-1 (N. Virginia) | As AWS's oldest, original, and largest footprint, nearly all brand-new services, public previews, and advanced machine learning hardware launch here first before trickling down to secondary regions. |

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

certain services have a wide range of prices depending on need. 

---

**Which AWS service are you most excited to learn about?**

unsure yet

---

**How comfortable do you feel navigating the AWS Console now?**

[Your answer: Scale 1-10 and why]
10
---

## Checklist

- [x ] All service dashboards visited and documented
- [x ] All CLI commands executed successfully
- [ x] All pricing research completed
- [ x] All documentation URLs found
- [ x] Region analysis completed
- [ x] All screenshots captured
- [x ] All questions answered
- [ x] Work committed to Git
- [ x] Pull request created

---

**Completed By:** [Balint Lojt]  
**Date:** [06/07/2026]

# Exploring AWS Services Lab - Solution

**Student Name:** [Balint Lojt]  
**Date Completed:** [06/07/2026]

---

## Exercise 1: Console Navigation

### Part A: Service Discovery

**EC2 (Compute):**
- Purpose: [Your answer]
- Screenshot: ![EC2 Dashboard](screenshots/console-navigation/ec2-dashboard.png)

**S3 (Storage):**
- Purpose: [Your answer]
- Screenshot: ![S3 Dashboard](screenshots/console-navigation/s3-dashboard.png)

**RDS (Database):**
- Purpose: [Your answer]
- Screenshot: ![RDS Dashboard](screenshots/console-navigation/rds-dashboard.png)

**VPC (Networking):**
- Purpose: [Your answer]
- Screenshot: ![VPC Dashboard](screenshots/console-navigation/vpc-dashboard.png)

**IAM (Security):**
- Purpose: [Your answer]
- Screenshot: ![IAM Dashboard](screenshots/console-navigation/iam-dashboard.png)

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
| Compute | [List 3-5 services] | [Use cases] |
| Storage | [List 3-5 services] | [Use cases] |
| Database | [List 3-5 services] | [Use cases] |
| Networking | [List 3-5 services] | [Use cases] |
| Security | [List 3-5 services] | [Use cases] |
| Management | [List 3-5 services] | [Use cases] |

### Research Question Answers:

**1. What's the difference between EC2 and Lambda?**

[Your answer]

---

**2. When would you use S3 vs EBS?**

[Your answer]

---

**3. What's the difference between RDS and DynamoDB?**

[Your answer]

---

**4. Why do you need a VPC?**

[Your answer]

---

**5. What does CloudWatch monitor?**

[Your answer]

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

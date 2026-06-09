## Role

**AWS Cloud & DevOps Engineer — Infrastructure, Automation & Reliability**

I design, deploy, and automate cloud infrastructure on AWS using Terraform, Docker, and CI/CD pipelines. My focus is on building scalable, highly available systems with Infrastructure as Code, monitoring, and automated recovery mechanisms.

My projects emphasize:

* AWS Infrastructure Design
* Infrastructure as Code with Terraform
* High Availability Architectures
* Docker-based Deployments
* CI/CD Automation
* Monitoring & Observability
* Production Troubleshooting

---

## 01 — Featured Project

### Auto-Healing Infrastructure on AWS

> Terraform · ALB · ASG · EC2 · CloudWatch · Docker · GitHub Actions

**Problem**

Applications deployed on a single EC2 instance become unavailable when infrastructure or application failures occur.

Manual deployments increase operational risk and reduce reliability.

**Solution**

Designed a highly available AWS architecture using Application Load Balancer, Auto Scaling Groups, health checks, and automated recovery mechanisms.

Integrated deployment automation using Docker and GitHub Actions while maintaining infrastructure through Terraform.

```text
Developer
    │
git push
    │
    ▼
GitHub Actions
    │
Docker Build
    │
Push to GHCR
    │
Deploy to EC2
    │
──────── AWS ────────

        ALB
         │
   ┌─────┴─────┐
   │           │
 EC2-1      EC2-2
 Docker     Docker
   │           │
   └─────┬─────┘
         │
     Auto Scaling
         │
 CloudWatch Monitoring
```

---

### Failure Scenarios Tested

| Scenario             | Recovery                                   |
| -------------------- | ------------------------------------------ |
| EC2 Failure          | Auto Scaling launched replacement instance |
| Application Crash    | Health checks isolated unhealthy instance  |
| Deployment Failure   | Pipeline stopped release                   |
| Instance Replacement | User Data automated application startup    |
| Health Check Failure | ALB redirected traffic to healthy targets  |

---

## 02 — Infrastructure & Automation

### Terraform Infrastructure

* Provisioned AWS infrastructure using Terraform
* Managed VPC, EC2, IAM, S3, CloudFront, ALB, and ASG
* Implemented remote state management using S3 and DynamoDB locking
* Built repeatable and scalable infrastructure deployments

### CI/CD Automation

* Automated build and deployment workflows using GitHub Actions
* Built and versioned Docker images
* Published images to GHCR
* Automated deployments on AWS EC2
* Troubleshot deployment and container failures

---

## 03 — Technical Stack

### Cloud Infrastructure

* AWS EC2
* VPC
* IAM
* S3
* CloudFront
* ALB
* Auto Scaling Groups
* CloudWatch

### Infrastructure as Code

* Terraform
* Remote State Management
* DynamoDB Locking

### Containers & Automation

* Docker
* GitHub Actions
* GHCR

### Monitoring

* CloudWatch Logs
* Metrics
* Alarms

### OS & Tools

* Linux
* Nginx
* Git

---

## 04 — Core Strengths

* AWS Infrastructure Design and Operations
* Infrastructure as Code with Terraform
* High Availability and Auto-Healing Architectures
* Debugging and Root Cause Analysis
* Monitoring and Observability
* CI/CD Automation and Containerized Deployments
* Application and Infrastructure Lifecycle Understanding

---

## 05 — Open To

| Role                     | Focus                    |
| ------------------------ | ------------------------ |
| AWS Cloud Engineer       | Cloud Infrastructure     |
| Cloud & DevOps Engineer  | Automation & Reliability |
| Infrastructure Engineer  | AWS & Terraform          |
| Junior Platform Engineer | Platform Infrastructure  |

---

## 06 — Connect

Portfolio: https://harikrish-portfolio25.web.app

LinkedIn: https://linkedin.com/in/hari-krish-13300b27a

GitHub: https://github.com/Harikrishna2525

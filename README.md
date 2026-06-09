<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=2,3,12&height=180&section=header&text=Hari%20Krishna&fontSize=52&fontColor=fff&fontAlignY=36&desc=AWS%20Cloud%20DevOps%20Engineer&descAlignY=58&descSize=17&descColor=a5f3fc"/>

<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=16&duration=2800&pause=900&color=22D3EE&center=true&vCenter=true&width=680&lines=AWS+Infrastructure+%26+Reliability;Auto+Scaling+%2B+Load+Balanced+Architectures;Terraform+%E2%86%92+AWS+Infrastructure+%E2%86%92+Docker+%E2%86%92+CI%2FCD;Infrastructure+Automation+%26+Monitoring"/>

<br/>

[![Portfolio](https://img.shields.io/badge/Portfolio-harikrish--portfolio25.web.app-22d3ee?style=for-the-badge&logo=googlechrome&logoColor=white)](https://harikrish-portfolio25.web.app)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0a66c2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/hari-krish-13300b27a)
[![GitHub](https://img.shields.io/badge/GitHub-Harikrishna2525-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Harikrishna2525)

</div>

---

## Role

**AWS Cloud & DevOps Engineer — Infrastructure, Automation & Reliability**

I build, deploy, and automate applications on AWS using CI/CD pipelines, Docker, and infrastructure as code, with a focus on reliability, scalability, and failure recovery.

My projects emphasize:

- Load-balanced architectures
- CI/CD automation
- Infrastructure defined using Terraform and Infrastructure as Code principles
- Observability using AWS-native monitoring

---

## 01 — Featured Project

### Auto-Healing Deployment Infrastructure on AWS

> Terraform · ALB · ASG · Docker · GitHub Actions · GHCR · CloudWatch

**Problem**

Applications running on a **single EC2 instance** become unavailable when the instance fails or the application crashes.

Manual deployments also introduce risk and slow down release cycles.

**Solution**

An automated deployment pipeline using **GitHub Actions and Terraform**, combined with **Auto Scaling and load balancing** to replace failed instances and maintain service availability.

Fully automated deployment pipeline from code push to production using Docker and GitHub Actions.

```
git push
  └─▶  GitHub Actions CI/CD
         ├─▶  Docker Build + Tag (SHA + latest)
         ├─▶  Push → GHCR  (ghcr.io/harikrishna2525/app)
         └─▶  Terraform Infrastructure Deployment
                    │
         ┌──────────▼──────────┐
         │  Application Load    │
         │     Balancer         │
         └────┬─────────┬──────┘
              │         │
         EC2 AZ-1   EC2 AZ-2     ← Auto Scaling Group
         [Docker]   [Docker]
              │         │
         Target Group + Health Checks
                    │
           CloudWatch Alarms + Logs
```

---

### Failure Scenarios Tested

| Scenario | Recovery | Outcome |
|---|---|---|
| EC2 terminated | ASG launched replacement automatically | Service automatically restored |
| Docker container stopped | Target Group marked unhealthy | Traffic routed to healthy instance |
| Health check failed | ALB stopped routing traffic | Fault isolated |
| Bad commit pushed | CI blocked deployment | Infrastructure unchanged |
| New instance boot | User Data pulled image from GHCR | Instance joined load balancer |

---

## 02 — CI/CD Pipeline

```yaml
# .github/workflows/deploy.yml

on: [push to main]

jobs:
  build-and-push:
    - Checkout code
    - Login to GHCR using GitHub Actions token
    - Build Docker image
    - Tag with commit SHA + latest
    - Push → ghcr.io/harikrishna2525/app

  deploy:
    - Authenticate to AWS using GitHub OIDC
    - Trigger Terraform infrastructure deployment
    - ASG instances pull new image during refresh
    - Health checks validate deployment
    - Rollback if deployment fails
```

**Toolchain:** GitHub Actions · Docker · GHCR · Terraform · AWS CLI


## Terraform AWS Infrastructure

Terraform-based AWS infrastructure including:

- VPC & Networking
- ALB & Auto Scaling
- EC2 Compute
- CloudFront Delivery
- IAM & Security
- Remote State (S3 + DynamoDB)


---

## 03 — Technical Stack

###### Infrastructure & IaC

![Terraform](https://img.shields.io/badge/Terraform-844FBA?style=flat-square&logo=terraform\&logoColor=white)
![EC2](https://img.shields.io/badge/EC2-FF9900?style=flat-square\&logo=amazonaws&logoColor=white)
![VPC](https://img.shields.io/badge/VPC-FF9900?style=flat-square\&logo=amazonaws&logoColor=white)
![ALB](https://img.shields.io/badge/ALB-FF9900?style=flat-square\&logo=amazonaws&logoColor=white)
![ASG](https://img.shields.io/badge/ASG-FF9900?style=flat-square\&logo=amazonaws&logoColor=white)
![CloudFront](https://img.shields.io/badge/CloudFront-8C4FFF?style=flat-square&logo=amazonaws\&logoColor=white)


### CI/CD & Containers
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![GHCR](https://img.shields.io/badge/GHCR-181717?style=flat-square&logo=github&logoColor=white)
![Nginx](https://img.shields.io/badge/Nginx-009639?style=flat-square&logo=nginx&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-E95420?style=flat-square&logo=ubuntu&logoColor=white)

### Serverless & Storage
![Lambda](https://img.shields.io/badge/Lambda-FF9900?style=flat-square&logo=awslambda&logoColor=white)
![API Gateway](https://img.shields.io/badge/API_Gateway-FF9900?style=flat-square&logo=amazonaws&logoColor=white)
![DynamoDB](https://img.shields.io/badge/DynamoDB-4053D6?style=flat-square&logo=amazondynamodb&logoColor=white)
![S3](https://img.shields.io/badge/S3-569A31?style=flat-square&logo=amazons3&logoColor=white)
![CloudFront](https://img.shields.io/badge/CloudFront-8C4FFF?style=flat-square&logo=amazonaws&logoColor=white)

### Monitoring & Security
![CloudWatch](https://img.shields.io/badge/CloudWatch-FF4500?style=flat-square&logo=amazonaws&logoColor=white)
![IAM](https://img.shields.io/badge/IAM-DD344C?style=flat-square&logo=amazonaws&logoColor=white)

---

## 04 — Security Practices

- IAM Roles scoped per service (EC2, Lambda)
- Least-privilege policies applied to infrastructure
- AWS authentication in CI using **GitHub Actions OIDC**
- Security Groups with restricted ingress rules
- No hardcoded credentials — environment variables or AWS Secrets Manager

---

## 05 — Open To

| Role | Type | Focus |
|---|---|---|
| **AWS Cloud & DevOps Engineer** | Full-time / Remote | AWS, Terraform, Cloud Infrastructure |
| **DevOps Engineer — Infra Heavy** | Full-time | AWS, IaC, Scalable Systems |
| **Junior Platform Engineer** | Full-time | Platform Infrastructure |

---

## 06 — Connect

| | |
|---|---|
| Portfolio | [harikrish-portfolio25.web.app](https://harikrish-portfolio25.web.app) |
| LinkedIn | [linkedin.com/in/hari-krish-13300b27a](https://linkedin.com/in/hari-krish-13300b27a) |
| GitHub | [github.com/Harikrishna2525](https://github.com/Harikrishna2525) |

---

<div align="center">
<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=2,3,12&height=100&section=footer&text=Build%20%C2%B7%20Deploy%20%C2%B7%20Scale%20%C2%B7%20Monitor&fontSize=13&fontColor=a5f3fc&fontAlignY=68"/>
</div>

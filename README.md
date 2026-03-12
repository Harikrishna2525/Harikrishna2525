<div align="center">

# Hari Krishna

**`Cloud / DevOps Engineer (Infra Heavy)`**

*I focus on how systems fail, recover, and scale — not just how they are deployed.*

<br>

![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonaws&logoColor=FF9900)
![EC2](https://img.shields.io/badge/EC2-FF9900?style=flat-square&logo=amazonec2&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)
![CloudFormation](https://img.shields.io/badge/CloudFormation-FF4F8B?style=flat-square&logo=amazonaws&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black)

</div>

---

## 🎯 Role

| Area | What I do |
|---|---|
| **Compute** | EC2 provisioning, Launch Templates, ASG lifecycle, User Data bootstrapping |
| **Networking** | Custom VPC, subnets, route tables, IGW, security groups |
| **Load Balancing** | ALB + Target Groups, HTTP health checks, traffic routing |
| **Containers** | Docker build → push GHCR → pull on EC2 → run as service |
| **CI/CD** | GitHub Actions — CloudFormation deploy, S3+CF frontend, EC2 container deploy |
| **IaC** | CloudFormation stacks — repeatable, version-controlled infra |
| **Monitoring** | CloudWatch logs, metrics, alarms — instance and app level |
| **IAM** | EC2 / Lambda roles, least-privilege policies, no hardcoded credentials |

---

## 🏗️ Featured Project — Auto-Healing Infrastructure (ALB + ASG)

> Single EC2 = single point of failure. This removes that.

**Architecture**

```
Internet
   │
   ▼
Application Load Balancer (ALB)
   │              │
   ▼              ▼
EC2 (AZ-1)    EC2 (AZ-2)       ← Auto Scaling Group
Docker App    Docker App        ← Image pulled from GHCR
   │
   ▼
CloudWatch (logs · metrics · alarms)
```

**Failure Scenarios Tested**

| # | Failure Injected | System Response |
|---|---|---|
| 1 | EC2 terminated manually | ASG detected drop → launched replacement |
| 2 | Docker container stopped inside instance | Target Group health check failed → Unhealthy |
| 3 | Instance marked Unhealthy by ALB | ALB stopped routing traffic immediately |
| 4 | ASG launched new instance via Launch Template | User Data ran → GHCR pull → app started → Healthy |
| 5 | Instance passed health checks | ALB resumed routing — zero user-visible downtime |

🔗 [github.com/Harikrishna2525/Aws-ALB-ASG-auto-healing](https://github.com/Harikrishna2525/Aws-ALB-ASG-auto-healing)

---

## 🚀 CI/CD Pipelines

**1 · CloudFormation — Infra Deploy**
```
push infra/** → AWS credentials → cfn deploy → stack updated ✓
```

**2 · S3 + CloudFront — Frontend Deploy**
```
push main → npm build → s3 sync → CF invalidation → live ✓
```

**3 · GHCR → EC2 — Container Deploy**
```
push main → docker build → push ghcr.io → SSH EC2 → docker pull & run → deployed ✓
```

---

## ☁️ Stack

**Compute & Networking**
![EC2](https://img.shields.io/badge/EC2-FF9900?style=flat-square&logo=amazonec2&logoColor=white)
![ALB](https://img.shields.io/badge/ALB-FF9900?style=flat-square&logo=amazonaws&logoColor=white)
![ASG](https://img.shields.io/badge/ASG-FF9900?style=flat-square&logo=amazonaws&logoColor=white)
![VPC](https://img.shields.io/badge/VPC-232F3E?style=flat-square&logo=amazonaws&logoColor=white)

**Containers & OS**
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![GHCR](https://img.shields.io/badge/GHCR-181717?style=flat-square&logo=github&logoColor=white)
![Ubuntu](https://img.shields.io/badge/Ubuntu-E95420?style=flat-square&logo=ubuntu&logoColor=white)
![Nginx](https://img.shields.io/badge/Nginx-009639?style=flat-square&logo=nginx&logoColor=white)

**Serverless & Backend**
![Lambda](https://img.shields.io/badge/Lambda-FF9900?style=flat-square&logo=awslambda&logoColor=white)
![API Gateway](https://img.shields.io/badge/API_Gateway-FF4F8B?style=flat-square&logo=amazonaws&logoColor=white)
![DynamoDB](https://img.shields.io/badge/DynamoDB-4053D6?style=flat-square&logo=amazondynamodb&logoColor=white)

**Storage & CDN**
![S3](https://img.shields.io/badge/S3-569A31?style=flat-square&logo=amazons3&logoColor=white)
![CloudFront](https://img.shields.io/badge/CloudFront-232F3E?style=flat-square&logo=amazonaws&logoColor=white)

**IaC & CI/CD**
![CloudFormation](https://img.shields.io/badge/CloudFormation-FF4F8B?style=flat-square&logo=amazonaws&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)

**Monitoring & Security**
![CloudWatch](https://img.shields.io/badge/CloudWatch-FF4F8B?style=flat-square&logo=amazonaws&logoColor=white)
![IAM](https://img.shields.io/badge/IAM-DD344C?style=flat-square&logo=amazonaws&logoColor=white)

---

## 📊 GitHub Stats

<div align="center">

![Hari's GitHub Stats](https://github-readme-stats.vercel.app/api?username=Harikrishna2525&show_icons=true&theme=github_dark&hide_border=true&count_private=true)

![Top Languages](https://github-readme-stats.vercel.app/api/top-langs/?username=Harikrishna2525&layout=compact&theme=github_dark&hide_border=true)

</div>

---

## 🎯 Open To

- 🔵 **Cloud Engineer** — L1–L2, AWS-native infra, compute & networking focus
- 🟢 **DevOps Engineer (Infra Heavy)** — CI/CD, containers, IaC, system reliability
- 🟣 **Junior Platform Engineer** — Internal tooling, EC2 + serverless hybrid, product startups

---

## 📫 Connect

[![Portfolio](https://img.shields.io/badge/Portfolio-000000?style=flat-square&logo=firefox&logoColor=white)](https://harikrish-portfolio25.web.app)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/hari-krish-13300b27a)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/Harikrishna2525)

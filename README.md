<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=2,3,12&height=180&section=header&text=Hari%20Krishna&fontSize=52&fontColor=fff&fontAlignY=36&desc=Cloud%20%2F%20DevOps%20Engineer%20%E2%80%94%20Infra%20Heavy&descAlignY=58&descSize=17&descColor=a5f3fc"/>

<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=16&duration=2800&pause=900&color=22D3EE&center=true&vCenter=true&width=680&lines=Failure-first+infrastructure+design;Auto-healing+AWS+%7C+Zero-downtime+deployments;git+push+%E2%86%92+CI+%E2%86%92+Docker+%E2%86%92+GHCR+%E2%86%92+CloudFormation;Infra-First.+Failure-Tested.+Production-Ready."/>

<br/>

[![Portfolio](https://img.shields.io/badge/Portfolio-harikrish--portfolio25.web.app-22d3ee?style=for-the-badge&logo=googlechrome&logoColor=white)](https://harikrish-portfolio25.web.app)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0a66c2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/hari-krish-13300b27a)
[![GitHub](https://img.shields.io/badge/GitHub-Harikrishna2525-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Harikrishna2525)

</div>

---

## Role

**Cloud / DevOps Engineer — Infra Heavy**

I design and operate AWS infrastructure focused on how systems **fail, recover, and scale** — not just how they deploy. Built for Indian product startups and remote-first teams that need solid infra without enterprise overhead.

---

## 01 — Featured Project

### Auto-Healing Cloud Infrastructure

> ALB · ASG · Docker · GitHub Actions · GHCR · CloudFormation

**Problem:** Single EC2 instances fail. Manual deploys bottleneck teams.

**Solution:** Fully automated, self-healing AWS stack — zero manual steps, zero downtime.

```
git push
  └─▶  GitHub Actions CI/CD
         ├─▶  Docker Build + Tag (SHA + latest)
         ├─▶  Push → GHCR  (ghcr.io/harikrishna2525/app)
         └─▶  CloudFormation Stack Update
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

### Failure Scenarios Tested

| Scenario | Recovery | Outcome |
|---|---|---|
| EC2 terminated | ASG launched replacement automatically | Zero downtime |
| Docker container stopped | Target Group marked unhealthy, traffic rerouted | Zero downtime |
| Health check failed | ALB drained and stopped routing | Zero downtime |
| Bad commit pushed | CI blocked deploy, infra unchanged | Protected |
| New instance boot | User Data pulled image from GHCR, app started | Auto-healed |

---

## 02 — CI/CD Pipeline

```yaml
# .github/workflows/deploy.yml

on: [push to main]

jobs:
  build-and-push:
    - Checkout code
    - Login to GHCR via GitHub Actions OIDC   # no long-lived secrets
    - Build Docker image
    - Tag with commit SHA + latest
    - Push → ghcr.io/harikrishna2525/app

  deploy:
    - Trigger CloudFormation stack update
    - ASG instances pull new image on refresh
    - Health checks validate rollout
    - Auto-rollback on failure
```

**Toolchain:** GitHub Actions · Docker · GHCR · CloudFormation · AWS CLI

---

## 03 — Technical Stack

### Infrastructure & IaC
![EC2](https://img.shields.io/badge/EC2-FF9900?style=flat-square&logo=amazonaws&logoColor=white)
![ALB](https://img.shields.io/badge/ALB-FF9900?style=flat-square&logo=amazonaws&logoColor=white)
![ASG](https://img.shields.io/badge/ASG-FF9900?style=flat-square&logo=amazonaws&logoColor=white)
![VPC](https://img.shields.io/badge/VPC-FF9900?style=flat-square&logo=amazonaws&logoColor=white)
![CloudFormation](https://img.shields.io/badge/CloudFormation-FF4500?style=flat-square&logo=amazonaws&logoColor=white)

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

- IAM Roles scoped per service — EC2, Lambda — no shared credentials
- Least-privilege policies across all resources
- GHCR auth via GitHub Actions OIDC — no long-lived secrets stored
- Security Groups: ingress restricted by port and source
- No hardcoded credentials — env variables or Secrets Manager
- CloudFormation drift detection enabled

---

## 05 — Open To

Targeting **Indian product startups** and **remote-first engineering teams.**

| Role | Type | Focus |
|---|---|---|
| **Cloud Infrastructure Engineer** | Full-time / Contract | AWS, IaC, CloudFormation, Networking |
| **DevOps Engineer — Infra Heavy** | Full-time / Remote | CI/CD, Docker, GHCR, Cloud Automation |
| **Junior Platform Engineer** | Full-time | Platform Infra + Automation |

---

## 06 — Connect

| | |
|---|---|
| Portfolio | [harikrish-portfolio25.web.app](https://harikrish-portfolio25.web.app) |
| LinkedIn | [linkedin.com/in/hari-krish-13300b27a](https://linkedin.com/in/hari-krish-13300b27a) |
| GitHub | [github.com/Harikrishna2525](https://github.com/Harikrishna2525) |

---

<div align="center">
<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=2,3,12&height=100&section=footer&text=Infra-First%20%C2%B7%20Failure-Tested%20%C2%B7%20Production-Ready&fontSize=13&fontColor=a5f3fc&fontAlignY=68"/>
</div>

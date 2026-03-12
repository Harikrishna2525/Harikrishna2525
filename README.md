# ☁️ Hari Krishna — Cloud / Infrastructure Engineer

<div align="center">

<img src="https://readme-typing-svg.herokuapp.com?font=Orbitron&weight=600&size=30&pause=900&color=36BCF7&center=true&vCenter=true&width=700&lines=Cloud+%2F+Infrastructure+Engineer;Auto-Healing+AWS+Architectures;Failure-Tested+Systems" />

</div>

Designing reliable, fault-tolerant AWS infrastructure with real failure testing and production-style deployment practices.

---

## 🎯 Role Definition

**Primary Role:**  
**Cloud / Infrastructure Engineer (L1–L2)**

**Responsibilities:**
- Design and deploy AWS infrastructure for web applications
- Build fault-tolerant and auto-healing systems
- Configure load balancing, health checks, and traffic routing
- Manage EC2-based and serverless workloads
- Debug infrastructure-level issues (networking, compute, service health)
- Automate deployments and bootstrapping using User Data and IaC
- Monitor systems using logs, metrics, and alarms

---

## 🧑‍💻 About Me

I’m a hands-on Cloud / Infrastructure Engineer focused on how systems **fail, recover, and scale**, not just how they are deployed.

I work with:
- Failure-first infrastructure design
- Real testing of unhealthy scenarios
- EC2 and serverless-based architectures
- AWS-native monitoring and logging
- Simple, explainable designs suitable for production

Flutter experience exists, but cloud infrastructure is my primary career focus.

---

## 🏗️ Featured Infrastructure Project

### Auto-Healing Cloud Infrastructure using ALB & ASG

**Problem**  
Single EC2 deployments create a single point of failure and downtime.

**Architecture**
- Custom VPC
- Public subnets across multiple Availability Zones
- Application Load Balancer
- Target Group with application-level health checks
- Auto Scaling Group with Launch Template
- EC2 instances running a Dockerized application
- CloudWatch for health metrics and monitoring

![Architecture Diagram](https://github.com/Harikrishna2525/Aws-ALB-ASG-auto-healing/blob/master/docs/architecture.png)

---

### Failure Scenarios Tested

- EC2 instance termination → ASG launched replacement automatically  
- Docker container stopped → Target Group marked instance unhealthy  
- ALB stopped routing traffic to unhealthy instance  
- New instance bootstrapped via User Data  
- Application became healthy and resumed traffic  

**Result:** No user-visible downtime.

---

### What This Project Demonstrates

- Load balancing and health check behavior
- Auto Scaling replacement mechanics
- CloudWatch-based monitoring awareness
- Fault-tolerant infrastructure design
- AWS networking fundamentals
- Production-style deployment mindset

---

## ☁️ Core Technical Stack

### Compute & Networking
- EC2
- Application Load Balancer (ALB)
- Auto Scaling Groups (ASG)
- Target Groups & Health Checks
- VPC, Subnets, Route Tables, Internet Gateway
- Security Groups

### Serverless & Backend Services
- AWS Lambda
- API Gateway (REST APIs)
- DynamoDB (NoSQL data storage)

### Storage & CDN
- Amazon S3 (static hosting, object storage)
- CloudFront (content delivery & caching)

### Containers & OS
- Docker
- Linux (Ubuntu)
- Nginx (reverse proxy & server configuration)

### Monitoring & Operations
- Amazon CloudWatch (logs, metrics, alarms)
- User Data bootstrapping
- Basic CloudFormation
- CI/CD fundamentals
- Cost-aware Free Tier testing

---

## 🔐 IAM Awareness

- IAM Roles for EC2 and Lambda
- Least-privilege access patterns
- Service-to-service authentication
- Avoiding hardcoded credentials

---

## 📁 Portfolio

🌐 **Cloud Portfolio:**  
https://harikrish-portfolio25.web.app/

Includes:
- EC2 + Nginx deployments
- Auto-healing infrastructure demos
- S3 static hosting + CloudFront
- Serverless APIs using Lambda & API Gateway
- DynamoDB-backed workflows
- SSL-enabled architectures

---

## 🚀 Target Roles

- Cloud Engineer (L1–L2)
- Infrastructure Engineer (Junior–Mid)
- Platform / Infra roles in startups or product teams
- Teams using EC2 + Serverless hybrid architectures

---

## 📫 Connect

- 🌐 Portfolio: https://harikrish-portfolio25.web.app  
- 💼 LinkedIn: https://linkedin.com/in/hari-krish-13300b27a  
- 🧑‍💻 GitHub: https://github.com/Harikrishna2525  

---

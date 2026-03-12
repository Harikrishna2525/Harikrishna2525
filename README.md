☁️ Hari Krishna — AWS Cloud Infrastructure & Automation Engineer
<div align="center"> <img src="https://readme-typing-svg.herokuapp.com?font=Orbitron&weight=600&size=30&pause=900&color=36BCF7&center=true&vCenter=true&width=700&lines=AWS+Cloud+Infrastructure+Engineer;Automation+%7C+Containers+%7C+CI%2FCD;Failure-Tested+Systems" /> </div>

Designing reliable, fault-tolerant AWS infrastructure with automation, containerized deployments, CI/CD pipelines, and production-style monitoring.

🎯 Role Definition

Primary Role:
AWS Cloud Infrastructure & Automation Engineer

Responsibilities:

Design and deploy AWS infrastructure for scalable web applications

Build fault-tolerant and auto-healing systems using load balancing and Auto Scaling

Automate infrastructure provisioning using Infrastructure as Code

Containerize applications using Docker

Build CI/CD pipelines for automated container delivery

Manage EC2-based and serverless workloads

Debug infrastructure-level issues (networking, compute, service health)

Monitor systems using logs, metrics, and health checks

🧑‍💻 About Me

I’m a hands-on Cloud Infrastructure Engineer focused on how systems fail, recover, and scale, not just how they are deployed.

My work focuses on building AWS environments that are automated, resilient, and observable.

I work with:

Fault-tolerant infrastructure design

Real testing of unhealthy scenarios

EC2 and serverless-based architectures

Containerized application deployments

CI/CD pipelines for automated delivery

AWS-native monitoring and logging

Background in Flutter and backend development, which helps me understand both application behavior and the infrastructure that supports it.

🏗️ Featured Infrastructure Project
Auto-Healing Cloud Infrastructure using ALB & ASG

Problem
Single EC2 deployments create a single point of failure and downtime.

Architecture

Custom VPC

Public subnets across multiple Availability Zones

Application Load Balancer

Target Group with application-level health checks

Auto Scaling Group with Launch Template

EC2 instances running a Dockerized application

CloudWatch for health metrics and monitoring

Deployment Workflow

GitHub → GitHub Actions CI/CD Pipeline → Docker Image Build
→ Push Image to GitHub Container Registry (GHCR)
→ EC2 Instances pull container during boot using User Data
→ Application container starts automatically
→ Instances register with ALB Target Group
→ Auto Scaling maintains healthy capacity

Infrastructure provisioning handled using CloudFormation and Launch Templates.

Failure Scenarios Tested

EC2 instance termination → ASG launched replacement automatically

Docker container stopped → Target Group marked instance unhealthy

ALB stopped routing traffic to unhealthy instance

New instance bootstrapped via User Data

Application container pulled and started automatically

Traffic resumed once the instance became healthy.

What This Project Demonstrates

Load balancing and health check behavior

Auto Scaling replacement mechanics

Infrastructure bootstrapping using User Data

Containerized application deployment

CI/CD-based container delivery

CloudWatch monitoring awareness

Fault-tolerant infrastructure design

AWS networking fundamentals

☁️ Core Technical Stack
Cloud Infrastructure

AWS EC2

Application Load Balancer (ALB)

Auto Scaling Groups (ASG)

Target Groups & Health Checks

VPC, Subnets, Route Tables, Internet Gateway

Security Groups

Containers

Docker

Containerized application deployment

GitHub Container Registry (GHCR)

Infrastructure as Code

AWS CloudFormation

Launch Templates

User Data bootstrapping

Infrastructure automation

CI/CD & Delivery

GitHub Actions

Docker image build pipelines

Automated container publishing to GHCR

Automated deployment workflows

Serverless & Backend Services

AWS Lambda

API Gateway (REST APIs)

DynamoDB (NoSQL data storage)

Storage & CDN

Amazon S3 (static hosting, object storage)

CloudFront (content delivery & caching)

Containers & OS

Linux (Ubuntu)

Nginx (reverse proxy & server configuration)

Monitoring & Operations

Amazon CloudWatch (logs, metrics, alarms)

Infrastructure health monitoring

Application health checks

Cost-aware Free Tier testing

🔐 IAM Awareness

IAM Roles for EC2 and Lambda

Least-privilege access patterns

Service-to-service authentication

Avoiding hardcoded credentials

📁 Portfolio

🌐 Cloud Portfolio:
https://harikrish-portfolio25.web.app/

Includes:

EC2 + Nginx deployments

Auto-healing infrastructure demos

S3 static hosting + CloudFront

Serverless APIs using Lambda & API Gateway

DynamoDB-backed workflows

SSL-enabled architectures

📫 Connect

🌐 Portfolio: https://harikrish-portfolio25.web.app

💼 LinkedIn: https://linkedin.com/in/hari-krish-13300b27a

🧑‍💻 GitHub: https://github.com/Harikrishna2525

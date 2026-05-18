# END-TO-END DEVOPS IMPLEMENTATION FOR AN E-COMMERCE APPLICATION

## Project Overview

This project demonstrates an End-to-End DevOps implementation for a cloud-native E-Commerce application using modern DevOps tools and practices such as Docker, Kubernetes, Terraform, GitHub Actions, Argo CD, AWS EKS, Ingress, and Route53.

The application is based on the OpenTelemetry Demo Application which simulates a real-world astronomy product E-Commerce platform built using multiple microservices written in different programming languages.

---

## Key Highlights

- Implemented DevOps practices such as:
  - Containerization
  - Container Orchestration
  - Infrastructure as Code
  - CI/CD Automation

- Worked on a multi-microservice architecture application.

- Strong hands-on experience with:
  - Terraform
  - AWS EKS
  - Docker
  - Kubernetes
  - GitHub Actions
  - Argo CD

- Implemented complete CI/CD automation for Java-based microservices.

- Exposed frontend securely using:
  - AWS Load Balancer
  - Route53 DNS

---

# Tech Stack

| Category | Tools / Services |
|---|---|
| Cloud Provider | AWS |
| Containerization | Docker |
| Container Orchestration | Kubernetes |
| Infrastructure as Code | Terraform |
| CI/CD | GitHub Actions, Argo CD |
| Kubernetes Platform | Amazon EKS |
| Networking | VPC, Route53, Load Balancer |
| Source Control | Git & GitHub |

---

# Architecture Workflow

```text
Developer → GitHub → GitHub Actions → DockerHub → ArgoCD → Kubernetes (EKS) → AWS LoadBalancer → Route53 → Users
```

---

# Microservices Used

| Service | Language |
|---|---|
| accounting | .NET |
| ad | Java |
| cart | .NET |
| checkout | Go |
| currency | C++ |
| email | Ruby |
| frontend | TypeScript |
| payment | JavaScript |
| product-catalog | Go |
| recommendation | Python |
| shipping | Rust |

---

# Features Implemented

## Docker Containerization

Containerized multiple microservices:
- Product Catalog Service (Go)
- Ad Service (Java)
- Recommendation Service (Python)

Implemented:
- Multi-stage Docker builds
- Lightweight production images
- Docker Compose setup

---

## Kubernetes Deployment

Implemented Kubernetes resources:
- Deployments
- Services
- Service Accounts
- LoadBalancer Services
- Ingress Resources

Features:
- Scaling
- Self Healing
- Service Discovery
- External Access

---

## Infrastructure as Code (Terraform)

Implemented:
- VPC Creation
- Public & Private Subnets
- Route Tables
- NAT Gateway
- Internet Gateway
- EKS Cluster
- S3 Remote Backend
- DynamoDB State Locking

Terraform Modular Approach:
- VPC Module
- EKS Module
- Backend Module

---

# CI/CD Pipeline

Implemented complete CI/CD automation using:
- GitHub Actions
- Argo CD

Pipeline Flow:

```text
Code Push → GitHub Actions → Build Docker Images → Push to DockerHub → Update Kubernetes Manifests → Argo CD Sync → Deploy to EKS
```

---

# AWS Services Used

- EC2
- EKS
- VPC
- IAM
- Route53
- Elastic Load Balancer
- S3
- DynamoDB

---

# Project Setup

## 1. Clone Repository

```bash
git clone <your-repository-url>
cd ultimate-devops-project-demo
```

---

## 2. Install Docker

```bash
sudo apt update
sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

Verify Docker:

```bash
docker --version
```

---

## 3. Install Kubectl

```bash
curl -LO "https://dl.k8s.io/release/stable.txt"
```

---

## 4. Install Terraform

```bash
sudo apt install terraform
```

Verify Terraform:

```bash
terraform -version
```

---

## 5. Configure AWS CLI

```bash
aws configure
```

---

## 6. Create Infrastructure

```bash
terraform init
terraform apply
```

---

## 7. Connect to EKS Cluster

```bash
aws eks update-kubeconfig --region ap-south-1 --name my-eks-cluster
```

Verify:

```bash
kubectl get nodes
```

---

# Kubernetes Deployment

## Create Service Account

```bash
kubectl apply -f serviceaccount.yaml
```

---

## Deploy Application

```bash
kubectl apply -f complete-deploy.yaml
```

Verify:

```bash
kubectl get pods
kubectl get svc
kubectl get all
```

---

# Access Application

Expose frontend service:

```bash
kubectl edit svc opentelemetry-demo-frontendproxy
```

Change:

```yaml
type: ClusterIP
```

to:

```yaml
type: LoadBalancer
```

---

# Docker Compose (Local Testing)

Run locally:

```bash
docker compose up -d
```

---

# Common Issues & Fixes

## No Space Left on Device

```bash
sudo growpart /dev/nvme0n1 1
sudo resize2fs /dev/nvme0n1p1
```

---

## Terraform Destroy DependencyViolation

Delete:
- Load Balancers
- ENIs
- NAT Gateways

before destroying infrastructure.

---

# Learning Outcomes

- Real-world DevOps workflow
- Kubernetes production concepts
- Infrastructure automation
- CI/CD automation
- AWS networking concepts
- GitOps deployment model
- Microservice deployment strategies

---

# Future Improvements

- Prometheus & Grafana Monitoring
- EFK Logging Stack
- Helm Charts
- Service Mesh using Istio
- HPA & Cluster Autoscaler

---

# Acknowledgement

This project is inspired by:
- OpenTelemetry Demo Application
- Kubernetes Documentation
- Terraform Documentation

---

# Author

## Arijeet Ghosh

DevOps | Cloud | Kubernetes | AWS | Terraform | CI/CD Enthusiast

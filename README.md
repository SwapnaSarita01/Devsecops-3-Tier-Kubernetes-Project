# 🔐 DevSecOps 3-Tier Kubernetes Project

## 📌 Overview
This project demonstrates the design and deployment of a **secure, scalable 3-tier architecture on Kubernetes** with an automated **CI/CD pipeline** using **Jenkins and ArgoCD**.  
Security, automation, and observability were key design principles — ensuring that the application is production-ready, resilient, and secure.

---

## 🏗️ Architecture

- **Frontend, Backend, Database** (3-tier app) deployed on Kubernetes
- **CI/CD**: Jenkins (CI) + ArgoCD (GitOps CD)
- **Security**: Trivy image scanning, Kubernetes RBAC, and secrets management
- **Infrastructure as Code**: Terraform for VPC, EKS cluster, and networking
- **Monitoring & Observability**: Prometheus + Grafana dashboards

```mermaid
flowchart TD
    Dev[Developer] -->|Push Code| Jenkins[CI Pipeline]
    Jenkins --> Trivy[Trivy Security Scan]
    Jenkins --> Docker[Build & Push Docker Image]
    Docker --> GitHub[Container Registry]
    GitHub --> ArgoCD[CD Pipeline]
    ArgoCD --> K8s[EKS Cluster]
    K8s --> FE[Frontend Pod]
    K8s --> BE[Backend Pod]
    K8s --> DB[Database Pod]
    K8s --> Prometheus[Monitoring]
    Prometheus --> Grafana[Dashboards]

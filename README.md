# 🚀 Build and Secure an End-to-End AKS CI/CD Pipeline

## 📌 Overview

This project demonstrates a complete end-to-end GitOps CI/CD pipeline deployment using:

- Azure Kubernetes Service (AKS)
- Argo CD
- Azure Container Registry (ACR)
- GitHub Actions
- Helm
- Workload Identity Federation
- Trivy
- CodeQL
- Kubescape

The goal of this project was to build and secure a modern Kubernetes deployment pipeline following DevSecOps and GitOps best practices.

---

# 🏗️ Architecture

The solution uses:

- **AKS** for Kubernetes orchestration
- **Argo CD** for GitOps continuous delivery
- **Azure Container Registry (ACR)** for OCI Helm charts and container storage
- **GitHub Actions** for CI/CD automation
- **Managed Identities + Workload Identity Federation** for passwordless authentication
- **Trivy + CodeQL + Kubescape** for security scanning


---

# 🔐 Security Features

## ✅ GitHub Advanced Security
- Enabled CodeQL code scanning
- Enabled Trivy vulnerability scanning

## ✅ Branch Protection Rules
- Pull requests required before merge
- Security scanning checks required before merge

## ✅ Kubernetes Security Scanning
- Helm templates rendered and scanned using Kubescape

## ✅ Passwordless Authentication
Implemented Azure Workload Identity Federation between:
- GitHub Actions → Azure
- Argo CD → Azure Container Registry

No secrets or credentials were stored directly inside the cluster.

---

# ⚙️ CI/CD Workflow

## Development Workflow
1. Create `dev` branch
2. Modify Helm configuration
3. Run local Kubernetes security scans
4. Push changes to GitHub
5. Open Pull Request
6. Run GitHub Actions security checks
7. Merge into `main`

---

# ☸️ Argo CD GitOps Deployment

Argo CD was deployed inside the AKS cluster and configured to:

- Pull Helm charts from Azure Container Registry
- Automatically synchronize deployments
- Deploy workloads into the `staging` namespace

---

# 🧪 Security Scanning

## Kubescape Findings
The cluster configuration was scanned for:
- Privilege escalation risks
- Missing network policies
- Service account mappings
- Non-root container enforcement
- Immutable filesystem recommendations

---

# 📸 Screenshots

## Argo CD Deployment
- Healthy application state
- Automatic synchronization enabled

## Kubescape Security Scan
- Kubernetes posture analysis
- Workload security findings

## Architecture Diagram
- AKS + Argo CD + ACR + GitHub integration

---

# 🛠️ Technologies Used

- Azure Kubernetes Service (AKS)
- Argo CD
- Azure CLI
- kubectl
- Helm
- GitHub Actions
- GitHub Advanced Security
- Trivy
- Kubescape
- Azure Managed Identities
- Workload Identity Federation

---

# 🎯 Key DevOps Concepts Demonstrated

- GitOps workflows
- Kubernetes continuous delivery
- OCI Helm repositories
- Infrastructure security scanning
- Federated identity authentication
- Pull request security enforcement
- Cloud-native CI/CD pipelines

---

# 📚 Learning Outcomes

Through this project I learned how to:

- Deploy and configure Argo CD on AKS
- Secure CI/CD pipelines using GitHub Advanced Security
- Configure Workload Identity Federation
- Integrate Azure Container Registry with Argo CD
- Scan Kubernetes manifests using Kubescape
- Implement GitOps workflows using Helm and Argo CD

---

# 👩‍💻 Author

**Adriana Martinez**  
Cloud / DevOps Engineer  
AWS • Azure • Kubernetes • Terraform • GitOp






# SimpleJSMicroservice

A two-tier microservice application for Kubernetes deployment.

- **Front-End:** React (product list, cart, fake checkout)
- **Back-End:** Node.js (Express) API
- **Database:** Azure Cosmos DB (MongoDB API)

## Features
- List grocery products
- Add/remove products to cart
- Fake checkout (no payment integration)
- Product images (to be provided)
- Database seeded with sample data on API startup

## Deployment
- Designed for Kubernetes

## Setup
This repository was split into separate services. Services live under `services/`.

Run product service locally:

```sh
cd services/product-service
npm install
npm run dev
```

Run cart service locally:

```sh
cd services/cart-service
npm install
npm run dev
```

The frontend lives in the `frontend/` folder and can be started with its existing scripts.

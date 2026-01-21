# 🚀 FastAPI Deployment on Kubernetes (AWS + KOps)

This repository contains the source code and configuration files for deploying a containerized **FastAPI** application on an **AWS Kubernetes Cluster** provisioned using **KOps**.

The project demonstrates a complete DevOps workflow: from Dockerizing a Python application to orchestrating it on the cloud with High Availability (HA) and Load Balancing.

---

## 🛠 Tech Stack
- **Application:** Python (FastAPI, Uvicorn)
- **Containerization:** Docker & Docker Hub
- **Orchestration:** Kubernetes (v1.28)
- **Infrastructure Provisioning:** KOps (Kubernetes Operations)
- **Cloud Provider:** AWS (EC2, S3, Route53, ELB)

---

## 📸 Proof of Work

### 1. Cluster Validation
*Infrastructure health check verifying Control Plane and Worker nodes are ready.*
![Cluster Validation](screenshots/Screenshot%20from%202026-01-21%2020-31-27.png)

### 2. Application Deployment Status
*Pods running successfully in the `curadocs` namespace.*
![Pod Status](screenshots/Screenshot%20from%202026-01-21%2020-31-27.png)

### 3. Public Access & Health Check
*External access via AWS Load Balancer confirming the API is live.*
![Health Check](screenshots/Screenshot%20from%202026-01-21%2019-34-11.png)

---

## 🔧 Architecture & Features
- **Scalable Deployment:** Runs multiple replicas of the FastAPI application.
- **Service Discovery:** Uses a Kubernetes Service of type `LoadBalancer` to expose the app to the internet.
- **Self-Healing:** Kubernetes automatically restarts failed containers.
- **Resource Optimization:** Tuned for `t3.small` and `t3.micro` instances to balance performance with cost efficiency.

---

## 🚀 Setup & Installation Guide

### 1. Prerequisites
- AWS CLI configured with IAM permissions.
- `kubectl` and `kops` installed.
- Docker installed locally.

### 2. Build & Push Docker Image
```bash
# Build the image
docker build -t sagarpatade1900/fastapi-kops .

# Push to Docker Hub
docker push sagarpatade1900/fastapi-kops

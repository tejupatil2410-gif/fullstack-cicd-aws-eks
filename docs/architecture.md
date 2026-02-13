🏗 System Architecture Documentation
1️⃣ System Overview

This project follows a cloud-native DevOps architecture designed to deploy a containerized Python application on AWS using Kubernetes and CI/CD automation.

The system is structured to support:
Containerized deployment
Automated CI/CD pipelines
Scalable infrastructure
Zero-downtime updates
Secure cloud communication

The architecture separates:

Application Layer
CI/CD Layer
Containerization Layer
Orchestration Layer
Cloud Infrastructure Layer

This separation ensures maintainability, scalability, and production-readiness.

2️⃣ High-Level Architecture
🔁 Logical Flow

Developer
   ↓
GitHub Repository
   ↓
Jenkins CI/CD Pipeline
   ↓
Docker Image Build
   ↓
Container Registry (DockerHub / ECR)
   ↓
Amazon EKS (Kubernetes)
   ↓
Application Load Balancer
   ↓
End Users

3️⃣ Architecture Diagram (Conceptual)
                   +------------------+
                   |   Developer      |
                   +--------+---------+
                            |
                            v
                   +------------------+
                   |     GitHub       |
                   +--------+---------+
                            |
                            v
                   +------------------+
                   |     Jenkins      |
                   |   CI/CD Server   |
                   +--------+---------+
                            |
                            v
                   +------------------+
                   |     Docker       |
                   |  Image Builder   |
                   +--------+---------+
                            |
                            v
                   +------------------+
                   | Container Registry|
                   +--------+---------+
                            |
                            v
                   +------------------+
                   |   Amazon EKS     |
                   | (Kubernetes)     |
                   +--------+---------+
                            |
                            v
                   +------------------+
                   |      ALB         |
                   +--------+---------+
                            |
                            v
                   +------------------+
                   |     End Users    |
                   +------------------+

4️⃣ Services Used
💻 Application Layer

Python
Streamlit

🐳 Containerization

Docker
Dockerfile

🔁 CI/CD

Jenkins
GitHub

☸ Orchestration

Kubernetes
Amazon EKS

☁ Cloud Infrastructure

AWS EC2
AWS EKS
AWS ALB
AWS RDS (Planned)
IAM Roles

Security Groups

5️⃣ Deployment Flow (Planned Implementation)

Step 1 – Code Commit
Developer pushes code to the main branch.

Step 2 – CI Trigger
GitHub webhook triggers Jenkins pipeline.

Step 3 – Build Stage
Install dependencies

Build Docker image
Tag image

Step 4 – Push Stage
Push image to DockerHub or Amazon ECR.

Step 5 – Deployment Stage
Kubernetes pulls latest image
Rolling update replaces old pods
Zero-downtime deployment ensured

Step 6 – Traffic Routing
Application Load Balancer routes external traffic to Kubernetes service.

6️⃣ Repository Architecture Structure
app/
  backend/
  frontend/

k8s/
  deployment.yaml
  service.yaml
  ingress.yaml

jenkins/
  Jenkinsfile

docs/
  architecture.md


This separation ensures infrastructure code is independent of application code.

7️⃣ Roles & Responsibilities
👨‍💻 Developer Responsibilities

Application logic (app.py)
Dependency management
API functionality
Feature development

⚙ DevOps Responsibilities
Repository structure
Docker image creation
CI/CD pipeline configuration
Kubernetes manifests
AWS infrastructure setup
Monitoring & deployment automation

8️⃣ Design Principles Followed
Infrastructure as Code (planned)
Immutable container images
Automated deployments
Modular repository structure
Environment isolation
Cloud-native scalability
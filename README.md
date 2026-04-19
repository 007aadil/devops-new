# 🚀 DevOps CI/CD Pipeline with Docker & AWS

This project demonstrates an end-to-end DevOps pipeline that automates the build, containerization, and deployment of a Node.js application using Docker, GitHub Actions, and AWS EC2.

---

## 📌 Project Overview

The goal of this project is to implement a fully automated CI/CD pipeline where every code push triggers:

1. Build of the application  
2. Docker image creation  
3. Push to Docker registry  
4. Deployment to AWS EC2  

This eliminates manual deployment and ensures faster, consistent releases.

---

## 🛠️ Tech Stack

- Node.js (Application)
- Docker (Containerization)
- GitHub Actions (CI/CD)
- Docker Hub (Image Registry)
- AWS EC2 (Deployment Server)
- Nginx (Reverse Proxy)

---

## ⚙️ Workflow Architecture

Developer → GitHub → GitHub Actions → Docker Build → Docker Hub → AWS EC2 → Live App


---

## 🔄 CI/CD Pipeline

The pipeline is configured using GitHub Actions and includes:

- Code checkout from repository  
- Docker image build  
- Push image to Docker Hub  
- SSH into EC2 instance  
- Pull latest image  
- Stop old container  
- Run updated container  

---

## 🐳 Docker Setup

The application is containerized using a Dockerfile:

- Uses Node.js base image  
- Copies application files  
- Installs dependencies  
- Exposes port 3000  
- Runs the application  

---

## ☁️ AWS EC2 Deployment

- EC2 instance created on AWS  
- Docker installed and configured  
- Application deployed as a container  
- Port 3000 exposed for access  

---

## 🌐 Nginx Configuration

Nginx is used as a reverse proxy:

- Routes traffic from port 80 → 3000  
- Enables clean URL access  
- Improves production readiness  

---

## 🔐 Security

- Sensitive credentials stored in GitHub Secrets  
- No hardcoded credentials in code  
- Secure SSH-based deployment  

---

## 🚀 How to Run Locally

```bash
git clone <your-repo-url>
cd devops-project

docker build -t devops-app .
docker run -p 3000:3000 devops-app

http://localhost:3000

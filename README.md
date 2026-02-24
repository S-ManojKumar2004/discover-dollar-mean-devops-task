#  DevOps MEAN Stack CI/CD Project – Docker, Cloud VM & Nginx

This project demonstrates an end-to-end DevOps implementation of a full-stack **MEAN (MongoDB, Express, Angular, Node.js)** application.

The application is:

- Containerized using Docker  
- Pushed to Docker Hub  
- Deployed on an Ubuntu Virtual Machine  
- Automated using GitHub Actions CI/CD  
- Exposed via Nginx Reverse Proxy on Port 80  

This implementation strictly follows all requirements mentioned in the assignment.

---

#  Assignment Requirement Mapping

|           Requirement            |        Implementation                 |
|----------------------------------|---------------------------------------|
| GitHub Repository Setup          | Code pushed to GitHub                 |
| Dockerfiles (Frontend & Backend) | Created                               |
| Docker Images Build & Push       | Automated via CI/CD                   |
| Ubuntu VM Setup                  | Deployed on Ubuntu 22.04 VM           |
| Docker Compose Deployment        | Used for multi-container setup        |
| MongoDB Setup                    |  Official MongoDB Docker Image        |
| CI/CD Pipeline                   |  GitHub Actions implemented           |
| Auto Image Build & Push          |  On every push to main                |
| Auto Deploy to VM                |  Images pulled & containers restarted |
| Nginx Reverse Proxy              |  Configured on Port 80                |
| Screenshots Included             |  Added in repository                  |

---

#  Architecture Overview

Client Browser
│
▼
Public IP (Ubuntu VM)
│
▼
Nginx (Port 80 Reverse Proxy)
│
├── / → Frontend Container (Angular + Nginx)
│
└── /api → Backend Container (Node.js + Express)
│
▼
MongoDB Container


---

#  Tools & Technologies Used

## Containerization
- Docker
- Docker Compose
- Docker Hub

## Application Stack
- MongoDB
- Express
- Angular
- Node.js

## CI/CD
- GitHub Actions
- GitHub Secrets

## Infrastructure
- Ubuntu 22.04 Virtual Machine
- Cloud-based VM
- UFW Firewall

## Reverse Proxy
- Nginx

---

#  Project Structure


crud-dd-task-mean-app/
│
├── backend/
│ ├── Dockerfile
│ ├── server.js
│ └── package.json
│
├── frontend/
│ ├── Dockerfile
│ ├── angular.json
│ └── src/
│
├── docker-compose.yml
├── .github/workflows/deploy.yml
└── README.md


---

#   Containerization & Deployment

## 🔹 Backend Dockerfile
- Base image: node:18
- Installs dependencies
- Exposes backend port
- Starts server using npm start

## 🔹 Frontend Dockerfile (Multi-Stage)
- Build stage: node:18
- Production stage: nginx:alpine
- Angular production build copied to Nginx

## 🔹 MongoDB
- Official MongoDB Docker image used
- Persistent Docker volume enabled

---

# ⚙ Docker Compose Deployment

Application deployed using:

```bash
docker compose up -d --build

Features:

Multi-container setup

Persistent MongoDB storage

Restart policy enabled

Internal Docker networking

Proper port mapping

☁ Cloud Infrastructure Setup

Ubuntu 22.04 VM provisioned

Docker & Docker Compose installed

UFW Firewall enabled

Ports allowed:

22 (SSH)

80 (HTTP)

CI/CD Pipeline – GitHub Actions

Pipeline automatically runs on push to main branch.

Steps Performed:

Checkout repository

Login to Docker Hub

Build backend Docker image

Build frontend Docker image

Push images to Docker Hub

SSH into Ubuntu VM

Pull latest images

Restart containers using Docker Compose

Secrets Used:

DOCKER_USERNAME

DOCKER_PASSWORD

VM_HOST

SSH_PRIVATE_KEY

No credentials are hard-coded.


Nginx Reverse Proxy Configuration

Nginx configured to:

Listen on Port 80

Route / → Frontend

Route /api → Backend

This ensures:

Clean routing

Centralized traffic handling

Production-style architecture

** Security Configuration **

MongoDB not exposed publicly

Firewall enabled

SSH key authentication used

Environment variables used for database config

Docker restart policy enabled


git clone discover-dollar-mean-devops-task
cd crud-dd-task-mean-app

# Start Application :
<img width="1154" height="158" alt="image" src="https://github.com/user-attachments/assets/7d1fa771-f71c-42f3-8063-1c632cdac3dc" />

# Verify Running Containers :
<img width="1672" height="137" alt="image" src="https://github.com/user-attachments/assets/49d49383-4860-4e6d-843e-e7984cdf011e" />


# Access Application --- >> "  http://localhost:8080/tutorials  "

📦 Docker Hub Images :
manojkumar2026/backend:latest
manojkumar2026/frontend:latest

<img width="1225" height="297" alt="image" src="https://github.com/user-attachments/assets/969edf79-648a-4fe1-9119-cc05245f8666" />

Docker Hub :   -->> "  https://hub.docker.com/u/manojkumar2026  "


 [gitHub Action]
(img width="1850" height="619" alt="image" src="https://github.com/user-attachments/assets/6c8f44c8-99bd-4097-8e59-442d4ff2ece5" /)
















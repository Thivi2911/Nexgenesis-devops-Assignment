# DEVOPS.md
## DevOps Assessment – Full Stack Deployment

---

## 1. Project Overview

This project is a full-stack "Hello World" application consisting of:
- **Backend**: Django REST API
- **Frontend**: React (Vite + TypeScript)

The goal of this assignment is to containerize the application, orchestrate services, and automate the build process using DevOps best practices.

---

## 2. Architecture Overview

- The **React frontend** runs inside an Nginx container.
- The **Django backend** runs inside a Python container.
- Both containers are orchestrated using **Docker Compose**.
- Frontend communicates with backend using Docker service names.


---

## 3. Prerequisites

To run this project locally, you need:
- Docker
- Docker Compose
- Git

---

## 4. Running the Application Locally

### Step 1: Clone the repository

```bash
git clone https://github.com/Thivi2911/Nexgenesis-devops-Assignment.git
cd Nexgenesis-devops-Assignment


---

docker compose up --build

---
Access the application

Frontend: http://localhost:3000

Backend API: http://localhost:8000/api/hello/

---
##Backend (Django)

# Uses a multi-stage Docker build

# Runs as a non-root user for security

# Dependencies are installed using requirements.txt

# SQLite database permissions handled inside the container

---
## Frontend (React)

# Uses Node.js only during build stage

# Final image uses Nginx to serve static files

# Optimized production-ready image
---

## Docker Compose Orchestration

# Docker Compose is used to:

# Run frontend and backend together

# Create a shared Docker network

# Enable service-name-based communication (backend:8000)


## CI/CD Pipeline (GitHub Actions)

# A CI/CD pipeline is implemented using GitHub Actions.

# Pipeline Trigger

# Runs automatically on every push to the main branch

# Pipeline Steps

# Checkout source code

# Login to Docker Hub using GitHub secrets

# Build Docker images for frontend and backend

# Push images to Docker Hub

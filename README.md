# Kanban Dashboard - Jenkins CI/CD Deployment

## Project Overview

This project demonstrates an automated CI/CD workflow for deploying a React + TypeScript Kanban Dashboard application using:

- GitHub
- Jenkins
- Docker
- Docker Hub
- AWS EC2
- Nginx

The complete deployment flow is:

**GitHub → Jenkins → Docker Build → Docker Hub → AWS EC2 → Docker Container → Health Check → Validation**

The deployment is automated through Jenkins, and the pipeline includes health validation and automatic rollback when a deployment fails.

---

## Application

The application is a Kanban-style task manager built using React and TypeScript with Vite.

### Application Details

| Item | Value |
|---|---|
| Frontend | React |
| Language | TypeScript |
| Build Tool | Vite |
| Web Server | Nginx |
| Application Port | 8080 |
| Container Name | `kanban-app` |
| Docker Registry | Docker Hub |

---

## GitHub Repository

Source code is maintained in GitHub.

Repository:

https://github.com/kishore-stack/kanban-dashboard.git

The Jenkins pipeline checks out the `main` branch from this repository.

---

# Docker Containerization

The application uses a multi-stage Docker build.

### Stage 1 - Build

The application is built using:

```dockerfile
FROM node:22-alpine AS builder
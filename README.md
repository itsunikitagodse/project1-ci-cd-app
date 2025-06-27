# 🚀 CI/CD Pipeline with GitHub Actions, Docker, and Minikube

This project demonstrates a complete **CI/CD pipeline** setup using **GitHub Actions**, **Docker**, **Docker Hub**, and **Minikube** — all without using any cloud services.

## Tech Stack

- Node.js (Express.js app)
- Docker & Docker Compose
- GitHub Actions (CI/CD)
- Docker Hub (image registry)
- Minikube (Kubernetes cluster)


## Objective

To automate the build, test, and deployment of a Node.js app using:

- **GitHub Actions** for CI/CD
- **Docker** for containerization
- **Docker Hub** for image storage
- **Minikube** for local Kubernetes deployment

## Project Structure

ci-cd-app/

├── app/

│ └── index.js # Express app

├── Dockerfile # Docker image build instructions

├── docker-compose.yml # Optional: Local dev with Docker Compose

├── package.json # Node dependencies and scripts

├── .github/

│ └── workflows/

│ └── ci-cd.yml # GitHub Actions CI/CD workflow

└── README.md

## ⚙️ GitHub Actions Workflow

The `.github/workflows/ci-cd.yml` file runs on every push to `main`. It performs the following:

1. ✅ Checks out the code

2. ✅ Installs Node.js dependencies

3. ✅ Runs test (dummy `npm test`)

4. ✅ Builds Docker image

5. ✅ Pushes Docker image to Docker Hub

## Docker Image

Docker image is built by GitHub Actions and pushed to Docker Hub.

- **Image Name:** `nikitagodse/ci-cd-app`
- **Docker Hub URL:** [https://hub.docker.com/r/nikitagodse/ci-cd-app](https://hub.docker.com/r/nikitagodse/ci-cd-app)

### Pull the Image Locally

>> docker pull nikitagodse/ci-cd-app:latest

**Local Deployment with Minikube**

✅ Prerequisites
Docker Desktop with WSL 2 backend

Minikube installed and running:

>> minikube start --driver=docker --memory=6144 --cpus=4

## Kubernetes Deployment

**Apply the deployment and service:**

>> kubectl apply -f deployment.yaml

>> kubectl apply -f service.yaml

**Check status:**

>> kubectl get pods

>> kubectl get svc

**Access the app:**

>> minikube service ci-cd-app --url

Open the URL in your browser to see the live app.

**📸 Screenshots**
Screenshot	Description
✅ GitHub Actions CI/CD pipeline

✅ Docker image on Docker Hub

✅ App running via Minikube


## Test Script
npm test
Currently runs a dummy test that always passes.

## Useful Commands

**Start Minikube**

>> minikube start --driver=docker --memory=6144 --cpus=4

**Build image manually (if needed)**

>> docker build -t nikitagodse/ci-cd-app:latest .

**Push image manually**

>> docker push nikitagodse/ci-cd-app:latest

**Delete everything in cluster**

>> kubectl delete all --all

**Access app**

>> minikube service ci-cd-app --url

## 📚 Learnings
- How to build a full CI/CD pipeline without cloud
- Using GitHub Actions to build, test, and push Docker images
- Deploying and exposing Docker containers on a local Kubernetes cluster with Minikube

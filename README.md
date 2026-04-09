# Edulab - Kubernetes Deployment Project

## Overview
**Edulab** is a static web application deployed locally on Kubernetes (Minikube) to demonstrate end-to-end DevOps and containerization skills. This project showcases proficiency in CI/CD pipelines, containerization with Docker, and orchestration with Kubernetes.

## Features
- Deployment of a static web app using **Nginx**.
- Fully containerized using **Docker** with a custom Dockerfile.
- Continuous Integration & Deployment pipeline implemented with **GitLab CI/CD** and **Jenkins**.
- Kubernetes deployment using **Minikube** to simulate a production-like environment.
- Port exposed on **80** for local access.

## Technology Stack
- **Frontend:** Static HTML/CSS (served via Nginx)
- **Containerization:** Docker, DockerHub
- **Orchestration:** Kubernetes (Minikube)
- **CI/CD:** GitLab, Jenkins
- **Other Tools:** Git for version control, YAML for Kubernetes manifests

## Architecture
1. **Code pushed to GitLab repository** triggers Jenkins pipeline.
2. **Docker image** is built using the Dockerfile and pushed to DockerHub.
3. **Kubernetes Deployment** pulls the Docker image from DockerHub.
4. **Service exposes the app** on port 80 in Minikube, making the static site accessible locally.

## Achievements / Highlights
- Implemented end-to-end CI/CD pipeline integrating GitLab, Jenkins, Docker, and Kubernetes.
- Built custom Nginx Docker image to serve the static web application.
- Successfully deployed application locally with Kubernetes, exposing it via port 80.
- Demonstrates knowledge of container orchestration, pipeline automation, and cloud-native deployment practices.

## Learning Outcomes
- Hands-on experience with Dockerfile creation and image management.
- Implemented Kubernetes deployment and services for local development.
- Gained practical skills in CI/CD automation using GitLab and Jenkins.

## License
- This project is open-source and available under the MIT License.

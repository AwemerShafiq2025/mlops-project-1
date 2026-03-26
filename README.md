# MLOps Project #1: Automated CI/CD Pipeline

## Project Overview
This project demonstrates a complete MLOps lifecycle, including application development, containerization, and automated deployment using Jenkins.

## Technical Details
* **Source Control:** GitHub
* **Containerization:** Docker
* **Automation:** Jenkins CI/CD (using Jenkinsfile/SCM)
* **Environment:** Ubuntu (WSL2)

## Docker Hub Information
* **Docker Hub Image:** `awemer/mlops-app:latest`
* **Pull Command:** `docker pull awemer/mlops-app:latest`

## Project Phases
1. **Development:** Created a Python application and a Dockerfile.
2. **Version Control:** Managed code via Git and pushed to this repository.
3. **Registry:** Successfully pushed the container image to Docker Hub.
4. **Automation:** Configured a Jenkins Pipeline (SCM) to pull, build, and deploy the application automatically.

## Final Verification
* **Jenkins Pipeline Status:** All stages (Checkout, Build, Push, Deploy) are Green.
* **Live App:** Accessible via `http://localhost:80` (Standard Nginx Port).

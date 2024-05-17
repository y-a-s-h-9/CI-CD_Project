# CI/CD Pipeline with Jenkins

This repository contains the source code and configurations for setting up a CI/CD pipeline using Jenkins.

## Project Overview
The project demonstrates the following:
- Jenkins setup and configuration
- Building a Docker image for a web application
- Running automated tests
- Deploying to a Kubernetes cluster

## Technologies Used
- Jenkins
- Docker
- Kubernetes
- GitHub

## Pipeline Stages
1. **Checkout Code:** Pull the latest code from the GitHub repository.
2. **Build Docker Image:** Create a Docker image for the application.
3. **Run Tests:** Execute unit and integration tests.
4. **Push to Registry:** Push the Docker image to Docker Hub.
5. **Deploy to Staging:** Deploy the application to a staging environment on Kubernetes.
6. **Deploy to Production:** Deploy the application to the production environment after approval.

## Setup Instructions
1. Clone the repository:
   ```sh
   git clone https://github.com/yourusername/ci-cd-pipeline-jenkins.git
   cd ci-cd-pipeline-jenkins

---


# Docker GitHub Action

## Overview
This project automates the building and pushing of a Docker image to Docker Hub using GitHub Actions. Every time code is pushed to the main branch, the workflow automatically builds a Docker image and pushes it to Docker Hub.

## Technologies Used
- Docker
- GitHub Actions
- Docker Hub
- Nginx

## How It Works

### Docker
Docker is used to containerize the HTML application. The `Dockerfile` uses an `nginx:alpine` base image to serve the HTML files. This ensures the app runs consistently in any environment.

### GitHub Actions
GitHub Actions automates the entire build and push process. The workflow is triggered on every push to the `main` branch and performs the following steps:
1. Checks out the repository
2. Logs into Docker Hub using stored secrets
3. Builds the Docker image
4. Pushes the image to Docker Hub

## How to Run Locally
Pull and run the image from Docker Hub:
```bash
docker pull your-dockerhub-username/myapp:tagname
docker run -d -p 80:80 --name myapp your-dockerhub-username/myapp:tagname
```
Then open your browser and go to `http://localhost`

## Repository Structure
- `Dockerfile` - Instructions to build the Docker image
- `index.html` - The main HTML page served by Nginx
- `.github/workflows/` - GitHub Actions workflow configuration

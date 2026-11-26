# 🚀 CI/CD Demo Project - DevOps in Action
> A simple website deployed using a fully automatic CI/CD Pipeline.
> Push Code → GitHub Actions Builds Image → Pushes to Docker Hub → Ready to Deploy Anywhere!

[Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
[GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white)
[Nginx](https://img.shields.io/badge/Nginx-009639?style=for-the-badge&logo=nginx&logoColor=white)
[HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)

## ✨ What is this Project?
This project is not about a fancy website. It's about **how real companies deploy software.**

I created a simple HTML website and built a complete **CI/CD Pipeline** for it. Now, whenever I change even 1 line of code and push it to GitHub, the new version is automatically built and deployed — without any manual work!

**Live Demo of CI/CD:**
- Version 1.0 → Pushed → Auto Deployed ✅
- Version 2.0 → Pushed → Auto Deployed ✅

## 🛠️ Tech Stack
| Tool | Why I Used It |
| :--- | :--- |
| **HTML** | Simple static website |
| **Docker** | To package website + server into one Image |
| **Nginx** | Lightweight web server to serve the website |
| **GitHub Actions** | To automate Build & Push (CI/CD) |
| **Docker Hub** | To store my Docker Images |

## 🔄 How CI/CD Works Here? (The Flow)
mermaid
graph LR
    A[💻 Code Change in VS Code] --> B[📤 Git Push to main]
    B --> C[⚙️ GitHub Actions Triggered]
    C --> D[🐳 Docker Image Built]
    D --> E[☁️ Pushed to Docker Hub]
    E --> F[🚀 Pull & Run Anywhere]


*Step-by-Step:*
1. I change `index.html` (e.g., Version 1.0 → 2.0)
2. I push code to `main` branch
3. GitHub Actions reads `.github/workflows/deploy.yml`
4. It builds a new Docker Image using my `Dockerfile`
5. It pushes the Image to Docker Hub as `suryansh700/cicd-demo:latest`
6. I just pull and run it — New version is live!

*📁 Project Structure*

cicd-pipeline-demo/
├── index.html                  # My Website
├── Dockerfile                  # Recipe to build Docker Image
├── README.md                   # You are reading this!
└── .github/
    └── workflows/
        └── deploy.yml          # The CI/CD Pipeline File


*🐳 Dockerfile Explained*

FROM nginx:alpine
COPY index.html /usr/share/nginx/html/index.html
EXPOSE 80


- `FROM nginx:alpine` → Use lightweight Nginx server as base
- `COPY ...` → Copy my website inside the server
- `EXPOSE 80` → Open Port 80 for website

*⚙️ Pipeline File - `deploy.yml` Explained*

name: Deploy to Docker Hub
on:
  push:
    branches: [ main ]


- Pipeline runs *only* when code is pushed to `main` branch.
- It uses *GitHub Secrets* for Docker Hub login — No password in code (Secure!).
- It builds the Image and pushes it with tag `latest`.

*▶️ How to Run This Project Yourself*
*Option 1: Run from Docker Hub (Easiest)*


bash
docker pull suryansh700/cicd-demo:latest
docker run -d -p 3000:80 suryansh700/cicd-demo:latest


Now open → `http://localhost:3000`

*Option 2: Build Locally*


bash
git clone https://github.com/suryanshdubey20/cicd-pipeline-demo.git
cd cicd-pipeline-demo
docker build -t cicd-demo .
docker run -d -p 3000:80 cicd-demo


*🎯 What I Learned*
- [x] How to write a Dockerfile
- [x] How to build & run Docker Containers
- [x] How to create GitHub Actions Workflow
- [x] How to use GitHub Secrets for secure login
- [x] How to push Images to Docker Hub
- [x] End-to-End CI/CD Concept

*👨‍💻 Author*
*Suryansh* - Learning DevOps, One Pipeline at a Time!

Connect with me on GitHub: https://github.com/suryanshdubey20

⭐ If you liked this project, give it a star!

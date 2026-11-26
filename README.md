# 🚀 CI/CD Demo Project - DevOps in Action

> A simple website deployed using a fully automatic CI/CD Pipeline.
> Push Code → GitHub Actions Builds Image → Pushes to Docker Hub → Ready to Deploy Anywhere!

![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white)
![Nginx](https://img.shields.io/badge/Nginx-009639?style=for-the-badge&logo=nginx&logoColor=white)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)

---

## ✨ What is this Project?

This project is not about a fancy website. It's about **how real companies deploy software.**

I created a simple HTML website and built a complete **CI/CD Pipeline** for it. Now, whenever I change even 1 line of code and push it to GitHub, the new version is automatically built and deployed — without any manual work!

**Live Demo of CI/CD:**
- Version 1.0 → Pushed → Auto Deployed ✅
- Version 2.0 → Pushed → Auto Deployed ✅

---

## 🛠️ Tech Stack

| Tool | Why I Used It |
| :--- | :--- |
| **HTML** | Simple static website |
| **Docker** | To package website + server into one Image |
| **Nginx** | Lightweight web server to serve the website |
| **GitHub Actions** | To automate Build & Push (CI/CD) |
| **Docker Hub** | To store my Docker Images |

---

## 🔄 How CI/CD Works Here? (The Flow)

```mermaid
graph LR
    A[💻 Code Change in VS Code] --> B[📤 Git Push to main]
    B --> C[⚙️ GitHub Actions Triggered]
    C --> D[🐳 Docker Image Built]
    D --> E[☁️ Pushed to Docker Hub]
    E --> F[🚀 Pull & Run Anywhere]
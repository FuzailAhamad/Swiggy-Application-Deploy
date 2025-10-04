# 🚀 Swiggy Clone - End-to-End CI/CD Pipeline  

This project demonstrates the implementation of a **fully automated CI/CD pipeline** for deploying a Node.js-based Swiggy clone on **AWS EC2 (t2.large)** using **Jenkins, Docker, SonarQube, Trivy, and OWASP Dependency-Check**.  

The objective was to automate **build, test, security scanning, and deployment** stages for a secure and efficient delivery pipeline.  

---

## 🛠️ Tech Stack & Tools  
- **Infrastructure Automation**: Terraform  
- **CI/CD**: Jenkins  
- **Version Control**: GitHub  
- **Code Quality**: SonarQube  
- **Security Scanning**: OWASP Dependency-Check, Trivy  
- **Containerization**: Docker & DockerHub  
- **Cloud Provider**: AWS EC2 (Ubuntu t2.large)  
- **Application**: Node.js (npm)  

---

## 📂 Project Architecture  

**Workflow:**  

`GitHub → Jenkins → SonarQube → OWASP Dependency-Check → Trivy → Docker → AWS EC2 Deployment`  

---

## ⚡ Terraform Setup  

### `main.tf`
- Creates **Security Group** opening required ports: `22, 80, 443, 8080, 9000, 3000`  
- Launches **t2.large Ubuntu EC2 instance**  
- Attaches `resource.sh` script for automatic installation  

### `provider.tf`
- Configures AWS provider (`ap-south-1` region).  

### `resource.sh`
- Installs **Java 17, Jenkins, Docker, SonarQube, Trivy** automatically.  
- Starts Jenkins service and SonarQube container.  

---

## 🔄 CI/CD Pipeline (Jenkinsfile)

1. **Clean Workspace**  
2. **Checkout from GitHub**  
3. **SonarQube Analysis & Quality Gate**  
4. **Install Dependencies (`npm install`)**  
5. **OWASP FS Scan**  
6. **Trivy FS Scan**  
7. **Docker Build & Push to DockerHub**  
8. **Trivy Image Scan**  
9. **Deploy Docker Container on EC2**  

---

## 🎯 Results  
- Successfully automated **Infrastructure + CI/CD + Security**.  
- Swiggy Node.js app deployed on **AWS EC2** and accessible via public IP on port `3000`.  

---

## 👥 Contributors  
- **Fuzail Ahamad**    

---

## 🎥 Demo Video  
🔗 [Watch Here](https://drive.google.com/file/d/1jkpmgwesMUhDTay8F931kAZgm7qReV5W/view?usp=sharing)  

---

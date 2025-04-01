# 🐳 Project 2: Image and Runtime Application Security

## 1. Overview 🚀
This project demonstrates how to **securely build, scan, and deploy** a containerized application using **Docker** and **Amazon ECS**, with dynamic security testing applied post-deployment. The CI/CD pipeline uses **Trivy** for vulnerability scanning and **OWASP ZAP** for DAST, helping catch both image-level and runtime threats.

---

## 2. Key Technologies 🛠
- **Docker** ⚙️  
  - Containerizes the application and static content.
- **Amazon ECS** ☁️  
  - Orchestrates container deployment with rolling updates and auto-scaling.
- **Trivy** 🔎  
  - Performs container image vulnerability scans.
- **OWASP ZAP** 🛡  
  - Scans the live app for XSS, SQLi, and other runtime issues.
- **GitHub Actions** 🤖  
  - Automates image build, scan, deployment, and runtime testing in a single pipeline.

---

## 3. Security Highlights 🔒
- **Trusted Base Images**  
  - Official base images reduce inherited vulnerabilities.
- **Automated Image Scanning**  
  - Trivy blocks insecure containers from reaching production.
- **DAST Integration**  
  - OWASP ZAP scans the deployed app for runtime threats.
- **Least Privilege IAM**  
  - ECS roles are tightly scoped for better security.
- **Zero-Downtime Deployment**  
  - Rolling updates maintain uptime and enforce version control.

---

## 4. CI/CD Workflow 🔄

### 🔧 Job 1: Build, Scan & Push
- Build the Docker image  
- Scan with Trivy (block on HIGH/CRITICAL)  
- Push to Docker Hub  

### 🚀 Job 2: ECS Deployment
- Use AWS credentials from GitHub Secrets  
- Force new deployment on ECS cluster  
- Rolling update with load balancing  

### 🧪 Job 3: Runtime DAST Scan
- Wait for app to stabilize  
- Use OWASP ZAP container to scan live endpoint  
- Generate vulnerability report (without failing the pipeline)

---

## 5. Value for Organizations 💼
- **Secure CI/CD Delivery**  
  - Integrated static + dynamic scanning pre- and post-deployment
- **Fast, Automated Workflows**  
  - Secure code goes live faster and with less human error
- **Cloud-Native Scalability**  
  - ECS ensures resilience, availability, and auto-scaling
- **Real-World Threat Coverage**  
  - Combines vulnerability scanning and runtime testing in one flow

---

## 6. Conclusion ✅
This project integrates **Docker**, **Trivy**, **OWASP ZAP**, **ECS**, and **GitHub Actions** into a modern DevSecOps pipeline. It enforces security from image build to live deployment — automatically. This ensures a fast, secure release cycle and aligns with real-world security practices.

---

🔗 [Back to my GitHub Profile](https://github.com/nfroze)
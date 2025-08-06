✅ Node.js CI/CD Pipeline with Jenkins and Docker

This project demonstrates a complete CI/CD pipeline using Jenkins, Docker, and GitHub for a simple Node.js application.

🛠 Technologies Used:

- Node.js
- Git & GitHub
- Jenkins
- Docker
- DockerHub
- WSL (Ubuntu on Windows)
- EC2 Ubuntu (for cloud)

📁 Project Structure:
```go
├── app.js
├── Dockerfile
├── Jenkinsfile
├── package.json
```
🚀 How the CI/CD Works:

1. Developer pushes code to GitHub (main branch).
2. Jenkins Pipeline (configured via Jenkinsfile) is triggered.
3. Jenkins:
   - Pulls code from GitHub
   - Builds Docker image using Dockerfile
   - Pushes the image to DockerHub under netrika0210/jenkins-node-app

📦 DockerHub:

Docker image is pushed here after successful Jenkins build:
- Image: https://hub.docker.com/repository/docker/netrika0210/jenkins-node-app

🖥️ LOCAL SETUP (WSL - Windows Ubuntu)

1. Install
  - Docker Desktop (with WSL integration enabled)
  - Java (sudo apt install default-jdk)
  - Git (sudo apt install git)

2. Start Jenkins
```bash
java -jar /mnt/c/Users/Netrika/jenkins/jenkins.war
```
3. Access Jenkins at: http://localhost:8080

☁️ EC2 SETUP (Ubuntu Server)

1. Install Prerequisites
```bash
  sudo apt update
  sudo apt install default-jdk git docker.io -y
  sudo systemctl start docker
  sudo systemctl enable docker
```
2. Create Jenkins User (optional)
```bash
  sudo adduser jenkins
  sudo usermod -aG docker jenkins
```
3. Start Jenkins
```bash
  java -jar jenkins.war
```
4. Open Jenkins on your browser
  = Go to: http://<EC2-IP>:8080

🔐 Jenkins Credentials

1. Add DockerHub credentials in Jenkins > Manage Credentials.
2. Use ID: dockerhub-creds (same as in Jenkinsfile).

✅ Triggering Pipeline

1. Create a Freestyle or Pipeline job.
2. Point GitHub URL to:
```
https://github.com/netrikadongre-source/Task-2.git
```
3. Jenkinsfile is auto-detected and used.

👤 Author:
Netrika Dongre
- GitHub:
https://github.com/netrikadongre-source
- DockerHub: https://hub.docker.com/u/netrika0210

📌License:
MIT License – free to use, modify, and share.

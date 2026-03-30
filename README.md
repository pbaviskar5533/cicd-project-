🚀 CI/CD Pipeline Project

📌 Overview

In this project, I implemented a complete CI/CD pipeline to automate the deployment of a web application using GitHub Actions, Docker, and AWS EC2.

The main goal was to reduce manual effort and make the deployment process faster, consistent, and reliable.

---

 🎯 What I Did

* Created a GitHub repository for the project
* Built a simple static web application using HTML
* Containerized the application using Docker
* Set up an AWS EC2 instance (Ubuntu) for deployment
* Installed and configured Docker on EC2
* Pushed Docker image to Docker Hub
* Deployed the application using Docker container on EC2
* Automated the entire workflow using GitHub Actions (CI/CD pipeline)

---

 🛠️ Tech Stack

* GitHub
* GitHub Actions
* Docker
* Docker Hub
* AWS EC2 (Ubuntu)
* Apache (httpd)

---

 📁 Project Structure

```bash
cicd-project/
├── index.html
├── Dockerfile
└── .github/workflows/deploy.yml
```

---

 ⚙️ Implementation Steps

 1. Application Setup

I created a simple HTML page (`index.html`) which will be served using Apache inside a Docker container.

---

2. Dockerization

```dockerfile
FROM httpd:2.4
COPY index.html /usr/local/apache2/htdocs/index.html
```

I used the official Apache image and copied my HTML file into the default serving directory.

---

 3. AWS EC2 Setup

* Launched Ubuntu EC2 instance
* Enabled ports: 22 (SSH), 80 (HTTP), 443 (HTTPS)
* Connected using EC2 Instance Connect

---

 4. Docker Installation on EC2

```bash
sudo apt update
sudo apt install docker.io -y
sudo systemctl start docker
```

---

 5. Build Docker Image

```bash
sudo docker build -t pbaviskar5533/cicd-project .
```

---

 6. Push Image to Docker Hub

```bash
sudo docker push pbaviskar5533/cicd-project
```

---

 7. Run Container on EC2

```bash
sudo docker run -d -p 80:80 pbaviskar5533/cicd-project
```

The application becomes accessible using the EC2 public IP.

---

 8. CI/CD Pipeline (GitHub Actions)

I created a workflow file (`deploy.yml`) which automates:

* Code checkout
* Docker image build
* Push to Docker Hub
* Deployment to EC2 via SSH

---

 🔐 Secrets Used

* DOCKER_USERNAME
* DOCKER_PASSWORD
* EC2_HOST
* EC2_SSH_KEY

These were stored securely in GitHub Secrets.

---

 ⏱️ Key Outcome

One of the main results of this project was reducing deployment time.

* Manual deployment: ~23 minutes
* Automated pipeline: ~14 minutes

This resulted in approximately **40% faster deployments**.

## 🧠 What I Learned

* End-to-end CI/CD pipeline implementation
* Docker image build and deployment lifecycle
* GitHub Actions automation
* Handling real-time errors (permissions, tagging, authentication)
* Importance of correct naming and configuration in DevOps

---

## 🚀 Future Improvements

* Kubernetes deployment
* Terraform for infrastructure automation
* Monitoring using Prometheus & Grafana

---

## 👨‍💻 Author

Piyush Baviskar
DevOps & Linux Enthusiast

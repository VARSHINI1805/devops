This folder contains the essential files used in Day4 of my DevOps project, focused on setting up and automating a CI/CD pipeline using Jenkins and Docker.

---

## 🚀 What’s Inside This Folder

| File | Purpose |
|------|---------|
| `Jenkinsfile` | Defines the Jenkins pipeline to build and deploy the Docker image automatically |
| `Dockerfile` | Instructions to build the Docker image using NGINX |
| `index.html` | A simple HTML page to serve inside the Docker container |

---

## 🧠 Overview

### 📌 Jenkinsfile

This file tells Jenkins how to:

1. Pull code from the repository
2. Build the Docker image
3. Stop and remove any existing container
4. Run a fresh container with the updated image

This automates your entire deployment process using CI/CD.

---

## 🐳 Dockerfile

The Dockerfile uses the official NGINX image and copies your web page into the container:

```dockerfile
FROM nginx:latest
COPY index.html /usr/share/nginx/html/index.html
This builds a simple web server using NGINX that displays your index.html.

🌐 index.html
Your HTML page shows an attractive DevOps project landing page with your name and purpose.

📌 How to Use
✅ Run Locally (Manual Docker Run)
docker build -t web134 .
docker run -d -p 5000:80 --name web134 web134
Open in browser:

http://<your-server-ip>:5000
🛠️ Jenkins CI/CD Integration
Your Jenkinsfile automatically performs:

Pull from GitHub day-4/Day4

Docker build and run

Container cleanup

Continuous deployment

⚠ Make sure Jenkins Pipeline configuration uses:

Script Path: Day4/Jenkinsfile
Branch Specifier: */day-4
Repository URL: https://github.com/VARSHINI1805/devops.git


This folder reflects my Day4 work focused on automated deployment using Jenkins and Docker.


---

### 📌 How to Add This to GitHub

1. Make sure you are in **day-4 branch**
2. Create a README file inside **Day4 folder**

```bash
cd ~/devops
git checkout day-4
nano Day4/README.md
Paste the content above

Save and exit

Ctrl + O → Enter  
Ctrl + X

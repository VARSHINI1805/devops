# 🐧 DevOps Day 1 – Linux Commands

This document contains basic Linux commands practiced as part of DevOps Day-1.

---

## 📁 1️⃣ Directory Commands

- `pwd` – Print Working Directory (Shows current location)
- `ls` – List files and folders
- `ls -l` – Detailed list format
- `ls -a` – Show hidden files
- `cd foldername` – Change directory
- `cd ..` – Go to parent directory
- `cd ~` – Go to home directory
- `mkdir newdir` – Create new directory
- `rmdir newdir` – Remove empty directory

---

## 📄 2️⃣ File Commands

- `touch file.txt` – Create empty file
- `vim file.txt` – Open file in Vim editor
- `cat file.txt` – Display file content
- `cp source.txt dest.txt` – Copy file
- `mv old.txt new.txt` – Move or rename file
- `rm file.txt` – Delete file
- `history` – Show previously used commands

---

## ⭐ 3️⃣ Wildcard Commands

- `ls *.txt` – List all `.txt` files
- `rm *.txt` – Remove all `.txt` files
- `ls file?.txt` – Match exactly one character

---

## 📦 4️⃣ Ubuntu Package Commands

- `sudo apt update` – Update package list
- `sudo apt upgrade -y` – Upgrade installed packages

---

## 🔐 5️⃣ SSH Commands

- `sudo apt install openssh-server` – Install SSH
- `sudo systemctl status ssh` – Check SSH status
- `sudo systemctl start ssh` – Start SSH service
- `sudo systemctl enable ssh` – Enable SSH at boot

---

## ⚙️ 6️⃣ Additional Important Commands

- `clear` – Clear terminal screen (Shortcut: **Ctrl + L**)
- `head file.txt` – Show first 10 lines
- `tail file.txt` – Show last 10 lines
- `tail -f file.txt` – Live monitoring
- `chmod +x script.sh` – Make file executable
- `ps` – Show running processes
- `top` – Real-time process monitoring
- `ip a` – Show IP address
- `ping google.com` – Check network connectivity

---

## 🎯 Learning Outcome

✔ Understanding Linux file system  
✔ Managing files and directories  
✔ Using wildcards  
✔ Installing packages  
✔ Configuring SSH  
✔ Monitoring processes and network  

---

# 🐳 DevOps Day 2 – Docker

This repository branch contains Day-2 focused on Docker installation, configuration, and container management.

---

## 📌 OBJECTIVE

The objective of Day-2 is to understand Docker fundamentals including:

- Installing Docker on Ubuntu
- Running containers
- Managing images
- Port mapping
- Container lifecycle management

---

## 🛠 STEP 1 – Install Docker

### Update system:
```bash
sudo apt update
```

### Install Docker:
```bash
sudo apt install docker.io -y
```

### Start Docker service:
```bash
sudo systemctl start docker
```

### Enable Docker at boot:
```bash
sudo systemctl enable docker
```

### Verify Docker:
```bash
docker --version
docker info
```

---

## 📦 STEP 2 – Basic Docker Commands

- `docker images` → Shows downloaded Docker images  
- `docker pull nginx` → Download nginx image from Docker Hub  
- `docker run nginx` → Run container from image  
- `docker run -d nginx` → Run container in background mode  
- `docker ps` → Show running containers  
- `docker ps -a` → Show all containers (including stopped)  
- `docker stop <container_id>` → Stop running container  
- `docker rm <container_id>` → Remove container  
- `docker rmi <image_name>` → Remove image  

---

## 🌐 STEP 3 – Run Nginx Container

### Run Nginx with port mapping:
```bash
docker run -d -p 8080:80 nginx
```

### Open browser:
```
http://<server-ip>:8080
```

Example:
```
http://192.168.117.128:8080
```

---

## 📂 STEP 4 – Docker File Structure Understanding

Image → Blueprint  
Container → Running instance of image  
Docker Hub → Online image repository  
Port Mapping → Connect container port to host port  

Example:
```
-p 8080:80
```

Host Port → 8080  
Container Port → 80  

---

## 🎯 LEARNING OUTCOME

✔ Installed Docker successfully  
✔ Understood Docker architecture  
✔ Pulled images from Docker Hub  
✔ Ran containers  
✔ Used port mapping  
✔ Managed container lifecycle  
✔ Practiced basic Docker commands  

---

## 📸 OUTPUT SCREENSHOTS

```
![](Day2/Screenshot%202026-02-10%20145958.png)
![](Day2/Screenshot%202026-02-12%20195410.png)
![](Day2/Screenshot%202026-02-12%20195616.png)
![](Day2/Screenshot%202026-02-12%20195715.png)
```

---

# DEVOPS DAY 3  
## GIT SSH CONFIGURATION AND BRANCH WORKFLOW

Repository: `devops`

---

## Objective

To configure Git with SSH authentication and create a new branch for development work.

---

## Step 1: Git Configuration

```bash
git config --global user.name "VARSHINI1805"
git config --global user.email "varshinisureshkumar224@gmail.com"
git config --list
```

Purpose:  
This ensures that all commits are recorded with correct author details.

---

## Step 2: SSH Key Generation

```bash
ssh-keygen -t ed25519 -C "varshinisureshkumar224@gmail.com"
cat ~/.ssh/id_ed25519.pub
ssh -T git@github.com
```

Added the SSH public key to GitHub under:  
Settings → SSH and GPG Keys  

Authentication was successful.

Purpose:  
SSH allows secure communication between local Ubuntu system and GitHub without using a password each time.

---

## Step 3: Repository Cloning

```bash
git clone git@github.com:VARSHINI1805/devops.git
cd devops
ls -a
```

Confirmed `.git` directory exists, which indicates it is a Git repository.

---

## Step 4: Branch Creation

```bash
git branch
git checkout -b new-branch
git branch
```

The active branch is marked with (*).

---

## Step 5: File Creation and Documentation

```bash
touch documentation.txt
nano documentation.txt
```

Added detailed workflow explanation inside the file.

---

## Conclusion

Git was successfully configured.  
SSH authentication was set up and tested.  
Repository was cloned securely.  
A new branch was created for independent development.  
Basic branch workflow was practiced successfully.

Status: Configuration and branch setup completed successfully.

---

## 📸 OUTPUT SCREENSHOTS

```
![](Day3/Screenshot%202026-02-12%20200945.png)
![](Day3/Screenshot%202026-02-12%20200952.png)
![](Day3/Screenshot%202026-02-12%20201004.png)
![](Day3/Screenshot%202026-02-12%20201010.png)
![](Day3/Screenshot%202026-02-12%20201018.png)
![](Day3/Screenshot%202026-02-12%20201024.png)
```

---

# DEVOPS DAY 4  
## JENKINS CI/CD WITH DOCKER

---

## OVERVIEW

This project demonstrates the implementation of a CI/CD pipeline using Jenkins and Docker.  
The objective is to automate Docker image building and container deployment using Jenkins integrated with GitHub.

---

## STEP 1 – Install Java

```bash
sudo apt update
sudo apt install openjdk-21-jre -y
java -version
```

---

## STEP 2 – Install Jenkins

```bash
sudo wget -O /etc/apt/keyrings/jenkins-keyring.asc \
https://pkg.jenkins.io/debian-stable/jenkins.io-2026.key

echo "deb [signed-by=/etc/apt/keyrings/jenkins-keyring.asc]" \
https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
/etc/apt/sources.list.d/jenkins.list > /dev/null

sudo apt update
sudo apt install jenkins -y
```

---

## STEP 3 – Start Jenkins

```bash
sudo systemctl start jenkins
sudo systemctl enable jenkins
sudo systemctl status jenkins
```

---

## STEP 4 – Unlock Jenkins

```bash
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```

Open browser:
```
http://<server-ip>:8080
```

---

## STEP 5 – Install Docker

```bash
sudo apt install docker.io -y
sudo systemctl start docker
sudo systemctl enable docker

sudo usermod -aG docker jenkins
sudo systemctl restart jenkins

groups jenkins
```

---

## STEP 6 – Create Docker Project Files

Dockerfile:
```dockerfile
FROM nginx:latest
COPY index.html /usr/share/nginx/html/index.html
```

index.html:  
Create an attractive HTML page displaying your name and project details.

---

## STEP 7 – Create Jenkinsfile

Jenkinsfile defines CI/CD pipeline stages:

- Build Docker image
- Stop old container
- Remove old container
- Run new container

---

## STEP 8 – Push Files to GitHub

```bash
git add .
git commit -m "Added Day4 Jenkins CI/CD files"
git push origin day-4
```

---

## STEP 9 – Configure Jenkins Pipeline

Create New Item → Pipeline  

Repository URL:
```
https://github.com/VARSHINI1805/devops.git
```

Branch Specifier:
```
*/day-4
```

Script Path:
```
Day4/Jenkinsfile
```

---

## STEP 10 – Build Pipeline

Click **Build Now**.

Pipeline will automatically:
1. Pull code from GitHub
2. Build Docker image
3. Stop old container
4. Remove old container
5. Run new container

---

## STEP 11 – Access Application

```
http://<server-ip>:5000
```

Example:
```
http://192.168.117.128:5000
```

---

## FINAL OUTCOME

- Jenkins successfully installed
- Docker integrated with Jenkins
- GitHub connected
- CI/CD pipeline automated
- Container deployed automatically
- Website running successfully

---

## LEARNING OUTCOME

- Jenkins installation and configuration
- GitHub integration with Jenkins
- Docker image lifecycle management
- Container deployment automation
- Understanding of CI/CD workflow

---

## 📸 OUTPUT SCREENSHOTS

```
![](Day4/Screenshot%202026-02-13%20111709.png)
![](Day4/Screenshot%202026-02-13%20085223.png)
![](Day4/Screenshot%202026-02-13%20112615.png)
![](Day4/Screenshot%202026-02-13%20085508.png)
![](Day4/Screenshot%202026-02-13%20101133.png)
![](Day4/Screenshot%202026-02-13%20101631.png)
```

---

# 🐳 DevOps Day 2 – Docker 

This repository branch contains  Day-2 focused on Docker installation, configuration, and container management.

------------------------------------------------------------
📌 OBJECTIVE
------------------------------------------------------------

The objective of Day-2 is to understand Docker fundamentals including:

- Installing Docker on Ubuntu
- Running containers
- Managing images
- Port mapping
- Container lifecycle management

------------------------------------------------------------
🛠 STEP 1 – Install Docker
------------------------------------------------------------

Update system:

sudo apt update

Install Docker:

sudo apt install docker.io -y

Start Docker service:

sudo systemctl start docker

Enable Docker at boot:

sudo systemctl enable docker

Verify Docker:

docker --version
docker info

------------------------------------------------------------
📦 STEP 2 – Basic Docker Commands
------------------------------------------------------------

docker images  
→ Shows downloaded Docker images

docker pull nginx  
→ Download nginx image from Docker Hub

docker run nginx  
→ Run container from image

docker run -d nginx  
→ Run container in background mode

docker ps  
→ Show running containers

docker ps -a  
→ Show all containers (including stopped)

docker stop <container_id>  
→ Stop running container

docker rm <container_id>  
→ Remove container

docker rmi <image_name>  
→ Remove image

------------------------------------------------------------
🌐 STEP 3 – Run Nginx Container
------------------------------------------------------------

Run Nginx with port mapping:

docker run -d -p 8080:80 nginx

Open browser:

http://<server-ip>:8080

Example:
http://192.168.117.128:8080

------------------------------------------------------------
📂 STEP 4 – Docker File Structure Understanding
------------------------------------------------------------

Image → Blueprint  
Container → Running instance of image  
Docker Hub → Online image repository  
Port Mapping → Connect container port to host port  

Example:

-p 8080:80  

Host Port → 8080  
Container Port → 80  

------------------------------------------------------------
🎯 LEARNING OUTCOME
------------------------------------------------------------

✔ Installed Docker successfully  
✔ Understood Docker architecture  
✔ Pulled images from Docker Hub  
✔ Ran containers  
✔ Used port mapping  
✔ Managed container lifecycle  
✔ Practiced basic Docker commands  

------------------------------------------------------------
📸 OUTPUT SCREENSHOTS
------------------------------------------------------------

![](Day2/Screenshot%202026-02-10%20145958.png)

![](Day2/Screenshot%202026-02-12%20195410.png)

![](Day2/Screenshot%202026-02-12%20195616.png)

![](Day2/Screenshot%202026-02-12%20195715.png)


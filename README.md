# ☁️ DevOps Day 5 – AWS, EC2 & Terraform


- AWS Account Creation
- EC2 Instance Setup (Windows & Ubuntu)
- Terraform Installation
- Terraform Basic Commands
- Implementation Screenshots

---

## 1️⃣ Create AWS Account

1. Go to https://aws.amazon.com  
2. Click Create an AWS Account  
3. Enter Email & Account Name  
4. Verify Email  
5. Set Root Password  
6. Fill Contact Info (Personal)  
7. Add Debit/Credit Card (Free Tier verification)  
8. Complete Identity Verification (OTP)  
9. Choose Basic Support (Free)  
10. Login → Sign In → Root User  

---

## 2️⃣ Create Windows EC2 Instance

- Go to EC2 → Launch Instance  
- Name: Windows-Server  
- AMI: Windows Server 2022  
- Instance Type: t2.micro  
- Create Key Pair (.pem)  
- Allow RDP (3389) and HTTP (80)  
- Launch & Connect using RDP  

---

## 3️⃣ Create Ubuntu EC2 Instance

- Go to EC2 → Launch Instance  
- Name: Ubuntu-Server  
- AMI: Ubuntu 22.04 LTS  
- Instance Type: t2.micro  
- Create Key Pair (.pem)  
- Allow SSH (22) and HTTP (80)  

---

## 4️⃣ Install Terraform (Ubuntu)

Update system:

sudo apt update -y

Install Terraform:

sudo apt install terraform -y

Check version:

terraform -version

---

## 5️⃣ Terraform Basic Commands

Initialize:

terraform init

Validate:

terraform validate

Plan:

terraform plan

Apply:

terraform apply

Destroy:

terraform destroy

---

# 📸 Screenshots

![](https://raw.githubusercontent.com/VARSHINI1805/devops/day-5/Day5/Screenshot%202026-02-13%20141404.png)

![](https://raw.githubusercontent.com/VARSHINI1805/devops/day-5/Day5/Screenshot%202026-02-13%20155754.png)

![](https://raw.githubusercontent.com/VARSHINI1805/devops/day-5/Day5/Screenshot%202026-02-13%20160634.png)

![](https://raw.githubusercontent.com/VARSHINI1805/devops/day-5/Day5/Screenshot%202026-02-14%20100116.png)

---


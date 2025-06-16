# 🌐 EC2 + ALB + ASG Based Real-World Cloud Deployment

This project demonstrates how to deploy a **highly available and scalable static website** on AWS using core services like EC2, Application Load Balancer (ALB), and Auto Scaling Group (ASG).

---

## 🚀 Tech Stack

- **Amazon EC23** – Hosts the static portfolio website using HTML
- **Application Load Balancer (ALB)** –  Distributes traffic evenly across EC2 instances 
- **Auto Scaling Group (ASG)** – Automatically scales the number of EC2 instances based on health
- **VPC, Subnets, Route Tables** – Provides network isolation and connectivity for AWS resources
- **Security Groups** - Controls inbound and outbound traffic to EC2 and ALB    
- **Target Group Health Checks** –  Monitors instance health and routes traffic only to healthy targets
- **HTML, CSS (static site)** – Portfolio website hosted on EC2 instances
- **GitHub** – Stores website code and project README

---

## 🌍 Live Website

🔗 [https://www.omkarcloudengineer.in/](https://www.omkarcloudengineer.in/)  
(Domain connected via Route 53 and HTTPS secured by CloudFront + ACM)

---

## Network Architecture

![Portfolio Website Digram](Architecture/Architure-digram.png)

---

## 🛠️ Steps to Deploy

### 1. Launch 2 EC2 Instances (Amazon Linux 2)
- Install httpd and git
- Deploy HTML via user data or manually
- Allow port 80 in SG


### 2. Create Target Group
- Type: Instance
- Port: 80
- Register both EC2 instances

### 3. Create Application Load Balancer
- Internet-facing, IPv4
- Listener: HTTP 80
- Add 2 public subnets (AZ-a, AZ-b)
- Attach Security Group (allow 80)
- Link to Target Group

### 4. est ALB URL (should load your website)

### 5. Create Launch Template
- Same AMI as EC2
- t2.micro
- User data: install httpd, clone HTML from GitHub
- Select VPC

### 6. Create Auto Scaling Group
- Use Launch Template
- Add both public subnets
- Attach to ALB + Target Group
- Desired: 2 | Min: 1 | Max: 3

### 7. Test ASG
- Terminate 1 instance
- ASG should auto-launch a new one

 ### 8. Done ✅ Website is live, load balanced, and scalable.
 
---

## 📸 Screenshots 

- **S3 bucket setup**
![cloud front](Images/S3-Bucket.png)

- **CloudFront**
![cloud front](Images/Cloud-front.png)

- **Route53-hosted-zones**
![CloudFront configuration](Images/Route53-hosted-zones.png)

- **SSl-Certificate**
![CloudFront configuration](Images/SSL-Certificate.png)

- **Final-Live-Site**
![Final-Live-Site](Images/Final-Live-Site.png)
  
---

## 🧠 Learnings

- Hands-on with deploying real-time websites on AWS
- Understanding of how Load Balancers and Auto Scaling work
- Managing EC2 instances and health checks

---

## 📬 Contact

Feel free to connect with me on [LinkedIn](https://www.linkedin.com/in/omkar-cloud-engineer/)
---

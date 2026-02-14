# AWS Auto Scaling Implementation with Application Load Balancer

## 📌 Project Overview

This project demonstrates the implementation of a scalable cloud architecture using Amazon Web Services (AWS).  
The infrastructure dynamically adjusts the number of EC2 instances based on CPU utilization to ensure high availability and cost optimization.

The setup includes:
- EC2 Web Server
- Custom AMI Creation
- Launch Template
- Application Load Balancer (ALB)
- Target Group
- Auto Scaling Group (ASG)
- CloudWatch Monitoring
- Stress Testing for CPU Load Simulation

---

## 🎯 Objective

To design and implement an auto-scaling infrastructure that:

- Automatically scales out when CPU usage increases
- Automatically scales in when load decreases
- Distributes traffic across multiple instances
- Ensures high availability and fault tolerance
- Optimizes infrastructure cost

---

## 🏗 Architecture Diagram

Users  
→ Application Load Balancer  
→ Auto Scaling Group  
→ EC2 Instances  
→ CloudWatch Monitoring  

---

## 🛠 Technologies Used

- Amazon EC2
- Amazon Machine Image (AMI)
- Launch Template
- Application Load Balancer
- Target Group
- Auto Scaling Group
- Amazon CloudWatch
- Linux (Amazon Linux 2023)
- Apache HTTP Server
- Stress Tool (CPU Load Testing)

---

## ⚙ Implementation Steps

### 1️⃣ Launch EC2 Instance
- Created EC2 instance (t3.micro)
- Installed Apache Web Server
- Created sample web page

### 2️⃣ Create Custom AMI
- Created AMI from configured instance
- Used AMI for scalable deployment

### 3️⃣ Create Launch Template
- Selected custom AMI
- Instance type: t3.micro
- Attached security group

### 4️⃣ Create Target Group
- Protocol: HTTP
- Port: 80
- Health checks enabled

### 5️⃣ Create Application Load Balancer
- Internet-facing
- Attached target group
- Configured listener on port 80

### 6️⃣ Create Auto Scaling Group
- Min capacity: 1
- Desired capacity: 1
- Max capacity: 3
- Attached Load Balancer
- Enabled scaling policy based on CPU utilization

### 7️⃣ Perform Stress Test
Installed stress tool:

```bash
sudo yum install stress -y
stress --cpu 4 --timeout 300


<img width="1093" height="594" alt="1_L-UzFLgWPrYM9RDczxX0xA" src="https://github.com/user-attachments/assets/d6f62f0e-31da-4ced-974f-10e91431f378" />

<img width="738" height="406" alt="1_QxJ3Fi6yfKSYx_AvlGV8mw" src="https://github.com/user-attachments/assets/91c84ff2-9339-42a5-8da0-fa5aa73517b9" />

<img width="861" height="680" alt="elb-tutorial-architecture-diagram" src="https://github.com/user-attachments/assets/e42a042c-4bbc-43a6-a7e4-4954aa58a1d6" />

# aws-autoscaling-webapp

## 🔗 Live URL
http://MyLoadBalancer-1327879497.ap-south-1.elb.amazonaws.com

## 📌 Project Overview
Deployed a highly available web application on AWS using
EC2, Application Load Balancer, and Auto Scaling Group.
The architecture automatically scales instances based on
CPU usage — no manual intervention needed.

## ⚙️ AWS Services Used

 Service | Purpose |
 Amazon EC2 | Virtual web server |
 Application Load Balancer | Distribute traffic across instances |
 Auto Scaling Group | Auto add/remove instances |
 CloudWatch | Monitor CPU and send alerts |
 Security Groups | Firewall — HTTP/HTTPS traffic |

## 🏗️ Architecture

User Request
↓
Application Load Balancer
↓
Auto Scaling Group
├── EC2 Instance 1
├── EC2 Instance 2  (auto created on high traffic)
└── EC2 Instance 3  (auto created on high traffic)

## 🚀 Steps Followed
1. Launched EC2 instance with Amazon Linux 2023
2. Installed Apache web server via User Data script
3. Created AMI from running EC2 instance
4. Created Target Group for Load Balancer
5. Created Application Load Balancer
6. Created Launch Template using AMI
7. Created Auto Scaling Group — Min:1 Max:3
8. Set scaling policy — CPU threshold 50%
9. Configured CloudWatch alarm for monitoring

## 🔧 User Data Script Used
```bash
#!/bin/bash
yum update -y
yum install -y httpd
systemctl start httpd
systemctl enable httpd
echo '<h1>Hello from AWS EC2 - Auto Scaling Project!</h1>' \
> /var/www/html/index.html


## 💡 What I Learned
- How to launch and configure EC2 instances
- How Application Load Balancer distributes traffic
- How Auto Scaling Group works automatically
- How CloudWatch monitors and alerts on metrics
- High availability architecture on AWS


## 📊 Key Benefits
 High Availability — traffic distributed across instances
 Auto Scaling — handles traffic spikes automatically
 Cost Efficient — scales down when traffic is low
 Monitoring — CloudWatch alerts on high CPU


## 👤 Author
**Jay Sutarsandhiya**
Cloud Computing  | AWS | Azure

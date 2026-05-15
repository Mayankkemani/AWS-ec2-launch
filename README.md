# AWS Day 2: EC2 Instance Launch 🚀

## Project Overview
Launched my first AWS EC2 instance using IAM user instead of root account. Deployed Apache web server via User Data script.

URL: http://15.206.79.233

## Architecture
IAM User `mayani-admin` → EC2 `t3.micro` → Security Group → Apache → Public Website

## Tech Stack
- **AWS Services:** EC2, IAM, VPC, Security Groups
- **OS:** Amazon Linux 2023
- **Web Server:** Apache httpd
- **Region:** ap-south-1 Mumbai

## Security Implementation
1. Root account locked with MFA
2. IAM user with AdministratorAccess for learning
3. SSH access restricted to My IP only
4. HTTP open for public website
5. Key pair `mayank-aws-key.pem` stored securely

## User Data Script
```bash
#!/bin/bash
yum update -y
yum install -y httpd
systemctl start httpd
systemctl enable httpd
echo "<h1>Mayank Kemani - AWS Cloud Engineer</h1><h2>First EC2 Live from Mumbai ap-south-1</h2><p>IAM User: mayani-admin | Instance: t3.micro | Cost: ₹0</p><p>Data Center to Cloud Journey Started 🚀</p><p>Launched: $(date)</p>" > /var/www/html/index.html

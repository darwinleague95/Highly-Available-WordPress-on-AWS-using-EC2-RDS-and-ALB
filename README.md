# Highly-Available-WordPress-on-AWS-using-EC2-RDS-and-ALB
Scalable via Auto Scaling Group  Redundant via Multi-AZ RDS (MySQL)  Secure and optimized with Application Load Balancer (ALB)

🧩 Key Components

1. VPC with Public and Private Subnets


2. EC2 instances (Auto Scaling Group) hosting WordPress


3. RDS MySQL Database in Multi-AZ


4. Application Load Balancer (ALB) to distribute traffic


5. S3 Bucket for Media Storage (Optional)


6. Route 53 for DNS (Optional)


✅ Step-by-Step Setup
1️⃣ VPC Setup
Create VPC (10.0.0.0/16)

Public Subnets (for ALB)

Private Subnets (for EC2 and RDS)

Create and attach Internet Gateway

Setup NAT Gateway for private subnet outbound internet access

2️⃣ RDS MySQL
Launch Multi-AZ MySQL RDS in private subnet

Enable automatic backups

Note the Endpoint, Username, Password

3️⃣ EC2 Instances
Install Apache, PHP, WordPress

Connect to RDS MySQL for database

Store media optionally in S3 bucket

4️⃣ Create AMI
Create an AMI of the configured EC2 instance

Use this in the Auto Scaling Group

5️⃣ Application Load Balancer
Deploy ALB in public subnet

Configure Target Group for EC2 Auto Scaling Group

Attach SSL (via ACM certificate if desired)

6️⃣ Auto Scaling Group
Launch EC2 instances across multiple AZs

Link to ALB Target Group

Define scaling policies (CPU, Network In, etc.)

7️⃣ Security
ALB Security Group: Allow HTTP/HTTPS from the world

EC2 Security Group: Allow only ALB traffic

RDS Security Group: Allow EC2 security group

8️⃣ Optional Enhancements
Use CloudFront as CDN

Use S3 + CloudFront for WordPress media

Integrate with Route 53 for custom domain

📌 Deliverables
✅ Architecture Diagram

✅ AWS Deployment

✅ GitHub README.md documentation

✅ Optional: Terraform/IaC automation

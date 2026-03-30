📌 AWS Backup Setup for EC2 and RDS
📖 Project Overview

This project demonstrates how to configure a centralized backup system using AWS Backup to protect cloud resources from data loss.

The setup includes:

Amazon EC2 instance (with Apache web server)
Amazon RDS instance (MySQL database)

The goal is to ensure data recovery and fault tolerance in case of system failure.

⚠️ Problem Statement

A system failure previously caused data loss due to missing backup policies.
To solve this, a centralized AWS Backup strategy is implemented.

🏗️ Architecture Diagram
EC2 Instance Running
        │
        │
RDS Database Running
        │
        │
AWS Backup Plan
        │
        │
Backup Jobs Executed
        │
        │
Recovery Points Stored in Backup Vault
🔄 System Flow
User
 │
 │
 AWS Console
 │
 ├── EC2 Instance
 │      └── Apache Web Server + Sample Data
 │
 ├── RDS MySQL Database
 │      └── Test Table + Data
 │
 └── AWS Backup
        │
        ├── Backup Plan
        ├── Backup Vault
        └── Recovery Points
🚀 Implementation Steps
🔹 1. Infrastructure Setup
✅ EC2 Instance Setup

Service: Amazon EC2

Steps:

Launch EC2 instance (Ubuntu / Amazon Linux 2)
Configure Security Group (SG)
Connect using SSH
Install Apache
sudo apt update
sudo apt install apache2 -y
Create sample data
echo "AWS Backup Demo Project" > /var/www/html/index.html
✅ RDS Setup

Service: Amazon RDS

Steps:

Create MySQL database
Configure DB access
Add sample data
CREATE DATABASE testdb;
USE testdb;

CREATE TABLE users (
    id INT PRIMARY KEY,
    name VARCHAR(50)
);

INSERT INTO users VALUES (1, 'Test User');
🔹 2. AWS Backup Setup
✅ Step 1: Create Backup Vault
Go to AWS Backup
Click Backup Vaults → Create Vault
Name: project-backup-vault
✅ Step 2: Create Backup Plan
Go to Backup Plans → Create Plan
Name: project-backup-plan

Configuration:

Frequency: Daily
Retention: 7 days
Vault: project-backup-vault
✅ Step 3: Assign Resources
Open backup plan
Click Assign Resources

Select:

EC2 instance
RDS database

IAM Role:

AWSBackupDefaultServiceRole
🔹 3. Create Recovery Point (On-Demand Backup)
✅ Step-by-Step

1️⃣ Click Create On-Demand Backup

2️⃣ Fill details:

Field	Value
Resource Type	EC2 / RDS
Resource ID	Instance ID / DB
Backup Vault	project-backup-vault
IAM Role	AWSBackupDefaultServiceRole
Retention	7 days

3️⃣ Click Create Backup

🔹 4. Verify Backup
✅ Check Backup Jobs

Go to:

AWS Backup → Jobs → Backup Jobs

Status:

Running → Completed
✅ Check Recovery Points

Go to:

AWS Backup → Vaults → project-backup-vault

You will see:

EC2 Recovery Point
RDS Recovery Point
📸 Screenshots Required

Include:

🖥️ Infrastructure
EC2 running
RDS running
🔐 Backup Setup
Backup Plan
Backup Vault
📦 Results
Backup Jobs
Recovery Points
📊 Key Configuration Details
Setting	Value
Backup Vault	project-backup-vault
Backup Plan	project-backup-plan
Frequency	Daily
Retention	7 Days
Resources	EC2 + RDS
IAM Role	AWSBackupDefaultServiceRole
🛠️ Services Used
Amazon EC2
Amazon RDS
AWS Backup
AWS Management Console
⚡ Issues Faced & Solutions
❌ No Recovery Points

Reason: No backup triggered
✔ Solution: Create on-demand backup

❌ Permission Error

Reason: Wrong IAM role
✔ Solution: Use AWSBackupDefaultServiceRole

❌ EC2 Not Visible

Reason: Wrong region selected
✔ Solution: Switch to correct AWS region

✅ Conclusion

The project successfully implemented a centralized backup solution using AWS Backup.

✔ Automated backups
✔ Secure storage using vault
✔ Recovery points created for EC2 and RDS

This ensures:

Data protection
Disaster recovery
Business continuity
⭐ Future Improvements
Enable cross-region backup
Add monitoring with CloudWatch
Automate using Terraform
🙌 Author

Your Name

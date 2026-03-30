📦 AWS Backup Setup for EC2 and RDS
📌 Project Title

Centralized Backup Strategy using AWS Backup for EC2 and RDS

📖 Introduction

In this project, a backup system was implemented using Amazon Web Services to protect cloud resources from data loss.

The solution uses AWS Backup, a centralized service that automates and manages backups across AWS resources.

The main objective of this project is:

To create a secure backup vault
To configure a backup plan
To protect resources like:
Amazon EC2 (Virtual Server)
Amazon RDS (Database)

This ensures data recovery in case of system failure or accidental deletion.

🏗️ Architecture Diagram (Flow)
<img width="1024" height="1536" alt="image" src="https://github.com/user-attachments/assets/1e8a0e19-aaf7-48c6-b16a-d113c9967b99" />


⚙️ Step-by-Step Implementation
1️⃣ Create Security Group
Navigate to EC2 Dashboard
Go to Security Groups
Click Create Security Group
Add rules:
HTTP (Port 80)
SSH (Port 22)
Save the Security Group

2️⃣ Launch EC2 Instance
Go to EC2 Dashboard
Click Launch Instance
Configure:
AMI: Amazon Linux
Instance Type: t2.micro
Attach created Security Group
Install Apache:
sudo yum update -y
sudo yum install httpd -y
sudo systemctl start httpd

3️⃣ Create RDS Database
Go to RDS Dashboard
Click Create Database
Select:
Engine: MySQL
Instance Type: Free tier
Configure DB name and credentials
Launch database

4️⃣ Create Backup Vault
Go to AWS Backup
Click Backup Vaults → Create Vault
Name: project-backup-vault
Use default encryption

✅ Backup Vault created successfully

5️⃣ Create Backup Plan
Navigate to Backup Plans
Click Create Backup Plan
Choose Build a new plan
Name: project-backup-plan

Configure:
Backup Frequency: Daily
Retention: 7 Days
Destination Vault: project-backup-vault

6️⃣ Assign Resources
Open Backup Plan
Click Assign Resources

Select:

EC2 Instance
RDS Database

IAM Role:

AWSBackupDefaultServiceRole

7️⃣ Create On-Demand Backup
Go to Backup Vault → project-backup-vault
Click Create On-Demand Backup

Fill details:

Resource Type: EC2 / RDS
Resource ID: Select instance
Vault: project-backup-vault
IAM Role: Default
Retention: 7 days

Click Create Backup

8️⃣ Monitor Backup Jobs
Navigate to:
AWS Backup → Jobs → Backup Jobs

Status:

Running → Completed ✅
9️⃣ Verify Recovery Points
Go to:
AWS Backup → Vaults → project-backup-vault

You will see:

EC2 Recovery Point
RDS Recovery Point
📊 Key Configuration
Setting	Value
Backup Vault	project-backup-vault
Backup Plan	project-backup-plan
Frequency	Daily
Retention	7 Days
Resources	EC2 + RDS
IAM Role	AWSBackupDefaultServiceRole
🛠️ Tools & Services Used
AWS Backup – Backup management
Amazon EC2 – Virtual server
Amazon RDS – Database
IAM – Role management
⚠️ Issues & Solutions
❌ Issue 1: No Recovery Points

Cause: No backup executed
✅ Solution: Create on-demand backup

❌ Issue 2: Permission Error

Cause: Incorrect IAM role
✅ Solution: Use AWSBackupDefaultServiceRole

❌ Issue 3: Resource Not Visible

Cause: Wrong region selected
✅ Solution: Select correct AWS region

📸 Screenshots Required

Include the following screenshots:

EC2 Instance Running
RDS Database Running
Backup Plan
Backup Jobs Status
Backup Vault with Recovery Points
✅ Conclusion

The project successfully demonstrates how to use AWS Backup for centralized data protection.

Backup vault and plan were created
EC2 and RDS were protected
Recovery points were generated

This setup ensures data safety, automation, and easy recovery in cloud environments.

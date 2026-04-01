<h1 align="center">📦 AWS Backup Plan for EC2 and RDS</h1>

<h3 align="center">Centralized Backup Strategy using AWS Backup</h3>

<hr>

<h2>📌 Project Overview</h2>

<p>
This project demonstrates how to implement a <b>centralized backup solution</b> using AWS Backup to protect critical cloud resources such as EC2 instances and RDS databases.
</p>

<p>
The solution ensures <b>data durability, automated backups, and quick recovery</b> in case of system failures or data loss incidents.
</p>

<hr>

<h2>⚠️ Scenario</h2>

<p>
A recent system failure caused significant data loss due to the absence of backup policies.
Management has mandated the implementation of a <b>centralized AWS Backup strategy</b> to prevent future data loss.
</p>

<hr>

<h2>🎯 Objective</h2>

<ul>
  <li>Configure AWS Backup for automated backups</li>
  <li>Protect EC2 and RDS resources</li>
  <li>Enable recovery through backup vaults</li>
  <li>Understand backup lifecycle and retention policies</li>
</ul>

<hr>

<h2>🛠️ Services Used</h2>

<ul>
  <li>AWS EC2 (Elastic Compute Cloud)</li>
  <li>AWS RDS (Relational Database Service)</li>
  <li>AWS Backup</li>
  <li>AWS IAM (Identity and Access Management)</li>
</ul>

<hr>

<h2>🏗️ Architecture</h2>

<pre>
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
Recovery Points stored in Backup Vault
</pre>

<hr>

<h2>🚀 Project Implementation</h2>

<h3>1️⃣ Infrastructure Setup</h3>

<h4>🔹 EC2 Instance</h4>
<ul>
  <li>Launched EC2 instance using Amazon Linux 2 / Ubuntu</li>
  <li>Installed web server (Apache/Nginx)</li>
  <li>Created sample data (HTML file / text file)</li>
</ul>

<h4>🔹 RDS Instance</h4>
<ul>
  <li>Launched RDS (MySQL / PostgreSQL)</li>
  <li>Created test database</li>
  <li>Inserted sample records into a table</li>
</ul>

<hr>

<h3>2️⃣ AWS Backup Configuration</h3>

<ul>
  <li>Created a <b>Backup Vault</b> to securely store backups</li>
  <li>Configured a <b>Backup Plan</b> with rules:</li>
  <ul>
    <li>Backup Frequency (Daily)</li>
    <li>Retention Period (e.g., 7–30 days)</li>
    <li>Lifecycle Policies</li>
  </ul>
  <li>Assigned resources:</li>
  <ul>
    <li>EC2 Instance</li>
    <li>RDS Database</li>
  </ul>
</ul>

<hr>

<h3>3️⃣ Validation & Testing</h3>

<ul>
  <li>Triggered <b>on-demand backup</b></li>
  <li>Verified backup jobs execution</li>
  <li>Checked recovery points in backup vault</li>
</ul>

<hr>

<h2>📊 Key Configuration Details</h2>

<table border="1" cellpadding="8">
  <tr>
    <th>Component</th>
    <th>Configuration</th>
  </tr>
  <tr>
    <td>Backup Frequency</td>
    <td>Daily</td>
  </tr>
  <tr>
    <td>Retention Period</td>
    <td>7–30 Days</td>
  </tr>
  <tr>
    <td>Backup Vault</td>
    <td>Default / Custom Vault</td>
  </tr>
  <tr>
    <td>Resources</td>
    <td>EC2 + RDS</td>
  </tr>
</table>

<hr>

<h2>📸 Deliverables</h2>

<ul>
  <li>EC2 instance running</li>
  <img width="940" height="432" alt="image" src="https://github.com/user-attachments/assets/05c022be-a1ec-47b1-939a-7a90297cebc6" />

  <li>RDS instance running</li>
  <img width="940" height="435" alt="image" src="https://github.com/user-attachments/assets/867c15eb-0dd2-473a-8f33-cb6a518609da" />

  <li>Backup plan configuration</li>
  <img width="940" height="462" alt="image" src="https://github.com/user-attachments/assets/cf396a83-b328-4646-a7b5-5c62d3b3c7d7" />

  <li>Backup jobs status</li>
  <img width="940" height="433" alt="image" src="https://github.com/user-attachments/assets/de25c0f1-57e5-4766-add7-26e1cbbb0c3f" />

  <li>Recovery points in backup vault</li>
  <img width="940" height="410" alt="image" src="https://github.com/user-attachments/assets/1ee5c805-f7cc-45f4-b280-be78ef7fc1e9" />

</ul>

<hr>

<h2>⚙️ Tools & Console Sections Used</h2>

<ul>
  <li>AWS Management Console</li>
  <li>AWS Backup Dashboard</li>
  <li>EC2 Dashboard</li>
  <li>RDS Dashboard</li>
  <li>IAM Roles & Policies</li>
</ul>

<hr>

<h2>⚠️ Challenges & Solutions</h2>

<ul>
  <li><b>Issue:</b> Backup role permissions missing  
      <br><b>Solution:</b> Attached required IAM policies</li>

  <li><b>Issue:</b> Resources not detected in backup plan  
      <br><b>Solution:</b> Used proper tagging or resource ID</li>

  <li><b>Issue:</b> Backup job failed initially  
      <br><b>Solution:</b> Verified region and service permissions</li>
</ul>

<hr>

<h2>✅ Conclusion</h2>

<p>
This project successfully demonstrates how to implement a <b>centralized and automated backup strategy</b> using AWS Backup.
It ensures data protection, improves reliability, and enables quick recovery during failures.
</p>

<hr>

<h2>📚 Future Improvements</h2>

<ul>
  <li>Enable cross-region backup</li>
  <li>Implement backup monitoring with CloudWatch</li>
  <li>Add automated recovery testing</li>
</ul>

<hr>

<h3 align="center">✨ Developed for Learning & Cloud Practice</h3>

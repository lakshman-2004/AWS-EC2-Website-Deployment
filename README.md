# AWS-EC2-Website-Deployment

This project demonstrates how to deploy a static website on **Amazon Web Services (AWS)** using an **EC2 virtual server and Apache web server.**
It follows the same approach used by real companies to host websites on cloud infrastructure.

**🚀 What This Project Does**
In this project, we:
> Create an **EC2 virtual server** on AWS
> Install and configure the **Apache web server**
> Deploy a website from a **GitHub repository**
> Make the website **publicly accessible** via the internet

**🛠️ Technologies Used**
- AWS EC2 – Virtual cloud server
Amazon Linux 2 – Operating system
Apache (httpd) – Web server
Git & GitHub – Source code management
SSH – Secure server access

📌 Prerequisites
Before starting, make sure you have:
An AWS account
A GitHub repository containing website files

Basic knowledge of Linux commands

🧭 Step-by-Step Deployment Process
STEP 1: Create an AWS Account & Select a Region
What is AWS?
Amazon Web Services (AWS) is a cloud platform that provides computing, storage, networking, and security services on a pay-as-you-go basis.

Create AWS Account
Open: ```
https://aws.amazon.com 
```
Click Create an AWS Account
Enter:
Root email
Strong password
Account name
Choose Personal or Professional
Enter billing details (required for verification)
Verify phone number (OTP)
Select Basic Support Plan (Free)

✅ Account setup completed
STEP 2: Sign in to AWS Console
Visit: ``` 
https://aws.amazon.com/console/ 
```
Click Sign In to Console
Select Root User
Enter your email and password
You are now inside the AWS Management Console.

STEP 3: Launch an EC2 Instance (Virtual Server)
Search for EC2 → Click Launch Instance
Configure instance:
Name: my-website-server
AMI: Amazon Linux 2 (Free Tier)
Instance Type: t2.micro (Free Tier)
Key Pair
Create new key pair
Name: website-key
Download .pem file (keep it safe)
Security Group (Firewall Rules)
SSH (22) → My IP
HTTP (80) → Anywhere
HTTPS (443) → Anywhere

Click Launch Instance

✅ EC2 server is running
STEP 4: Connect to EC2 Instance
Right-click on your EC2 instance
Click Connect
Choose EC2 Instance Connect or SSH client
Connect to the server terminal

STEP 5: Install Apache Web Server
Run the following commands:
```
sudo yum update -y
sudo yum install httpd -y
sudo systemctl start httpd
sudo systemctl enable httpd
```
What this does:
Updates the system
Installs Apache (httpd)
Starts the web server
Enables Apache to start on reboot

STEP 6: Deploy Website Files from GitHub
Install Git
``` 
sudo yum install -y git
```

Clone Your Repository
``` 
git clone https://github.com/thebugbounter/preet-watches.git /var/www/html/
```

Set Correct Permissions
```
sudo chown -R apache:apache /var/www/html
sudo chmod -R 755 /var/www/html
```
These permissions allow Apache to read and serve website files securely.

STEP 7: Access Your Website
Go to EC2 Dashboard
Copy the Public IPv4 DNS or Public IP
Open it in your browser:
``` 
http://<your-public-ip>
```


🎉 Your website is now live on AWS!

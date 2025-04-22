# 3-Tier Web Application on AWS 🚀

[![AWS](https://img.shields.io/badge/AWS-CloudFormation-orange?logo=amazonaws)](https://aws.amazon.com/cloudformation/) 
[![Infrastructure as Code](https://img.shields.io/badge/IaC-CloudFormation-blueviolet)](https://aws.amazon.com/cloudformation/) 
[![Built with Flask](https://img.shields.io/badge/Backend-Flask-lightgrey?logo=flask)](https://flask.palletsprojects.com/) 
[![Database](https://img.shields.io/badge/Database-RDS_MySQL-blue?logo=mysql)](https://aws.amazon.com/rds/) 
[![Deployed](https://img.shields.io/badge/Deployed-Yes-success)](#) 
[![License](https://img.shields.io/badge/License-MIT-yellow)](LICENSE)

## 📚 Table of Contents
- [Architecture Overview](#architecture-overview)
- [Project Status](#project-status)
- [Project Structure](#project-structure)
- [Technologies Used](#technologies-used)
- [Prerequisites](#prerequisites)
- [Testing](#testing)
- [Project Screenshot](#project-screenshot)
- [Notes](#notes)
- [Upcoming Enhancements](#upcoming-enhancements)
- [Deployment Screenshots](#deployment-screenshots)
- [RDS Tier](#rds-tier)
- [App Tier](#app-tier)
- [Web Tier](#web-tier)
  
This project demonstrates a fully functional 3-tier web application infrastructure deployed on AWS using CloudFormation.

## Architecture Overview
<p align="center">
  <img src="assets/architecture/architecture.png" alt="Architecture Diagram">
</p>

```
      [Web Tier - Public EC2 with Apache]
                  |
     [App Tier - Private EC2 with Flask]
                  |
 [Database Tier - RDS MySQL in Private Subnet]

```
## ✅ Project Status
- ✅ Database Tier (RDS) deployed successfully
- ✅ App Tier (Flask App) EC2 instance configured
- ✅ Web Tier (Apache) EC2 instance live with HTML page
- ⏳ Reverse Proxy from Apache to Flask App

## 📁 Project Structure
```
cloudformation-templates/
├── db-tier.yaml
├── app-tier.yaml
└── web-tier.yaml

assets/
├── architecture/
│   └── architecture.png
└── screenshots/
    └── screenshot.png
```

## 🔧 Technologies Used
- AWS CloudFormation
- Amazon EC2
- Amazon RDS (MySQL)
- Flask (Python Web Framework)
- Apache Web Server (httpd)

## 📌 Prerequisites
- AWS CLI Configured
- Valid SSH Key Pair (e.g., `bus.key` on your local machine)
- Python 3 & Flask installed (for App Tier)

## 🧪 Testing
To test the app end-to-end:

1. SSH into the Web Tier:
   ```bash
   ssh -i ~/Desktop/ec2-key ec2-user@<Web-Tier-Public-IP>
   ```

2. Confirm Apache is running:
   ```bash
   curl http://localhost
   ```

3. Set up reverse proxy to App Tier (Private IP on port 8080) by editing the Apache config:
   ```bash
  sudo nano /etc/httpd/conf.d/proxy.conf


4. Access from browser:
   ```
   http://<Web-Tier-Public-IP>
   ```

## 📸 Deployment Screenshots

### RDS Tier – Database Layer
This section captures the deployment of the **Database Tier** using AWS CloudFormation. The screenshots include the RDS MySQL instance creation process, event logs, output values, deployed resources, and the associated CloudFormation template.  
<div align="center">
  <img src="assets/RDS%20test%20completion.JPG" width="300"/>
  <img src="assets/RDS-Tier%20Event%20and%20completion.JPG" width="300"/>
  <img src="assets/RDS-Tier%20creating%20in%20progess.JPG" width="300"/>
  <img src="assets/RDS-Tier%20outputs.JPG" width="300"/>
  <img src="assets/RDS-Tier%20resource.JPG" width="300"/>
  <img src="assets/RDS-Tier%20template.JPG" width="300"/>
</div>

### App Tier – Backend Flask API  
These screenshots highlight the **Application Tier** deployment. You’ll see the creation of the private EC2 instance running a Flask application, the CloudFormation template used, and the testing process to confirm backend functionality.  
<div align="center">
  <img src="assets/app-tier%20completed%20and%20event.JPG" width="300"/>
  <img src="assets/app-tier%20creating%20process.JPG" width="300"/>
  <img src="assets/app-tier%20resource.JPG" width="300"/>
  <img src="assets/app-tier%20template.JPG" width="300"/>
  <img src="assets/app-tier%20testing.JPG" width="300"/>
</div>

### Web Tier – Apache Frontend  
This section showcases the **Web Tier**, where a public EC2 instance is launched and configured with Apache. The images demonstrate the deployment events, resources created, and successful integration with the other tiers.  
<div align="center">
  <img src="assets/web%203-tier%20completed.JPG" width="300"/>
  <img src="assets/web%203-tier%20completing%20process.JPG" width="300"/>
  <img src="assets/web%203-tier%20event.JPG" width="300"/>
  <img src="assets/web%203-tier%20resource.JPG" width="300"/>
  <img src="assets/web%203-tier%20template.JPG" width="300"/>
  <img src="assets/web%203-tier.JPG" width="300"/>
</div>

## 📌 Notes
- Use `python3 -m http.server 8080` on App Tier for quick testing

## 🔜 Upcoming Enhancements
Enable HTTPS with Let's Encrypt
Use Route 53 for DNS management
Add Auto Scaling & Load Balancing

---

Contributions welcome! ⭐
---

**Author:** Emma – AWS Junior Solution Architect

[![LinkedIn](https://img.shields.io/badge/LinkedIn-blue?logo=linkedin&style=flat-square)](https://www.linkedin.com/in/cloud-architect-emma)  
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow?style=flat-square)](LICENSE)

---

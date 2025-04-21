# 3-Tier Web Application on AWS 🚀
## 🚀 3-Tier Web App on AWS

[![AWS](https://img.shields.io/badge/AWS-CloudFormation-orange?logo=amazonaws)](https://aws.amazon.com/cloudformation/)
[![Infrastructure as Code](https://img.shields.io/badge/IaC-CloudFormation-blueviolet)](https://aws.amazon.com/cloudformation/)
[![Built with Flask](https://img.shields.io/badge/Backend-Flask-lightgrey?logo=flask)](https://flask.palletsprojects.com/)
[![Database](https://img.shields.io/badge/Database-RDS_MySQL-blue?logo=mysql)](https://aws.amazon.com/rds/)
[![Deployed](https://img.shields.io/badge/Deployed-Yes-success)](#)
[![License](https://img.shields.io/badge/License-MIT-yellow)](LICENSE)

This project demonstrates a fully functional 3-tier web application infrastructure deployed on AWS using CloudFormation.

## 🏗️ Architecture Overview

```
             [CloudFront - Optional Layer]
                      |
          [Web Tier - Public EC2 with Apache]
                      |
         [App Tier - Private EC2 with Flask]
                      |
     [Database Tier - RDS MySQL in Private Subnet]
```

## ✅ Project Status
- [x] Database Tier (RDS) deployed successfully
- [x] App Tier (Flask App) EC2 instance configured
- [x] Web Tier (Apache) EC2 instance live with HTML page
- [ ] Reverse Proxy from Apache to Flask App
- [ ] CloudFront configuration (Optional)

## 📁 Project Structure
```
cloudformation-templates/
├── db-tier.yaml
├── app-tier.yaml
└── web-tier.yaml
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
   ssh -i ~/Desktop/bus.key ec2-user@<Web-Tier-Public-IP>
   ```

2. Confirm Apache is running:
   ```bash
   curl http://localhost
   ```

3. Set up reverse proxy to App Tier (Private IP on port 8080).

4. Access from browser:
   ```
   http://<Web-Tier-Public-IP>
   ```

## 📌 Notes
- Use `python3 -m http.server 8080` on App Tier for quick testing
- CloudFront distribution can improve performance and add HTTPS

## 🔜 Upcoming Enhancements
- Enable HTTPS with Let's Encrypt or CloudFront
- Use Route 53 for DNS management
- Add Auto Scaling & Load Balancing

---

Contributions welcome! ⭐

---

**Author:** Emma - AWS Junior Solution Architect

[![LinkedIn](https://img.shields.io/badge/LinkedIn-blue)](https://www.linkedin.com/in/cloud-architect-emma)

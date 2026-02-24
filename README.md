# aws-serverless-feedback-system

# 🚀 AWS Serverless Feedback Collection System

A fully serverless feedback collection application built using AWS services with automated CI/CD deployment using GitHub Actions.

This project demonstrates an end-to-end event-driven cloud architecture using production-style AWS best practices.

---

## 🏗 Architecture Overview

**Frontend**
- Hosted on Amazon S3
- Delivered globally via Amazon CloudFront

**Backend**
- Amazon API Gateway (REST API)
- AWS Lambda (Python)
- Amazon DynamoDB (NoSQL database)
- Amazon S3 (PDF storage)
- Amazon SES (Email notifications)

**CI/CD**
- GitHub Actions
- Automatic S3 sync
- Automatic CloudFront cache invalidation

---

## 📂 Project Structure
├── .github/
│ └── workflows/
│ └── deploy.yml # CI/CD pipeline for frontend deployment
│
├── frontend/
│ └── index.html # Static UI (HTML, CSS, JS)
│
├── lambda/
│ └── SubmitFeedBackFunction.py # Lambda backend logic
│
└── README.md


---

## 🔄 Application Flow

1. User accesses the UI via CloudFront.
2. Static content is served from S3.
3. Feedback form sends POST request to API Gateway.
4. API Gateway triggers AWS Lambda.
5. Lambda:
   - Stores feedback in DynamoDB
   - Uploads PDF attachment to S3
   - Generates a pre-signed URL
   - Sends formatted HTML email via SES
6. Response is returned to frontend.

---

## ⚙️ Key Features

- Fully serverless architecture
- Secure S3 access using Origin Access Control (OAC)
- DynamoDB integration for structured data storage
- Pre-signed URL generation for secure file access
- Email notifications via Amazon SES
- CI/CD automation with GitHub Actions
- CloudFront cache invalidation after deployment
- CORS handling for API requests
- CloudWatch logging for monitoring and debugging

---

## 🔐 AWS Services Used

- Amazon S3
- Amazon CloudFront
- Amazon API Gateway
- AWS Lambda (Python)
- Amazon DynamoDB
- Amazon SES
- AWS IAM
- Amazon CloudWatch

---

## 🚀 CI/CD Pipeline

GitHub Actions workflow:

- Triggers on push to `main`
- Configures AWS credentials securely
- Syncs frontend folder to S3
- Invalidates CloudFront cache

This ensures automatic deployment of UI updates.

---

## 🧠 Technical Challenges Solved

- DynamoDB validation errors
- Environment variable misconfiguration
- CloudFront caching issues
- CORS configuration
- SES sandbox restrictions
- IAM permission debugging
- GitHub Actions AWS authentication setup

---

## 📈 What This Project Demonstrates

- Event-driven architecture design
- Serverless backend implementation
- Multi-service AWS integration
- CI/CD automation
- Production-style cloud debugging
- Infrastructure troubleshooting
- Secure file handling in cloud environments

---

## 🎯 Future Improvements

- Add authentication using Amazon Cognito
- Move SES to production mode
- Add custom domain + ACM certificate
- Implement infrastructure as code (Terraform / CloudFormation)
- Add monitoring dashboards and alarms
- Add input validation and rate limiting

---

## 👨‍💻 Author

Praveen Pandarinathan  
  

---

## 📬 Contact

Feel free to connect with me on LinkedIn to discuss cloud architecture and serverless systems.
https://www.linkedin.com/in/praveen-p-0382b8200/

Thanks for reading :)

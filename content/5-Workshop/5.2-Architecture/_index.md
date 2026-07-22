---
title: "System Architecture"
date: 2026-07-17 
weight: 2
chapter: false
pre: " <b> 5.2. </b> "
---

#### Project Overview

**MoMoPay AWS** is a secure, scalable payment platform that integrates with MoMo, designed for merchants and businesses in Vietnam. The system supports payment URL generation, webhook processing, transaction management, real-time notifications, and admin dashboards.

Instead of using traditional servers, MoMoPay AWS leverages a fully **Serverless Architecture** on Amazon Web Services (AWS). This approach reduces operational costs, enables automatic scaling based on transaction volume, and ensures high availability without managing infrastructure.

#### System Architecture

MoMoPay AWS follows the **Frontend – API – Serverless Backend – Database** pattern, where each AWS service plays a specific role in the payment flow.

+ **Frontend (React / Electron)** is hosted on **Amazon S3** and delivered globally via **Amazon CloudFront** for fast loading.
+ **Amazon API Gateway** receives and routes API requests to **AWS Lambda Functions**.
+ **Amazon Cognito** handles user authentication and authorization (Merchant & Admin).
+ **AWS Lambda** processes core payment logic: creating Payment URLs, handling MoMo webhooks, updating transaction status, etc.
+ **Amazon DynamoDB** stores transaction records, webhook logs, and audit data with high scalability.
+ **Amazon S3** stores payment receipts, invoices, and other documents.
+ **Amazon SQS** manages asynchronous processing and retry mechanisms.
+ **Amazon SNS** sends real-time notifications (Email / SMS) to merchants and customers.
+ **Amazon CloudWatch + X-Ray** monitors system performance, logs, and errors.
+ **AWS Serverless Application Model (SAM)** is used to define and deploy the entire infrastructure as code.

#### System Workflow

1. Merchants access the dashboard through **Amazon CloudFront**.
2. Users (Merchants) authenticate via **Amazon Cognito** and receive a JWT token.
3. The frontend sends requests to **Amazon API Gateway**.
4. API Gateway validates the token and triggers the corresponding **AWS Lambda Function**.
5. Lambda functions interact with **Amazon DynamoDB** to record transactions.
6. When a customer initiates payment, Lambda generates a Payment URL and returns it to the frontend.
7. MoMo sends IPN Webhook to the system → processed by Lambda and stored in DynamoDB.
8. **Amazon SQS** handles retry logic for failed webhooks.
9. **Amazon SNS** sends confirmation notifications to merchants and customers.
10. All activities are monitored in real-time by **Amazon CloudWatch**.

#### Workshop Objectives

In this workshop, you will build and deploy a complete Serverless payment system integrated with MoMo on AWS:

+ Deploy the frontend using **Amazon S3** and **Amazon CloudFront**.
+ Build secure REST APIs with **Amazon API Gateway** and **AWS Lambda**.
+ Store transaction data using **Amazon DynamoDB**.
+ Configure authentication and authorization with **Amazon Cognito**.
+ Handle MoMo Webhook securely with signature verification.
+ Implement retry mechanism using **Amazon SQS**.
+ Send notifications via **Amazon SNS**.
+ Monitor the system with **Amazon CloudWatch**.
+ Deploy the entire infrastructure using **AWS SAM** (Infrastructure as Code).

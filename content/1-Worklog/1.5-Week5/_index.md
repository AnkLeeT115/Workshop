---
title: "Week 5 Worklog"
date: 2024-01-01
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

# Week 5 Worklog

## Week 5 Objectives

- Understand **Microservices Architecture**, **Cloud-Native Architecture**, and **Serverless** model in the context of a payment system.
- Design a serverless payment backend integrated with MoMo.
- Practice building scalable payment processing, automated pipelines, and monitoring solutions using AWS services.

## Tasks Completed This Week

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | - Study the migration from **Monolithic** to **Microservices Architecture** for payment systems.<br>- Analyze how to divide the payment system into independent services:<br>&emsp;+ Payment Initiation Service<br>&emsp;+ Webhook Processing Service<br>&emsp;+ Transaction Management Service<br>&emsp;+ Notification Service | 18/05/2026 | 18/05/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 3 | - Design a **Serverless Payment Backend Architecture**.<br>- Practice using key AWS services:<br>&emsp;+ AWS Lambda for payment logic<br>&emsp;+ API Gateway for REST API<br>&emsp;+ Amazon SQS & SNS for async processing<br>&emsp;+ DynamoDB / RDS for transaction storage<br>&emsp;+ S3 for storing payment receipts | 19/05/2026 | 19/05/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 4 | - Develop core payment APIs:<br>&emsp;+ Create Payment URL API<br>&emsp;+ Webhook IPN Handler API<br>&emsp;+ Transaction Query API<br>- Study Amazon Cognito for Merchant & Admin authentication. | 20/05/2026 | 20/05/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos<br>MoMo API Docs |
| 5 | - Implement automated deployment using **AWS SAM** and **AWS CodePipeline**.<br>- Set up CI/CD pipeline for payment services.<br>- Use Amazon CloudWatch and AWS X-Ray to monitor Lambda and transaction performance. | 21/05/2026 | 21/05/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 6 | - Explore AWS AI/ML services for payment system.<br>- Research AI applications:<br>&emsp;+ Fraud detection<br>&emsp;+ Transaction anomaly detection<br>&emsp;+ Smart receipt processing | 22/05/2026 | 22/05/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |

## Week 5 Achievements

- Understood how to migrate from **Monolithic** to **Microservices Architecture** and apply it to a payment processing system.

- Designed independent services for MoMoPay AWS:
  - Payment Initiation Service
  - Webhook Processing Service
  - Transaction Management Service
  - Notification Service

- Built a solid understanding of **Serverless Payment Architecture** using AWS services:
  - **AWS Lambda** for core payment logic
  - **Amazon API Gateway** for secure API management
  - **Amazon SQS / SNS** for asynchronous processing and notifications
  - **DynamoDB / RDS** for transaction data
  - **Amazon S3** for receipt storage

- Developed key payment APIs:
  - Create Payment URL
  - MoMo IPN Webhook Handler
  - Transaction Status Query

- Integrated **Amazon Cognito** for secure authentication and role-based access (Merchant & Admin).

- Mastered automated deployment workflows:
  - AWS SAM for Serverless applications
  - AWS CodePipeline for CI/CD
  - CloudWatch + X-Ray for monitoring and troubleshooting

- Explored AI applications in payment systems:
  - Fraud detection
  - Anomaly detection
  - Intelligent receipt processing

- Gained comprehensive knowledge of modern payment system development on AWS.

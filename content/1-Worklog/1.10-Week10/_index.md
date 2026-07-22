---
title: "Week 10 Worklog"
date: 2024-01-01
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

# Week 10 Worklog

## Week 10 Objectives

- Build the backend foundation for the **MoMoPay AWS Payment System** using AWS Serverless services.
- Design DynamoDB data models and implement backend functions using AWS Lambda.
- Develop core payment features including payment creation, webhook processing, and transaction management.

## Tasks Completed This Week

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 2 | - Design the NoSQL database structure using **Amazon DynamoDB**.<br>- Create data models for:<br>&emsp;+ Transactions<br>&emsp;+ Webhook Logs<br>&emsp;+ Users/Merchants<br>&emsp;+ Audit Logs<br>- Define partition keys and access patterns for efficient queries. | 22/06/2026 | 22/06/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 3 | - Create and configure DynamoDB tables.<br>- Insert sample transaction data.<br>- Test database operations (CRUD). | 23/06/2026 | 23/06/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 4 | - Build backend services using **AWS Lambda**.<br>- Develop Lambda functions for:<br>&emsp;+ Create Payment URL<br>&emsp;+ Process MoMo IPN Webhook<br>&emsp;+ Update Transaction Status<br>&emsp;+ Query Transaction | 24/06/2026 | 24/06/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 5 | - Configure **Amazon API Gateway** and connect it with Lambda functions.<br>- Create REST API endpoints for payment operations.<br>- Test API requests and responses. | 25/06/2026 | 25/06/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 6 | - Implement receipt storage using **Amazon S3**.<br>- Configure upload workflow for payment documents.<br>- Test full integration between S3, Lambda, DynamoDB and MoMo Webhook. | 26/06/2026 | 26/06/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |

## Week 10 Achievements

- Designed the DynamoDB database structure for the payment system:
  - Created data models for transactions, webhooks, users, and audit logs.
  - Defined efficient access patterns.

- Successfully configured DynamoDB tables and added sample transaction data.

- Developed core backend logic using **AWS Lambda**:
  - Payment URL generation.
  - MoMo IPN Webhook processing.
  - Transaction status management.

- Built REST APIs using **Amazon API Gateway**:
  - Connected endpoints with Lambda functions.
  - Tested payment flows.

- Integrated **Amazon S3** for storing payment receipts and documents.

- Improved understanding of Serverless backend development for payment systems:
  - DynamoDB modeling for transactions.
  - Lambda business logic.
  - API Gateway integration.
  - Secure webhook handling.
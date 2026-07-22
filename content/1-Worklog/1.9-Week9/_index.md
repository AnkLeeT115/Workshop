---
title: "Week 9 Worklog"
date: 2024-01-01
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

# Week 9 Worklog

## Week 9 Objectives

- Learn the architecture, development process, and main components of the **MoMoPay AWS Payment System**.
- Set up the development environment and become familiar with AWS services used in the payment system.
- Understand the interaction between frontend, backend services, authentication, payment gateway, and data storage.

## Tasks Completed This Week

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 2 | - Learn the overview of the **MoMoPay AWS** project.<br>- Study system objectives, main features, and Serverless architecture.<br>- Understand core functions: Payment URL generation, Webhook processing, Transaction management. | 15/06/2026 | 15/06/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 3 | - Set up the development environment.<br>- Configure AWS CLI, AWS SAM, and required tools.<br>- Run and test backend services locally. | 16/06/2026 | 16/06/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 4 | - Learn AWS services used in the payment system.<br>- Research:<br>&emsp;+ Amazon API Gateway<br>&emsp;+ AWS Lambda<br>&emsp;+ Amazon SQS / SNS<br>&emsp;+ Amazon DynamoDB / RDS<br>&emsp;+ Amazon S3<br>&emsp;+ Amazon Cognito | 17/06/2026 | 17/06/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 5 | - Study the payment processing workflow.<br>- Design database structures for transactions, webhooks, and audit logs.<br>- Learn how DynamoDB/RDS stores payment data. | 18/06/2026 | 18/06/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 6 | - Learn authentication and authorization using **Amazon Cognito**.<br>- Understand Merchant & Admin user management.<br>- Become familiar with coding conventions, Git workflow, and deployment process. | 19/06/2026 | 19/06/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |

## Week 9 Achievements

- Gained an overview of the **MoMoPay AWS** payment system:
  - Understood Serverless architecture.
  - Learned the responsibilities of frontend, backend services, and AWS components.
  - Understood the full payment flow (Payment URL → Webhook → Transaction → Notification).

- Successfully prepared the development environment:
  - Configured AWS CLI and AWS SAM.
  - Installed required tools.
  - Tested backend services locally.

- Understood the roles of AWS services in the payment system:
  - **Amazon API Gateway**: Manages payment APIs.
  - **AWS Lambda**: Handles business logic and webhook.
  - **Amazon SQS/SNS**: Processes asynchronous transactions and notifications.
  - **DynamoDB/RDS**: Stores transaction records.
  - **Amazon S3**: Stores receipts and logs.
  - **Amazon Cognito**: Provides secure authentication.

- Learned payment system workflows:
  - Payment URL creation.
  - IPN Webhook processing.
  - Transaction management.
  - Notification delivery.

- Designed basic database structures for:
  - Transaction records.
  - Webhook logs.
  - Audit and reporting.

- Became familiar with development practices:
  - Authentication using Amazon Cognito.
  - Git workflow.
  - Coding conventions.
  - Serverless deployment process.
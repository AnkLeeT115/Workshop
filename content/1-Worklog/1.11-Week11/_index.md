---
title: "Week 11 Worklog"
date: 2024-01-01
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

# Week 11 Worklog

## Week 11 Objectives

- Implement user authentication and authorization using **Amazon Cognito and JWT**.
- Develop payment processing, webhook handling, and transaction validation features.
- Perform API testing and improve CI workflow for the payment backend.

## Tasks Completed This Week

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 2 | - Configure **Amazon Cognito User Pool** for Merchant and Administrator authentication.<br>- Implement registration and login flows.<br>- Generate and validate JWT tokens for secure requests. | 06/07/2026 | 06/07/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 3 | - Implement authorization using JWT and Cognito groups.<br>- Configure access control for Merchant and Admin functions.<br>- Test protected API endpoints through API Gateway. | 07/07/2026 | 07/07/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 4 | - Develop payment processing workflow using AWS Lambda.<br>- Implement:<br>&emsp;+ Create Payment URL<br>&emsp;+ Process MoMo IPN Webhook<br>&emsp;+ Validate Transaction<br>&emsp;+ Update Transaction Status | 08/07/2026 | 08/07/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 5 | - Write API tests for payment, webhook, and transaction services.<br>- Test authentication scenarios (valid users, invalid tokens, unauthorized access). | 09/07/2026 | 09/07/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 6 | - Improve CI workflow for Serverless payment application.<br>- Configure automated testing before deployment.<br>- Review Lambda functions, API Gateway, and DynamoDB operations. | 10/07/2026 | 10/07/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |

## Week 11 Achievements

- Successfully implemented authentication using **Amazon Cognito**:
  - Created Merchant and Administrator flows.
  - Integrated JWT token validation.
  - Protected payment APIs with authorization.

- Developed authorization management:
  - Applied Cognito groups for role-based access.

- Completed core payment processing functions:
  - Payment URL creation.
  - MoMo IPN Webhook handling.
  - Transaction validation and status updates.

- Performed comprehensive API testing:
  - Payment APIs.
  - Webhook endpoints.
  - Transaction queries.
  - Authentication and authorization scenarios.

- Improved development workflow:
  - Added automated testing into CI pipeline.
  - Enhanced reliability of the Serverless payment backend.
  - Reviewed Lambda, API Gateway, and DynamoDB integration.
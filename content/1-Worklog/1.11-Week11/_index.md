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
- Develop order processing and inventory validation features for the e-commerce system.
- Perform API testing and improve CI workflow for Serverless backend deployment.

## Tasks Completed This Week

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 2 | - Configure **Amazon Cognito User Pool** for customer and administrator authentication.<br>- Implement user registration and login flows.<br>- Generate and validate JWT tokens for authenticated requests. | 06/07/2026 | 06/07/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 3 | - Implement authorization mechanisms using JWT and Cognito groups.<br>- Configure access control for customer and admin functions.<br>- Test protected API endpoints through API Gateway. | 07/07/2026 | 07/07/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 4 | - Develop order processing workflow using AWS Lambda.<br>- Implement:<br>&emsp;+ Create order<br>&emsp;+ Check product availability<br>&emsp;+ Update inventory quantity<br>&emsp;+ Update order status | 08/07/2026 | 08/07/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 5 | - Write API tests for product, inventory, and order services.<br>- Test authentication scenarios:<br>&emsp;+ Valid users<br>&emsp;+ Invalid tokens<br>&emsp;+ Unauthorized access attempts | 09/07/2026 | 09/07/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 6 | - Improve CI workflow for Serverless application testing.<br>- Configure automated testing before deployment.<br>- Review Lambda functions, API Gateway configuration, and DynamoDB operations. | 10/07/2026 | 10/07/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |

## Week 11 Achievements

- Successfully implemented authentication using **Amazon Cognito**:
  - Created customer and administrator authentication flows.
  - Integrated JWT token validation.
  - Protected backend APIs using authorization mechanisms.

- Developed authorization management:
  - Applied Cognito user groups for role management.
  - Controlled access between customers and administrators.

- Completed order processing functions:
  - Created order workflow using AWS Lambda.
  - Validated product availability before checkout.
  - Updated inventory after successful orders.
  - Managed order status changes.

- Performed backend API testing:
  - Tested product APIs.
  - Tested inventory APIs.
  - Tested order APIs.
  - Verified authentication and authorization scenarios.

- Improved development workflow:
  - Added automated testing into CI pipeline.
  - Improved reliability of Serverless backend deployment.
  - Reviewed Lambda, API Gateway, and DynamoDB integration.
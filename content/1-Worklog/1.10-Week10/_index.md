---
title: "Week 10 Worklog"
date: 2024-01-01
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

# Week 10 Worklog

## Week 10 Objectives

- Build the backend foundation for the **Genuine Scale Models E-commerce Backend** using AWS Serverless services.
- Design DynamoDB data models and implement backend functions using AWS Lambda.
- Develop core e-commerce features including product management, inventory management, and order processing.

## Tasks Completed This Week

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 2 | - Design the NoSQL database structure using **Amazon DynamoDB**.<br>- Create data models for:<br>&emsp;+ Products<br>&emsp;+ Users<br>&emsp;+ Orders<br>&emsp;+ Inventory<br>- Define partition keys and access patterns for efficient data retrieval. | 22/06/2026 | 22/06/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 3 | - Create and configure DynamoDB tables.<br>- Insert sample product data including:<br>&emsp;+ Model name<br>&emsp;+ Brand<br>&emsp;+ Category<br>&emsp;+ Price<br>&emsp;+ Official product verification status<br>- Test database operations. | 23/06/2026 | 23/06/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 4 | - Build backend services using **AWS Lambda**.<br>- Develop Lambda functions for:<br>&emsp;+ Product listing<br>&emsp;+ Product creation<br>&emsp;+ Product update<br>&emsp;+ Inventory checking<br>- Organize source code following Serverless development practices. | 24/06/2026 | 24/06/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 5 | - Configure **Amazon API Gateway** and connect it with Lambda functions.<br>- Create REST API endpoints for:<br>&emsp;+ Product management<br>&emsp;+ Inventory management<br>&emsp;+ Order processing<br>- Test API requests and responses. | 25/06/2026 | 25/06/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |
| 6 | - Implement product image storage using **Amazon S3**.<br>- Configure upload workflow for product images.<br>- Test integration between S3, Lambda, and DynamoDB.<br>- Review backend architecture and improve code structure. | 26/06/2026 | 26/06/2026 | https://cloudjourney.awsstudygroup.com/<br>https://www.youtube.com/@AWSStudyGroup/videos |

## Week 10 Achievements

- Designed the DynamoDB database structure for the e-commerce system:
  - Created data models for products, users, orders, and inventory.
  - Defined access patterns and partition keys for efficient NoSQL data management.

- Successfully configured DynamoDB tables:
  - Added sample genuine scale model products.
  - Managed product information including:
    - Model name.
    - Brand.
    - Category.
    - Price.
    - Official product verification status.
    - Stock quantity.

- Developed backend logic using **AWS Lambda**:
  - Implemented product management functions.
  - Built inventory checking functions.
  - Prepared backend services for order processing.

- Built REST APIs using **Amazon API Gateway**:
  - Connected API endpoints with Lambda functions.
  - Tested communication between client requests and backend services.

- Integrated **Amazon S3** for product image management:
  - Stored product images securely.
  - Connected image upload workflow with Lambda and DynamoDB.

- Improved understanding of Serverless backend development:
  - DynamoDB data modeling.
  - Lambda-based business logic.
  - API Gateway integration.
  - S3 object storage management.
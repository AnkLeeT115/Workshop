---
title: "Project Proposal"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# PrimeScale - Genuine Scale Models E-commerce Platform
## Serverless AWS Solution for Authentic Model Commerce

### 1. Executive Summary
PrimeScale is designed for retailers and enthusiasts of genuine scale models (Gundam, Bandai, Warhammer, Figures, etc.) in Vietnam. The platform supports product catalog management, order processing, inventory tracking, and high-quality image delivery for up to thousands of monthly users.

It leverages a fully serverless AWS architecture to provide real-time shopping experience, secure authentication, and cost efficiency. The system is built with React/Next.js frontend, AWS Lambda backend, and is limited to authorized users and admins through Amazon Cognito.

### 2. Problem Statement
**Current Challenges**  
The genuine scale model market faces several issues:

* Difficulty verifying authentic products vs replicas.
* Manual inventory management leading to stock errors, especially during new model releases.
* Poor online shopping experience with slow image loading and lack of product verification.
* High operational costs and scaling difficulties with traditional servers.
* Shop owners struggle with real-time order and stock management.

**Solution**  
PrimeScale uses a modern AWS serverless architecture with Amazon S3 + CloudFront for images, API Gateway and Lambda for business logic, DynamoDB for data storage, and Cognito for authentication. Similar to small-scale Shopify or specialized e-commerce platforms, users can browse official models, place orders, and admins can manage inventory. Key features include fast product search, secure checkout, and real-time stock updates.

**Benefits and ROI**  
The solution creates a reliable foundation for selling genuine models, provides high-quality shopping experience, and reduces manual operations. It enables shop owners to focus on business growth rather than infrastructure. Monthly cost is estimated at under $50 (using AWS Pricing Calculator). No additional hardware is required. ROI is expected within 3–6 months through increased sales, reduced operational overhead, and improved customer trust.

### 3. Solution Architecture
PrimeScale applies a fully serverless AWS architecture optimized for e-commerce workloads. Product images are served via CloudFront, orders and inventory are handled through Lambda functions, and data is stored in DynamoDB for high performance and scalability.

![PrimeScale Architecture](/images/2-Proposal/primescale_architecture.png)

**AWS Services Used**
- **Amazon S3 + CloudFront**: Store and deliver high-resolution product images.
- **AWS Lambda**: Handle business logic (product CRUD, orders, inventory).
- **Amazon API Gateway**: Expose RESTful APIs for frontend.
- **Amazon DynamoDB**: Store products, orders, and inventory data.
- **Amazon Cognito**: User authentication and authorization.
- **Amazon SES/SNS**: Order confirmation emails and notifications.

**Component Design**
- **Frontend**: React/Next.js web application (mobile-responsive).
- **Backend**: Serverless Lambda functions triggered by API Gateway.
- **Storage**: S3 for images with signed URLs; DynamoDB for structured data.
- **Authentication**: Cognito User Pools for customers and admins.
- **Data Flow**: Users browse via CloudFront → API calls → Lambda → DynamoDB.

### 4. Technical Implementation
**Implementation Phases**  
The project is divided into clear phases:

1. **Research & Architecture Design**: Study requirements and design serverless architecture (1–2 weeks).
2. **Cost Calculation & Feasibility**: Use AWS Pricing Calculator and prototype core services (Month 1).
3. **Architecture Optimization**: Refine for cost and performance (e.g., optimize Lambda, DynamoDB indexing).
4. **Development, Testing, Deployment**: Implement frontend, backend, integrations, testing, and staging deployment (Month 2–3).

**Technical Requirements**
- **Frontend**: React or Next.js with responsive design.
- **Backend**: Node.js/Python Lambda functions using AWS SAM or CDK.
- **Database**: DynamoDB with proper indexing for fast queries.
- **Integrations**: S3 signed URLs for image upload, Cognito JWT authentication.

### 5. Roadmap & Milestones
- **Preparation (Week 0)**: Requirements gathering and initial architecture.
- **Month 1**: Environment setup, authentication, product management.
- **Month 2**: Order flow, inventory, frontend integration.
- **Month 3**: Admin portal, testing, CI/CD, staging deployment.
- **Post-launch**: Monitoring, optimization, and feature expansion.

### 6. Budget Estimation

**Infrastructure Cost (Monthly - Staging/MVP)**  
- AWS Lambda + API Gateway: ~$10–25  
- Amazon S3 + CloudFront: ~$5–15  
- Amazon DynamoDB: ~$5–15  
- Amazon Cognito: ~$5–10  
- Others (SES/SNS): ~$2–5  

**Total**: ~$25–80 per month (scales with usage).  
**Development Phase**: Near $0 using Free Tier.  
**One-time costs**: Minimal (domain, optional tools).

### 7. Risk Assessment
**Risk Matrix**  
- API/Lambda latency: Medium impact, Low probability.  
- Cost overrun: Medium impact, Low probability.  
- Data security breach: High impact, Low probability.  
- Requirement changes: Medium impact, Medium probability.

**Mitigation Strategies**  
- Latency: Optimize code and use caching.  
- Cost: Set budget alerts and monitor usage.  
- Security: Follow least privilege and Cognito best practices.  

**Contingency Plans**  
- Fallback to manual processes if needed.  
- Use Infrastructure as Code for quick recovery.

### 8. Expected Outcomes
**Technical Improvements**: Fully functional serverless e-commerce platform with fast image delivery, secure authentication, and real-time inventory. Easy to scale from MVP to production.

**Long-term Value**: A production-ready platform for genuine scale model retailers, reusable codebase for future expansions (AI recommendations, analytics), and a strong portfolio project demonstrating AWS serverless expertise.
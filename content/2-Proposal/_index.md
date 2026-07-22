---
title: "Project Proposal"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# CloudPay - AWS Payment Processing System
## Serverless Payment Architecture on AWS

### 1. Executive Summary

CloudPay implements a secure and scalable cloud-native payment processing system for an e-commerce platform selling genuine scale models. The payment architecture is built entirely on AWS serverless services and integrates with the MoMo payment gateway to provide secure online transactions.

The solution leverages Amazon Cognito for user authentication, Amazon API Gateway and AWS Lambda for business logic, Amazon SQS for asynchronous processing, Amazon SNS for notifications, Amazon RDS for transaction storage, and Amazon CloudWatch/X-Ray for monitoring. The architecture ensures high availability, fault tolerance, and real-time payment processing while minimizing operational costs.

---

### 2. Problem Statement

#### Current Challenges

Traditional payment systems often face several operational issues:

- Synchronous payment processing may fail during high traffic.
- Payment callbacks can be lost due to temporary network failures.
- Lack of retry mechanisms results in incomplete transactions.
- Limited monitoring makes troubleshooting difficult.
- Scaling payment services requires significant infrastructure investment.

#### Proposed Solution

PrimeScale adopts a serverless event-driven payment architecture on AWS.

Users authenticate through Amazon Cognito before initiating payments. Payment requests are routed through Amazon API Gateway to AWS Lambda, which generates a secure payment URL for the MoMo payment gateway.

After payment completion, MoMo sends a webhook callback to AWS Lambda. The webhook validates the digital signature and pushes transaction data into Amazon SQS. Worker Lambda functions asynchronously process payment events, update Amazon RDS, publish notifications via Amazon SNS, and send confirmation emails or SMS messages.

Dead Letter Queue (DLQ) automatically stores failed transactions for retry, ensuring reliability and preventing data loss.

#### Benefits

- Highly scalable payment processing
- Secure JWT authentication
- Reliable asynchronous transaction handling
- Automatic retry for failed events
- Real-time notifications
- Centralized monitoring and logging
- Low operational cost using serverless computing

---

### 3. Solution Architecture

The payment platform follows an event-driven serverless architecture deployed entirely on AWS.

The payment workflow consists of the following stages:

1. User authentication using Amazon Cognito.
2. Frontend sends payment request through Amazon API Gateway.
3. AWS Lambda creates a payment URL.
4. Customer is redirected to the MoMo payment gateway.
5. MoMo sends a signed webhook callback after payment.
6. Webhook Lambda validates the signature.
7. Transaction is pushed into Amazon SQS.
8. Worker Lambda processes the payment asynchronously.
9. Payment status is stored in Amazon RDS.
10. Amazon SNS sends Email/SMS notifications.
11. Amazon CloudWatch and AWS X-Ray monitor the entire workflow.

![AWS Payment Architecture](/images/2-Proposal/payment_architecture.png)

---

### AWS Services Used

| AWS Service | Purpose |
|-------------|---------|
| Amazon Cognito | User authentication and JWT authorization |
| Amazon API Gateway | REST API endpoint |
| AWS Lambda | Payment processing and business logic |
| Amazon SQS | Queue payment events |
| Amazon SQS DLQ | Store failed transactions |
| Amazon SNS | Email/SMS notifications |
| Amazon RDS | Store payment records |
| Amazon RDS Proxy | Efficient database connections |
| Amazon CloudFront | Deliver frontend application |
| Amazon S3 | Static website hosting |
| AWS WAF | Protect against malicious traffic |
| Amazon CloudWatch | Monitoring and logging |
| AWS X-Ray | Distributed tracing |
| MoMo Payment Gateway | Online payment provider |

---

### 4. Technical Implementation

#### Phase 1 – Authentication

- User login via Amazon Cognito.
- JWT Token generated after successful authentication.
- API Gateway validates JWT before forwarding requests.

#### Phase 2 – Payment Creation

- Lambda creates payment request.
- Generate secure payment URL.
- Return payment URL to frontend.
- Redirect customer to MoMo.

#### Phase 3 – Payment Verification

- MoMo calls Webhook API.
- Lambda validates HMAC Signature.
- Verify payment status.
- Push payment event into Amazon SQS.

#### Phase 4 – Asynchronous Processing

Worker Lambda:

- Reads messages from Amazon SQS.
- Updates transaction status.
- Writes payment information into Amazon RDS.
- Publishes events to Amazon SNS.
- Sends Email/SMS confirmation.

If processing fails:

- Message is automatically moved to Amazon SQS Dead Letter Queue.
- Admin can retry failed transactions using the Admin API.

---

### 5. Roadmap & Milestones

| Phase | Activities |
|--------|------------|
| Week 1 | Design payment architecture |
| Week 2 | Configure Cognito, API Gateway |
| Week 3 | Implement Payment Lambda |
| Week 4 | Integrate MoMo Payment Gateway |
| Week 5 | Implement Webhook verification |
| Week 6 | Configure Amazon SQS and Worker Lambda |
| Week 7 | Integrate Amazon SNS notifications |
| Week 8 | Deploy monitoring with CloudWatch and X-Ray |
| Week 9 | Load testing and optimization |
| Week 10 | Final deployment |

---

### 6. Budget Estimation

#### Estimated Monthly AWS Cost

| Service | Estimated Cost |
|----------|----------------|
| Amazon API Gateway | $5 |
| AWS Lambda | $8 |
| Amazon SQS | $2 |
| Amazon SNS | $2 |
| Amazon Cognito | $3 |
| Amazon RDS | $20 |
| Amazon CloudWatch | $5 |
| Amazon S3 | $2 |
| Amazon CloudFront | $5 |
| AWS WAF | $5 |

**Estimated Total:** **$50–60/month**

Using the AWS Free Tier during development, infrastructure costs remain close to zero.

---

### 7. Risk Assessment

| Risk | Impact | Mitigation |
|------|--------|------------|
| Payment callback failure | High | Retry using Amazon SQS DLQ |
| Database unavailable | High | Amazon RDS Multi-AZ deployment |
| Unauthorized API access | High | Amazon Cognito JWT authentication |
| High traffic | Medium | Automatic Lambda scaling |
| Payment fraud | High | Verify MoMo HMAC Signature |
| Monitoring failure | Medium | CloudWatch alarms and SNS alerts |

---

### 8. Expected Outcomes

The proposed AWS payment processing architecture provides a highly available, secure, and scalable payment platform capable of handling thousands of payment transactions with minimal operational effort.

Expected achievements include:

- Secure authentication using Amazon Cognito.
- Reliable payment processing through MoMo integration.
- Asynchronous event-driven architecture using Amazon SQS.
- Automatic notification services via Amazon SNS.
- Durable transaction storage in Amazon RDS.
- Centralized monitoring through CloudWatch and AWS X-Ray.
- Automatic retry and fault recovery using Dead Letter Queue.
- Cost-efficient serverless deployment with automatic scaling.
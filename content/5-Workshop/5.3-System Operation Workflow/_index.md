---
title : "AWS Operation Architecture - PrimeScale"
date : 2026-07-17
weight : 5
chapter : false
pre : " <b> 5. </b> "
---

# AWS Operation Architecture of the PrimeScale System

## 1. User Authentication & Access Control

The PrimeScale system supports three main user roles:

- **Customer**: Views product quality inspection information.
- **Seller**: Uploads products and submits inspection requests.
- **Admin**: Manages the system, reviews AI inspection results, and monitors operations.

The system uses **Amazon Cognito** for user authentication and access management.

Authentication Flow:

Amazon Cognito is responsible for:

- User registration and login.
- User account management.
- Role-based access control for Customer, Seller, and Admin.
- Issuing JWT tokens to secure APIs.

---

## 2. Frontend Delivery Layer

PrimeScale deploys its user interface using a **Serverless Architecture** with a React application.

Architecture:

Amazon S3

Amazon S3 stores:

- React Frontend Application.
- Product images.
- AI inspection result images.

Amazon CloudFront

CloudFront is responsible for:

- High-speed content delivery.
- Reducing access latency.
- Supporting a large number of concurrent users.

---

## 3. API Management Layer

### Amazon API Gateway

Amazon API Gateway serves as the entry point for all requests from the PrimeScale application.

Main APIs:

```text
POST   /product/upload

POST   /inspection/start

GET    /inspection/result/{id}

GET    /product/history/{id}
```

API Gateway responsibilities:

- Validate JWT tokens issued by Amazon Cognito.
- Route incoming requests.
- Enforce access control.
- Connect requests to AWS Lambda.

---

## 4. Product Image Processing System

Sellers upload product images to the system.

Examples include:

- Gundam box.
- Completed model.
- Individual parts.
- Manufacturer logo.
- Damaged areas of the product.

Processing Flow:

---

## 5. AI Quality Inspection Processing

### AWS Lambda Worker

AWS Lambda processes product inspection requests.

Responsibilities:

- Receive product information.
- Send images to the AI inspection service.
- Analyze AI results.
- Generate quality inspection reports.

Processing Flow:

---

## 6. AI Image Analysis

### Amazon Rekognition

Amazon Rekognition is used to analyze product images.

### Product Detection

The system can:

- Identify model types.
- Detect objects in images.
- Verify manufacturer logos.

### Defect Detection

The AI detects defects such as:

- Scratches.
- Cracks.
- Missing accessories.
- Incorrect colors.
- Damaged packaging.

Example inspection result:

```json
{
  "productId": "GUNDAM001",
  "qualityScore": 95,
  "condition": "Excellent",
  "defects": [],
  "status": "Verified"
}
```

---

## 7. Inspection Queue Management

### Amazon SQS

To ensure stable performance during peak traffic, PrimeScale uses **Amazon SQS** to manage inspection requests through asynchronous processing.

Example:

```text
1000 Product Images Uploaded
```

Asynchronous Processing:

Benefits:

- Prevents Lambda overload.
- Supports asynchronous processing.
- Provides automatic retry for failed tasks.

---

## 8. Product Data Storage

### Amazon DynamoDB

Amazon DynamoDB stores product information and inspection results.

### Product Table

```json
{
  "productId": "PS001",
  "name": "MG Gundam",
  "seller": "user001",
  "status": "Verified"
}
```

### Inspection Table

```json
{
  "inspectionId": "INS001",
  "score": 95,
  "result": "Approved",
  "checkedDate": "2026-07-17"
}
```

Advantages:

- High-speed data retrieval.
- Automatic scaling.
- No database server management required.

---

## 9. Notification System

### Amazon SNS

After the inspection process is completed, the system sends notifications to users.

Notification Flow:

---

## 10. Monitoring & Logging

### Amazon CloudWatch

Amazon CloudWatch monitors all system activities.

Metrics include:

- Lambda Execution.
- API Requests.
- AI Processing Time.
- Failed Inspections.
- System Errors.

Monitoring Flow:

PrimeScale may also use:

### AWS X-Ray

For analyzing:

- API Latency.
- Lambda Performance.
- Workflow Bottlenecks.

---

## 11. Complete PrimeScale AWS Operation Architecture

The PrimeScale AWS Serverless Architecture integrates all AWS services into a unified workflow, including authentication, frontend hosting, API management, AI-based image inspection, queue processing, data storage, notifications, and monitoring.

---

# Conclusion

The PrimeScale AWS Serverless Architecture enables the system to:

- Automatically inspect product quality using AI.
- Reduce manual inspection time.
- Store transparent and traceable product verification history.
- Scale efficiently as the number of products increases.
- Provide a reliable marketplace experience for Gundam, Figure, Warhammer, and Scale Model enthusiasts in Vietnam.
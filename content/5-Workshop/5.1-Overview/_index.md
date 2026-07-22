---
title: "Project Overview"
date: 2026-07-19
weight: 1
chapter: false
pre: " <b> 5.1. </b> "
---

# Project Background and System Design Challenges

## Project Background

One of the biggest challenges in building a payment system is not only ensuring transactions are fast, but also making them absolutely secure, transparent, and reliable. Users (Merchants and Customers) expect smooth and instant payment experiences, but behind the scenes there are numerous risks: fraud, replay attacks, double spending, synchronization errors, and rising cloud operational costs during traffic spikes.

**MoMoPay AWS** applies the principle of **“Server is the Source of Truth”** — the server must be the ultimate decision-maker for all critical rules (creating payment URLs, validating webhooks, updating transaction status, issuing rewards, etc.). Every action receives clear, timely, and auditable feedback, building trust for both Merchants and the system.

## Problem Statement and Project Goals

Traditional payment systems often struggle to balance **speed – security – cost**. Server-based systems can be secure but are hard to scale and expensive. Pure client-side systems are vulnerable to fraud. Therefore, the project aims to build a **serverless payment platform** that can handle high traffic securely while keeping operational costs under control.

The project builds a MoMo-integrated payment system on **AWS Serverless**, combined with **ReactJS + Electron** (or Web) on the client side. The core goal is to create a payment system that is fast, secure, transparent, and highly scalable. Specific objectives include:

- Fast generation of Payment URLs and reliable processing of MoMo webhooks;
- Strong protection against fraud (double payment, replay attacks, fake transactions);
- Reliable asynchronous processing and retry mechanisms when webhooks fail;
- Real-time transaction dashboard for Merchants;
- Reliable notification system (Email/SMS);
- Optimized cloud costs even during traffic surges;
- Foundation for future AI/ML features such as fraud detection.

## Target Audience

### Merchants (Businesses / Store Owners)

They need a stable, easy-to-integrate payment system with a clear dashboard for real-time transaction monitoring, revenue reports, and refund management. They especially value webhook reliability and automatic error handling.

### End Customers

They expect a fast, secure, uninterrupted payment process with clear receipts. They need confidence that their transactions are processed correctly and can be easily tracked.

### Shared Values

Both groups need a system that is **fast – secure – transparent**. The project focuses on making every transaction verifiable, trackable, and automatically recoverable, thereby building long-term trust.

## Core Technical Challenges

### 1. Preventing Payment Fraud

MoMo IPN webhooks can be replayed, forged, or sent multiple times. The system must validate signatures, use idempotency keys, enforce expiration times, and check transaction status on the server before updating. Multiple updates or double crediting must be prevented.

### 2. Reliable Asynchronous Processing & Retry

Webhooks may fail due to network issues or temporary errors. The system uses **SQS + DLQ + Retry Mechanism** to ensure every transaction is eventually processed correctly, even during failures.

### 3. Data Integrity and Consistency

Transactions, balances, receipts, and audit logs must always remain consistent. The system uses conditional updates, transactions, idempotent processing, and server-side validation to avoid double payments or data loss.

### 4. Efficient Client-Server Synchronization

The desktop/web app needs fast UI loading. Constant polling would increase latency and cost. The system uses caching, version-based sync, aggregated endpoints, and event-driven updates to maintain responsiveness while reducing unnecessary calls.

### 5. Cloud Cost Optimization

User activity varies. The system leverages Serverless services (Lambda, API Gateway, DynamoDB, SQS, SNS) that scale automatically and charge based on usage, combined with smart caching, batch processing, and TTL to keep costs low.

## Cross-cutting Requirements

- **Security:** Cognito authentication, JWT protection, WAF, least privilege IAM, data encryption.
- **Observability:** Structured logging, metrics, tracing, cost alerts.
- **Scalability & Maintainability:** Domain-driven design, Infrastructure as Code.
- **Compliance:** Secure handling of payment data and full audit trails.

## Expected Project Value

MoMoPay AWS serves as a practical case study of building a secure, scalable, and cost-efficient serverless payment system on AWS. It provides a solid foundation for future enhancements such as AI-powered fraud detection, subscription management, automated refunds, and more.
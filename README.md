# Project-3-Serverless-REST-API-with-DynamoDB-and-API-Gateway
## Overview

This project implements a **serverless REST API** to manage records (e.g., a to-do list or customer records) using **Amazon API Gateway**, **AWS Lambda**, and **Amazon DynamoDB**. A simple front-end is hosted on **Amazon S3**. Monitoring is handled using **Amazon CloudWatch**, and access is secured using **AWS IAM** roles and permissions.

---

## Architecture Diagram (Flow)

**Front-end hosting**
- User Browser → **S3 Static Website Hosting**

**API calls**
- User Browser → **API Gateway** → **Lambda** → **DynamoDB**

**Monitoring**
- **API Gateway → CloudWatch** (logs/metrics)
- **Lambda → CloudWatch** (logs/metrics)

---

## Key AWS Services Used

### Amazon S3 (Static Website Hosting)
- Hosts the front-end (static files).
- The browser loads the website from S3, then calls the API Gateway endpoints.

### Amazon API Gateway
- Exposes REST endpoints for CRUD operations.
- Receives HTTP requests from the front-end and invokes Lambda.

### AWS Lambda
- Implements CRUD logic (Create, Read, Update, Delete).
- Reads/writes data in DynamoDB.

### Amazon DynamoDB
- Stores application records (to-dos or customer records) in a managed NoSQL table.

### AWS IAM
- Controls permissions using roles and policies:
  - Lambda execution role to access DynamoDB
  - API Gateway permission to invoke Lambda

### Amazon CloudWatch
- Captures and monitors:
  - API Gateway logs and metrics
  - Lambda logs and metrics
  - DynamoDB metrics

 — Delete an item

---

## Logging & Monitoring (CloudWatch)

- **Lambda logs**: request handling, errors, and application logs
- **API Gateway logs**: request/response logs 

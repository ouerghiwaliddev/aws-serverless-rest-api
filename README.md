# Serverless REST API on AWS with Cognito, Lambda, DynamoDB & WAF

## 📌 Project Overview

This project demonstrates the design and deployment of a secure, scalable, and fully serverless REST API on AWS.

The solution leverages Amazon API Gateway, AWS Lambda, Amazon DynamoDB, and Amazon Cognito to deliver a highly available backend capable of handling authentication, authorization, CRUD operations, and event-driven processing.

To enhance security and performance, AWS WAF protects the API against common web threats, while Amazon CloudFront provides global content delivery and caching capabilities. AWS X-Ray enables end-to-end distributed tracing, helping identify bottlenecks and optimize system performance.

The architecture follows AWS Well-Architected Framework principles with a focus on Security, Reliability, Performance Efficiency, Operational Excellence, and Cost Optimization.

---

## 🎯 Objectives

- Build a fully serverless REST API on AWS.
- Implement secure user authentication with Amazon Cognito.
- Create CRUD operations using AWS Lambda.
- Store application data in Amazon DynamoDB.
- Protect public endpoints using AWS WAF.
- Improve performance with CloudFront and API Gateway caching.
- Enable distributed tracing with AWS X-Ray.
- Process real-time events using DynamoDB Streams.
- Apply AWS Well-Architected best practices.

---

## 🏗 Architecture Diagram

architecture/architecture-diagram.png

### Architecture Flow

```text
Users
   │
   ▼
Amazon CloudFront
   │
   ▼
AWS WAF
   │
   ▼
Amazon API Gateway
   │
   ▼
Amazon Cognito User Pool
   │
   ▼
AWS Lambda Functions
   │
   ▼
Amazon DynamoDB
   │
   ▼
DynamoDB Streams

Monitoring:
CloudWatch + AWS X-Ray

Frontend:
Amazon S3 + CloudFront
```

---

## 🏛 AWS Services Used

### API Layer

- Amazon API Gateway
- REST API Endpoints
- Cognito JWT Authorizer
- Usage Plans
- Response Caching

### Authentication

- Amazon Cognito User Pools
- Hosted UI
- JWT Authentication
- User Registration & Login

### Compute

- AWS Lambda
- Event-Driven Functions
- IAM Execution Roles
- Environment Variables

### Database

- Amazon DynamoDB
- On-Demand Capacity
- Global Secondary Indexes (GSIs)
- DynamoDB Streams

### Security

- AWS WAF
- Rate-Based Rules
- Geo Restrictions
- AWS Managed Rule Sets
- OWASP Protection

### Content Delivery

- Amazon CloudFront
- Edge Caching
- HTTPS Delivery

### Monitoring & Observability

- Amazon CloudWatch
- AWS X-Ray
- CloudWatch Logs
- Metrics & Alarms

### Frontend Hosting

- Amazon S3
- Amazon CloudFront

---

## 🚀 Key Features

### Authentication & Authorization

✅ User Sign-Up

✅ User Sign-In

✅ Cognito Hosted UI

✅ JWT Token Validation

✅ Protected API Endpoints

---

### CRUD Operations

#### Create Record

```http
POST /items
```

#### Retrieve All Records

```http
GET /items
```

#### Retrieve Record by ID

```http
GET /items/{id}
```

#### Update Record

```http
PUT /items/{id}
```

#### Delete Record

```http
DELETE /items/{id}
```

---

### Security Features

✅ AWS WAF Protection

✅ Rate Limiting

✅ Bot Mitigation

✅ Geo Blocking

✅ IAM Least Privilege

✅ Encryption at Rest

✅ HTTPS Everywhere

---

### Performance Optimizations

✅ CloudFront Edge Caching

✅ API Gateway Response Caching

✅ DynamoDB On-Demand Scaling

✅ Serverless Auto Scaling

---

## 🗃 DynamoDB Data Model

### Table: Items

#### Partition Key

```text
userId
```

#### Sort Key

```text
itemId
```

### Sample Item

```json
{
  "userId": "user-001",
  "itemId": "task-1001",
  "title": "Study AWS Solutions Architect Associate",
  "status": "Pending",
  "createdAt": "2026-07-06T10:00:00Z"
}
```

---

## 📊 Monitoring & Observability

### Amazon CloudWatch

Monitor:

- API Requests
- Lambda Invocations
- Error Rates
- Response Latency
- WAF Requests
- DynamoDB Consumption

### AWS X-Ray

End-to-end tracing:

```text
CloudFront
    │
    ▼
API Gateway
    │
    ▼
Lambda
    │
    ▼
DynamoDB
```

Benefits:

- Latency Analysis
- Root Cause Investigation
- Service Dependency Mapping
- Performance Troubleshooting

---

## 🔐 Security Controls

### Authentication

- Amazon Cognito User Pools
- JWT-Based Authentication
- Managed User Directory

### Network Protection

- AWS WAF
- OWASP Managed Rules
- Rate-Based Rules
- Geo Restriction

### Access Management

- IAM Roles
- Least Privilege Principle
- Scoped Permissions

### Data Protection

- Encryption at Rest
- Encryption in Transit
- HTTPS/TLS

---

## ⚡ DynamoDB Streams

DynamoDB Streams capture table modifications and can trigger downstream event-driven processing.

Example use cases:

- Real-Time Notifications
- Audit Logging
- Event Analytics
- Workflow Automation

---

## 🌍 High Availability & Scalability

### High Availability

- API Gateway Multi-AZ
- Lambda Managed Availability
- DynamoDB Managed Availability
- Cognito Managed Service

### Scalability

- Lambda Automatic Scaling
- DynamoDB On-Demand Capacity
- CloudFront Global Edge Network
- API Gateway Managed Scaling

---

## 🏗 AWS Well-Architected Framework

### Operational Excellence

- CloudWatch Monitoring
- X-Ray Tracing
- Centralized Logging

### Security

- Cognito Authentication
- AWS WAF Protection
- IAM Least Privilege

### Reliability

- Managed Serverless Services
- Fault-Tolerant Design
- Multi-AZ Architecture

### Performance Efficiency

- CloudFront Caching
- API Gateway Caching
- DynamoDB On-Demand

### Cost Optimization

- Pay-As-You-Go Pricing
- Serverless Compute
- Managed Infrastructure

---

## 🎓 Skills Demonstrated

- Serverless Architecture Design
- Amazon API Gateway
- Amazon Cognito Authentication
- JWT Authorization
- AWS Lambda Development
- DynamoDB Data Modeling
- DynamoDB Streams
- AWS WAF Configuration
- CloudFront Optimization
- AWS X-Ray Distributed Tracing
- CloudWatch Monitoring
- Event-Driven Architecture
- AWS Security Best Practices
- AWS Well-Architected Framework

---

## 📁 Repository Structure

```text
aws-serverless-rest-api
│
├── architecture
│   └── architecture-diagram.png
│
├── docs
│   ├── deployment-guide.md
│   ├── testing-guide.md
│
├── lambda
│   ├── create-item
│   ├── get-items
│   ├── update-item
│   └── delete-item
│
├── screenshots
│   ├── api-gateway.png
│   ├── cognito-user-pool.png
│   ├── dynamodb-table.png
│   ├── waf-rules.png
│   ├── cloudfront-distribution.png
│   └── xray-traces.png
│
└── README.md
```

---

## 📚 Learning Outcomes

By completing this project I gained hands-on experience with:

- Building production-ready serverless applications on AWS.
- Implementing authentication and authorization using Amazon Cognito.
- Designing efficient DynamoDB schemas and access patterns.
- Protecting APIs using AWS WAF managed rule sets.
- Improving application performance with CloudFront and API Gateway caching.
- Tracing distributed requests with AWS X-Ray.
- Building event-driven solutions using DynamoDB Streams.
- Applying AWS Well-Architected Framework best practices.

---

## 👨‍💻 Author

**Walid OUERGHI**

AWS Solutions Architect Associate Learning Project.
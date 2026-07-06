# Deployment Guide - AWS Serverless REST API

## Overview

This guide describes the deployment steps for the AWS Serverless REST API project using Cognito, API Gateway, Lambda, DynamoDB, WAF, CloudFront, and X-Ray.

## Prerequisites

- AWS Account
- AWS CLI configured
- IAM permissions for Cognito, Lambda, API Gateway, DynamoDB, WAF, CloudFront and X-Ray

## Step 1 - Create DynamoDB Table

Table Name: Tasks

- Partition Key: userId
- Sort Key: taskId
- Billing Mode: On-Demand
- Enable DynamoDB Streams

## Step 2 - Create Cognito User Pool

- Create User Pool
- Enable self-registration
- Use email as sign-in option
- Create App Client
- Enable Hosted UI

Record:

- User Pool ID
- App Client ID
- Cognito Domain

## Step 3 - Create Lambda Functions

Create functions:

- createTask
- getTasks
- getTask
- updateTask
- deleteTask

Environment Variable:

TABLE_NAME=Tasks

Grant DynamoDB access through IAM.

## Step 4 - Configure API Gateway

Create a REST API with:

- POST /tasks
- GET /tasks
- GET /tasks/{id}
- PUT /tasks/{id}
- DELETE /tasks/{id}

Integrate each endpoint with the corresponding Lambda function.

## Step 5 - Configure Cognito Authorizer

- Create Cognito Authorizer
- Attach User Pool
- Protect all API methods

## Step 6 - Enable API Gateway Caching

Stage: prod

- Enable caching
- Cache size: 0.5 GB
- TTL: 300 seconds

## Step 7 - Enable AWS X-Ray

- Enable X-Ray in API Gateway
- Enable Active Tracing on Lambda

## Step 8 - Create AWS WAF Web ACL

Add:

- AWS Managed Common Rules
- Known Bad Inputs Rules
- SQL Injection Rules
- Rate Limiting Rule

## Step 9 - Create CloudFront Distribution

Origin:

- API Gateway endpoint

Associate Web ACL.

## Step 10 - Validation

Verify:

- User registration
- Authentication
- CRUD operations
- WAF protection
- X-Ray traces
- CloudFront delivery

## Expected Architecture

User → CloudFront → WAF → API Gateway → Cognito Authorizer → Lambda → DynamoDB → DynamoDB Streams

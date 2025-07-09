---
title : "Introduction"
date : 2023-10-25 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---

#### System Introduction

This workshop will guide you through building and deploying a **dynamic e-commerce website** on AWS's modern serverless platform.  
You will leverage core components such as **API Gateway**, **AWS Certificate Manager**, **IAM**, **S3**, **Lambda**, **CloudFormation**, **CloudFront**, **DynamoDB**, **Route 53**, **CloudWatch**, and **SAM CLI** to automate, scale, and optimize the cost of your system.

#### Overall Architecture

Below is the overall architecture of the system.  
     ![Overall Architecture](/images/fcjfashionshop_drawio.png)

- **Frontend:** Uses a Hugo theme, stored statically on Amazon S3 and distributed via CloudFront.
- **Backend:** Communicates via RESTful API with API Gateway and processes business logic with AWS Lambda.
- **Database:** Uses DynamoDB for dynamic, easily scalable data storage.
- **Infrastructure Management:** CloudFormation automatically creates and configures AWS resources; SAM CLI is used for deploying and automating serverless infrastructure.
- **Domain & Operations Management:** Route 53 manages domain/DNS; CloudWatch monitors, logs, and provides alerts for the entire system; AWS Certificate Manager provides free SSL certificates for the website.

#### Data Flow Diagram

The following diagram illustrates the main data flow and interactions between system components.  
*(Insert data flow or sequence diagram here)*

#### List of AWS Services Used

- **API Gateway:** Creates REST APIs for frontend-backend communication.
- **S3:** Stores static website assets and resources.
- **Lambda:** Handles serverless backend logic.
- **DynamoDB:** Dynamic, scalable NoSQL database.
- **CloudFormation:** Infrastructure as Code (IaC) management.
- **Route 53:** Domain registration and DNS configuration.
- **CloudFront:** Global content delivery (CDN), accelerates access and enhances security.
- **AWS Certificate Manager:** Free SSL certificate provisioning and management.
- **IAM:** AWS account management and resource access control.
- **CloudWatch:** System monitoring, logging, and alerting.
- **SAM CLI:** Automates deployment of serverless resources.

#### Key Features of the Website

- **Fully serverless architecture on AWS.**
- Deploy a secure, auto-scaling dynamic website.
- User-friendly interface with Hugo.
- Dynamic backend using RESTful APIs via API Gateway & Lambda.
- Dynamic data storage with DynamoDB.
- Real-time data processing with Lambda & DynamoDB.
- Integrated monitoring, logging, DNS, CDN, and SSL auto-configuration.
- Infrastructure as Code (IaC) with CloudFormation & SAM CLI.

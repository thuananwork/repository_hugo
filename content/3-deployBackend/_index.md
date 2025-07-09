---
title: "Deploying the Backend"
date: 2023-10-25
weight: 3
chapter: false
pre: " <b> 3. </b> "
---

Deploying the backend for your dynamic e-commerce website is accomplished using the **AWS SAM CLI** in combination with **CloudFormation**. With these tools, you can easily deploy serverless services such as **API Gateway**, **Lambda**, and **DynamoDB**.

#### Main Tools Used:
- **SAM CLI**: A command-line tool for developing, testing, and deploying serverless applications. SAM CLI makes it easy to deploy API Gateway, Lambda functions, and other serverless resources on AWS.
- **CloudFormation**: An infrastructure as code service that allows you to automate the deployment and management of AWS resources.

In this section, you will learn how to deploy a serverless backend for your website using SAM CLI, including the creation of resources such as **API Gateway**, **Lambda**, and **DynamoDB**.

{{% notice info %}}
Note: Please ensure you have completed the environment preparation steps (including installing the SAM CLI and configuring AWS IAM) before starting the backend deployment.
{{% /notice %}}

### Contents
- [Deploying the backend with SAM CLI/CloudFormation](3.1-deploy-backend/)
- [Managing backend resources with CloudFormation/SAM CLI](3.2-check-status-log-backend/)

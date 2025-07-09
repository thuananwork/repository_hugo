---
title : "Deploying the Backend with SAM CLI/CloudFormation"
date : 2025-07-06
weight : 4
chapter : false
pre : " <b> 3.1 </b> "
---

#### Deploying the Backend with SAM CLI/CloudFormation

In this section, you will deploy the backend for your dynamic e-commerce website using **SAM CLI** and **CloudFormation**. We will use the provided **`template.yaml`** file in your project to automatically create resources such as **API Gateway**, **Lambda**, and **DynamoDB**.

#### Step 1: Configure AWS CLI

Before using **SAM CLI** for deployment, you need to configure **AWS CLI** with your AWS account credentials. This allows **SAM CLI** to use the access rights granted to your IAM User.

1. **Run the `aws configure` command**:
   - Open your terminal and enter the following command to configure AWS CLI:

          aws configure

2. **Enter your configuration information**:
   - **AWS Access Key ID**: Enter the **Access Key ID** generated when creating your IAM User.
   - **AWS Secret Access Key**: Enter the **Secret Access Key** associated with your Access Key ID.
   - **Default region name**: Enter `ap-southeast-1` (Singapore).
   - **Default output format**: You can enter `json` or leave it as the default (`None`).
![Error image](/images/aws_configure.png)

   - Once finished, AWS CLI will save the configuration in the `~/.aws/credentials` file (Linux/macOS) or `C:\Users\<username>\.aws\credentials` (Windows).

#### Step 2: Deploy the Backend with SAM CLI

1. **Check the `template.yaml` file**:
   - If you don’t have a **`template.yaml`** file, check your project directory. This file defines resources like **API Gateway**, **Lambda**, and **DynamoDB**.
   - If the file exists, make sure it is correctly configured for the resources you need.

2. **Build the project**:
   - After ensuring that **`template.yaml`** is in your project,
   - Navigate to your backend project folder and use **SAM CLI** to build:

          sam build

   - If you see **Build Succeeded**, you have successfully installed and configured SAM CLI.
  ![Error image](/images/build_success_samcli.png)

3. **Validate the Template**:
   - Check your `template.yaml` configuration to ensure there are no syntax or configuration errors:
   - Run **sam validate** to check your template:

          sam validate

   - If you see the message below, your **template.yaml** is valid.
      ![Error image](/images/sam_validate.png)

4. **Deploy resources to AWS**:
   - After building and validating, deploy resources to AWS using:

          sam deploy --guided

   - When using **SAM CLI** to deploy, you’ll be prompted for configuration options. Suggested values:

     - **Stack Name**: `sam-app`
     - **AWS Region**: `ap-southeast-1`
     - **Confirm changes before deploy**: `y` 
     - **Allow SAM CLI IAM role creation**: `y` 
     - **Disable rollback**: `n` (do not disable rollback)
     - **ExpressApiFunction has no authentication. Is this okay?**: `y` 
     - **Save arguments to configuration file**: `y` 
     - **SAM configuration file**: Press **Enter** 
     - **SAM configuration environment**: Press **Enter** 

      ![Error image](/images/deploy_this_changeset.png)

     - **Deploy this changeset**: `y`
     - Wait about 5 minutes for serverless resources (API Gateway, Lambda, DynamoDB, etc.) to be set up from your machine to AWS.

      ![Error image](/images/create_sam_app_success.png)

5. **Verify Deployment**:
   - After successful deployment, SAM CLI will provide information about the resources created. You can check **API Gateway**, **Lambda function**, **S3**, **CloudFormation**, and **DynamoDB** in the AWS Management Console to confirm that everything has been set up correctly.
{{% notice tip %}}
Your backend has been successfully deployed! Resources like API Gateway, Lambda function, and DynamoDB have been automatically created. You can check them in the AWS Console.
{{% /notice %}}
     - Go to [API Gateway](https://ap-southeast-1.console.aws.amazon.com/apigateway/main/) to see your API Gateway.

      ![Error image](/images/create_API_gateway.png)

     - Go to [Lambda function](https://ap-southeast-1.console.aws.amazon.com/lambda/home/) to see your Lambda functions.

      ![Error image](/images/create_auto_lambda.png)

     - Go to [Amazon S3](https://ap-southeast-1.console.aws.amazon.com/s3/home) to see your S3 buckets.

      ![Error image](/images/access_s3_after_setup_samcli.png)

     - Go to [CloudFormation](https://ap-southeast-1.console.aws.amazon.com/cloudformation/home) to see your CloudFormation stacks.

      ![Error image](/images/create_auto_cloud_foumation.png)

     - Go to [DynamoDB](https://ap-southeast-1.console.aws.amazon.com/dynamodbv2/home?region=ap-southeast-1#tables) to see your DynamoDB tables.

      ![Error image](/images/create_auto_dynamoDB.png)


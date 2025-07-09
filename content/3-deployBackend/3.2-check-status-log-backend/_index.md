---
title : "Checking Backend Status and Logs After Deployment"
date : 2023-10-25
weight : 5
chapter : false
pre : " <b> 3.2 </b> "
---

#### Checking Backend Status and Logs After Deployment

After deploying your backend on AWS using SAM CLI and CloudFormation, the next crucial step is to **check the resource status** and **review backend logs** to ensure all components are functioning correctly.

- Make sure that API Gateway, Lambda, DynamoDB, etc. have been created successfully and are running.
- Quickly identify and resolve deployment or logic errors if any issues occur.
- Prepare for API testing using Postman or your frontend application.

1. **Check CloudFormation Stack and Resource Status**

   - Access the [AWS CloudFormation Console](https://console.aws.amazon.com/cloudformation).
   - Select the recently deployed Stack (e.g., `sam-app`).

![Stack-sampsamdeloy](/images/choose_sam_app.png)

   - In the Status tab, if the status is `CREATE_COMPLETE` or `UPDATE_COMPLETE`, your deployment was successful.

![Stack-sampsamdeloy](/images/status_completele_sam_app.png)

   - In the Resources tab, view the list of created resources (API Gateway, Lambda, DynamoDB, S3, etc.).

{{% notice tip %}}
If you see a status like `ROLLBACK` or `FAILED`, click on the Events tab to view error details and identify the root cause.
{{% /notice %}}

2. **View Lambda Logs with CloudWatch**

   - In the [AWS Console](https://aws.amazon.com/console/), go to Lambda → select your deployed function.
   ![Click-lambda-sammapp](/images/click_lambda_samapp.png)

   - Scroll down and click on the **Monitor** tab, then select **View CloudWatch logs** to access detailed logs.
   ![Monitor](/images/Monitor.png)

   - Scroll down and click on the **Log streams** tab, then select the first log stream.
   ![LogSrteam](/images/log_steams.png)

   - Each time a request is made (GET/POST, etc.), Lambda writes logs to CloudWatch. Here you can:
     - View received requests.
     - Check returned responses.
     - Debug issues if the code crashes or returns a 500 error.

3. **Verify API Gateway Functionality**

   - In the [AWS Console](https://aws.amazon.com/console/), go to API Gateway → select the API you just created.
      ![API Gateway](/images/api_sam_app.png)

   - Go to **Stages** → select the relevant **stage** → choose `prod`.

   - Copy the Invoke URL to prepare for testing with Postman/curl in the next step.
      ![Stages Prod](/images/stages_prod.png)

{{% notice info %}}
Once you've verified that all resources are functioning properly and there are no critical errors in the logs, you're ready to test your backend API using Postman or integrate with your frontend!
{{% /notice %}}

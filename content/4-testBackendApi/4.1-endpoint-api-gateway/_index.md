---
title : "Retrieving the API Gateway Endpoint"
date : 2023-10-25
weight : 5
chapter : false
pre : " <b> 4.1 </b> "
---

#### Retrieving the API Gateway Endpoint

After deploying the backend using SAM CLI/CloudFormation, the system will automatically generate an endpoint address for your API Gateway. This is the address you will use to send test requests via Postman, curl, or integrate with your frontend later.

{{% notice tip %}}
**Note:**  
Use the previously saved endpoint if you already have it.
{{% /notice %}}

**Steps to follow:**

1. **Access the AWS Management Console**

   - Log in to the [AWS Console](https://console.aws.amazon.com/).
   - Select **API Gateway** from the list of AWS services.

2. **Select the Recently Deployed API**

   - In the API Gateway interface, you'll see a list of existing APIs.
   - Find and click on the name of the API you just deployed.
   - ![API Gateway](/images/api_sam_app.png)

3. **Retrieve the Endpoint from Stages**

   - In the left-hand menu, select **Stages**.
   - Click on the stage you have deployed (e.g., `prod`).
   - At the top, you'll see the **Invoke URL**. This is the API Gateway endpoint you will use for testing.
   - Copy this URL.
   - ![Stages Prod](/images/stages_prod.png)

4. **Verify the Endpoint**

- You can copy this endpoint and paste it into your browser or Postman to check the basic response.
- Typically, if you haven't configured specific resources (e.g., `/products`), accessing the root endpoint will return a “Missing Authentication Token” error or HTTP 403. This is normal—just make sure to append the correct resource route when testing your API.

{{% notice tip %}}
**Tip:**  
It is recommended to save this endpoint in your project README or personal notes to avoid having to revisit the AWS Console multiple times during API testing.
{{% /notice %}}

---
title : "Testing Backend APIs with Postman"
date : 2023-10-25
weight : 4
chapter : false
pre : " <b> 4 </b> "
---

#### Testing Backend APIs with Postman

After successfully deploying your backend with **API Gateway** and **Lambda**, the next step is to test your APIs to verify that the backend system is functioning correctly before integrating with the frontend.

**Postman** is a powerful and widely-used tool that allows you to send requests (GET, POST, PUT, DELETE, ...) to API endpoints, view responses, verify processing logic, and debug errors.

You can download Postman here: [**Download Postman**](https://www.postman.com/downloads/)

**Objectives of this section:**
- Guide you on how to retrieve the **API Gateway endpoint** that you just deployed on AWS to use with Postman.
- Practice sending **GET/POST** requests to the API, analyze the returned responses to verify backend correctness.
- Identify and troubleshoot common errors encountered during API testing.

**This section covers:**
1. **Retrieving the API Gateway endpoint:**  
   Instructions on how to locate and copy the endpoint URL from the AWS Console for API testing purposes.
2. **Sending GET/POST requests to verify backend responses:**  
   Step-by-step guidance on how to send GET/POST requests with Postman, enter payload data, and review backend responses.

{{% notice info %}}
**Note:**  
Before testing APIs with Postman, make sure that the backend has been deployed successfully and there are no errors from previous steps (CloudFormation/Lambda must be in a successful state).
{{% /notice %}}

**By the end of this section, you will:**
- Know how to obtain the API Gateway endpoint for testing.
- Be proficient in using Postman to send GET/POST requests to your backend.
- Be able to analyze and verify API responses, and be ready to connect your tested backend with the frontend.


### Contents
- [Retrieve the API Gateway endpoint](4.1-api-gateway-endpoint/)
- [Send GET/POST requests to verify backend responses](4.2-get-post-response/)

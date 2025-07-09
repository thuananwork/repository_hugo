---
title : "Sending GET/POST Requests to Verify Backend Responses"
date : 2023-10-25
weight : 6
chapter : false
pre : " <b> 4.2 </b> "
---

#### Sending GET/POST Requests to Verify Backend Login Responses

After obtaining the API Gateway endpoint, you need to send **POST** and **GET** requests to the API to confirm that the backend is functioning properly. This is typically done using **Postman**, the most popular API testing tool.

**Steps to follow:**

1. **Testing POST Method with Postman**

   - Open Postman, select **New** → **HTTP Request**.
   - Set the method to **POST**.
   - Enter the full endpoint URL, for example:
     ```
     https://ars3538v1i.execute-api.ap-southeast-1.amazonaws.com/Prod/api/users
     ```
   - Switch to the **Body** tab → select **raw** → choose **JSON**.
      ![Test-api-postman](/images/test_api_postman.png)

   - **Enter sample data in the body as follows:**
     ```json
     {
       "username": "AdminUser",
       "email": "firstcloudjourney@example.com",
       "password": "AdminUser123@",
       "firstName": "Admin",
       "lastName": "User",
       "isAdmin": true,
       "googleId": null,
       "avatar": "https://i.imgur.com/avatar.jpg",
       "phone": "0912345678",
       "address": "",
       "isDeleted": false
     }
     ```
   - Click **Send** to submit the request.
   - If the API works correctly, you will receive a confirmation response.
   - Copy the returned `token` to use for subsequent requests.
      ![Test-api-postman](/images/body_raw_postman_method_get.png)

  {{% notice tip %}}
  If the API requires authentication (`API Key`, Bearer Token, etc.) or custom headers, add them in the **Headers** tab of Postman before sending the request!
  {{% /notice %}}

2. **Testing GET Method for Login with Postman**

   - Go to [DynamoDB](https://ap-southeast-1.console.aws.amazon.com/dynamodbv2/home?region=ap-southeast-1) on the AWS Console.
   - Select the **ShopUser** table.
      ![Test-api-postman](/images/select_shopuser_db.png)

   - Choose **Explore table items** to check the data for the newly created user.
      ![Explore table item](/images/explore_table_item.png)

   - Scroll down and edit the **isAdmin** field for the created user to `true`.
      ![IsAdmin](/images/isAdmin_true.png)

   - Create a new request in Postman, set the method to **GET**.
   - Enter the full endpoint URL, for example:
     ```
     https://ars3538v1i.execute-api.ap-southeast-1.amazonaws.com/Prod/api/users
     ```
   - In the Authorization section, choose: **Bearer Token**.
   - In the Token field: paste the previously saved token.
   - Click **Send** to submit the request.
      ![Test-api-postman-get-method](/images/test_api_postman_get_method.png)
   - If the API is functioning correctly, you will receive a response with the user data from the database.
   - Check the HTTP status code (should be 200 OK) and the response body.
      ![Test-api-backend-success](/images/test_api_backend_success.png)

  {{% notice tip %}} 
  You can test other project functionalities by reviewing the code to find the respective API URLs.
  {{% /notice %}}

3. **Analyzing Results and Handling Common Errors**

   - If you receive the correct response data → the backend is working as expected.
   - If you encounter errors like `403 Forbidden`, `401 Unauthorized`, or `Missing Authentication Token`:
     - Verify the endpoint and ensure the correct resource route is used.
     - Check the API Gateway configuration and mapping templates.
     - Review the Lambda logs in CloudWatch for detailed error information.
   - If you receive a `500 Internal Server Error`:
     - This is often due to an error in the Lambda code. Go to CloudWatch logs to debug.

**Conclusion:**  
Testing the API using POST/GET requests is an essential step to confirm that the backend is functioning correctly before integrating with the frontend or deploying to production. If errors occur, check CloudWatch logs or review the API Gateway and Lambda configurations for timely troubleshooting.

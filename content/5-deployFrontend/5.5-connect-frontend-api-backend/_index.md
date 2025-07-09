---
title : "Connect the Frontend to the Backend API"
date : 2023-10-25
weight : 10
chapter : false
pre : " <b> 5.5 </b> "
---

#### Connect the Frontend to the Backend API

After uploading your website to S3 and successfully enabling static hosting, the final step is to **connect the frontend to the backend through the API Gateway endpoint** that you previously tested. This step is crucial for your website to fetch/send dynamic data and function as a modern e-commerce application.

**Steps to follow:**

1. **Identify the Backend API Endpoint**

   - Use the API Gateway endpoint obtained in the backend testing step.  
     For example:
     ```
     https://ars3538v1i.execute-api.ap-southeast-1.amazonaws.com/Prod/api/users
     ```

2. **Update the Endpoint Configuration in the Frontend Source Code**

   - Open your frontend project folder.
   - Open the `.env` file in the **Frontend** directory.
   - Open the `index.js` file in the **Frontend** directory.
   - Paste the copied API Gateway URL into the base URL variable in your code.
    ![edit_api_env](/images/edit_api_env.png)
    ![edit_api_env](/images/edit_api_index.png)

**Conclusion:**  
Once you have successfully connected the frontend to the backend, your website is ready to operate dynamically with real data from AWS. You can proceed to configure a custom domain, enable SSL security, or deploy CloudFront for further optimization.

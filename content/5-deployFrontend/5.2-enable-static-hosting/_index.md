---
title : "Enable Static Hosting, Configure CORS, and Set S3 Bucket Permissions"
date : 2023-10-25
weight : 7
chapter : false
pre : " <b> 5.2 </b> "
---

### Enable Static Hosting, Configure CORS, and Grant Permissions for the S3 Bucket

After uploading your frontend source code to the S3 Bucket, you need to **enable static website hosting**, set up the index and error documents, configure CORS policy, and grant public read permissions so your website runs stably, is accessible from browsers, and can connect to the backend API.

#### Step 1: Enable Static Hosting and Configure CORS

1. **Enable static website hosting for the bucket**
   - Go to your frontend bucket in the [AWS S3 Console](https://s3.console.aws.amazon.com/s3/).
   - Select the **Properties** tab.
   - Scroll down to **Static website hosting** and click **Edit**.
   ![static_website_hosting](/images/static_website_hosting.png)
   - Select **Enable**.
   - Enter `index.html` in the **Index document** field.
   - You may also enter `index.html` for the **Error document** field (recommended for SPA deployments).
   - Save the settings.
   ![static_website_hosting](/images/enable_static_website_hosting.png)
   - AWS will generate a **Website endpoint** like:
     ```
     http://fcjfashionshop.com.s3-website-ap-southeast-1.amazonaws.com
     ```
   - Copy this URL for the next step.
   ![bucket_website_hosting](/images/bucket_website_hosting.png)

2. **Configure CORS for the bucket**
   - Go to the **Permissions** tab → scroll down to **CORS configuration** → click **Edit**.
   ![cors](/images/cors.png)
   - Add the following sample configuration (JSON) to allow the frontend to access resources or upload images to S3 from other domains:
     ```json
     [
       {
         "AllowedOrigins": ["*"],
         "AllowedMethods": ["GET", "HEAD", "PUT", "POST", "DELETE"],
         "AllowedHeaders": ["*"]
       }
     ]
     ```
   - To restrict to a specific domain for better security:
     ```json
     [
       {
         "AllowedOrigins": ["https://your-domain.com"],
         "AllowedMethods": ["GET", "HEAD"],
         "AllowedHeaders": ["*"]
       }
     ]
     ```
   - Click **Save** to apply.


#### Step 2: Grant Public Permissions to the S3 Bucket

1. **Set permissions for the Frontend Bucket**
   - Go to the **Permissions** tab of the bucket, scroll down to **Bucket policy** → **Edit**.
   ![click_edit_bucket_policy](/images/click_edit_bucket_policy.png)
   - Add a policy to allow public read access, for example:
     ```json
     {
       "Version": "2012-10-17",
       "Statement": [
         {
           "Sid": "PublicReadGetObject",
           "Effect": "Allow",
           "Principal": "*",
           "Action": "s3:GetObject",
           "Resource": "arn:aws:s3:::fcjfashionshop.com/*"
         }
       ]
     }
     ```
   - Click **Save** to apply.
   ![edit_permission_bucket_avata](/images/edit_permission_bucket_avata.png)

2. **Set permissions for the avatar upload bucket (if any)**
   - Go to the **Permissions** tab of the bucket → **Bucket policy**.
   ![click_bucket_myfrontend](/images/permission_upload_avata.png)
   - Add a policy to allow public read access, for example:
     ```json
     {
       "Version": "2012-10-17",
       "Statement": [
         {
           "Sid": "PublicReadGetObject",
           "Effect": "Allow",
           "Principal": "*",
           "Action": "s3:GetObject",
           "Resource": "arn:aws:s3:::uploads-avatars-2025/*"
         }
       ]
     }
     ```
   - Click **Save** to apply.
   ![edit_permission_bucket_avata](/images/edit_permission_bucket_avata.png)


#### Step 3: Verify Website Operation

- Use the **Website endpoint** link to test your website.
- If `index.html` loads successfully, your website is running on S3.
  ![front_website_s3](/images/front_s3_website.png)
- If you encounter 403/404 errors:
  - Double-check your bucket policy permissions.
  - Make sure static hosting is enabled.
  - Verify that your index/error file names are correct.

{{% notice warning %}}
**Note:**  
You should only use `"*"` for development/testing. When deploying to production, always specify your real website domain in `AllowedOrigins` for better security.
{{% /notice %}}


**Conclusion:**  
Properly enabling static hosting, configuring CORS, and setting public permissions will ensure your frontend website on S3 operates reliably, can call the backend API, and provides optimal load speed and user experience.

---
title : "Deploy Frontend"
date : 2023-10-25
weight : 5
chapter : false
pre : " <b> 5 </b> "
---

### Deploy Frontend

After the backend is ready and has passed all tests, the next step is to **deploy the website frontend to AWS S3** as a static website, optimizing for both cost and page load speed.  
At the same time, you will configure hosting, caching, and CORS so the frontend works smoothly and securely when connecting to the backend API.

**Objectives of this section:**
- Guide you through uploading and deploying your frontend code to an AWS S3 Bucket.
- Enable static website hosting, configure cache and CORS so your frontend is accessible, stable, and secure.
- **Grant public permissions to your S3 Bucket** so the website can be accessed publicly.
- Connect the frontend to the backend API endpoint that has been successfully tested in previous steps.

{{% notice info %}}
**Note:**  
Make sure you have installed **yarn** in your project directory.
{{% /notice %}}

**By the end of this section, you will:**
- Successfully deploy your frontend website to S3, ensuring public accessibility.
- Master hosting, caching, and CORS configuration—enabling your website to load quickly, safely, and remain compatible with the backend.
- **Know how to grant public permissions to your S3 bucket, avoiding 403 errors when accessing your website.**
- Be ready to upgrade your system with custom domains, CloudFront, or other new features in the next steps.

### Contents
- [Deploy frontend to S3 Bucket](5.1-frontend-s3/)
- [Enable static hosting, configure CORS](5.2-enable-static-hosting/)
- [Grant public permissions to S3 Bucket](5.3-s3-bucket-permission3/)
- [Configure Google OAuth2 Client ID and Client Secret](5.4-clientid-clientserver/)
- [Connect frontend with backend API](5.5-connect-frontend-api-backend/)

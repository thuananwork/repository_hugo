---
title : "Configure Google OAuth2 Client ID and Client Secret"
date : 2023-10-25
weight : 9
chapter : false
pre : " <b> 5.4 </b> "
---

#### Configure Google OAuth2 Client ID and Client Secret

After creating the Google OAuth2 Project and enabling the required APIs during the environment preparation step, you need to create an **OAuth2 Client ID and Client Secret** to integrate Google Sign-In into your e-commerce system.

**Steps to follow:**

1. **Access Google Cloud Console**
   - Open [Google Cloud Console](https://console.cloud.google.com/) and select the correct project you created earlier.
 ![api_services](/images/api_services.png)

2. **Create OAuth2 Client ID**
   - Navigate to **APIs & Services** → **Credentials**.
![credentials](/images/credentials.png)

   - Click **+ Create Credentials** → **OAuth client ID**.
![create_oAuth_client_id](/images/oAuth_client_id.png)

   - Click **Configure consent screen**.
![configure_consent_screen](/images/configure_consent_screen.png)

   - Click **Get Started**.
![get_started](/images/get_started.png)

   - Fill in the following information:
     - App name: `FcjFashionShop`
     - User support email: **Enter your email**
     - Click **Next**
![information_google_oauth](/images/information_google_oauth.png)

     - Email addresses: **Enter your email**
     - Click **Next**
![contact_information](/images/contact_information.png)

     - Check **I agree to the Google API Services: User Data Policy.**
     - Click **Continue** and then **Create**
![finish_create_oauth](/images/finish_create_oauth.png)

   - In **Metrics**, click **Create OAuth client**
![select_create_oauth_client](/images/select_create_oauth_client.png)

   - For Application type, select **Web application**
   - Name: `FcjFashionShop`
![info_oauth_client_id](/images/info_oauth_client_id.png)

   - In **Authorized JavaScript origins**
     - Click **Add URI** to add a new URL
     - Paste your **S3 Bucket website endpoint** (the static website URL you copied earlier)
   - In **Authorized redirect URIs**
     - Click **Add URI** to add a new URL
     - Paste the **Invoke URL of your API Gateway** that you copied earlier, replacing **your-API-Gateway-domain** in the example below
     - Click **Create**
      ```
      your-API-Gateway-domain/api/users/auth/google/callback
      ```
   ![create_oauth_client_id](/images/create_oauth_client_id.png)

     - **ClientID** and **ClientSecret** have been created successfully. Copy and save them for later use.
   ![success_clientid_client_secret](/images/success_clientid_client_secret.png)

{{% notice info %}}
Authorized JavaScript origins: this is your frontend domain (the S3 Static Website endpoint).  
Authorized redirect URIs: this is the backend endpoint (API Gateway) that handles the Google callback.
{{% /notice %}}

{{% notice warning %}}
**Security note:**  
Never publish your **Client Secret** on Github or anywhere public!
{{% /notice %}}

**Conclusion:**  
After completing these steps, you have all the necessary information to configure Google OAuth2 for both backend and frontend, and are ready to implement Google Sign-In for your e-commerce website project on AWS.

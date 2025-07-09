---
title : "Create Google OAuth2 Project"
date : 2023-10-25
weight : 7
chapter : false
pre : " <b> 2.5 </b> "
---

#### Create Google OAuth2 Project

To integrate Google Sign-In functionality into your e-commerce website, you need to register and create a Google OAuth2 Project.

**Steps to follow:**

1. **Access Google Cloud Console**

   - Open [Google Cloud Console](https://console.cloud.google.com/).
   - Log in with your Google account.

2. **Create a New Project (if you don’t have one yet)**

   - Click **Select a project** > **New Project**.
![create_project_google_auth](/images/create_project_google_auth.png)

   - Enter a project name, choose the location, and click **Create**.
![create_FcjFashionShop_ggouth](/images/create_FcjFashionShop_ggouth.png)

   - After the project is created, click **Select a project**.
![create_FcjFashionShop_ggouth](/images/select_FcjFashionShop.png)

   - Select the newly created **FcjFashionShop** project.
![create_FcjFashionShop_ggouth](/images/select_project_FcjFashionShop.png)

3. **Enable Google OAuth2 API**
   - Under **Quick access**, select **API & Services**.
   - Or, in the left menu, select **APIs & Services** → **Library**.
![api_services](/images/library.png)

   - Type `Google+ API` in the search box and press **Enter**.
![search_google_API](/images/search_google_API.png)

   - Click the **Google+ API** service.
![search_google_API](/images/select_google_api.png)

   - Click **Enable**.
![search_google_API](/images/enable_google_api.png)

{{% notice tip %}} 
At this preparation step, you only need to create the Google OAuth2 Project and enable the necessary APIs. Creating the OAuth Consent Screen and configuring the Client ID/Client Secret will be done in later steps, after you have your actual domain/frontend URL.
{{% /notice %}}

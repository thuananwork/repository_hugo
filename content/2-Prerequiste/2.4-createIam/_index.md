---
title: "Create Account and Configure IAM"
date: 2023-10-25
weight: 6
chapter: false
pre: " <b> 2.4 </b> "
---

#### Create Account and Configure IAM

AWS Identity and Access Management (IAM) allows you to securely manage access to AWS resources. In this step, you will create an IAM user, grant appropriate permissions, and configure an Access Key for use in subsequent steps of the workshop.

#### Create IAM User

1. Go to the [AWS Management Console](https://aws.amazon.com/console/) and navigate to the **IAM** service.

   ![Error image](/images/iam_access.png)

2. In the left navigation pane, select **Users** and click **Create users** from the left menu.

   ![Error image](/images/create_user.png)

3. Create the IAM user:
   - Set the User name as `AdminUser` (or any name you prefer).
   - Check **Provide user access to the AWS Management Console – optional**.
   - Under **User type**, select **I want to create an IAM user**.
   - Choose **Custom password** – enter your password.
   - Uncheck **Users must create a new password at next sign-in – Recommended**.
   - Click **Next**.

   ![Error image](/images/create_info_iam_user_1.png)
   ![Error image](/images/create_info_iam_user_2.png)

4. Grant permissions to the user:
   - Select **Attach policies directly**.
   - Search for and select the following policies: **AWSCloudFormationFullAccess, AmazonDynamoDBFullAccess, AWSLambda_FullAccess, AmazonS3FullAccess, AmazonAPIGatewayAdministrator, IAMFullAcces** to grant the necessary project permissions.
   - Scroll down and click **Next**.

   ![Error image](/images/add_user_permissions.png)

5. Review the information on the Permissions summary page.
   - Click **Create user** to create the AWS IAM account.

   ![Error image](/images/create_user_iam.png)

6. The IAM user has been created successfully.
   - Click **Download .csv file** to save the account credentials.
   - Click **View user** to see detailed information.

   ![Error image](/images/create_user_iam_success.png)

#### Create Access Key

1. Display and save the Access Key and Secret Access Key:
   - Click **Create access key** to generate an access key for the user.

   ![Error image](/images/create_access_key.png)

   - Check **Command Line Interface (CLI)** and click **Next**.
   - Click **Show** to reveal the **Secret access key** value.

   ![Error image](/images/command_line_interface.png)

   - Click **Create access key**.

   ![Error image](/images/create_access_key_lasted.png)

   - Click **Download .csv file** to store the credentials.
   - Then click **Done**.

---
title: "Clean Up Resources"
date: 2023-10-25
weight: 8
chapter: false
pre: "<b>8. </b>"
---

### Clean Up Resources

After completing the demo and project experience, you should **clean up your AWS resources** to avoid incurring unnecessary charges.  
{{% notice tip %}}
It is recommended to delete S3 Buckets before deleting the CloudFormation Stack to ensure the stack is deleted successfully!
{{% /notice %}}

#### 1. Delete S3 Buckets for Frontend and Upload Files

1. Go to the [AWS S3 Console](https://s3.console.aws.amazon.com/s3/home).
2. Select each bucket you created for the frontend and avatar uploads (e.g., `fcjshop-frontend-website`, `uploads-avatars-2025`).
3. Click `Empty`.

     ![Delete S3 bucket](/images/empty_fcjfashioshop_S3.png)
     ![confirm_empty_fcjfashioshop_S3](/images/confirm_empty_fcjfashioshop_S3.png)

4. Select **fcjshop-frontend-website** again.
5. Click **Delete**.

     ![select_delete_fcjfashion_shop](/images/select_delete_fcjfashion_shop.png)
    ![select_delete_fcjfashion_shop](/images/delete_fcjfashion.png)

- Do the same for **uploads-avatars-2025**.

#### 2. Delete the Stack via CloudFormation

1. Go to the [CloudFormation Console](https://console.aws.amazon.com/cloudformation/home).
2. Select the **stack** you deployed (e.g., `fcjfashioshop.com` or your stack's name).
3. Click **Delete**.
     ![delete_stack](/images/delete_samap_cloudformation.png)

4. Confirm the delete action.
     ![deletconfirm_delete_samappe_stack](/images/confirm_delete_samapp.png)
5. Repeat for any other **Stacks** you deployed.

{{% notice info %}}
**Note:**  
After deleting the CloudFormation stack, all backend resources such as Lambda, API Gateway, DynamoDB tables, IAM roles, etc. will be automatically removed.
{{% /notice %}}

**Conclusion:**  
You have cleaned up all AWS resources used for this project, ensuring there are no unwanted charges. If you want to try again, simply redeploy from scratch!

{{% notice tip %}}
Check the **AWS Billing** page to ensure there are no remaining chargeable services.
{{% /notice %}}

---
title : "Cấu hình Google OAuth2 Client ID và Client Secret"
date : 2023-10-25
weight : 9
chapter : false
pre : " <b> 5.4 </b> "
---

#### Cấu hình Google OAuth2 Client ID và Client Secret

Sau khi đã tạo Google OAuth2 Project và bật các API cần thiết ở bước chuẩn bị môi trường, bạn cần tạo **OAuth2 Client ID và Client Secret** để tích hợp đăng nhập Google cho hệ thống thương mại điện tử.

**Các bước thực hiện:**

1. **Truy cập vào Google Cloud Console**
   - Mở [Google Cloud Console](https://console.cloud.google.com/) và chọn đúng project đã tạo ở bước trước.
 ![api_services](/images/api_services.png)


2. **Tạo OAuth2 Client ID**
   - Vào **APIs & Services** → **Credentials**.
![credentials](/images/credentials.png)

   - Click vào **+ Create Credentials** → **OAuth client ID**.
![create_oAuth_client_id](/images/oAuth_client_id.png)

   - Click vào **Configure consent srcreen**.
![configure_consent_screen](/images/configure_consent_screen.png)

   - Click vào **Get Started**.
![get_started](/images/get_started.png)

   - Bạn điền các thông tin như sau:
     - App name: `FcjFashionShop`
     - User support email: **Nhập email của bạn**
     - Nhấn vào **Next**
![information_google_oauth](/images/information_google_oauth.png)

     - Email addresses: **Nhập email của bạn**.
     - Nhấn vào **Next**
![contact_information](/images/contact_information.png)

     - Tích chọn **I agree to the Google API Services: User Data Policy.**
     - Chọn **Continue** và chọn **Create**
![finish_create_oauth](/images/finish_create_oauth.png)

   - Tại **Metrics** click vào **Create OAuth client**
![select_create_oauth_client](/images/select_create_oauth_client.png)

   - Tại Application type chọn **Web application**
   -  Name: `FcjFashionShop`
![info_oauth_client_id](/images/info_oauth_client_id.png)

   - Tại **Authorized JavaScript origins**
     - Chọn **Add URI** để thêm URl mới
     - Dán URL của **S3 Bucket website endpoint** bạn đã copy trước đó
   - Tại **Authorized redirect URIs**
     - Chọn **Add URI** để thêm URl mới
     - Dán URL của **Invoke URL của API Gateway** bạn đã copy trước đó thay thế đoạn **your-API-Gateway-domain** trong command bên dưới
     - Nhấn **create**
      ```
      your-API-Gateway-domain/api/users/auth/google/callback
      ```
   ![create_oauth_client_id](/images/create_oauth_client_id.png)

     - **ClientID** và **ClientSecret** đã được tạo thành công, bạn hãy copy và lưu lại để dùng ở bước sau
   ![success_clientid_client_secret](/images/success_clientid_client_secret.png)

{{% notice info %}}
Authorized JavaScript origins: là domain frontend (S3 Static Website endpoint).
Authorized redirect URIs: là endpoint backend (API Gateway) xử lý callback Google.
{{% /notice %}}

{{% notice warning %}}
**Lưu ý bảo mật:**  
Không public **Client Secret** lên Github hoặc bất cứ đâu!  
{{% /notice %}}


**Kết luận:**  
Sau khi hoàn thành các bước này, bạn đã có đủ thông tin để cấu hình Google OAuth2 cho cả backend và frontend, sẵn sàng triển khai tính năng đăng nhập Google cho dự án website thương mại điện tử trên AWS.


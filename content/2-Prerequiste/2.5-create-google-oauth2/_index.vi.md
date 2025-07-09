---
title : "Tạo Google OAuth2 Project"
date : 2023-10-25
weight : 7
chapter : false
pre : " <b> 2.5 </b> "
---

#### Tạo Google OAuth2 Project

Để tích hợp chức năng đăng nhập Google (Google Sign-In) cho website thương mại điện tử, bạn cần đăng ký tạo 1 project Google OAuth2 Project.

**Các bước thực hiện:**

1. **Truy cập Google Cloud Console**

   - Mở [Google Cloud Console](https://console.cloud.google.com/).
   - Đăng nhập bằng tài khoản Google của bạn.

2. **Tạo mới một Project (nếu chưa có)**

   - Nhấn **Select a project** > **New Project**.
![create_project_google_auth](/images/create_project_google_auth.png)

   - Đặt tên project, chọn vị trí, nhấn **Create**.
![create_FcjFashionShop_ggouth](/images/create_FcjFashionShop_ggouth.png)

   - Tạo project thành công - click **Select a project**.
![create_FcjFashionShop_ggouth](/images/select_FcjFashionShop.png)

   - Chọn vào project **FcjFashionShop** vừa tạo.
![create_FcjFashionShop_ggouth](/images/select_project_FcjFashionShop.png)

3. **Kích hoạt API Google OAuth2**
   - Tại **Quick access** chọn vào mục **API & Services**.
   - Hoặc trong menu bên trái, chọn **APIs & Services** 
 ![api_services](/images/api_services.png)
 
   - Chọn **Library**. 
 ![api_services](/images/library.png)

   - Gõ `Google+ API` vào ô tìm kiếm và nhấn **Enter**.
![search_google_API](/images/search_google_API.png)

   - Chọn vào dịch vụ **Google+ API**.
![search_google_API](/images/select_google_api.png)

   - Bạn chọn **Enable**.
![search_google_API](/images/enable_google_api.png)

{{% notice tip %}} 
Bạn chỉ cần tạo Google OAuth2 Project và enable các API cần thiết ở bước chuẩn bị này. Việc tạo OAuth Consent Screen và cấu hình Client ID/Client Secret sẽ thực hiện ở các bước tiếp theo sau khi đã có domain/frontend URL cụ thể.
{{% /notice %}}
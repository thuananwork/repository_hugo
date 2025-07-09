---
title : "Cài đặt NodeJS"
date : 2023-10-25
weight : 3
chapter : false
pre : " <b> 2.1 </b> "
---

NodeJS là một môi trường chạy JavaScript mạnh mẽ và phổ biến, được sử dụng để phát triển các ứng dụng web động. Trong bước này, bạn sẽ cài đặt NodeJS trên các hệ điều hành để phát triển website thương mại điện tử động của mình.

#### Bước 1: Cài đặt NodeJS

1. **Tải NodeJS từ trang chính:**
   - Truy cập trang chính của NodeJS tại [Node.js](https://nodejs.org/) và tải phiên bản LTS cho hệ điều hành của bạn (Windows, macOS, hoặc Linux).
   - Tải bản **.msi** cho Windows, **.pkg** cho macOS hoặc **.tar.xz** cho Linux.

2. **Cài đặt NodeJS trên Windows:**
   - Sau khi tải file **.msi**, mở file và làm theo hướng dẫn cài đặt.
   - Chắc chắn rằng bạn đã tích chọn **Add to PATH** trong quá trình cài đặt.
   
3. **Cài đặt NodeJS trên macOS:**
   - Cài đặt thông qua **Homebrew**:
              brew install node

4. **Cài đặt NodeJS trên Linux (Ubuntu):**
   - Sử dụng lệnh sau để cài đặt NodeJS:

          sudo apt install nodejs


5. **Kiểm tra cài đặt:**
   - Sau khi cài đặt, mở terminal (hoặc Command Prompt trên Windows) và nhập lệnh sau để kiểm tra phiên bản NodeJS:

          node -v
   - Nếu cài đặt thành công, bạn sẽ thấy phiên bản NodeJS hiện ra.

   **Ví dụ**
   - Sau khi cài đặt, mở terminal (hoặc Command Prompt trên Windows) và nhập lệnh sau để kiểm tra phiên bản NodeJS:

          C:\Users\thuan>node -v
            v20.17.0

   {{% notice success %}}
   NodeJS đã được cài đặt thành công! Bạn có thể bắt đầu xây dựng các ứng dụng JavaScript cho frontend và backend của website.
   {{% /notice %}}

#### Bước 2: Cài đặt npm

1. **Npm (Node Package Manager)** là công cụ dùng để quản lý các thư viện và gói phần mềm trong dự án NodeJS.
   - Truy cập vào thư mục Frontend trong code và gõ lệnh:

          npm i
   
2. **Kiểm tra npm:**
   - Npm được cài đặt tự động khi bạn cài đặt NodeJS.
   - Kiểm tra phiên bản npm bằng lệnh:

          npm -v


3. **Cập nhật npm (nếu cần):**
{{% notice note %}}
Cập nhật npm (nếu cần)
{{% /notice %}}
  
          npm install -g npm


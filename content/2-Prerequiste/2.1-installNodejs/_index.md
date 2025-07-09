---
title: "Installing NodeJS"
date: 2023-10-25
weight: 3
chapter: false
pre: " <b> 2.1 </b> "
---

NodeJS is a powerful and popular JavaScript runtime environment, widely used for developing dynamic web applications. In this step, you will install NodeJS on your operating system to build your dynamic e-commerce website.

#### Step 1: Install NodeJS

1. **Download NodeJS from the official website:**
   - Visit the official NodeJS website at [Node.js](https://nodejs.org/) and download the LTS version for your operating system (Windows, macOS, or Linux).
   - Download the **.msi** file for Windows, **.pkg** for macOS, or **.tar.xz** for Linux.

2. **Install NodeJS on Windows:**
   - After downloading the **.msi** file, open it and follow the installation instructions.
   - Make sure to check **Add to PATH** during the installation process.

3. **Install NodeJS on macOS:**
   - Install via **Homebrew**:
         brew install node

4. **Install NodeJS on Linux (Ubuntu):**
   - Use the following command to install NodeJS:

         sudo apt install nodejs

5. **Verify the installation:**
   - After installation, open your terminal (or Command Prompt on Windows) and run the following command to check the NodeJS version:

         node -v
   - If the installation is successful, you will see the NodeJS version displayed.

   **Example**
   - After installation, open your terminal (or Command Prompt on Windows) and enter the following command to check the NodeJS version:

         C:\Users\thuan>node -v
         v20.17.0

   {{% notice success %}}
   NodeJS has been installed successfully! You can now start building JavaScript applications for both the frontend and backend of your website.
   {{% /notice %}}

#### Step 2: Install npm

1. **npm (Node Package Manager)** is a tool used to manage libraries and packages in NodeJS projects.

   - Open the Frontend directory in your project. 
   - Run the following command:

          npm i

2. **Check npm:**
   - npm is automatically installed when you install NodeJS.
   - Check the npm version with the command:

         npm -v

3. **Update npm (if needed):**
   {{% notice note %}}
   Update npm (if needed)
   {{% /notice %}}

         npm install -g npm

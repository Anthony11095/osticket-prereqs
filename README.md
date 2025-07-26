<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

## Prerequisites

Before beginning the osTicket installation, ensure you have the following:

- **Operating System**: Windows 10 (64-bit)
- **Virtualization**: Access to Microsoft Azure or any VM platform
- **Virtual Machine Specs**:
  - Name: `osticket-vm`
  - 4 vCPUs
  - Username: `labuser`
- **Required Software/Tools**:
  - osTicket Installation ZIP Package  
  - PHP (version 7.3.8)  
  - MySQL (version 5.5.62)  
  - IIS (Internet Information Services) with CGI enabled  
  - PHP Manager for IIS  
  - URL Rewrite Module  
  - VC++ Redistributable  
  - HeidiSQL (for MySQL GUI management)

> ⚠️ Ensure all software is downloaded and available before beginning the installation process.  
> Administrative privileges are required for setup.

<h2>Installation Steps</h2>

Image 1.

## 🔧 osTicket Virtual Machine Installation – Step-by-Step Instructions

This guide provides clear, structured steps to install and configure a virtual machine using Microsoft Azure, as part of the osTicket installation project.

<img width="1896" height="859" alt="creating a virtual machine for osticket part 1" src="https://github.com/user-attachments/assets/6b21324a-4e61-4df7-b002-6608fefcabf8" />

### 1. Create a Virtual Machine

- Go to the [Microsoft Azure Portal](https://portal.azure.com/).
- Navigate to **Virtual Machines** > **Create** > **Azure virtual machine**.
- Fill out the **Basics** tab:
  - **Subscription**: Choose your Azure subscription.
  - **Resource Group**: Create or select an existing resource group.
  - **Virtual machine name**: Enter a recognizable name (e.g., `osTicket-VM`).
  - **Region**: Select the closest or recommended data center.
  - **Availability options**: Leave as default unless required.
  - **Image**: Select `Windows 10 Pro`, or another supported OS image.
  - **Size**: Choose a size that meets your project needs.
  - **Administrator account**: Create a username and password.
- Click **Next** through the remaining configuration tabs or keep defaults.
- Click **Review + create**, then **Create**.

### 2. Confirm Deployment Completion

<img width="1907" height="864" alt="created virtual machine for osticket" src="https://github.com/user-attachments/assets/9c4425e7-ac0e-4b48-86c4-84f252cb68e8" />

- Wait for the VM deployment process to complete.
- You will see a confirmation message: **Your deployment is complete**.
- Click **Go to resource** to access the virtual machine's settings and details.

### 3. Configure Network and Connect

![IMG_7682](https://github.com/user-attachments/assets/2eb0c861-c8b2-4991-81dd-c956f59a19e7)

- In the **Virtual machines** section, locate and select your VM.
- Click **Connect**, then choose **RDP** to open the connection options.
- Set up your connection:
  - **IP Address**: Ensure it’s a public IP.
  - **Port**: Typically set to 3389.
  - Enable the checkbox to allow access through Windows Firewall.
- Download the `.rdp` file and open it to connect to the VM.

- ### 4. Log In to the Virtual Machine

![image](https://github.com/user-attachments/assets/ffca73e8-b89d-4109-915a-5cb337706fc3)

- Open the `.rdp` file downloaded from the Azure portal.
- Enter the administrator username and password set during VM creation.
- Wait for the Windows login screen to appear and complete the sign-in process.
- Once logged in, the Windows desktop environment will load.

### 5. Complete Initial Windows Setup

<img width="2360" height="1640" alt="image" src="https://github.com/user-attachments/assets/ece4e4c0-91f0-432a-9a8e-748e31dbdc60" />

- Upon first login, the system will prompt you to configure privacy settings.
- Review and adjust the following options:
  - Location
  - Find my device
  - Inking & typing
  - Tailored experiences
  - Advertising ID
  - Diagnostic data
- After reviewing all settings, click **Accept** to proceed to the desktop.

- ### 5. Download the osTicket Installation Files

  ![image](https://github.com/user-attachments/assets/79e96e3e-d017-4479-8306-57988621cce8)

- Open the download link provided for the `osTicket-Installation-Files.zip`.
- Since the file is large, Google Drive may not scan it for viruses.
- Click **Download anyway** to begin the download.
- Wait for the file to finish downloading completely.

---

### 6. Extract the Installation Files

![image](https://github.com/user-attachments/assets/04ff085e-1b94-47ff-b021-ec9e3eed6947)

- Locate the downloaded `.zip` file in your browser's downloads bar or Downloads folder.
- Right-click the file and choose **Extract All...** or use the default extraction prompt.
- Choose a destination folder (e.g., Desktop\osTicket-Installation-Files).
- Ensure the checkbox **Show extracted files when complete** is selected.
- Click **Extract**.

---

### 7. Confirm Files Were Extracted

![image](https://github.com/user-attachments/assets/e1fa0426-f086-409b-aef4-19ce762690ff)

- Navigate to the folder where the zip file was extracted.
- Verify the `osTicket-Installation-Files` folder appears on the Desktop or chosen location.
- Open the folder to confirm that its contents are accessible.

---

### 8. Open Control Panel

![image](https://github.com/user-attachments/assets/168e32a0-7291-4b2f-9734-54bb2cd587e8)

- Click the **Start** menu and type `Control Panel`, then press Enter.
- In the Control Panel, locate and click on **Programs**.
- Under **Programs**, click **Uninstall a program**.
- This section will allow you to verify existing software installations or remove any conflicting software before proceeding with osTicket setup.

![image](https://github.com/user-attachments/assets/6f20edf0-2e1c-4edb-bce9-ff50ee2aced9)

![image](https://github.com/user-attachments/assets/61d6e725-6981-45ea-808d-a6b39b3984d6)

![image](https://github.com/user-attachments/assets/9c9dc8ad-8f0a-46ce-aa0a-665842caa7fa)

![image](https://github.com/user-attachments/assets/04bc4651-8b02-400e-ba5c-28961697db4c)





















![osTicket Installer - Installation Success](https://user-images.githubusercontent.com/YOUR_IMAGE_LINK.jpg)

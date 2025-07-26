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

- ### 6. Download the osTicket Installation Files

  ![image](https://github.com/user-attachments/assets/79e96e3e-d017-4479-8306-57988621cce8)

- Open the download link provided for the `osTicket-Installation-Files.zip`.
- Since the file is large, Google Drive may not scan it for viruses.
- Click **Download anyway** to begin the download.
- Wait for the file to finish downloading completely.

---

### 7. Extract the Installation Files

![image](https://github.com/user-attachments/assets/04ff085e-1b94-47ff-b021-ec9e3eed6947)

- Locate the downloaded `.zip` file in your browser's downloads bar or Downloads folder.
- Right-click the file and choose **Extract All...** or use the default extraction prompt.
- Choose a destination folder (e.g., Desktop\osTicket-Installation-Files).
- Ensure the checkbox **Show extracted files when complete** is selected.
- Click **Extract**.

---

### 8. Confirm Files Were Extracted

![image](https://github.com/user-attachments/assets/e1fa0426-f086-409b-aef4-19ce762690ff)

- Navigate to the folder where the zip file was extracted.
- Verify the `osTicket-Installation-Files` folder appears on the Desktop or chosen location.
- Open the folder to confirm that its contents are accessible.

---

### 9. Open Control Panel

![image](https://github.com/user-attachments/assets/168e32a0-7291-4b2f-9734-54bb2cd587e8)

- Click the **Start** menu and type `Control Panel`, then press Enter.
- In the Control Panel, locate and click on **Programs**.
- Under **Programs**, click **Uninstall a program**.
- This section will allow you to verify existing software installations or remove any conflicting software before proceeding with osTicket setup.

 ### 10. Open Windows Features

![image](https://github.com/user-attachments/assets/6f20edf0-2e1c-4edb-bce9-ff50ee2aced9) 

- Go to **Control Panel** > **Programs** > **Turn Windows features on or off**.
- A new window titled **Windows Features** will open.
- Scroll through the list to find the required components.

---

### 11. Enable Internet Information Services (IIS)

![image](https://github.com/user-attachments/assets/61d6e725-6981-45ea-808d-a6b39b3984d6)

- In the Windows Features list, check the box for **Internet Information Services**.
- Expand the node by clicking the ➕ icon next to it.
  
### 12. Expand and Configure IIS Components

![image](https://github.com/user-attachments/assets/9c9dc8ad-8f0a-46ce-aa0a-665842caa7fa)

- Under **Internet Information Services**, expand the following:
  - **Web Management Tools**
  - **World Wide Web Services**

---

### 13. Enable Application Development Features

- Under **World Wide Web Services**, expand **Application Development Features**.
- Check the following options:
  - **.NET Extensibility 4.8**
  - **ASP**
  - **ASP.NET 3.5**
  - **ASP.NET 4.8**
  - **CGI**
  - **ISAPI Extensions**
  - **ISAPI Filters**
  - **Server-Side Includes**

---

### 14. Apply Changes and Wait for Configuration to Complete

![image](https://github.com/user-attachments/assets/04bc4651-8b02-400e-ba5c-28961697db4c)

- After selecting all required features, click **OK**.
- Windows will begin applying changes.
- Wait until the progress bar completes and the system confirms the features were successfully installed.

### 15. Open the Installation Files Directory

![image](https://github.com/user-attachments/assets/6b35f614-1284-4c41-9d0d-f0f35c1f176f)

- Navigate to the folder where you extracted the osTicket installation files.
- Open the folder named `osTicket-Installation-Files` to view the contents.

---

### 16. Review Installation Package Contents

![image](https://github.com/user-attachments/assets/35607569-71d8-4620-ae73-3f8ba21d94ee)

- The folder should contain multiple setup files, including:
  - HeidiSQL
  - MySQL installer
  - osTicket archive
  - PHP package
  - PHP Manager for IIS
  - URL Rewrite module
  - Visual C++ Redistributable

---

### 17. Install PHP Manager for IIS

![image](https://github.com/user-attachments/assets/1b53f7f7-fe3a-47d1-b9e2-945079b18adb)

- Locate and double-click `PHPManagerForIIS_V1.5.0`.
- In the setup wizard that appears, click **Next** to proceed through the installation steps.
- Complete the installation using default settings.

---

### 18. Install URL Rewrite Module

![image](https://github.com/user-attachments/assets/65b97158-f4c0-406e-b010-cf811c0fc89b)

- Locate and run the `rewrite_amd64_en-US` installer.
- Accept the license terms by checking **I accept the terms in the License Agreement**.
- Click **Install** and wait for the setup to complete.
- After installation finishes, click **Finish** to exit the wizard.

  ### 20. Accept the License Terms for URL Rewrite Module

  ![image](https://github.com/user-attachments/assets/eb1dec65-8129-486e-a6a8-d29e3b3b5e7c)

- When prompted, check the box labeled **I accept the terms in the License Agreement**.
- Click **Install** to begin installation.

---

### 21. Complete the URL Rewrite Installation

![image](https://github.com/user-attachments/assets/ab3accf2-e3cb-46f1-bc2e-84a426cc3b1b)

- After installation completes, a confirmation screen will appear.
- Click **Finish** to exit the setup wizard.

---

### 22. Open File Explorer to Access Installation Files

![image](https://github.com/user-attachments/assets/cd82c5b8-3fb8-4fcd-a5dc-d6fb1d69cd80)

- Launch **File Explorer** and locate the `osTicket-Installation-Files` folder.
- Verify that all necessary installation files are present in the folder.

---

### 23. Navigate to the C: Drive

![image](https://github.com/user-attachments/assets/fa9ed4dd-0a4c-4705-aaff-241606570866)

- In File Explorer, click on **This PC** and then **Windows (C:)**.
- You will extract PHP files into this location.

---

### 24. Create the PHP Directory on the C: Drive

![image](https://github.com/user-attachments/assets/6b455a62-3d36-4808-8cbf-fca2fc4860a8)

- In the `C:\` drive, right-click in an empty space.
- Select **New > Folder** and name the folder `PHP`.




![image](https://github.com/user-attachments/assets/5925941f-644d-419c-bf25-d873e1c1a214)

![image](https://github.com/user-attachments/assets/408076be-58d2-4868-8bff-9bf58fbc13f4)

![image](https://github.com/user-attachments/assets/dca9d67e-9678-4370-8fff-34781f8281b3)

![image](https://github.com/user-attachments/assets/6fbe51a6-d0c6-4d2d-a387-234f1f1933c3)

![image](https://github.com/user-attachments/assets/0ea4ee0d-7ae7-451c-8f5b-eda66ec9e106)

![image](https://github.com/user-attachments/assets/8a325819-4de4-4b77-9d2a-d333d175e4b7)

![image](https://github.com/user-attachments/assets/af77d00a-2097-4ce1-8b7e-764168404815)

![image](https://github.com/user-attachments/assets/fc50cfe7-98a4-48b0-be21-2e6d2ea8db53)






































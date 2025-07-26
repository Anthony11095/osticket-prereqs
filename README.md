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

### 25. Create PHP Folder in C: Drive

![image](https://github.com/user-attachments/assets/5925941f-644d-419c-bf25-d873e1c1a214)

- Open File Explorer.
- Navigate to the `C:\` drive.
- Right-click in an empty area and select **New > Folder**.
- Name the new folder: `PHP`.

---

### 26. Extract PHP Files

![image](https://github.com/user-attachments/assets/408076be-58d2-4868-8bff-9bf58fbc13f4)

- Go to the `osTicket-Installation-Files` folder.
- Right-click on the `php-7.3.8-nts-Win32-VC15-x86.zip` file.
- Select **Extract All...** from the context menu.
- Click **Browse**, then navigate to and select `C:\PHP`.
- Confirm the folder path shows as `C:\PHP`, then click **Extract**.

---

### 27. Wait for PHP Extraction to Complete

![image](https://github.com/user-attachments/assets/dca9d67e-9678-4370-8fff-34781f8281b3)

- Allow time for all files to be copied.
- Once the progress bar reaches 100%, confirm the PHP files are located in `C:\PHP`.

---

### 28. Run Visual C++ Redistributable Installer

![image](https://github.com/user-attachments/assets/6fbe51a6-d0c6-4d2d-a387-234f1f1933c3)

- In the `osTicket-Installation-Files` folder, double-click `VC_redist.x86.exe`.
- On the license screen, check **I agree to the license terms and conditions**.
- Click **Install** to begin the setup.

---

### 29. Complete Visual C++ Installation

![image](https://github.com/user-attachments/assets/6fbe51a6-d0c6-4d2d-a387-234f1f1933c3)

- Wait for the installation to finish.
- Once complete, click **Close** to exit the installer.

---

### 30. Begin MySQL Server 5.5 Setup

![image](https://github.com/user-attachments/assets/0ea4ee0d-7ae7-451c-8f5b-eda66ec9e106)

- Locate and double-click the `mysql-5.5.62-win32` setup file.
- The setup wizard will launch and begin the installation process.
- Wait for the status bar to show progress.

---

### 31. Launch MySQL Configuration Wizard

![image](https://github.com/user-attachments/assets/8a325819-4de4-4b77-9d2a-d333d175e4b7)

- After installation, the **MySQL Server Instance Configuration Wizard** will automatically launch.
- You will begin configuring MySQL Server 5.5 settings in the next steps.

  ### 32. Select Configuration Type for MySQL

![image](https://github.com/user-attachments/assets/af77d00a-2097-4ce1-8b7e-764168404815)

- When the MySQL Server Instance Configuration Wizard opens, select **Detailed Configuration**.
- Click **Next** to proceed.

---

### 33. Set Root Password for MySQL

![image](https://github.com/user-attachments/assets/fc50cfe7-98a4-48b0-be21-2e6d2ea8db53)

- Check the box for **Modify Security Settings**.
- Enter a secure password in both **New root password** and **Confirm** fields.
- Leave **Create An Anonymous Account** unchecked.
- Click **Next**.

---

### 34. Complete MySQL Configuration

![image](https://github.com/user-attachments/assets/f262588c-6aa2-4442-9b32-cbf111690273)

- The wizard will begin processing configuration steps:
  - Prepare configuration
  - Write configuration file
  - Start service
  - Apply security settings
- Wait for the process to complete.

---

### 35. Open Internet Information Services (IIS) Manager

![image](https://github.com/user-attachments/assets/5785a4c9-9095-4828-9bb2-0bb84ecfb416)

- Click **Start** and search for `IIS`.
- Right-click **Internet Information Services (IIS) Manager** and choose **Run as administrator**.

---

### 36. Launch PHP Manager in IIS

![image](https://github.com/user-attachments/assets/45a1f5bc-00a5-4573-b898-7d7aa04cdba1)

- In IIS Manager, under your server name, select your site (e.g., `osticket-vm`).
- In the center pane, double-click **PHP Manager**.

---

### 37. Open PHP Manager in IIS

![image](https://github.com/user-attachments/assets/9a85a3de-5e1c-4986-a00a-fe9e2aa0f2d6)

- In IIS Manager under the `osticket-vm` site, double-click **PHP Manager**.

---

### 38. Register PHP Executable

![image](https://github.com/user-attachments/assets/c0d21028-7d14-41c2-b3e1-23ca30c8be92)

- In PHP Manager, click **Register new PHP version**.
- Navigate to `C:\PHP`.
- Select `php-cgi.exe`.
- Click **Open** to confirm.

---

### 39. Verify PHP Registration

![image](https://github.com/user-attachments/assets/76ef105a-de06-4a21-96b9-65a0b4ebaa9b)

- Confirm that **PHP version** and **PHP executable** are now displayed in PHP Manager.

---

### 40. Add New Website in IIS

![image](https://github.com/user-attachments/assets/3c7625f7-a8fa-481c-acb0-623b34d2bd23)

- In the left panel under **Sites**, right-click and select **Add Website...**.

---

### 41. Extract osTicket Zip File

![image](https://github.com/user-attachments/assets/79f4b70a-a697-4a77-a2f5-b023fe2569f4)

- In File Explorer, navigate to `osTicket-Installation-Files`.
- Right-click the `osTicket-v1.15.8.zip` file.
- Select **Extract All...** to extract the contents for later use in IIS setup.

### 42. Select Extract Location for osTicket Files

![image](https://github.com/user-attachments/assets/fb4d00ff-7e43-456a-a907-7f2e56d13396)

- When prompted, confirm the destination folder where osTicket will be extracted (e.g., `C:\Users\[YourName]\Desktop\osTicket-Installation-Files\osTicket-v1.15.8`).
- Ensure **"Show extracted files when complete"** is checked.
- Click **Extract**.

---

### 43. Wait for Extraction to Complete

![image](https://github.com/user-attachments/assets/27abff5d-7315-49b0-8f0b-8d71862577cb)

- Allow all files to finish extracting.
- You should see a progress window showing file copy completion.

---

### 44. Open File Explorer

![image](https://github.com/user-attachments/assets/f837e0f3-e258-4746-aa1d-9397c8dc45d8)

- Open **File Explorer** from the taskbar or Start Menu.
- Navigate to the extracted folder `osTicket-v1.15.8`.

---

### 45. Locate the Upload Folder

![image](https://github.com/user-attachments/assets/3ade8947-3914-44d2-8ec5-1e0141923f42)

- Inside the `osTicket-v1.15.8` directory, identify the `upload` folder.
- This folder contains the web files needed for deployment.

---

### 46. Navigate to the IIS Web Root Directory

![image](https://github.com/user-attachments/assets/d64905ed-0582-488e-ace8-138db68f9c9c)

- In File Explorer, go to:  
  `C:\inetpub\wwwroot`

---

### 47. Move Upload Folder to IIS Root

![image](https://github.com/user-attachments/assets/0093e009-3ed9-4605-8b86-721a52161535)

- Drag the entire `upload` folder from the osTicket extraction directory into the `C:\inetpub\wwwroot` folder.

---

### 48. Confirm Upload Folder Placement

![image](https://github.com/user-attachments/assets/4dedcbc6-2a35-4e39-b33a-1ea8e581bc20)

- Ensure `upload` is now visible under `wwwroot`:  
  `C:\inetpub\wwwroot\upload`
- This sets up osTicket to be accessible through the local web server.

### 49. Create New osTicket Site in IIS

![image](https://github.com/user-attachments/assets/c57d0faf-9e35-4b51-b1e0-0b4e89d73e75)

- In **IIS Manager**, right-click **Sites** and select **Add Website...**.
- For **Site name**, enter: `osTicket`
- For **Physical path**, browse to:  
  `C:\inetpub\wwwroot\upload`
- For **Binding**, set the **Port** to `80` (default).
- Click **OK** to create the new site.

---

### 50. Verify osTicket Site in IIS

![image](https://github.com/user-attachments/assets/d0133aed-bbe9-4c08-a039-348cf6e66d20)

- Under **Sites**, confirm that `osTicket` appears beneath **Default Web Site**.
- Ensure the site is in a **Started** state.

### 51. Review PHP Prerequisites

![image](https://github.com/user-attachments/assets/1fbe20a9-8fce-4ec9-ac3a-39edcca5b8d3)

- Verify that all **Required** components show green checkmarks:
  - PHP 7.2 or greater
  - MySQLi extension for PHP
- Review the list of **Recommended** PHP extensions and take note of which are missing (marked with red ❌).

---

### 52. Open PHP Manager in IIS

![image](https://github.com/user-attachments/assets/c79ded4d-3e6e-419f-a9dd-18c4f3c5f246)

- In IIS, select the `osTicket` site.
- Double-click **PHP Manager** in the middle pane.

---

### 53. Enable Missing PHP Extensions

![image](https://github.com/user-attachments/assets/3744f375-2559-492f-89bd-6e86c8452a3f)

- Click **Enable or disable an extension**.
- Enable required and recommended extensions, such as:
  - `php_imap.dll`
  - `php_intl.dll`
  - `php_xml.dll`
  - `php_apcu.dll`
  - `php_opcache.dll`
- Confirm that their status updates to **Enabled**.

---

### 54. Refresh osTicket Setup Page

![image](https://github.com/user-attachments/assets/b287b4a1-7f52-4a93-9d6e-d2c94d1d8dfe)

- Return to the browser and reload `http://localhost/osTicket/setup`.
- Confirm that the extension warnings are now resolved.
- Click **Continue** to proceed with installation.











































![image](https://github.com/user-attachments/assets/3ae6b9ca-a5ca-4292-aa18-9e7840f7b756)

![image](https://github.com/user-attachments/assets/ac16d6fc-86ba-43f3-b05c-df7f778090ae)

![image](https://github.com/user-attachments/assets/cc54e587-15fb-43ac-873c-f41ca47b9858)

![image](https://github.com/user-attachments/assets/6e08fd28-a95e-469d-b5c4-9776c7d97424)

![image](https://github.com/user-attachments/assets/8599cbfa-de74-473a-94b8-b03dea500f03)

![image](https://github.com/user-attachments/assets/ffcc65b8-4c0f-49d3-b536-f07c3e3900d4)

![image](https://github.com/user-attachments/assets/ea296d60-b9e7-4450-922c-681c8663c786)

![image](https://github.com/user-attachments/assets/e32ce106-8fa7-42a1-9393-f78e92efa951)

![image](https://github.com/user-attachments/assets/66a9abd9-8836-4589-8008-9ba0d2f3874b)

![image](https://github.com/user-attachments/assets/c06caf4b-74a7-4a01-a025-c3ab16aa982d)

![image](https://github.com/user-attachments/assets/7b223d84-f770-41dc-8e5b-b616ba9fc826)

![image](https://github.com/user-attachments/assets/5a1f34bd-eebb-4392-a65f-5de85865813a)

![image](https://github.com/user-attachments/assets/83104af5-65b3-406f-97dc-86fc9f677445)

![image](https://github.com/user-attachments/assets/7c558d2f-3fae-4856-8165-522e3f14ac0a)

![image](https://github.com/user-attachments/assets/e9c8221d-1223-480f-8005-36d7da06c1f0)

![image](https://github.com/user-attachments/assets/d92683e3-a512-4d65-a026-41f69841db7a)

![image](https://github.com/user-attachments/assets/acfe43cd-6650-420c-a916-34f4539c329a)

![image](https://github.com/user-attachments/assets/8dac7613-4d64-47e6-bb2d-6eb140c8e2ff)

![image](https://github.com/user-attachments/assets/524fc438-dbce-4d97-a510-a405a9b8fd69)

![image](https://github.com/user-attachments/assets/229fdd59-ff17-443d-b7ac-035d37fd2943)

![image](https://github.com/user-attachments/assets/229bf3eb-9ffe-4746-b78f-5f785ac57cb3)

![image](https://github.com/user-attachments/assets/d43eeb02-d598-469d-b257-2a656bf9cb98)

![image](https://github.com/user-attachments/assets/f31830e3-cc9a-48d4-92ec-8893bc3354e0)

![image](https://github.com/user-attachments/assets/5153462d-3d70-4462-bc39-06384d4808f8)












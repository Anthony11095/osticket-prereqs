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

<h2>List of Prerequisites</h2>

## 🧰 osTicket VM Setup – Prerequisites Summary

### 1. Azure VM Configuration
- **OS:** Windows 10  
- **vCPUs:** 4  
- **VM Name:** `osticket-vm`  
- **Username:** `labuser`  
- **Password:** `osTicketPassword1!`  

### 2. Access
- Connect via **Remote Desktop (RDP)**

### 3. Installation Resources
- Download and extract: `osTicket-Installation-Files.zip`  
- Folder name: `osTicket-Installation-Files`

### 4. Enable IIS with CGI
- Enable feature:  
  `World Wide Web Services → Application Development Features → CGI`

### 5. Install Dependencies (from extracted folder)
- PHP Manager for IIS (`PHPManagerForIIS_V1.5.0.msi`)
- IIS Rewrite Module (`rewrite_amd64_en-US.msi`)
- PHP 7.3.8  
  - Unzip `php-7.3.8-nts-Win32-VC15-x86.zip` into `C:\PHP`
- Visual C++ Redistributable (`VC_redist.x86.exe`)
- MySQL 5.5.62 (`mysql-5.5.62-win32.msi`)  
  - Use **Typical Setup** and run **Configuration Wizard** post-installation
## ⚙️ osTicket Configuration & IIS Setup

### 6. Open IIS as Administrator

### 7. Register PHP with IIS
- In **PHP Manager**, register PHP using the following path:  
  `C:\PHP\php-cgi.exe`

### 8. Reload IIS
- Open IIS, then **Stop** and **Start** the server.

### 9. Install osTicket v1.15.8
- Unzip `osTicket-v1.15.8.zip` from the `osTicket-Installation-Files` folder.
- Copy the `upload` folder to:  
  `C:\inetpub\wwwroot`
- Rename `upload` to `osTicket`:  
  `C:\inetpub\wwwroot\osTicket`

### 10. Reload IIS Again
- Stop and Start the IIS server once more.

### 11. Launch osTicket in Browser
- Go to: **Sites → Default Web Site → osTicket**
- On the right pane, click: **Browse \*:80**

### 12. Enable Required PHP Extensions
- In IIS:  
  Go to **Sites → Default Web Site → osTicket**
- Double-click **PHP Manager**
- Click: **Enable or disable an extension**, then enable the following:
  - `php_imap.dll`
  - `php_intl.dll`
  - `php_opcache.dll`
- Refresh the osTicket page in your browser to reflect changes.

### 13. Rename Configuration File
- Rename the sample config file:
  - From:  
    `C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php`
  - To:  
    `C:\inetpub\wwwroot\osTicket\include\ost-config.php`

### 14. Assign Permissions to `ost-config.php`
- Disable inheritance → Remove All permissions
## 🧩 Final Configuration & Database Setup

### 15. Continue osTicket Setup in Browser
- Click **Continue** on the osTicket setup page.
- Enter basic configuration:
  - **Helpdesk Name**
  - **Default Email Address** (for receiving tickets)

### 16. Create MySQL Database using HeidiSQL
- From the `osTicket-Installation-Files` folder, install **HeidiSQL**.
- Open **HeidiSQL** and:
  - Create a new session with:
    - **Username:** `root`
    - **Password:** `root`
  - Connect to the session
  - Create a new database named: `osTicket`

### 17. Complete Installation via Browser
- Fill in the database info in the setup form:
  - **MySQL Database:** `osTicket`
  - **Username:** `root`
  - **Password:** `root`
- Click **Install Now!**

### 18. Post-Installation Access
- Admin Login URL:  
  [http://localhost/osTicket/scp/login.php](http://localhost/osTicket/scp/login.php)
- End-User Portal:  
  [http://localhost/osTicket/](http://localhost/osTicket/)

### 19. Final Cleanup Steps
- Delete the setup directory:
  ```bash
  C:\inetpub\wwwroot\osTicket\setup




<h2>Installation Steps</h2>

<p>
<img width="1896" height="859" alt="creating a virtual machine for osticket part 1" src="https://github.com/user-attachments/assets/6b21324a-4e61-4df7-b002-6608fefcabf8" />

### ☁️ Creating a Virtual Machine in Microsoft Azure

The following steps were used to provision a Windows 10 virtual machine to host the osTicket web application:

1. **Navigate to Azure Portal**  
   Open [https://portal.azure.com](https://portal.azure.com) and sign in with your Azure account.

2. **Create a Resource Group**  
   If you don’t have one, create a new resource group to organize your virtual machine and related services.

3. **Start VM Creation**  
   Go to **Virtual Machines** → Click **+ Create** → **Azure Virtual Machine**

4. **Basic Configuration**
   - **Virtual Machine Name:** `osticket-vm`
   - **Region:** Choose a region close to your location (e.g., `East US 2`)
   - **Availability Zone:** Default (or choose based on redundancy needs)
   - **Image:** Windows 10 Pro, version 21H2 (or latest available)
   - **Size:** Standard D2s v3 (2–4 vCPUs recommended)
   - **Authentication Type:** Password  
     - **Username:** `labuser`  
     - **Password:** `osTicketPassword1!`

5. **Networking and Inbound Ports**
   - Enable RDP (port 3389) to allow remote desktop access
   - Open port **80 (HTTP)** for web access

6. **Review and Create**
   - Click **Review + create**, then **Create** after validation passes.

Once deployment is complete, connect to the VM using **Remote Desktop (RDP)** and proceed with the osTicket installation process.

> 📸 *The image above shows the VM creation screen in Azure Portal.*

Image 2 <p>
<img width="1907" height="864" alt="created virtual machine for osticket" src="https://github.com/user-attachments/assets/9c4425e7-ac0e-4b48-86c4-84f252cb68e8" />

</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
(https://github.com/user-attachments/assets/e3e4e406-f057-4b7e-b025-4e4ffacfdc42)


</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

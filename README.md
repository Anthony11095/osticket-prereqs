<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)

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

---




<h2>Installation Steps</h2>

<p>
<img width="1896" height="859" alt="creating a virtual machine for osticket part 1" src="https://github.com/user-attachments/assets/6b21324a-4e61-4df7-b002-6608fefcabf8" />



</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
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

</p><!DOCTYPE html>
<html>

<body>

<p align="center">
    <img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

# Installing osTicket on Azure Virtual Machine

This lab guides you through setting up osTicket, an open-source support ticket system, on a Windows 10 Virtual Machine in Microsoft Azure.

## Part 1: Create Virtual Machine in Azure

For detailed steps on creating a virtual machine in Azure, refer to the [Azure VM Creation Lab](https://github.com/gabe-IT/azure-vm).

### Summary of Steps:
1. Create a **Resource Group** in Azure.
2. Create a **Windows 10 Virtual Machine (VM)** with 2-4 virtual CPUs.
3. Configure a **new Virtual Network (Vnet)** for the VM.

## Part 2: Installation of osTicket

### Prerequisites
- Download the osTicket Installation Files from [here](https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6).

### Setup Steps

### 1. Configure Virtual Machine:
   - Name: `Vm-osticket`
   - Username: `labuser` (or your choice)
   - Password: `osTicketPassword1!` (or your choice)

### 2. Install and Enable IIS in Windows:
   - Navigate to Control Panel > Programs > Turn Windows features on or off. 
     ![image](https://github.com/gabe-IT/osticket-prereqs/assets/148400020/abd89e85-8618-4d8c-99a2-f5bcef83ae72)
-Include CGI, Common HTTP Features, and IIS Management Console.
![274989273-e770403c-5def-4c58-a2ad-24b61a859078](https://github.com/gabe-IT/osticket-prereqs/assets/148400020/eb7fb805-812f-4202-86fd-4083bc69981a)
- To verify that IIS has been successfully installed, open a web browser and type "127.0.0.1" in the search bar and hit enter. You should see something like the image displayed below. If you do not see this, please uninstall and reinstall IIS. 
![image](https://github.com/gabe-IT/osticket-prereqs/assets/148400020/ca575f86-1478-40d2-b121-9e16233264d5)

    
### 3. Install PHP Manager for IIS
- Download `PHPManagerForIIS_V1.5.0.msi` from the Installation Files.
- Run the installer to integrate PHP management capabilities into IIS.

### 4. Install Rewrite Module
- Download `rewrite_amd64_en-US.msi` from the Installation Files.
- Execute the installer, adding URL rewriting features to IIS necessary for osTicket.

### 5. Setup PHP
- Create a directory `C:\PHP` on your system drive.
- Download PHP 7.3.8 and extract it into `C:\PHP`.

### 6. Install VC_redist.x86.exe
- Locate `VC_redist.x86.exe` in the Installation Files and run it.
- This installs the necessary Visual C++ Redistributable for running PHP on Windows.

### 7. Install MySQL 5.5.62
- Begin MySQL installation with `mysql-5.5.62-win32.msi`.
- Choose 'Typical Setup' and follow with 'Standard Configuration' post-install.
- Set the MySQL root password as `Password1`.

### 8. Configure IIS
- Open IIS Manager as an admin.
- Register PHP in IIS pointing to the `C:\PHP` directory.
- Restart the IIS server to apply changes.

### 9. Install osTicket v1.15.8
- Download and extract osTicket v1.15.8 from the Installation Files.
- Copy the “upload” folder to `c:\inetpub\wwwroot` and rename it to “osTicket”.
- Reload IIS for the changes to take effect.

### 10. Configure osTicket in IIS
- In IIS Manager, go to Sites -> Default Website -> osTicket.
- Access the setup page by browsing `*:80`.
- Enable PHP extensions: `php_imap.dll`, `php_intl.dll`, `php_opcache.dll`.

### 11. Configure `ost-config.php`
- Rename `ost-sampleconfig.php` to `ost-config.php` in `C:\inetpub\wwwroot\osTicket\include`.
- Adjust file permissions for security.

### 12. Database Setup
- Install and open HeidiSQL.
- Create a new session with `root/Password1`.
- Create a new database named “osTicket”.

### 13. Finalize osTicket Setup
- Complete the osTicket setup through the browser using the MySQL details.
- Click “Install Now!” to finalize installation.

### 14. Access osTicket
- Help Desk Login Page: `http://localhost/osTicket/scp/login.php`
- End Users URL: `http://localhost/osTicket/`

### 15. Post-Installation Cleanup
- Delete the `setup` directory in `C:\inetpub\wwwroot\osTicket`.
- Set `ost-config.php` to "Read-only" permissions.

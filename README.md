
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

1. **Configure Virtual Machine:**
   - Name: `Vm-osticket`
   - Username: `labuser` (or your choice)
   - Password: `osTicketPassword1!` (or your choice)

2. **Install and Enable IIS in Windows:**
   - Include CGI, Common HTTP Features, and IIS Management Console.

3. **Install PHP Manager for IIS:**
   - Use `PHPManagerForIIS_V1.5.0.msi` from the Installation Files.

4. **Install Rewrite Module:**
   - Use `rewrite_amd64_en-US.msi` from the Installation Files.

5. **Setup PHP:**
   - Create the directory `C:\PHP`.
   - Download and unzip PHP 7.3.8 into `C:\PHP`.

6. **Install VC_redist.x86.exe:**
   - Available in the Installation Files.

7. **Install MySQL 5.5.62:**
   - Use `mysql-5.5.62-win32.msi` from the Installation Files.
   - Post-install, choose Typical Setup and Standard Configuration.
   - Set MySQL password to `Password1`.

8. **Configure IIS:**
   - Open IIS as an Admin.
   - Register PHP within IIS.
   - Reload IIS by stopping and starting the server.

9. **Install osTicket v1.15.8:**
   - Download from the Installation Files.
   - Extract and copy the “upload” folder to `c:\inetpub\wwwroot`.
   - Rename “upload” to “osTicket”.
   - Reload IIS.

10. **Configure osTicket in IIS:**
    - Go to sites -> Default -> osTicket.
    - Browse `*:80` to view the osTicket setup page.
    - Enable PHP extensions: `php_imap.dll`, `php_intl.dll`, `php_opcache.dll`.

11. **Configure `ost-config.php`:**
    - Rename `ost-sampleconfig.php` to `ost-config.php`.
    - Set appropriate permissions for `ost-config.php`.

12. **Database Setup:**
    - Install HeidiSQL.
    - Create a new session with `root/Password1`.
    - Create a MySQL database named “osTicket”.

13. **Finalize osTicket Setup:**
    - Complete the setup in the browser with the MySQL database details.
    - Click “Install Now!” to finalize.

14. **Access osTicket:**
    - Help Desk Login Page: `http://localhost/osTicket/scp/login.php`
    - End Users URL: `http://localhost/osTicket/`

15. **Post-Installation Cleanup:**
    - Delete `C:\inetpub\wwwroot\osTicket\setup`.
    - Set `ost-config.php` permissions to “Read” only.

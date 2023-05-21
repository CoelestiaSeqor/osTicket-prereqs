<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b>

<h2>List of Prerequisites</h2>

Prerequisites:
- Microsoft Azure
- Remote Desktop software
   - Remote Desktop Connection on Windows, Microsoft Remote Desktop on macOS
-osTicket installation files

<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

Step 1: Create an Azure Virtual Machine
- Create a Resource Group
- Create a Windows 10 Virtual Machine (VM) with 2-4 Virtual CPUs
   - When creating the VM, allow it to create a new Virtual Network (Vnet)
   
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
   
Step 2: Create an Azure Virtual Machine Windows 10, 4 vCPUs
- Name: Vm-osticket
- Username: labuser (for example/whatever you chose)
- Password: osTicketPassword1! (for example/whatever you chose)
   
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
   
Step 3: Remote into VM
- In Azure click on your Virtual Machine "Vm-osticket"
- Find the Public IP Address
- Click start and type "Remote Desktop Connection"
- Enter the puiblci IP for the VM and the username
- Enter password when prompted for credentials
- When dialog pops up, click "Yes" to connect
      
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
   
Step 4: Install and Enable IIS with CGI
- In the VM click the windows icon and search for "Control Panel"
- Click on "Programs"
- Click "Turn Windows features on or off"
- Check and expand "Internet Information Services" 
- Check and expand "World Wide Web Services"
- Check and expand "Application Development Features"
- Check "CGI"
    
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

Step 5: Install PHP Manager for IIS and Rewrite Module
- Download and install "PHP Manager for IIS" (PHPManagerForIIS_V1.5.0.msi) from the installation files.
   - Follow prompts to install.
- Download and install the "Rewrite Module" (rewrite_amd64_en-US.msi) from the installation files.
   
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

Step 6: Install PHP
- Create a directory called "C:\PHP".
   - To do this open file explorer, navigate to "This PC" then to "Windows (C:)"
   - Create a new folder in the C: Drive, name it "PHP"
- Download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) from the installation files.
- Extract the contents of the zip file into the "C:\PHP" directory.
   
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

Step 5: Install VC_redist.x86.exe
- Download and install "VC_redist.x86.exe" from the installation files.
   
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

Step 7: Install MySQL
- Download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi) from the installation files.
- Choose the "Typical Setup".
- Launch the MySQL Configuration Wizard after installation and select "Standard Configuration".
- Set the password to your preferred password.
- Click "Execute"

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
   
Step 8: Open IIS as an Admin and Register PHP
- Click on the windows button and type "IIS"
- Open Internet Information Services (IIS) as an administrator.
- Register PHP by clicking on the server name (Vm-osticket\labuser) under the "Connections tab, and double-clicking "PHP Manager".
- Click "Register new PHP version" and browse to the PHP installation directory (C:\PHP).
   
</p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
   
Step 9: Reload IIS and Install osTicket
- Stop and start the IIS server to reload the changes.
- Download osTicket v1.15.8 from the installation files.
- Extract the contents of the zip file and copy the "upload" folder to "c:\inetpub\wwwroot".
- Rename the "upload" folder to "osTicket".
   
</p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
   
Step 10: Enable PHP Extensions
- Open IIS, stop and start the IIS server to reload the changes.
- In the "Connections" tab, expand the server name (Vm-osTicket\labuser).
   - Expand "Sites" .
   - Select "Default Web Site".
   - Double-click "PHP Manager".
- Click "Enable or disable an extension" and enable the following extensions: php_imap.dll, php_intl.dll, php_opcache.dll.
   - You can filter the extensions to make it easier to find the ones listed.
   
</p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
   
Step 11: Rename and Assign Permissions to ost-config.php
- Rename "ost-sampleconfig.php" to "ost-config.php" located at "C:\inetpub\wwwroot\osTicket\include\".
- Disable inheritance for "ost-config.php" and remove all permissions.
   - Right click on "ost-configr.php" select "Properties".
   - Select "Security" Tab, then click "Advanced".
   - Click "Disable inheritance", Select "Remove all inherited permissions on this object".
- Add a new permissions for "Everyone".
   - Click "Add", click "Select a principal".
   - In the text field type "everyone", then click "Check Names", then "OK".
- Select "Full Control", this will check all elligible boxes.
- Click "Apply" and "OK" on all boxes until you arrive back at the "ost-config.php" file
   
</p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
   
Step 12: Set up the Database with HeidiSQL
- Download and install HeidiSQL from the installation files.
   - Follow prompts until installed.
- Open HeidiSQL and create a new session using "root" as the username and "Password1" as the password.
- Connect to the session and create a database called "osTicket".
   - Right Click on "Unamed" tab, select "Create New", select "datatbase".
   - Name new database "osTicket", click "OK".
   
</p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
   
Step 13: Complete osTicket Setup
- Click "Browse *:80(http)" in IIS
   - If "osTicket" does not appear under "Default Web Site" please close and reopen IIS.
- In the browser, click "Continue" to proceed with osTicket setup.
- Provide a name for the helpdesk and the default email address to receive customer emails.
- Enter the following database details: 
   - MySQL Database: osTicket
   - MySQL Username: root
   - MySQL Password: Password1
- Click "Install Now!" to complete the installation.
   
</p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
   
Step 14: Clean Up
Before setting up osTicket perform the following clean up:
- Delete: C:\inetpub\wwwroot\osTicket\setup.
   - Navigate to folder, right click on folder and select "Delete".
- Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php.
   - Navigate to folder, right click on folder and select "Properties".
   - Select "Security Tab", click "Advanced"
   - Select "Everyone", click "Edit"
   - Uncheck all boxes except "Read", click "OK"
   - Click "Apply" and "OK" until back at file.
- Congratulations! Your osTicket installation has been completed successfully.
   - You can access the help desk login page at http://localhost/osTicket/scp/login.php.
   - The end-users can access osTicket at http://localhost/osTicket/.

 </p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

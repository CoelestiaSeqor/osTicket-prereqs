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

Prerequisites:
1. Windows operating system (e.g., Windows 10, Windows Server 2016/2019)
2. Web server software (e.g., Apache, Nginx)
3. PHP version 7.2 or later
4. MySQL or MariaDB database server
5. PHP extensions: curl, gd, imap, intl, json, mbstring, xml, zip
6. A text editor (e.g., Notepad++, Sublime Text)

Now, let's move on to the installation process:

<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

Step 1: Create an Azure Virtual Machine
- Create a Windows 10 virtual machine with 4 vCPUs.
- Set a name (e.g., "Vm-osticket").
- Choose a username (e.g., "labuser") and password (e.g., "osTicketPassword1!").
   
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

Step 2: Install and Enable IIS with CGI
- Open the "Server Manager" on the Azure Virtual Machine.
- Go to "Manage" -> "Add Roles and Features".
- Select "Web Server (IIS)" and click "Next".
- Enable CGI under "Application Development Features" by checking the box.
- Complete the installation process.
   
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

Step 3: Install PHP Manager for IIS and Rewrite Module
- Download and install "PHP Manager for IIS" (PHPManagerForIIS_V1.5.0.msi) from the installation files.
- Download and install the "Rewrite Module" (rewrite_amd64_en-US.msi) from the installation files.
   
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

Step 4: Install PHP
- Create a directory called "C:\PHP".
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

Step 6: Install MySQL
- Download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi) from the installation files.
- Choose the "Typical Setup" and set the password to "Password1" (or your preferred password).
- Launch the MySQL Configuration Wizard after installation and select "Standard Configuration".

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
   
Step 7: Open IIS as an Admin and Register PHP
- Open Internet Information Services (IIS) as an administrator.
- Register PHP by clicking on the server name and double-clicking "PHP Manager".
- Click "Register new PHP version" and browse to the PHP installation directory (C:\PHP).
   
</p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
   
Step 8: Reload IIS and Install osTicket
- Stop and start the IIS server to reload the changes.
- Download osTicket v1.15.8 from the installation files.
- Extract the contents of the zip file and copy the "upload" folder to "c:\inetpub\wwwroot".
- Rename the "upload" folder to "osTicket".
   
</p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
   
Step 9: Enable PHP Extensions
- Open IIS, go to "Default Web Site", and double-click "PHP Manager".
- Click "Enable or disable an extension" and enable the following extensions: php_imap.dll, php_intl.dll, php_opcache.dll.
- Refresh the osTicket site in your browser to observe the changes.
   
</p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
   
Step 10: Rename and Assign Permissions to ost-config.php
- Rename "ost-sampleconfig.php" to "ost-config.php" located at "C:\inetpub\wwwroot\osTicket\include\".
- Disable inheritance for "ost-config.php" and remove all permissions.
- Add a new permission for "Everyone" with "Read" access.
   
</p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
   
Step 11: Continue osTicket Setup in the Browser
- In the browser, click "Continue" to proceed with osTicket setup.
- Provide a name for the helpdesk and the default email address to receive customer emails.
- Click "Continue" and proceed with the installation.
   
</p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
   
Step 12: Set up the Database with HeidiSQL
- Download and install HeidiSQL from the installation files.
- Open HeidiSQL and create a new session using "root" as the username and "Password1" as the password.
- Connect to the session and create a database called "osTicket".
   
</p>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
   
Step 13: Complete osTicket Setup
- Continue the osTicket setup in the browser.
- Enter the following database details: MySQL Database: osTicket, MySQL Username: root, MySQL Password: Password1.
- Click "Install Now!" to complete the installation.
   
</p>
<p>
   
Congratulations! osTicket should now be installed without errors. You can access the help desk login page at http://localhost/osTicket/scp/login.php. The end-users can access osTicket at
Congratulations! You have successfully installed osTicket on Windows. You can now begin using it to manage your support tickets.

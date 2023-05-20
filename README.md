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

Step 1: Set up a Web Server
1. Install a web server software of your choice (e.g., Apache, Nginx).
2. Configure the web server to work with PHP. This typically involves enabling the PHP module and restarting the server.
   
 <p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

Step 2: Install PHP
1. Download the latest version of PHP for Windows from the official PHP website (https://www.php.net/downloads.php).
2. Extract the downloaded PHP archive to a directory of your choice (e.g., `C:\php`).
3. Rename the `php.ini-development` file to `php.ini`.
4. Open the `php.ini` file in a text editor.
5. Make the following changes (uncomment by removing the semicolon `;` at the beginning of each line):
   - Enable the PHP extensions required by osTicket (e.g., curl, gd, imap, intl, json, mbstring, xml, zip).
   - Set the date.timezone parameter to your timezone (e.g., `date.timezone = America/New_York`).
6. Save the `php.ini` file.
   
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

Step 3: Set up a Database Server
1. Install MySQL or MariaDB on your Windows system.
2. Create a new database for osTicket.
3. Create a new user and grant it all privileges on the osTicket database.
   
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

Step 4: Download and Configure osTicket
1. Visit the official osTicket website (https://osticket.com/) and download the latest stable release.
2. Extract the downloaded osTicket archive to your web server's document root directory (e.g., `C:\webroot\osticket`).
3. Rename the `upload/include/ost-sampleconfig.php` file to `ost-config.php`.
4. Open the `ost-config.php` file in a text editor.
5. Configure the database settings by providing the database server, database name, username, and password.
6. Save the `ost-config.php` file.
   
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

Step 5: Set Permissions
1. Grant read and write permissions to the web server process on the `ost-config.php` file.
2. Ensure that the web server has sufficient permissions to read and write to other necessary directories within the osTicket installation.
   
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

Step 6: Complete the Installation
1. Open a web browser and navigate to the osTicket URL (e.g., `http://localhost/osticket`).
2. Follow the on-screen instructions to complete the installation process.
3. Provide the requested information, such as the system email address, administrator account details, and SMTP settings (if applicable).
4. Finish the installation and log in to the osTicket admin panel.

Congratulations! You have successfully installed osTicket on Windows. You can now begin using it to manage your support tickets.

<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>Prerequisites and the installation process for osTicket </h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- 1 desktop/laptop computer
- Microsoft Azure Account
- Create a Virtual Machine in Azure that is Windows 10, 4 vCPUs

<h2>Installation Steps</h2>

Step 1. Download <a href="https://drive.usercontent.google.com/download?id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD&export=download&authuser=0"> osTicket-Installation-Files.zip


Step 2. Unzip and extract those files

Step 3. Install and enable IIS in Windows WITH CGI

World Wide Web Services -> Application Development Features -> [X] CGI

<h2>Inside osTicket folder Install</h2>
Step 1. Open “osTicket-Installation-Files” folder and install PHP Manager (PHPManagerForIIS_V1.5.0.msi) and Rewrite module (rewrite_amd64_en-US.msi)

Step 2. Create a folder on the C: drive called “PHP”

Step 3. Open “osTicket-Installation-Files” again and then unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder

Step 4. Open “osTicket-Installation-Files” and install VC_redist.x86 and mysql-5.5.62-win32
        
        Launch Configuration wizard -> Standard Configuration ->
              
              Username: root
              
              Password: root

Step 5. Open IIS as admin -> press "start" -> search IIS -> run as admin

Step 6. Register PHP from within IIS (PHP Manager -> C:\PHP\php-cgi.exe)

Step 7. Reload IIS (Open IIS, Stop and Start the server)

<h2>Installing osTicket</h2>

Step 1. From the “osTicket-Installation-Files” folder -> unzip “osTicket-v1.15.8.zip” -> copy the “upload” folder into “c:\inetpub\wwwroot”
Within “c:\inetpub\wwwroot” -> Rename “upload” to “osTicket”

Step 2. Reload IIS (Start then Stop the server)

<h2>Open osTicket</h2>

Step 1. Go to sites -> Default -> osTicket
On the right, click “Browse *:80”

Step 2. Some extentions are not enabled
          
          > Go back to IIS, sites -> Default -> osTicket
          
          > Double-click PHP Manager
          
          > Click “Enable or disable an extension”
          
          > Enable: php_imap.dll
          
          > Enable: php_intl.dll
          
          > Enable: php_opcache.dll

Step 3. Refresh the osTicket site in your browser observe the changes

Step 4. Rename: ost-config.php

          > From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
          
          > To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

Step 5. Assign Permissions: ost-config.php

          > Disable inheritance -> Remove All
          
          > New Permissions -> Everyone -> All

<h2>Set up rest of osTicket</h2>

Step 1. Setup your username and password

         > username: user1
         
         > Password: Password1

Step 2. from “osTicket installation files” install “HeidiSQL_12.3.0.6589_Setup”
         
             > Open Heidi SQL -> Create new session -> root/root
             
             
Step 3. Create data base called “osTicket”

You can now continue to set up from browser
               
               > MySQL Database: osTicket
               
               > MySQL Username: root
               
               > MySQL Password: root

<h2>osTicket is installed!!!</h2>

        > login page: http://localhost/osTicket/scp/login.php
              
        > Username: user1
               
        > Password: password1


<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

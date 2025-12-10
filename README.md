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

> 1 desktop/laptop computer
> Microsoft Azure Account
> Create a Virtual Machine in Azure that is Windows 10, 4 vCPUs

<h2>Installation Steps</h2>

Step 1. Download <a href="https://drive.usercontent.google.com/download?id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD&export=download&authuser=0"> osTicket-Installation-Files.zip

Step 2. Unzip and extract those files

<img width="1404" height="706" alt="image" src="https://github.com/user-attachments/assets/cf754b42-1279-4f53-9153-3957b37042bb" />

The files should look like this when they are unzipped and extracted


Step 3. Install and enable Internat Information Services (IIS) in Windows WITH CGI

Begin by pulling up the "Control Panel" -> Programs -> Turn on/off windows features -> Internet Information Services -> World Wide Web Services -> Application Development Features -> [X] CGI

<h2>Inside osTicket folder Install</h2>
Step 1. Open “osTicket-Installation-Files” folder and install PHP Manager (PHPManagerForIIS_V1.5.0.msi) and Rewrite module (rewrite_amd64_en-US.msi)

Step 2. Create a folder on the C: drive called “PHP”

Step 3. Open “osTicket-Installation-Files” again and then unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder

<img width="1623" height="714" alt="image" src="https://github.com/user-attachments/assets/349b08e2-aebc-4d8b-b461-a95b13c11d42" />

This should be how your computer looks when you are extracting your files into the PHP folder

Step 4. Open “osTicket-Installation-Files” and install VC_redist.x86 and mysql-5.5.62-win32
        
      After you install Launch Configuration wizard -> Standard Configuration ->
              
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

<img width="1920" height="990" alt="image" src="https://github.com/user-attachments/assets/22671d18-0d62-40ac-b1c9-e200e250885b" />

This should be what you see when you click “Browse *:80”

Step 2. Some extentions are not enabled
          
> Go back to IIS, sites -> Default -> osTicket
          
> Double-click PHP Manager
          
> Click “Enable or disable an extension”

<img width="1424" height="738" alt="image" src="https://github.com/user-attachments/assets/2f836a61-d1a6-459c-8e25-2bbe68053cd2" />
          
> Enable: php_imap.dll
          
> Enable: php_intl.dll
          
> Enable: php_opcache.dll

Step 3. Refresh the osTicket site in your browser observe the changes

Step 4. Rename: ost-config.php

> From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
          
> To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

Step 5. Assign Permissions: ost-config.php

> Start by right clicking "ost-config.php" -> properties -> secutirity -> SYSTEM -> advanced

<img width="1466" height="773" alt="image" src="https://github.com/user-attachments/assets/e8f26795-5482-478a-b084-c74f72d57173" />

> Disable inheritance -> Remove All inherited permissions from this object
          
> New Permissions -> Everyone -> All

<img width="487" height="630" alt="image" src="https://github.com/user-attachments/assets/c64022da-96f3-433f-8ae2-b98f514461f9" />


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

<img width="1920" height="948" alt="image" src="https://github.com/user-attachments/assets/401020c0-bcc8-486d-9087-c46eadce1d74" />

> login page: http://localhost/osTicket/scp/login.php
              
> Username: user1
               
> Password: password1

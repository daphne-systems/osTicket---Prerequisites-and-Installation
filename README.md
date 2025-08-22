# osTicket---Prerequisites-and-Installation
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.
<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>My dashboard after installing</h2>

- <img width="1087" height="445" alt="image" src="https://github.com/user-attachments/assets/9d8a0856-1bd0-4b64-a4c3-77c18764b861" />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>Start 20 step process</h2>

- Step 1: download the osTicket-Installation-Files.zip and unzip/extract

  &emsp;- link -> https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD

- Step 2: Install / Enable IIS in Windows WITH CGI
  
  &emsp;- Control panel -> Programs -> Uninstall Programs -> Turn Windows features onoff
  
  &emsp;- Check Internet Information Services
  
  &emsp;- www  services -> App Dev Features -> CGI

- Step 3: Inside osTicket folder Install
- 
  &emsp;- PHP (PHPManagerForIIS_V1.5.0.msi)

  &emsp; - Rewrite module (rewrite_amd64_en-US.msi)

- Step 4: Create a folder on C drive called “PHP”

  
- Step 5: in osTicket folder extract all from -> (php-7.3.8-nts-Win32-VC15-x86.zip) into PHP folder
<img width="913" height="652" alt="image" src="https://github.com/user-attachments/assets/0991647c-b378-4b70-8414-e09a2436a708" />

<p>
This is what you should see once you extract all files from (php-7.3.8-nts-Win32-VC15-x86.zip). 
</p>
- Step 6: install VC_redist.x86

- Step 7: install mysql-5.5.62-win32
  
  &emsp;- Launch standard configuration
  
  &emsp;- Username: root
  
  &emsp;- Password: root




<h2>osTicket Installation Files</h2>

<p>
<img width="1151" height="658" alt="inside the installation folder" src="https://github.com/user-attachments/assets/520379cc-6bed-4d9e-af19-9d725c4321e8" />
</p>
<p>
</p>
<br />

- Step8: open IIS as admin -> start -> search “iis” -> run as adim

- Step9: Register PHP from within IIS -> php manager -> register new php version -> browse to php folder inside get “php-cgi”

- Step 10: refresh IIS -> top left of IIS under “connections” right click “practice-osTicket” -> click stop -> wait -> click start

<p>
<img width="1343" height="795" alt="image" src="https://github.com/user-attachments/assets/a73c4eb1-0c75-48cb-a537-7a7c7e676fcd" />
</p>
<p>
This is the ISS and how to (Start | Stop) it

- Step 11: Install “osTicket-v1.15.8.zip” -> extract -> it will open folder w “scripts | upload”
  
<img width="989" height="665" alt="image" src="https://github.com/user-attachments/assets/5cd32e94-6a80-4aa9-b207-37f3a3e686da" />

  &emsp;- Put the “upload” folder into “c:\inetpub\wwwroot” and rename “upload” to “osTicket”

- Step 12: reload ISS (stop | start)

- Step 13: Load os ticket site
  
   &emsp;- ISS -> sites -> default -> osTicket
  
   &emsp;- On the right click “Browse*.80(http)” (this should pull up the osTicket site)

<p>
<img width="861" height="773" alt="image" src="https://github.com/user-attachments/assets/5662ea93-d41b-4b84-9401-c9de99e09a08" />
</p>
<p>
This is what you should be seeing after clicking on-->((Browse*:80 (http)). If you don't see the osticket site then you may need to start from the beginning.
</p>
<br />

- Step 14: Notice some extensions are not enabled

  &emsp;- ISS -> Sites -> Default sites -> osTicket
  
  &emsp;&emsp;&emsp;- double click PHP manager (icon)

  &emsp;&emsp;&emsp;- click "enable or disable an extension" 

  &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;- Enable: php_imap.dll

  &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;- Enable: php_intl.dll

  &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;- Enable: php_opcache.dll
  
<img width="1049" height="738" alt="image" src="https://github.com/user-attachments/assets/4d415bd8-3aac-4bb1-a1e5-102c94ae7bce" />

  &emsp;- Refresh osTicket browser and see they are enabled

- Step 15: rename ost-config.php

  &emsp; - From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
  
  &emsp; - From: C:\inetpub\wwwroot\osTicket\include\ost-config.php

- Step16: Assign permissions - ost-config.php

  &emsp; - Right click-> properties -> security -> advancted -> Disable inheritance -> remove all

  &emsp; - Click add -> principal -> Everyone -> ok -> check “full control” -> ok ok ok (now osTicket has control to the configuration file)

<img width="775" height="529" alt="image" src="https://github.com/user-attachments/assets/9360ae79-55c5-4d27-99df-b2898d5d230f" />
<p>
</p>
<p>
The access should look something like this
</p>
<br />

- Step 17: Set up rest of osTicket

  &emsp; - username : Cyber123(or whatever you want)

  &emsp;- Password: Password1

- Step 18: from “osTicket installation files” install “HeidiSQL_12.3.0.6589_Setup”

  &emsp;- Double click -> check accept box -> ok ok ok

  &emsp;- Create new session -> click new root/root

  &emsp;- Create data base called “osTicket” -> rightclick dolphin -> create new -> database

- Step19: continue setting up osTicket from browser

  &emsp;- MySQL Database: osTicket

  &emsp;- MySQL Username: root

  &emsp;- MySQL Password: root

  &emsp;- Install now

- Step 20: Congratulations osTicket is installed!
- 
<img width="928" height="754" alt="image" src="https://github.com/user-attachments/assets/c98941f3-6d58-43cb-9c6e-170da8999722" />

  If done correctly you should see this on your browser
  
  &emsp;- login page: http://localhost/osTicket/scp/login.php

  &emsp;&emsp;- Username: Cyber123(this may be diffrent for you so try to use what you typed in earlier).

  &emsp;&emsp;- Password: Password1

  &emsp;- Enter Tickets: http://localhost/osTicket/







  

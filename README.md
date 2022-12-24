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

- Windows 11 Pro</b> (22H2)

<h2>List of Prerequisites</h2>

- Connect to your Virtual Machine with Remote Desktop
- Install / Enable IIS in Windows
- Install Web Platform Installer
- Install osTicket v1.15.8
- Download and Install HeidiSQL

<h2>Installation Steps</h2>
<p>
First, we will need connect to our Virtual Machine with Remote Desktop using the VM's public IP address. 
</p>
<p align="center">
<img src="https://i.imgur.com/DGOWrS5.png" height="80%" width="80%" alt="image of public IP address"/>
</p>
<br />
<p>To connect to the virtual machine, we search on the local machine for 'Remote Desktop Connection' and the following window opens and you can now copy and paste the public IP address into the provided space.
</p>
<p align="center">
<img src="https://i.imgur.com/06af4yH.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>

<br/>
<p>
Next, Install Web Platform Installer by doing a search for the Control Panel --> under programs select 'Uninstall a Program'.
</p>
<p align="center">
<img src="https://i.imgur.com/YlZlw6C.png" height="80%" width="80%" alt="unistall a program"/>
</p>
<br />
<p>After we've reached the next page, we can now select to 'Turn Windows features on or off' --> then enable the 'Internet Information Services' (IIS) from the available services.</p>
<p align="center">
<img src="https://i.imgur.com/XYQQlpa.png" height="80%" width="80%" alt="enable IIS"/>
</p>
</br>
<p>Now we can download and install Web Platform Installers. Web Platform Installers (WebPI) provides a simplified installation workflow for installing common open source web applications and web platform technologies.</p>
<p align="center">
<img src="https://i.imgur.com/59FS3S4.png" height="65%" width="65%" alt="download WebPI"/>
</br>
<p> Once WebPI is installed, we can now add MySQL 5.5 database, PHP 5.6.31, and the various verisons of between PHP (x86) 7.0 and 7.3.</p>
<p align="center">
<img src="https://i.imgur.com/SwHYmt7.png" height="650%" width="65%" alt="image of add MySql"/>
</p>
</br>
<p align="center">
<img src="https://i.imgur.com/DwQqpH8.png" height="65%" width="65%" alt="install PHP"/>
</p>
</br>
<p>MySQL 5.5 will require a name and password, root and Password1 respectively when you try to install. Make note of the name / password in a text file as you will need it again later on in the installation process.</p>
<p align="center">
<img src="https://i.imgur.com/IIFCRPG.png" height="65%" width="65%" alt="password request"/>
</p>
<p>If necessary, fix any failures (download from within lab files:
Fix any failures in the installation by going to Google Drive to <a href="https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6">download </a> and install PHP 7.3.8, PHP Manager, and Microsoft Visual C++ 2009 Redistributable Package.
</p>
<p>From the downloaded files, we can now install and extract the osTicket file. Extract and copy the “upload” folder INTO c:\inetpub\wwwroot 3. Within c:\inetpub\wwwroot, Rename “upload” to “osTicket”</p>
<p align="center">
<img src="https://i.imgur.com/F1wPGL1.png" height="65%" width="65%" alt="exacted osTicket files."/>                                                                        </p>
 <p>-Reload IIS (Open IIS, Restart the server)** 1. Go to sites -> Default -> osTicket 2. On the right, click “Browse *:80”</p>
 <p align="center">
    <img src="https://i.imgur.com/A8LBhGS.png" height="65%" width="65%" alt="IIS restart"/>
    </p>
    <p align="center"> 
<img src="https://i.imgur.com/bbcdcJo.png" height=45% width="45%" alt="browse: 80"/>
    </p> 
    </br>
    <p>Once browse: 80 is selected a browser window will open presenting osTicket installer page along with the recommendation/prerequisites of use.
    </p>
    <p align="center">
    <img src="https://i.imgur.com/wcCxx5C.png" height="45%" width="45%" alt="os ticket installer"/>
    </p>
    </br>
<p> Next we'll go back to IIS, sites -> Default -> osTicket 2. Double-click PHP Manager 3. Click “Enable or disable an extension” 1. Enable: php_imap.dll 2. Enable: php_intl.dll 3. Enable: php_opcache.dll -
 <p align="center"<img src="https://i.imgur.com/YVjKOMp.png" height="50%" width="50%" alt="php manager"/>
 </p>
 </br>
 <p align="center">
 <img src="https://i.imgur.com/elGuTsd.png" height="45%" width="45%" alt="php extension enabled"/>
 </p>
 </br>
 <p align="center">
 <img src="https://i.imgur.com/cMtCuaA.png" height="45%" width="45%" alt="php extension enabled"/>
 </p>
 </br>
Refresh the osTicket site in your browser to see what has changed after enabling the PHP extensions  
<p align="center">
<img src="https://i.imgur.com/PPNziV5.png" height="45%" width="45%" alt="refreshed osticket installer"/>
 </p>
 </br>
Rename: From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php --->	To: C:\inetpub\wwwroot\osTicket\include\ost-config.php
 <p align="center">
 <img src="https://i.imgur.com/u0bCrDC.png" height="50%" width="50%" alt="ost-sample image"/>
 </p>
<p align="center">
 <img src="https://i.imgur.com/mkBhToH.png" height="50%" width="50%" alt="ost-config image"/>
 </p>
<hr>
Assign Permissions: ost-config.php 
 To change the permissions, right-click ost-config --> select properties --> select the 'Security' tab at the top --> select the 'Advanced' button1. Disable inheritance -> Remove All 2. New Permissions -> Everyone -> All
 <p align="center">
 <img src="https://i.imgur.com/Ds8JUvt.png" height="50%" width="50%" alt="properties selection"/>
 </p>
 <p align="center">
 <img src="https://i.imgur.com/rKhcHkW.png" height="50%" width="50%" alt="change permissions"/>
</p>
</br>
<p align="center">
<img src="https://i.imgur.com/IxpkEaE.png" height="50%" width="50%" alt="disable inheritance"/>
 </p>
<p align="center">
<img src="https://i.imgur.com/xajjPGK.png" height="50%" width="50%" alt="remove all inherited"/>
 </p>
Then add new permissions for everyone and give Full Control.
<p align="center">
 <img src="https://i.imgur.com/Q9XQLXm.png" height="50%" width="50%" alt="add permssions for everyone"/>
 </p>
 <p>After returning to the browser windows with osTicket installer and press 'Continue', you will now see the below form to complete before continuing.  
 <p align="center">
 <img src="https://i.imgur.com/fjKAgGk.png" height="50%" width="50%" alt="osticket form"/>
</p>
<p> Download and install HeidiSQL from <a href="https://drive.google.com/drive/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6">Google Drive</a> using the provided defaults that are available in the install wizard.
 <hr>
<p align="center">
 <img src="https://i.imgur.com/oImw5w0.png" height="50%" width="50%" alt="completion of heidisql install"/>
 <p> Next we will do the following in HeidiSql:</p>
<ol>
 <li>Create a new session, username:root/password:Password1</li>
 <li>Connect to the session</li>
<li>Create a database called “osTicket”</li>
 </ol>
 <p align="center">
 <img src="https://i.imgur.com/D2QfMEb.png"  height="50%" width="50%" alt="create HeidiSql session"/> </p>
 <p align="center">
 <img src="https://i.imgur.com/3bMHP2K.png" height="50%" width="50%" alt="create database HeidiSql"/> </p>
 <p>Created database for "osTicket":</p>
 <p align="center">
 <img src="https://i.imgur.com/mLg4tOl.png" height="50%" width="50%" alt="create data base osTicket"/> 
</p>
<p> After the database is created, we can now enter those details into osTicket Installer 
<li>MySQL Username: root</li>
 <li>MySQL Password: Password1</li>
<li>Click <b><i>“Install Now!”</i></b></li>
</p>
<p> Congratulations, hopefully it is installed with no errors!
</p>
<p align="center">
 <img src="https://i.imgur.com/V3GSvvT.png" height="50%" width="50%" alt="congratulations of completion for osTicket"/>
</p>
 <p> Results below are from of choosing for <u>"Your Staff Control Panel"</u> or <u>"Your osTicket URL:"</u> </p>
 <p align="center"><img src="https://i.imgur.com/LhTgI92.png" height="50%" width="50%" alt="available links to choose help desk or admin"/>
 </p>
 <p align="center">
 <img src="https://i.imgur.com/jNkPZNC.jpg" height="65%" width="65%" alt="Admin login for osTicket"/>
</p>
<p> "Your osTicket URL" will direct us to the "End User" Portal where Users can submit tickets for assistance from the help desk.
 <p align="center">
  <img src="https://i.imgur.com/ErvbCg6.png" height="65%" width="65%" alt="End user login page to open/check ticket status"/>
  </p>
  <p> - <i>Clean up</i>
    <ol>
    <li> Delete: C:\inetpub\wwwroot\osTicket\setup</li>
    <li> Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php</li> 
    <li><i>Login to the osTicket Admin Panel</i> ([http://localhost/osTicket/scp/login.php](http://localhost/osTicket/scp/login.php))
  </p>
  <p align="center">
 <img src="https://i.imgur.com/XGHz3lx.png" height="65%" width="65%" alt="delete setup folder"/>
 </p>
 <p> Set Permission to "Read" only can be acheived by choosing to right-click on 'ost-config.php' --> select properties --> select the 'Security' tab near the top --> then click the 'Advanced' button (not pictured below) --> once advanced settings is selecting, you can now select the 'Everyone' principle and now we can select to choose 'Read' only as the preferred permission(s)</p>
 <p align="center">
 <img src="https://i.imgur.com/AXCIeQN.png"  height="65%" width="65%" alt="read-only permissions"/>
 </p>
 <p align="center">
 <img src="https://i.imgur.com/R11rIMd.png"  height="65%" width="65%" alt="read-only allow is shown for osticketcong file"/>
 </p>



                                                                                 

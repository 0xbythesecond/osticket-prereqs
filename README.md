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
<img src="https://i.imgur.com/06af4yH.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
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
    <p>Once browse: 80 is selected a browser window will open presenting osTicket installer page
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
                                                                                 

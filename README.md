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
<img src="https://i.imgur.com/DGOWrS5.png" height="80%" width="80% alt="image of public IP address"/>
</p>
<br />
<p>
To connect to the virtual machine, we search on the local machine for 'Remote Desktop Connection' and the following window opens and you can now copy and paste the public IP address into the provided space.
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
<p>After we've reached the next page, we can now select to 'Turn Windows features on or off' --> then enable the 'Internet Information Services' (IIS) from the available services.
<p align="center">
<img src="https://i.imgur.com/XYQQlpa.png" height="80%" width="80%" alt="enable IIS"/>
</p>
</br>
<p>Now we can download and install Web Platform Installers. Web Platform Installers (WebPI) provides a simplified installation workflow for installing common open source web applications and web platform technologies.</p>
<p align="center">
<img src="https://i.imgur.com/59FS3S4.png" height="80%" width="80%" alt="download WebPI"/>
</br>
<p> Once WebPI is installed, we can now add MySQL 5.5 database, PHP 5.6.31, and the various verisons of between PHP (x86) 7.0 and 7.3.
<p align="center">
<img src="https://i.imgur.com/SwHYmt7.png" height="80%" width="80%" alt="image of add MySql"/>
</p>
<p align="center">
<img src="https://i.imgur.com/DwQqpH8.png" height="80%" width="80%" alt="install PHP"/>
</p>

<p>MySQL 5.5 will require a name and password, root and Password1 respectively when you try to install. Make note of the name / password in a text file as you will need it again later on in the installation process.</p>
<p align="center">
<img src="https://i.imgur.com/IIFCRPG.png" height="80%" width="80%" alt="password request"/>
</p>
<p>If necessary, fix any failures if required (download from within lab files: [<a href="https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6>link</a>]
    1. Install PHP Version 7.3.8 (or any other version if necessary, [archives](<a>https://windows.php.net/downloads/releases/archives/</a>))
    2. Install PHP Manager 1.5.0 for IIS 10 (the folder you unzipped on the desktop)
    3. Install Microsoft Visual C++ 2009 Redistributable Package
- **Install osTicket v1.15.8**
    1. Download osTicket (download from within lab files: [link](<a>https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6</a>))
    2. Extract and copy the “upload” folder INTO c:\inetpub\wwwroot
    3. Within c:\inetpub\wwwroot, Rename “upload” to “osTicket”

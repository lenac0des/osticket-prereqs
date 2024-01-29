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

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Azure Virtual Machine
- osTicket Installation files
- Heidi SQL


<h2>Installation Steps</h2>

<p>
Hello, welcome to my explanation of osTicket Installation and Prerequisites.  Before diving in, we will have to create a Virtual machine (VM) using the Microsoft Azure portal. We will be using a VM, which is a remote computer. We are using a VM in order to protect our physical machine just in case something breaks. Create a resource group and title it "osTicket." Afterwards, create a VM with 2-4 CPUs. In this example, I will be using 4 CPUs.
</p>
<br />

<p>
<img src="https://github.com/lenac0des/osticket-prereqs/assets/71302899/cdb81f21-1d91-445e-a56a-66be1f5a6485" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
Next, simply connect to your newly created VM using RDP using the public IPv4 address. If you are a Mac user, you will have to download Microsoft RDP. Since I am a Windows user, I will be using remote desktop. 
</p>
<br />

<p>
<img src="https://github.com/lenac0des/osticket-prereqs/assets/71302899/7afa2159-4a75-474b-903e-c735c373fc5f" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Alright, now that you are connected to your VM, you will have to enable IIS. Simply access the control panel, then select Uninstall a program. Off to the left, select "Turn Windows features on or off." A list will appear, and then you will enable Internet Information Services.
</p>
<br />

<p>
<img src="https://github.com/lenac0des/osticket-prereqs/assets/71302899/964066ee-7be5-4918-931d-d3048d5b7e28" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p> Now that you have enabled IIS, we need to install Web Platform Installer. I have provided a link here: https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6. That link will provide you with all of the material you need to download to get osTicket up and running. Simply click the link and install the Web Platform Installer.
</p>
<br />

<p>
<img src="https://github.com/lenac0des/osticket-prereqs/assets/71302899/49b4487f-b75a-4415-8e20-38a1a1b77627" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once the Web Installer Platform has been installed, open it. From inside the application, you are going to install MySQL 5.5. Afterwards, install x86 version of PHP up until 7.3. There are some failed files, such as the C++ redistributable package, PHP 7.3.8, and PHP Manager for IIS; those files can be found with the install link.

<br />

<p>
<img src="https://github.com/lenac0des/osticket-prereqs/assets/71302899/6ffaef6b-479a-4130-8ff3-ed9f623e412f" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next, download osTicket. Then extract and copy the "upload" folder into c:\inetpub\wwwroot. Afterwards, rename the folder to osTicket:
</p>
<br />

<p>
<img src="https://github.com/lenac0des/osticket-prereqs/assets/71302899/c5e9f696-2676-487f-a508-73561638013e" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Open IIS Manager and restart the server. Once inside the IIS manager, go to Sites->Default->osTicket on the right, and click "Browse*.80" From there, your default browser should open the osTicket webserver.
</p>
<br />
<p>
<img src="https://github.com/lenac0des/osticket-prereqs/assets/71302899/fc9e801b-7a53-46b2-b9c4-ef227046eb29" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
Go back into the IIS manager and enable some extensions. To do this, you have to go to Sites->Default->osTicket, Then double-click on PHP manager. Click on "Disable or enable an extension." Enable "php_intl.dll" & "php_opcache.dll," then refresh the osTicket webserver and observe the changes. "Intl Extension" should now be enabled.
</p>
<br />

<p>
<img src="https://github.com/lenac0des/osticket-prereqs/assets/71302899/7c9a7b9a-52d2-4ff8-803f-c401428cee10" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
Go back into c:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php and rename the file to c:\inetpub\wwwroot\osTicket\include\ost-config.php Assign permissions to ost-config.php Disable inheritance->Removeall New Permissions->Everyone->all.
</p>
<br />

<p>
<img src="https://github.com/lenac0des/osticket-prereqs/assets/71302899/07e0e4a3-d870-4cfd-9241-801288faed78" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
Afterward, continue setting up osTicket in the browser (click continue), and then you will name the Helpdesk to your liking. Select a default email that will receive emails from customers who submit tickets.
</p>
<br />
<p>
<img src="https://github.com/lenac0des/osticket-prereqs/assets/71302899/4279149e-0191-4190-981c-f0f2f2105d95" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
<p>
Continue Setting up osTicket in the browser MySQL Database: osTicket MySQL Username: root, MySQL Password: Password1 Click “Install Now!” Congratulations! Hopefully, it is installed with no errors! Clean up Delete: C:\inetpub\wwwroot\osTicket\setup Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php Login to the osTicket Admin Panel (http://localhost/osTicket/scp/login.php)
</p>
<br />
<p>
<img src="https://github.com/lenac0des/osticket-prereqs/assets/71302899/a5eb6a7b-a0ea-41cf-9e1f-69ee499d33b6" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
<p>
Finished!
</p>
<br />



<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server
- Windows 11

<h2>High-Level Deployment and Configuration Steps</h2>

- Step 1
- Step 2
- Step 3
- Step 4

<h2>Deployment and Configuration Steps</h2>
<p></p>Start off setting up a virtual machines, the first should be a Domain Controller that must be set up as a windows server for the image, the next can be a standard windows VM, once these have been created open up the domain controler, Server Manger will automatically open and set up will start here.
<br />
For an actual Active Directory there will need to be properly configured firewall settings, however for this testing purpose the firewall was turned off, in a real world application this would not be advised. Take the Private IP address of the domain controller and go to the client side virtual machines network settings and set up the DNS servers to point to that domain controller IP address. Opening Client one and running the powershell command should allow you to ping the domain controller, running IPConfig /all should show the DNS settings are pointing to the domain controller IP.
<br />
Now that these are both connected, back in the domain controller under Server Manager Select "add roles and features" go through the set up and be sure to select "Active Directory Domain Services" under the server roles, this will be the main thing to check during this install for this purpose. Once active directory is installed domain controller will need to be configured to be used as a domain controller by setting up a new forest. After restarting the domain controller you should finally be able to check "Active Directory Users and computers and begin setting up your AD.
</p>
<p alignment=center><img src="https://github.com/JakeMandeville/course-pictures/blob/main/AD/AD%20running.png"></p>


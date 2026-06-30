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

- Download the Active Directory
- Set up the domain controller forest
- Begin setting up organizational groups and add users to them.
- Connect your client side VM to the domain account.
- 

<h2>Deployment and Configuration Steps</h2>
<p></p>Start off setting up a virtual machines, the first should be a Domain Controller that must be set up as a windows server for the image, the next can be a standard windows VM, once these have been created open up the domain controler, Server Manger will automatically open and set up will start here.
<br />
For an actual Active Directory there will need to be properly configured firewall settings, however for this testing purpose the firewall was turned off, in a real world application this would not be advised. Take the Private IP address of the domain controller and go to the client side virtual machines network settings and set up the DNS servers to point to that domain controller IP address. Opening Client one and running the powershell command should allow you to ping the domain controller, running IPConfig /all should show the DNS settings are pointing to the domain controller IP.
<br />
Now that these are both connected, back in the domain controller under Server Manager Select "add roles and features" go through the set up and be sure to select "Active Directory Domain Services" under the server roles, this will be the main thing to check during this install for this purpose. Once active directory is installed domain controller will need to be configured to be used as a domain controller by setting up a new forest. After restarting the domain controller you should finally be able to check "Active Directory Users and computers and begin setting up your AD.
<p align="center"><img src="https://github.com/JakeMandeville/course-pictures/blob/main/AD/creating%20AD%20in%20windows%20server%20manager.png"></p>
</p>
<p align="center"><img src="https://github.com/JakeMandeville/course-pictures/blob/main/AD/AD%20running.png"></p>
<p>
  Here you can begin creating new organization units under the forest, in this instance it is simply named "mydomain.com"
  <p align="center"><img src="https://github.com/JakeMandeville/course-pictures/blob/main/AD/create%20org%20units.png"></p>
  You can begin creating users under the _ADMINS and _EMPLOYEES groups, these groups will allow both types of users to easily have different types of access within the server.
  <p align="center"><img src="https://github.com/JakeMandeville/course-pictures/blob/main/AD/Add%20user%20-%20adjust%20groups.png"></p>
  This will allow Jane does to log into the Domain controller as jane doe in the "mydomain.com\" domain allow Jane to also have admin capabilities under this domain, she should be capable of adding users as well.
</p>
<br />
<p>
  At this point start up the client side VM under and under the PC settings "About" page select "Rename this PC (advanced)" select "Change" and set the domain of the device to "mydomain.com".
  <br />
  Back in the domain controller you can open the Active directory users and computers and confirm that the client side device is now listed under computers
  <p align="center"><img src="https://github.com/JakeMandeville/course-pictures/blob/main/AD/add%20computer%20to%20AD.png"></p>
</p>
<p>
  
</p>

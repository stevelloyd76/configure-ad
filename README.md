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

- Windows Server 2022
- Windows 10 (22H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Setup Resources in Azure - Creating Virtual Machines x2
- Install Active Directory / Create an Admin and Normal User Account
- Create an Admin and Normal User Account in AD / Create an Organizational Unit (OU) called “_EMPLOYEES” and “ADMINS”

- Create a bunch of additional users and attempt to log into with one of the users

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://i.imgur.com/L7Ffjt1.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<img src="https://i.imgur.com/AQj2Iqf.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<img src="https://i.imgur.com/Lw8Mizu.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p>
To set up resources in Azure, you'll need to create a Domain Controller VM on Windows Server 2022. Make sure you write down the Resource Group and Virtual Network (Vnet) that was created during the process. These values will be used later to create the Client VM. To avoid problems later, set the Domain Controller's NIC Private IP address to be static. Once that's done, create the Client VM on Windows 10 using the same Resource Group and Virtual Network as the Domain Controller. Both VMs must be in the same Virtual Network. You can check the topology with Network Watcher. That's it! With these simple steps, you'll have your Azure resources set up in no time.
</p>
<br />

<p>
<img src="https://i.imgur.com/34YRTgh.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
To create an Admin and Normal User Account in AD, you can follow these steps:

1. Open Active Directory Users and Computers (ADUC).
2. Right-click on your domain name and select "New" > "Organizational Unit" to create a new Organizational Unit (OU).
3. Name the new OU "_EMPLOYEES" and click "OK".
4. Right-click on the "_EMPLOYEES" OU and select "New" > "User" to create a new user account.
5. Enter the required details for the user, such as first name, last name, and username.
6. Choose a password for the user and set any other required options.
7. Click "Next" and then "Finish" to create the user account.

To create an Admin user account, you'll need to repeat this process for a new OU called "_ADMINS". Once you've created the "_ADMINS" OU, create a new user account and make sure to give it administrative privileges by adding it to the appropriate security groups.
</p>
<br />

<p>
<img width="1440" alt="ECB4B08B-39B1-4CAB-82D8-B8A030F5E2C8" src="https://github.com/stevelloyd76/configure-ad/assets/162848869/f9fd4ec9-d291-477d-bf14-8c6e326580d6">

</p>
<p>
Created additional users in PowerShell
</p>
<br />

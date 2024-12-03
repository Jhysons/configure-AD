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
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Install Active Directory
- Create Domain Admin User
- Configure Active Directory
- Setup Remote Desktop

<h2>Connect to the Server via Remote Desktop</h2>


Open Remote Desktop Connection: On your local machine, press Win + R, type mstsc, and press Enter.

Enter the Server's IP Address: In the Remote Desktop Connection window, enter the IP address or hostname of the server you want to connect to and click Connect.

Log In: Enter your credentials to log in to the server.

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://i.imgur.com/0W2jNdX.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Open Server Manager: Click on the Start menu, then select Server Manager.

Add Roles and Features: In Server Manager, click on "Add Roles and Features".

Role-based or feature-based installation: Select this option and click Next.

Select the server: Choose the server you want to install AD DS on and click Next.

Select server roles: Check the box for "Active Directory Domain Services" and click Next.

Add features: Click "Add Features" when prompted, then click Next.

Confirm installation selections: Review the selections and click Install.
<br />

<p>
<img src="https://i.imgur.com/W4wHbmB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Open the AD DS Configuration Wizard: After the installation completes, click on the flag icon in Server Manager and select "Promote this server to a domain controller".

Deployment Configuration: Choose "Add a new forest" and enter a root domain name (e.g., example.com).

Domain Controller Options: Select the forest and domain functional levels, and set a Directory Services Restore Mode (DSRM) password.

DNS Options: Click Next (you might see a warning about DNS delegation, which you can ignore for now).

Additional Options: Verify the NetBIOS name and click Next.

Paths: Specify the locations for the AD database, log files, and SYSVOL folder, or leave the defaults and click Next.

Review Options: Review your selections and click Next.

Prerequisites Check: The wizard will run a prerequisites check. Once it passes, click Install.
</p>
<br />

<p>
<img src="https://i.imgur.com/itJLPQ6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Open Active Directory Users and Computers: After the server restarts, open Server Manager, go to Tools, and select "Active Directory Users and Computers".

Create Organizational Units (OUs): Right-click your domain, select New > Organizational Unit, and name it (e.g., "Users").

Create Users: Right-click the OU you created, select New > User, and fill in the details.

Create Groups: Right-click the OU, select New > Group, and name it
Add Computers to the Domain: On client machines, go to System Properties, click "Change settings" under Computer name, domain, and workgroup settings, and join the domain.

Assign Permissions: Use Active Directory Users and Computers to assign users to groups and set permissions.
</p>
<br />

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
- Join Client-1 to Domain
- Setup Remote Desktop

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://i.imgur.com/0W2jNdX.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Install AD DS: Log into DC-1 and install Active Directory Domain Services.
Promote to DC: Set up a new forest (e.g., mydomain.com), restart, and log back into DC-1
</p>
<br />

<p>
<img src="https://i.imgur.com/W4wHbmB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create OUs: In ADUC, create Organizational Units (OUs).
Create User: Create a new employee.Add to Group: Add Admins to the Domain Admins Security Group.
Log in as Admin: Log out and log back in.
</p>
<br />

<p>
<img src="https://i.imgur.com/itJLPQ6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Set DNS: Set Client-1's DNS settings to the DC's Private IP address in the Azure Portal.
Restart Client-1: Restart Client-1 from the Azure Portal.
Join Domain: Log into Client-1 as the local admin and join it to the domain.
Verify in ADUC: Verify Client-1 shows up in ADUC.
Move to OU: Create a new OU named and move Client-1 into it.
Create Users: Log into DC-1, create additional users.
Verify Users: Verify the accounts in ADUC and attempt to log into Client-1 with one of the new accounts.  
</p>
<br />

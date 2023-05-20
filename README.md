# network-file-share<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Network File Shares and Permissions</h1>
This tutorial builds upon the on-premises Active Directory guide and showcases the process of network file sharing and configuring permissions on the domain controller.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- Command Line

<h2>Operating Systems Used </h2>

- Windows Server 2022

<h2>Network File Sharing and Permissions</h2>

- Creating Folders in Domain Controller
- Assigning Permissions to Folders
- Access files in Client Computer
- Create Security Group in Active Directory

<h2>Creating Folders in Domain Controller</h2>
<p>
<img src="https://imgur.com/JroTrs4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once logged into both the Domain Controller and Client computer, we can navigate to "File Explorer" and proceed to create four folders on the C: drive. Simply right-click in the C: drive, select "New," then choose "Folder" and provide the desired names (Read-Access, Write-Access, No-Access, Accounting).
</p>
<br />
<h2>Assigning Permissions to Folders</h2>
<p>
<img src="https://imgur.com/LjoS2vH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Within the Read-Access and Write-Access folders, we have the ability to allocate permissions to the "Domain Users" group. In the Read-Access folder, "Domain Users" will have read-only privileges, while in the Write-Access folder, they will have both read and write permissions. On the other hand, the "Domain Admins" group will have read and write access in the No-Access folder. To configure permissions, simply right-click on the folder, select "Properties," navigate to the "Share" tab, enter "Domain Users" in the textbox, click "Add," choose either "Read" or "Read or Write" for the Domain Users group, and click "Share." Remember to apply the same steps for both the Read-Access and Write-Access folders. For the "No-Access" folder, ensure that "Domain Admins" are added. Currently, it is advised not to assign any permissions to the accounting folder.
</p>
<br />
<h2>Access files in Client Computer</h2>
<p>
<img src="https://imgur.com/xPYVKJO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Subsequently, log in to Client-1 using a regular user account from the employee roster to observe the accessible files or add new files.
</p>
<br />
<h2>Create Security Group in Active Directory</h2>
<p>
<img src="https://imgur.com/FDCLZj4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Within Server Manager on the domain controller, we have the option to create a new security group named "Accountants". To do so, right-click below the domain name, select "Group", and assign a name to the group. Afterward, navigate to the "accounting folder" to allocate permissions and restrict access solely to the "Accountants" group. Right-click on the "Accounting" folder, access "Properties", proceed to "Share", input "Accountants" in the provided textbox, click "Add", choose either "Read or Write" for the Accountants group, and finalize by clicking "Share", "Apply", and "Ok" to apply the permissions. Following this, add a user to the "accountant group" by selecting "Members", clicking "Add", and entering the "Created User Name" from the previous lab. Lastly, sign in as the designated user, and you should gain access to the accounting folder accordingly.
</p>
<br />

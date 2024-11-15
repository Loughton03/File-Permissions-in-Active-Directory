<p align="center">
<img src="https://i.imgur.com/cvGKzqB.png" alt="logo"/>
</p>

<h1>Understanding File Permissions in an Active Directory Enviornment</h1>
This lab explores configuring file permissions and shared folders within an Active Directory domain, a critical process for ensuring users access files appropriately in a business environment. Building on a previous lab, I am logged into the domain controller VM as "Jane Doe" (admin account) and on the client VM as a standard user.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines)
- Remote Desktop Connection
- Active Directory Domain Services

<h2>Environments and Technologies Used</h2>

- Windows Server 2022
- Windows 10 Pro

<h2>File Permissions Configuration Steps</h2>

<img src="https://i.imgur.com/fmGRmxl.png" height="80%" width="80%" alt="folder-creation-for-file-persmisions"/>

<img src="" height="80%" width="80%" alt="place-holder"/>

<p>
I logged in as an admin on the domain controller and created four folders on the C:\ drive with names indicating their intended access level. To configure sharing, I accessed each folder's Properties, selected "Share" under the Sharing tab, and specified network users and permissions:
</p>

- Domain Users have **Read** access to the "read-access" folder and **Read/Write** access to the "write-access" folder.
- Domain Admins have **Read/Write** access to the "no-access" folder.

<img src="" height="80%" width="80%" alt="place-holder"/>

<p>
On the client VM, I navigated to \dc-1 in File Explorer to view the shared folders. As expected, specific folders only allowed viewing without modification, while others had no access. This demonstrated how folder permissions correspond to Security Group memberships and each folder's specific access settings.
</p>

<img src="" height="80%" width="80%" alt="place-holder"/>

<img src="" height="80%" width="80%" alt="place-holder"/>

<p>
To control access to an "accounting" folder, I created a new Security Group called "ACCOUNTANTS" in the domain controller's Active Directory Users and Computers panel. I then granted Read/Write permissions to this group for the "accounting" folder.
</p>

<img src="" height="80%" width="80%" alt="place-holder"/>

<img src="https://i.imgur.com/aSMil2y.png" height="80%" width="80%" alt="accessing-accounting-folder"/>

<p>
To finalize access, I added the client user, bon.rovej, to the ACCOUNTANTS group. After logging off and back on, bon.rovej could access the "accounting" folder, validating the permissions configuration.
</p>

<h3>Lessons Learned</h3>

<p>
This lab provided practical insight into configuring file permissions within an Active Directory domain. In a real-world setting, permissions should be carefully tailored so that users can access only the resources necessary for their roles, maintaining security and minimizing access.
</p>

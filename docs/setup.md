# Setup Guide

## 1. Installing Windows Server 2022 and Windows 11 Pro
I used a Windows Server 2022 Evaluation iso, a Windows 11 Pro iso, and VirtualBox to setup my Windows Server
and Windows 11 Pro client.

# 1.1. Connecting the server and client to the same LAN
In VirtualBox, I set the network adapters of both the Windows Server 2022 and Windows 11 Pro virtual machines
to "Internal Network" to simulate both devices being connected to a switch.

## 2. Setting a static IP address for the Windows Server
Since the server is a device that (in the real world) will need to be reliabily accessed, 
I configured a static IP address inside ethernet adapter properties for IPv4, and set its 
DNS as it's own IP address to ensure AD and other domain services function correctly.

## 3. Adding AD roles to the Windows Server
In this step, I go through the process of adding Active Directory roles to the server to 
manage users, computers, and network resources in a Windows domain.

# 4. Promoting the Windows Server to the domain controller
After adding AD Domain Services to the server, Server Manager requires the administrator to 
promote the server to a domain controller. This installs and configures DNS with it.

# 5. Adding a root domain name
In the Active Directory Domain Services Configuration Wizard, I deployed the server to a new forest and named
the root domain to lab.local.

# 5.1. Configurating the rest of the settings in the AD Domain Services Configuration Wizard
I kept the default settings for the rest of the settings, like Domain Controller Options,
DNS Options, Additional Options, and Paths, since they work for my simple lab deployment.

# 6. Adding DHCP Server role and creating an IP scope
I added DHCP Server roles to the server and completed the DHCP Post-Install configuration, which involved
authorizing the server and creating an IP address scope for the DHCP server to lease to its clients. I configured
the lease duration for 8 days, since there is only one computer registered in the domain currently. In the real-world,
the amount of users connecting to the network would determine how much time would be assigned to leases, with a shorter
lease time for networks that have users constantly joining and leaving or there are too many users for the amount of IP
addresses.

# 7. Connecting the Windows 11 Pro Host to the Windows Server's DHCP.
On the Windows 11 Pro Host, I configure the Internal Network Ethernet Adapter in Control Panel to receive an IP address
from the DHCP server on the Windows Server domain controller. I verify that the client leased an IP address through the
ipconfig /all command in the Windows Command Prompt.

# 8. Joining the Windows 11 Pro Host to the lab.local domain.
On the Windows 11 Pro VM, I configure it as a member of the domain lab.local in the System Properties tab in Settings. 
Windows prompts me to enter the user name and password of an account with permission in order to add the Windows 11 Pro 
VM, so I input the administrative user's credentials. I confirm the computer joined the domain in Active Directory Users
and Computers in Server Manager. 

# 9. Creating Organizational Units
In Active Directory Users and Computers in Server Manager, I create the OU titled "Employees" and another OU within it called "IT".
In Employees, I created the user John Smith and in IT, I created the user Jane Doe. This was to practice OU organization and
blocking GPO inheritance. 

# 10. Restricting Access for users in the Employees OU.
I created a GPO that prohibited access to Control Panel and PC Settings and applied it to the Employees OU. Since GPOs are inherited
by sub-GPOs due to AD's hierarchical structure and users in the IT department need access to these applications, blocking its 
inheritance is necessary.

# 11. Adding CMD shortcut to users in the IT OU's desktop
In this GPO, I created a shortcut located on the Desktop with a target path of C:\Windows\System32\cmd.exe for easy access when a user
of the IT OU may be troubleshooting.

# 12. Verifying users Jane Doe and John Smith are affected by their appropriate OU's GPO.
I logged onto John Smiths's account on the Windows 11 Pro Virtual Machine and was denied permission to open the Control Panel 
and Settings applications. When logged into Jane Doe's account, I was able to open both applications as well as see the CMD shortcut
on my desktop. 




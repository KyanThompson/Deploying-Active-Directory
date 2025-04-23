# Deploying-Active-Directory# Preparing-Ad-infrastructure<p align="center">
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

- Active Directory Domain Services were installed on DC-1, and the server was promoted to a Domain Controller for the domain mydomain.com.

- I created two Organizational Units (OUs) called _EMPLOYEES and _ADMINS. Then, I made a domain admin user named jane_admin and added her to the Domain Admins group.

- Client-1 was connected to the domain successfully, and I moved it into a new OU named _CLIENTS in Active Directory to keep things organized.

<h2>Deployment and Configuration Steps</h2>



![image](https://github.com/user-attachments/assets/4e380727-eeb1-4f19-98bb-0371a6c7c319)![image](https://github.com/user-attachments/assets/1ab8c11c-46f9-4cb6-bd70-56a25ddaa89f)
![image](https://github.com/user-attachments/assets/0f113cad-3218-4efc-b8dc-4566ff03d893)![image](https://github.com/user-attachments/assets/8c441ade-0e6e-4ce6-bf54-1b83c5dab66e)



Part 1: Setting Up Active Directory

Sign in to DC-1: Start by logging into the server named DC-1.

Add Active Directory Role: Open Server Manager and install the "Active Directory Domain Services" (AD DS) role.

Make DC-1 a Domain Controller:
While installing AD DS, you'll get the option to promote the server to a domain controller. Select the option to create a new forest, and enter your domain name (for example, mydomain.com).

Restart the Server: Once the setup is done, restart DC-1 so the changes can take effect.

Log Back In: After the restart, log in to DC-1 using your domain credentials, like this: mydomain.com\labuser.




![image](https://github.com/user-attachments/assets/f6c56b9b-7dd0-4ce5-a587-f9b9e7a0215f)![image](https://github.com/user-attachments/assets/b152083e-fda2-4bbf-a5ee-b04bb1634419)
![image](https://github.com/user-attachments/assets/4dd3a947-bd11-4ef4-8ab7-fe43e2a6035a)![image](https://github.com/user-attachments/assets/c851d8f6-f031-4ec7-9ac1-301c282be772)

Part 2: Create a Domain Admin and Add Client-1 to the Domain

Set Up Organizational Units:
Open Active Directory Users and Computers (ADUC). Create two new Organizational Units (OUs): one called _EMPLOYEES and another called _ADMINS.

Add a Domain Admin User:
Make a new user account named Jane Doe with the username jane_admin and password Cyberlab123!. Then, add jane_admin to the Domain Admins group to give her admin privileges.

Sign in as jane_admin:
Log out of DC-1, then log back in using the jane_admin account (mydomain.com\jane_admin). From now on, use this account for admin tasks.

Connect Client-1 to the Domain:
On the Client-1 machine, sign in as the local admin (labuser). Join Client-1 to the domain mydomain.com. The computer will restart. After that, log back into DC-1 and check ADUC to make sure Client-1 shows up.

Move Client-1 to a New OU:
In ADUC, create a new OU called _CLIENTS, then drag Client-1 into that OU to keep things organized.





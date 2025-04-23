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





![image](https://github.com/user-attachments/assets/4e380727-eeb1-4f19-98bb-0371a6c7c319)![image](https://github.com/user-attachments/assets/1ab8c11c-46f9-4cb6-bd70-56a25ddaa89f)
![image](https://github.com/user-attachments/assets/0f113cad-3218-4efc-b8dc-4566ff03d893)![image](https://github.com/user-attachments/assets/8c441ade-0e6e-4ce6-bf54-1b83c5dab66e)








Part 1: Setting Up Active Directory

Sign in to DC-1: Start by logging into the server named DC-1.

Add Active Directory Role: Open Server Manager and install the "Active Directory Domain Services" (AD DS) role.

Make DC-1 a Domain Controller:
While installing AD DS, you'll get the option to promote the server to a domain controller. Select the option to create a new forest, and enter your domain name (for example, mydomain.com).

Restart the Server: Once the setup is done, restart DC-1 so the changes can take effect.

Log Back In: After the restart, log in to DC-1 using your domain credentials, like this: mydomain.com\labuser.


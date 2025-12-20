<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Post-Install Configuration</h1>
This tutorial outlines the post-install configuration of the open-source help desk ticketing system osTicket.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 11

<h2>Post-Install Configuration Objectives</h2>

- Set up role-based access to control agent permissions

- Organize ticket flow using departments and teams

- Configure agent and user accounts

- Allow public ticket creation for unregistered users

- Apply SLA rules to manage ticket priority and response times

- Create help topics to route tickets correctly

<h2>Configuration Steps</h2>

<p>
<img width="1035" height="554" alt="Screenshot 2025-12-19 161543" src="https://github.com/user-attachments/assets/05ffb1e2-e3e7-475d-ac3c-b01d0413be29" />
</p>
<p>
First we are going to create a new role called Supreme Admin. This role provides full permissions to manage users, settings, and tickets. It can be created by navigating to Admin Panel → Agents → Roles and selecting Add New Role, allowing proper control of user access.
</p>
<br />

<p>
<img width="1036" height="788" alt="Screenshot 2025-12-19 164727" src="https://github.com/user-attachments/assets/2abda4fe-f410-42fd-b4a5-ae5967a266db" />
</p>
<p>
Okay, now we are creating a new department called SysAdmins.
Departments are used to organize tickets and control which agents can view and manage them.

This page can be accessed by going to Admin Panel → Agents → Departments and selecting Add New Department. Creating this department helps separate system administration tickets from other support requests and keeps ticket routing organized.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

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
<img width="800" alt="Screenshot 2025-12-19 161543" src="https://github.com/user-attachments/assets/05ffb1e2-e3e7-475d-ac3c-b01d0413be29" />
</p>
<p>
First we are going to create a new role called Supreme Admin. This role provides full permissions to manage users, settings, and tickets. It can be created by navigating to Admin Panel → Agents → Roles and selecting Add New Role, allowing proper control of user access.
</p>
<br />

<p>
<img width="800" alt="Screenshot 2025-12-19 164727" src="https://github.com/user-attachments/assets/2abda4fe-f410-42fd-b4a5-ae5967a266db" />
</p>
<p>
Okay, now we are creating a new department called SysAdmins.
Departments are used to organize tickets and control which agents can view and manage them.

This page can be accessed by going to Admin Panel → Agents → Departments and selecting Add New Department. Creating this department helps separate system administration tickets from other support requests and keeps ticket routing organized.
</p>
<br />

<p>
<img width="800" alt="Screenshot 2025-12-19 174946" src="https://github.com/user-attachments/assets/0cdf0b43-95bc-4bd5-b9bc-9449d1bdb8d7" />
</p>
<p>
Okay, now we are creating a new team called Online Banking.
Teams are used to group agents from different departments so they can work together on related tickets.

This page can be accessed by going to Admin Panel → Agents → Teams and selecting Add New Team.
</p>
<br />

<p>
<img width="800" alt="Screenshot 2025-12-23 172745" src="https://github.com/user-attachments/assets/94135e09-f45e-4dc3-bc92-08a2e9a79577" />
</p>
<p>
To configure agents (workers), go to Admin Panel → Agents → Add New. Fill in the agent’s name and email, then assign a role and department to define their permissions and responsibilities in osTicket.
</p>
<br />

<p>
<img width="800" alt="Screenshot 2025-12-23 174337" src="https://github.com/user-attachments/assets/6aa2d392-7dce-4752-b510-e3bfce4b3a83" />
</p>
<p>
To configure users (customers), navigate to Agent Panel → Users → Add New. Add users such as Karen and Ken by entering their basic details, including name and email address, so they can submit and track their support tickets.
</p>
<br />

<p>
<img width="873" height="376" alt="Screenshot 2025-12-23 181218" src="https://github.com/user-attachments/assets/903edf59-b8f9-44b8-8e4e-0300b82839aa" />
</p>
<p>
Okay, now we are configuring SLAs.
From the Admin Panel → Manage → SLA, we create different severity level SLAs and assign proper grace periods and schedules to control response times.</p>
<br />

<p>
<img width="861" height="530" alt="Screenshot 2025-12-23 182458" src="https://github.com/user-attachments/assets/f83a9481-8d93-49a5-8345-69c47ff0910d" />
</p>
<p>
Okay, now we are creating help topics.
These help topics guide users during ticket creation and help route tickets to the correct department. This page can be accessed through Admin Panel → Manage → Help Topics.

This completes the post-install configuration of the osTicket helpdesk in a home lab environment.
</p>
<br />

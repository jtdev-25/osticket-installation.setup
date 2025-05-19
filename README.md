<p align="center"><a href="https://osticket.com/">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</a></p>

# 🎫 osTicket Installation & Setup Guide

This tutorial is a complete step-by-step guide for installing and configuring the open-source **osTicket** support ticketing system(Linux(Ubuntu.22), Apache, MySQL, PHP). Includes database setup, web configuration, user creation, and post-install best practices; osTicket helps businesses and IT teams manage customer support, service requests, or internal IT help desk operations.

<h2>  <ul>  [Ticketing Systems Project (osTicket)]:</h2>
  <p>
<ol><h4>i.	DEFINE:</h4> osTicket is an extension app accessed through any browser to install/configure a web server and a database
  
  - Key functions include:
     - Centralized Ticket Management🎟️: Converts emails, phone calls, and web form submissions into tickets stored in one dashboard.
     - Workflow Automation🔁: Assigns, prioritizes, and routes tickets automatically based on rules.
     - User Support Portal🙋‍♂️: Offers a self-service portal for users to submit and track their own tickets.
     - SLA & Reporting📝: Tracks service level agreements (SLAs), agent performance, and ticket history for accountability.
<ol>1.	Internet Information Services(IIS): A built-in web server found on your browser</ol>
<ol>2.	phpManager: A backend server that allows osTicket to run on it.</ol>
<h4>ii.	Objective:</h4> increase familiarity w/Azure, use ticketing system as (user, admin, worker), better comprehend SLAs, and understanding of ticketing system per departments
<h4>iii.	Setup process:</h4>
      <ul>
        
  - Assuming the virtual machine creating process has already been completed proceed:
    - If not scroll down to "Environments and Technologies Used"
  - CHECKLIST REQUIRED: <a href="https://docs.google.com/document/d/1DyjX8LeVU98LjhXO2t2K2F0aHywI2N9GD57T3taO5qo/edit?tab=t.0"> osTicket Installation Checklist </a> 
  - Within your VM download osTicket zipfile provided: <a href="https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD">osTicket file</a>
    - Side note: To open link in a new tab you can use "CTRL+click" (on Windows and Linux) or "CMD+click" (on MacOS) since github does not support (target="_blank") from html
  - Drag the file to the desktop then "extract all" then access the actual file/folder with the content required for the following steps.
  - From the VM web browser open up a new tab and search "127.0.0.1"
    - This is the loopback ip address for the computer. When a web server like osTicket is installed it will upload here and become accessible.
  - Open “control panel” from search bar in VM homescreen ➡️ select "unistall programs" in the programs section ➡️ select "turn windows features on/off"
  - Select/expand ISS ➡️ select/expand WWW Services ➡️ select CGI and hit "ok" to confirm
    - Complete in exact chronological order to avoid errors.
    - <img width="250" height="215" alt="Screenshot 2025-05-14 at 11 03 07 PM" src="https://github.com/user-attachments/assets/36d6a834-6a58-4547-97d9-fd4030b23f8d" />
      <img width="250" height="215" alt="Screenshot 2025-05-14 at 11 06 48 PM" src="https://github.com/user-attachments/assets/b93ea5bb-99b9-4bd9-be9f-26de0b49dbc8" />
  - Reboot the 127.0.0.1 screen in browser
  - Pretty blue screen looks beter than the previous one.
  - From the previously downloaded osTicket folder select the "PHPManager" file and install: 
    -  select "yes" and "next" all the way through the installation process to let it run in the background for IIS.
    -  <img width="250" alt="Screenshot 2025-05-14 at 11 16 46 PM" src="https://github.com/user-attachments/assets/813de0dc-637c-4ec2-b9fe-dde348f83404" />
  - Install VC_redist: transfers data from one location to another; & MySQL: used to store entire database for ENTIRE ticketing system
    - <img width="250" alt="Screenshot 2025-05-14 at 11 33 23 PM" src="https://github.com/user-attachments/assets/35edf5ee-70e6-4035-824b-50ce9bd2c5df" />
      - Remove all inheritance; everyone “all access”; sign into osTicket
  - Create a folder on "C: windows" called "PHP" and allow to store all files pertaining to php manager by unzipping "php-7.3.8-nts-Win32-VC15-x86" file into new PHP folder.
  - Following installation download the MySQL(make sure it's "Typical" setup), root for user/pass and start using ticketing system
  - Access ISS from home and "Run as Administrator" ➡️ select PHP Manager ➡️ 2xClick “register new PHP version” ➡️ browse:/cfolder/PHP/cgi_jargin ➡️ reboot(stop and start)
    - <img width="300" alt="Screenshot 2025-05-19 at 7 53 33 AM" src="https://github.com/user-attachments/assets/9a1d33f9-ac8c-4c4d-b8c3-8f4a942a7f65" />
  - Extract main osTicketing system into C: wwwindows folder copy the "upload" folder into the proceeding path
    - Following this rename "upload" ➡️ "osTicket"
  - Reopen PHP Manager as admin again and reboot ➡️ under "Sites" select "osTicket" ➡️ select "Browse" to access osTicket from defaukt web browser.
    - <img width="300" alt="Screenshot 2025-05-19 at 8 03 47 AM" src="https://github.com/user-attachments/assets/6545afbf-3b84-44e0-a634-5ca60c050712" />
  - Reopen PHP Manager and access "PHP Extensions" to enable the following: "php_imap.dll", "php_intl.dll", "php_opcache.dll"
    - each extension should be right-clicked to enable.
    - <img width="305" alt="Screenshot 2025-05-19 at 8 11 22 AM" src="https://github.com/user-attachments/assets/82382c7a-fa75-4d5d-9f6e-8386fa2b4346" /> <img width="375" alt="Screenshot 2025-05-19 at 8 20 57 AM" src="https://github.com/user-attachments/assets/628cfd2b-41a7-4b11-819a-f1997206a4cb" />
  - Rename this file following this path. what is in paranthesis indicates what was oriiginally there but changed.
    - C: windows ➡️ inetpub ➡️ wwwroot ➡️ include ➡️ ost-config.php(reconfig)
  - Grant full access in permissions to "everyone" after renaming file.
  - Revisit osTicket webpage and select "continue" to input your information for the creation of your osTicketing system.
    - <img width="365" alt="Screenshot 2025-05-19 at 8 30 56 AM" src="https://github.com/user-attachments/assets/d037da80-0ce0-4a47-826a-23c9cb3480a7" />
  - Install heidiSQL; “new” followed by creating new (username/password) ➡️ “open”; select “Unnamed” create new ➡️ "database" ➡️ name = "osTicket"

      
  </ul>
  
<h4>iv.	 Post-installation:</h4> There are 3 different viewing options
<ul>
<li>1.	Admin: Handles maintenance of the osTicketing system, employees, and modifies different section pertaining to info or operations(who can access what).</li>
<li>2.	Agent: View for a help desk agent that works tickets and sees the different tickets being managed that are specific to them/their department.</li>
<li>3.	End user: This screen contains the least visibility but allows people to create tickets and contact support.</li>
</ul>
<h4>v.	Post-install steps:</h4>
  - CHECKLIST REQUIRED: <a href="https://docs.google.com/document/d/1EemwcNJBrCkZMARXThUriy74IH9ewwZSm-mHf4wvUWg/edit?tab=t.0"> osTicket Setup Checklist </a>
    - 
<ol>1.	Configure roles: make different permissions then assign to various people
<ul>a.	Roles: displays different access-levels and we must create “supreme admin” with access to everything</ul>
2.	Configure departments/teams: Places select users in different domains with varying accessibility. Groups members from different departments on the same project.
<ul>a.	Departments: access Agents ➡️ Departments +➡️(add new role) “SysAdmins” w/ all default settings for now
b.	Teams: Agents ➡️ Departments +➡️(add new team) “Online Banking” w/ all default settings for now
</ul>
3.	Adjust settings: Enable settings to allow end users to access ticket creation w/o creds.
<ul>a.	Path: Settings ➡️ Users ➡️ “Registration Required”(UNCHECK)</ul>
4.	Configure Agents: Create 2 agents and 1 end user or however many you want.
<ul>a.	Path: [ADMIN PANEL] Agents ➡️ Agents +➡️ (add new agent)  
b.	Configuration: First/Last name, email, user, “set pass”, uncheck, fill, uncheck; be mindful of team/permissions</ul>
5.	Configure End Users: These are the people making tickets
<ul>a.	Path: [AGENT PANEL] Users +➡️ (add user)</ul>
6.	Configure SLAs: Service Level Agreements state that certain tasks should be completed in a certain time frame and withing certain hours of the day. 
<ul>a.	Path: [ADMIN PANEL] Manage ➡️ SLAs +➡️ (add new sla plan) ➡️ follow template<ul>
-	Sev-A (Grace Period: 1 hour, Schedule: 24/7)
<br>-	Sev-B (Grace Period: 4 hours, Schedule: 24/7)
<br>-	Sev-C (Grace Period: 8 hours, Business Hours)
</ul>
      - <img width="350" alt="Screenshot 2025-05-19 at 9 11 36 AM" src="https://github.com/user-attachments/assets/6a10cbbf-fcca-4bec-a179-31d221c8e2af" /> <img width="350" alt="Screenshot 2025-05-19 at 9 12 24 AM" src="https://github.com/user-attachments/assets/df3591cf-7baa-4244-878d-4551e458276f" />
  <br>
</ul>
7.	Configure Help Topics: Creates a brief explanation of what the topic will cover
<ul>a.	Path: Manage ➡️ Help Topics +➡️ (add new help topic) ➡️ follow template
<ul>
-	(RAP)Sev-A (Grace Period: 1 hour, Schedule: 24/7)
<br>-	(RAP)Business Critical Outage
<br>-	(RAP)Personal Computer Issues
<br>-	(GI)Equipment Request
<br>-	(RAP)Password Reset
<br>-	(GI)Other
  </ul>
  - <img width="350" alt="Screenshot 2025-05-19 at 9 20 23 AM" src="https://github.com/user-attachments/assets/f617d618-e615-4565-b18e-5fe3fdb5d3c2" /> <img width="350" alt="Screenshot 2025-05-19 at 9 21 06 AM" src="https://github.com/user-attachments/assets/29ed96d0-f9d0-4c84-babe-15bdcab897c6" />
  </ul>
  </ol>
  </ol>
</ul>

</p>

<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com/watch?v=7fVeClRrURM)
  <img src="https://media1.tenor.com/m/GekYPcvThhkAAAAC/kanye-graduation.gif">
  

## Environments and Technologies Used

- Microsoft Azure (Virtual Machines/Compute)
  - In Azure you can create a virtual machine with a "windows 10 pro" as the image
    <img width="400" alt="Screenshot 2025-05-14 at 9 02 16 AM" src="https://github.com/user-attachments/assets/9e038732-09b5-4127-9feb-a83b60b0855a" />
  - VM Creation Steps: In Azure create a resource group:
    -  Select resource group and and name it anything pertaining to ticketing systems ➡️ leave everything else as default and select "Review + Create"
    -  Do the same for your VM ➡️ make sure the resuorce group for the vm is the same as the one you just created ➡️ select "windows 10 pro" for image ➡️ create an admin passwrod and user for the vm account ➡️ the virtual net should also align with the resource group you created since the vnets are built automatically
  - Images pertaining to steps:
    -  <img width="450" alt="Screenshot 2025-05-14 at 11 04 26 AM" src="https://github.com/user-attachments/assets/f6a56e3c-3b24-4f71-bd90-87d530fc2849" />
    - <img width="450" alt="Screenshot 2025-05-14 at 11 05 33 AM" src="https://github.com/user-attachments/assets/70f93d15-24c3-42cd-98be-6c9eeaad8146" />
    - <img width="450" alt="Screenshot 2025-05-14 at 11 07 00 AM" src="https://github.com/user-attachments/assets/46995999-d112-4fd4-855b-406c3dce781b" />
    - <img width="450" alt="Screenshot 2025-05-14 at 11 09 19 AM" src="https://github.com/user-attachments/assets/2b942a38-2479-47b4-b694-30c2cf63267b" />
    - <img width="450" alt="Screenshot 2025-05-14 at 11 10 26 AM" src="https://github.com/user-attachments/assets/899168d7-0045-4716-a0a9-2e7b7704b3c1" />


- Remote Desktop
  - In the case you have a macbook in the "Windows App" you can use your new virtual machine via the remote desktop connection after adding a new pc<br>
    <img width="400" alt="Screenshot 2025-05-14 at 10 43 34 AM" src="https://github.com/user-attachments/assets/eee88207-99a4-4b59-983d-55cbfb7b25b5" />
  
- Internet Information Services (IIS)
  - 3 Phase:
    - (Initial "127.0.0.1" search)
      - This is a result of searching the loopback ip address for the computer without a webserver being installed.
      - <img width="365" alt="Screenshot 2025-05-14 at 10 50 59 PM" src="https://github.com/user-attachments/assets/d1b54d7d-fe48-4e59-9e4c-4a71292ee54b" />

    - (Control Panel Modifications)
      - After making the modifications in the "Programs" section of the control panel this is what the default webserver looks like.
      - <img width="365" alt="Screenshot 2025-05-14 at 11 10 00 PM" src="https://github.com/user-attachments/assets/c55d9ad6-2ab7-4541-9aaa-733192159ca2" />
   
    - (OS Ticket Installation)
      - Following the installation of all the appropriate files from the osTicket file the server should now look like a regular webpage.
      - <img width="365" alt="Screenshot 2025-05-18 at 1 06 54 AM" src="https://github.com/user-attachments/assets/04fbd758-ae17-43f4-b360-10be02ddad63" />
   
---

## 🖥️ System Requirements

- Ubuntu 20.04 or 22.04
- Apache 2.4 or Nginx
- MySQL 5.7+ or MariaDB
- PHP 8.0–8.1 (minimum 7.4)
- osTicket latest release

---

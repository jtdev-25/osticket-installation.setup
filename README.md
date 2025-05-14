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
        
  - Download osTicket zipfile provided: <a href="https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD">osTicket file</a>
    - Side note: To open link in a new tab you can use "CTRL+click" (on Windows and Linux) or "CMD+click" (on MacOS) since github does not support (target="_blank") from html
  - open “control panel” from search bar in VM
  - select/expand ISS, select/expand WWW Services, select CGI
  - reboot the 127.0.0.1 screen in browser
  - pretty screen says hello; alter html with Admin notepad
  - create php file with file explorer and relocate/extract php zipfile from course
  - Install VC_redist: transfers data from one location to another; & MySQL: used to store entire database for ENTIRE ticketing system
  - Following installation download the mySQL, root for user/pass and start using ticketing system
  - Access ISS from home, 2xClick “register new” after opening php manager; browse:/cfolder/PHP/cgi_jargin; reboot(stop and start)
  - extract main osTicketing system into C: wwwindows folder
  - C: windows ➡️ inetpub ➡️ wwwroot ➡️ include ➡️ ost-config.php(reconfig)
  - remove all inheritance; everyone “all access”; sign into osTicket
  - Install heidiSQL; “new” followed by (user/pass: root) ➡️ “open”; select “Unnamed”create 
      
  </ul>
  
<h4>iv.	 Post-installation:</h4> There are 3 different viewing options
<ul>
<li>1.	Admin: Handles maintenance of the osTicketing system, employees, and modifies different section pertaining to info or operations(who can access what).</li>
<li>2.	Agent: View for a help desk agent that works tickets and sees the different tickets being managed that are specific to them/their department.</li>
<li>3.	End user: This screen contains the least visibility but allows people to create tickets and contact support.</li>
</ul>
<h4>v.	Post-install steps:</h4>
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
  </ul>
8.	Tickets/Ticket Life cycle: This portion of the lab focuses on the running and usage of the osTicketing system at all 3 levels.
<ul> a.	Steps: Make sure the “Sys Admin” = "-Top Level D-" ➡️ DELETE the maintenance department; Tickets auto-sync to this department instead of support ➡️ create ticket as Karen, it should be specific to (Report issue/BCO) user error leads to general (Report issue)
<br>b.	
<br>c.	 
<br>d.	 
<br>e.	 
<br>f.
</ul> 
  </ol>
  </ol>
</ul>

</p>

<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com/watch?v=7fVeClRrURM)
  <img src="https://media1.tenor.com/m/GekYPcvThhkAAAAC/kanye-graduation.gif">
  

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
  - In Azure you can create a virtual machine with a "windows 10 pro" as the image
    <img width="400" alt="Screenshot 2025-05-14 at 9 02 16 AM" src="https://github.com/user-attachments/assets/9e038732-09b5-4127-9feb-a83b60b0855a" />


- Remote Desktop
  - In the case you have a macbook in the "Windows App" you can use your new virtual machine via the remote desktop connection after adding a new pc<br>
    <img width="400" alt="Screenshot 2025-05-14 at 10 43 34 AM" src="https://github.com/user-attachments/assets/eee88207-99a4-4b59-983d-55cbfb7b25b5" />

  
- Internet Information Services (IIS)
  - 3 Phase:
    - (Primary Assessment)
      - This is a result of 
    - (OS Ticket Installation)
   
    - ()

## 🖥️ System Requirements

- Ubuntu 20.04 or 22.04
- Apache 2.4 or Nginx
- MySQL 5.7+ or MariaDB
- PHP 8.0–8.1 (minimum 7.4)
- osTicket latest release

---

## 🔹 Step 1: Update Your Server


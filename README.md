<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

# 🎫 osTicket Installation & Setup Guide

This tutorial is a complete step-by-step guide for installing and configuring the open-source **osTicket** support ticketing system(Azure Microsoft, Apache, MySQL, PHP). Includes database setup, web configuration, user creation, and post-install best practices; osTicket helps businesses and IT teams manage customer support, service requests, or internal IT help desk operations.

  - Key functions include:
     - Centralized Ticket Management🎟️: Converts emails, phone calls, and web form submissions into tickets stored in one dashboard.
     - Workflow Automation🔁: Assigns, prioritizes, and routes tickets automatically based on rules.
     - User Support Portal🙋‍♂️: Offers a self-service portal for users to submit and track their own tickets.
     - SLA & Reporting📝: Tracks service level agreements (SLAs), agent performance, and ticket history for accountability.</p>
 <br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)
  <img src="https://media1.tenor.com/m/GekYPcvThhkAAAAC/kanye-graduation.gif">
  

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)



---

## 📁 Table of Contents

- [Overview](#overview)
- [System Requirements](#system-requirements)
- [Step 1: Update Your Server](#step-1-update-your-server)
- [Step 2: Install LAMP Stack](#step-2-install-lamp-stack)
- [Step 3: Create Database and User](#step-3-create-database-and-user)
- [Step 4: Download & Configure osTicket](#step-4-download--configure-osticket)
- [Step 5: Configure Apache for osTicket](#step-5-configure-apache-for-osticket)
- [Step 6: Complete Web Installer](#step-6-complete-web-installer)
- [Step 7: Post-Installation Setup](#step-7-post-installation-setup)
- [Optional: Email Piping Setup](#optional-email-piping-setup)
- [Troubleshooting](#troubleshooting)
- [Screenshots](#screenshots)
- [References](#references)

---

## 📝 Overview

osTicket is a widely-used open source support ticket system. This guide walks through installing it on Ubuntu Linux using Apache, MySQL, and PHP (LAMP). Tested on Ubuntu 20.04 & 22.04.

---

## 🖥️ System Requirements

- Ubuntu 20.04 or 22.04
- Apache 2.4 or Nginx
- MySQL 5.7+ or MariaDB
- PHP 8.0–8.1 (minimum 7.4)
- osTicket latest release

---

## 🔧 Step 1: Update Your Server

```bash
sudo apt update && sudo apt upgrade -y

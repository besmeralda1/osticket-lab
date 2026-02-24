# 🎫 OSTicket Help Desk Lab

A hands-on IT lab documenting the full deployment and configuration of **OSTicket**, an open-source ticketing system, hosted on a Windows 11 Virtual Machine. This project simulates a real-world IT support environment structured around data center operations.

---

## 🛠️ Technologies Used

- Microsoft Azure (Virtual Machine)
- Windows 11
- IIS (Internet Information Services)
- PHP & PHP Manager
- MySQL
- OSTicket
- C++ Redistributable
- HeidiSQL

---

## 📋 Lab Overview

### 1. Virtual Machine Setup
- Provisioned a Windows 11 VM in Azure to serve as the OSTicket admin host
- Remoted into the VM to begin the installation process
<img width="976" height="468" alt="image" src="https://github.com/user-attachments/assets/0d7f3909-710f-4c87-8512-63387366bed7" />

### 2. Pre-Installation Checks
- Verified the loopback address (`127.0.0.1`) to confirm no existing Windows Server was running before configuring a new one
<img width="820" height="794" alt="image" src="https://github.com/user-attachments/assets/43ccf2da-0d50-41e4-9724-037a2c95d141" />

### 3. Enabling IIS and CGI
- Manually enabled **IIS (Internet Information Services)** and **CGI** within the Windows VM
- Verified the changes by loading the loopback address in the VM's browser
<img width="1046" height="544" alt="image" src="https://github.com/user-attachments/assets/b343bbc8-7c07-43ca-a61f-7b5e93e60036" />

### 4. Installing OSTicket Dependencies
- Installed **PHP Manager** and **URL Rewrite Module**
- Installed the **C++ Redistributable** required by OSTicket
- Created a PHP directory on the C: drive and installed the required PHP files
<img width="1100" height="678" alt="image" src="https://github.com/user-attachments/assets/2d502a14-840b-43d6-8ad1-faa667ec8dba" />
<img width="1046" height="606" alt="image" src="https://github.com/user-attachments/assets/408dff5e-3148-4f54-af86-9ab9dc9cd800" />

### 5. MySQL Database Setup
- Installed and configured a **MySQL database** to serve as the OSTicket backend
<img width="800" height="612" alt="image" src="https://github.com/user-attachments/assets/74f9c4a2-3a14-494c-8062-942b2d5e509a" />

### 6. IIS and PHP Registration
- Ran IIS as Administrator
- Registered the PHP installation through PHP Manager so the web server could recognize it
<img width="898" height="518" alt="image" src="https://github.com/user-attachments/assets/96bcc75c-bd57-4c9b-adf8-83bc5a3b352b" />

### 7. OSTicket Installation
- Installed OSTicket files into the IIS root directory (C: drive)
- Loaded OSTicket through IIS to verify the installation
<img width="852" height="468" alt="image" src="https://github.com/user-attachments/assets/78f27a76-0c6f-4bf0-9b98-f03704aed5ec" />
<img width="642" height="446" alt="image" src="https://github.com/user-attachments/assets/71dcdd67-565a-4b71-867b-dd602b3e5b9c" />

### 8. PHP Extension Configuration
- Enabled all required **OSTicket PHP extensions** to unlock full platform capabilities
<img width="1248" height="752" alt="image" src="https://github.com/user-attachments/assets/9f256a6d-700c-4eb2-9523-4b538a0aca54" />


### 9. Configuration File Setup
- Renamed `ost-sampleconfig.php` → `ost-config.php` to allow OSTicket to manage backend configurations
<img width="1100" height="574" alt="image" src="https://github.com/user-attachments/assets/cb2ca0e1-c6b3-4e57-bb30-07fa646d0714" />

### 10. Final Setup & Admin Login
- Configured OSTicket admin credentials and connected the MySQL database
- Successfully logged into OSTicket as an administrator
<img width="986" height="584" alt="image" src="https://github.com/user-attachments/assets/4db43574-e607-4481-acae-add6b313f37b" />
<img width="1256" height="438" alt="image" src="https://github.com/user-attachments/assets/e7880db9-23b6-4d2a-86d0-530ed49116c4" />

---

## ⚙️ OSTicket Configuration

### Roles & Departments
- Created a **Supreme Admin** role with full permissions
<img width="822" height="442" alt="image" src="https://github.com/user-attachments/assets/12b56ce1-bbd8-4d11-8b6f-4ee8109bcf08" />
- Configured a **Top Level Department** for high-priority ticket escalation
<img width="892" height="702" alt="image" src="https://github.com/user-attachments/assets/ae3dae96-e509-427b-8f96-6c9f7132e6c6" />

### Teams & Agents
- Created a **Data Center Team**
<img width="1052" height="470" alt="image" src="https://github.com/user-attachments/assets/b5e3cb50-7ab2-4337-bcc5-d8bf4f7e6e4c" />
  
- Added agents:
  - **Jane** — Top Level Department / Data Center Team (Network Engineer)
  - **John** — Support Department (Technician)
<img width="1266" height="488" alt="image" src="https://github.com/user-attachments/assets/ddf44219-13de-4b53-8b35-6aa5fbe82fc1" />

### Users
- Created end user **Karen** within the Agent Panel
<img width="1160" height="438" alt="image" src="https://github.com/user-attachments/assets/80ea832a-7d67-479a-a726-d9bebe89a9fa" />

### SLA Configuration
- Configured SLA plans with escalating grace periods based on ticket severity
- Set operations to **24/7** to mirror real data center availability requirements
<img width="1140" height="442" alt="image" src="https://github.com/user-attachments/assets/b24f0186-feff-4a3a-b6d6-02aec3af48b2" />


### Help Topics
- Configured multiple help topics, including several tailored to **data center operations**
<img width="846" height="446" alt="image" src="https://github.com/user-attachments/assets/060f343f-197e-4b6f-addc-529d986e6883" />

---

## 🎟️ Ticket Lifecycle Walkthrough
1. **Ticket Created** — End user Karen submitted a ticket reporting that a client could not access cloud resources
<img width="1020" height="862" alt="image" src="https://github.com/user-attachments/assets/130c2212-9560-4a8e-8bab-b9a0ad4ccc59" />

2. **Initial Triage** — Technician John observed the ticket; it was set to high priority with the default SLA, unassigned beyond the Support Department
<img width="1022" height="654" alt="image" src="https://github.com/user-attachments/assets/9d7a98d1-1425-41ee-bfef-ee0865ba6448" />

3. **Escalation** — Ticket was escalated and reassigned to Jane (Network Engineer) with an updated SLA and a response sent to the end user
<img width="888" height="524" alt="image" src="https://github.com/user-attachments/assets/e76307de-6b13-479e-94d4-28019402f202" />

4. **Resolution** — Jane resolved the network connectivity issue and closed the ticket
<img width="852" height="472" alt="image" src="https://github.com/user-attachments/assets/a3a53316-1a76-4871-a18f-9d9f4a45acd4" />

---

## 💡 Key Takeaways

- Gained hands-on experience deploying and configuring a full help desk ticketing system from scratch
- Practiced real-world IT support workflows including ticket triage, escalation, and resolution
- Structured the environment to reflect data center operational standards (24/7 SLAs, tiered roles, team-based escalation)
- Reinforced skills in IIS administration, PHP configuration, and MySQL database management

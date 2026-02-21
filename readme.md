
# Active Directory Vulnerability Lab (VulnLab)

## Project Summary
Designed and deployed an isolated Active Directory lab environment using VMware Workstation Pro to simulate enterprise identity infrastructure and practice lateral movement techniques used in real-world domain compromises.

## Environment Details

Domain Name:
vulnlab.local

Network Type:
Host-only (VMnet1)
Isolated from host and internet

Subnet:
192.168.50.0/24

---

### Domain Controller

Hostname: DC01  
OS: Windows Server 2022  
IP: 192.168.50.10  
Roles Installed:
- Active Directory Domain Services
- DNS Server

---

### Domain Client

Hostname: CLIENT01  
OS: Windows 10 Pro  
Domain Joined: Yes  
User Login Tested:
- VULNLAB\helpdesk

---

### File Server

Hostname: FILE01  
OS: Windows Server 2022  
IP: 192.168.50.30  
Role:
- SMB File Share Host

Shared Resource Created:

\\FILE01\Deploy

Access Granted To:
- VULNLAB\helpdesk (Read)

---

### Domain Users Created

helpdesk (Standard Domain User)

svc-deploy (Service Account)
Password Never Expires: Enabled

---

### Service Principal Name Assigned

deploysvc/FILE01

---

## Attack Simulation Performed

Low-privileged domain user authenticated to CLIENT01  
Requested Kerberos service ticket for deploysvc/FILE01  
Domain Controller issued TGS ticket  
Ticket stored in user memory  
Ticket encrypted using svc-deploy password hash  

This configuration enables offline password cracking using Kerberoasting techniques.

---

## Skills Demonstrated

Active Directory Deployment  
DNS Configuration  
Domain Join Operations  
User and Service Account Management  
SPN Configuration  
SMB Share Permissions  
Kerberos Authentication Flow  
Kerberoasting Attack Setup  
Enterprise Network Segmentation
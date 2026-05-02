Active Directory Group Policy Security Hardening Project


📌 Project Title


AD-GPO-Security-Hardening


🧠 Overview


This project demonstrates enterprise-level Active Directory security hardening using Group Policy Objects (GPOs) in a Windows Server environment. The goal is to enforce security controls across domain-joined machines including USB access control, password policies, account lockout policies, and firewall rule enforcement.


🏗️ Project Requirement


Windows Server (Domain Controller)


Active Directory Domain Services (AD DS)


Windows 10/11 Client VM (Domain-Joined)


Group Policy Management Console (GPMC)


PowerShell for verification


Domain Name- ravikumar.online


Machine	Role and IP Address


ROOTDC - Server1 - Primary Domain Controller	10.0.0.1/8


ADC - Server100 - Additional Domain Controller	10.0.0.100/8


RODC - Server101 - Read-Only Domain Controller	10.0.0.101/8


Client PC - PC1 - 10.0.0.160/8


🔐 Implemented Security Policies


1️⃣ USB Storage Blocking Policy


🎯 Objective


Prevent unauthorized USB storage devices from being used on domain-joined systems.


⚙️ Configuration


![USB](screenshots/USB/USB_ACCESSIBLE.png)


![USB](screenshots/USB/DISABLE_USB_STORAGE.png)


![USB](screenshots/USB/DISABLE_USB_STORAGE_ALL_REMOVABLE_DEVICES.png)


![USB](screenshots/USB/DISABLE_USB_STORAGE_PATH.png)


![USB](screenshots/USB/DISABLE_USB_STORAGE_PATH_CONTD.png)


![USB](screenshots/USB/DISABLE_USB_STORAGE_ALL_REMOVABLE_DEVICES_ENABLED.png)


![USB](screenshots/USB/USB_ACCESS_DENIED.png)


![USB](screenshots/FIREWALL/FIREWALL_GPO_LISTED.png)



2️⃣ Password Policy Enforcement


🎯 Objective


Enforce strong password standards across all domain users.


⚙️ Configuration Path


![PASSWORD](screenshots/PASSWORD/PASSWORD_CRITERIA.png)


![PASSWORD](screenshots/PASSWORD/NET_ACCOUNTS.png)


3️⃣ Account Lockout Policy


🎯 Objective


Protect against brute-force password attacks.


⚙️ Configuration:


![LOCKOUT](screenshots/LOCKOUT/ACCOUNT_LOCKOUT_CRITERIA.png)


![LOCKOUT](screenshots/PASSWORD/NET_ACCOUNTS.png)


![LOCKOUT](screenshots/LOCKOUT/LOCKOUT_PC.png)


![LOCKOUT](screenshots/LOCKOUT/UNLOCKED_ACCOUNT.png)


4️⃣ Firewall ICMP (Ping) Blocking


🎯 Objective


Block ping requests to improve network security and reduce reconnaissance attacks.


⚙️ Configuration:


![FIREWALL](screenshots/FIREWALL/FIREWALL_GPO_ENABLED.png)


![FIREWALL](screenshots/FIREWALL/FIREWALL_GPO_LISTED.png)


![FIREWALL](screenshots/FIREWALL/FIREWALL_GPO_PATH.png)


![FIREWALL](screenshots/FIREWALL/FIREWALL_INBOUND_RULE_TYPE.png)


![FIREWALL](screenshots/FIREWALL/FIREWALL_INBOUND_PROGRAM.png)


![FIREWALL](screenshots/FIREWALL/FIREWALL_INBOUND_PROTOCOL.png)


![FIREWALL](screenshots/FIREWALL/FIREWALL_INBOUND_ACTION.png)


![FIREWALL](screenshots/FIREWALL/FIREWALL_INBOUND_PROFILE.png)


![FIREWALL](screenshots/FIREWALL/FIREWALL_INBOUND_NAME.png)


![FIREWALL](screenshots/FIREWALL/FIREWALL_INBOUND_RULES.png)


![FIREWALL](screenshots/FIREWALL/FIREWALL_PING_BLOCKED.png)


![FIREWALL](screenshots/FIREWALL/NO_MORE_FIREWALL_GPO_LISTED.png)


![FIREWALL](screenshots/FIREWALL/FIREWALL_PING_RESTORED.png)


📊 Testing & Validation


Each policy was tested using:


gpupdate /force


gpresult /r


Ping tests (ping <IP>)


Login failure attempts


USB device insertion tests


🧠 Key Learnings


Group Policy is a powerful centralized security tool in Active Directory


Policy scope and OU placement are critical for correct enforcement


Overly restrictive policies can impact administrative tools if not properly configured


Security hardening requires balancing usability and protection


🚀 Skills Demonstrated


Active Directory Administration


Group Policy Management (GPO)


Windows Server Security Hardening


Endpoint Security Control


Network Security (Firewall & ICMP control)


PowerShell verification commands


👨‍💻 Author


Ravi Kumar


Windows Server | Active Directory | Network Security Lab

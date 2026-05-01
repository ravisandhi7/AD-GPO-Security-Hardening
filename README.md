Active Directory Group Policy Security Hardening Project


📌 Project Title


AD-GPO-Security-Hardening


🧠 Overview


This project demonstrates enterprise-level Active Directory security hardening using Group Policy Objects (GPOs) in a Windows Server environment. The goal is to enforce security controls across domain-joined machines including USB access control, password policies, account lockout policies, and firewall rule enforcement.


🏗️ Lab Environment


Windows Server (Domain Controller)


Active Directory Domain Services (AD DS)


Windows 10/11 Client VM (Domain-Joined)


Group Policy Management Console (GPMC)


PowerShell for verification


🔐 Implemented Security Policies


1️⃣ USB Storage Blocking Policy


🎯 Objective


Prevent unauthorized USB storage devices from being used on domain-joined systems.


⚙️ Configuration


![IPCONFIG](screenshots/USB/USB_ACCESSIBLE.png)


![IPCONFIG](screenshots/USB/DISABLE_USB_STORAGE.png)


![IPCONFIG](screenshots/USB/DISABLE_USB_STORAGE_ALL_REMOVABLE_DEVICES.png)


![IPCONFIG](screenshots/USB/DISABLE_USB_STORAGE_PATH.png)


![IPCONFIG](screenshots/USB/DISABLE_USB_STORAGE_PATH_CONTD.png)


![IPCONFIG](screenshots/USB/DISABLE_USB_STORAGE_ALL_REMOVABLE_DEVICES_ENABLED.png)


![IPCONFIG](screenshots/USB/USB_ACCESS_DENIED.png)


2️⃣ Password Policy Enforcement


🎯 Objective


Enforce strong password standards across all domain users.


⚙️ Configuration Path


![IPCONFIG](screenshots/PASSWORD/PASSWORD_CRITERIA.png)


![IPCONFIG](screenshots/PASSWORD/NET_ACCOUNTS.png)


NET_ACCOUNTS
Computer Configuration →


Policies →


Windows Settings →


Security Settings →


Account Policies →


Password Policy


🔧 Settings Applied


Minimum password length: 8 characters


Password complexity: Enabled


Maximum password age: 30 days


Minimum password age: 1 day


🧪 Verification


Weak passwords are rejected during password change


Strong password requirement enforced at login


3️⃣ Account Lockout Policy


🎯 Objective


Protect against brute-force password attacks.


⚙️ Configuration:


![IPCONFIG](screenshots/LOCKOUT/ACCOUNT_LOCKOUT_CRITERIA.png)


![IPCONFIG](screenshots/PASSWORD/NET_ACCOUNTS.png)


![IPCONFIG](screenshots/LOCKOUT/LOCKOUT_PC.png)



![IPCONFIG](screenshots/LOCKOUT/UNLOCKED_ACCOUNT.png)



UNLOCKED_ACCOUNT

LOCKOUT_PC

ACCOUNT_LOCKOUT_CRITERIA
Computer Configuration →


Policies →


Windows Settings →


Security Settings →


Account Policies →


Account Lockout Policy


🔧 Settings Applied


Account lockout threshold: 5 invalid attempts


Lockout duration: 15 minutes


Reset lockout counter: 15 minutes


🧪 Verification


After 5 failed login attempts, account is locked


Admin can unlock account via Active Directory Users and Computers


4️⃣ Firewall ICMP (Ping) Blocking


🎯 Objective


Block ping requests to improve network security and reduce reconnaissance attacks.


⚙️ Configuration Path


Computer Configuration →


Policies →


Windows Settings →


Security Settings →


Windows Defender Firewall with Advanced Security →


Inbound Rules


🔧 Settings Applied


Disabled File and Printer Sharing (Echo Request - ICMPv4-In)


OR custom rule:


Inbound ICMPv4 Echo Request: Block


🧪 Verification


Ping requests from DC to client VM are blocked


No ICMP echo reply received


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


📸 Suggested Additions (for GitHub)


Add screenshots of:


GPO configuration settings


USB blocked access error


Password policy enforcement


Account lockout message


Ping failure results


gpresult /r output


👨‍💻 Author


Ravi Kumar


Windows Server | Active Directory | Network Security Lab

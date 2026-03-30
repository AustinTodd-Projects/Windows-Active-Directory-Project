# 🏢 Active Directory Home Lab  

## 📌 Overview  
This project demonstrates the setup and configuration of a Windows Active Directory environment in a lab setting. The goal was to simulate a real-world enterprise network with centralized user management, authentication, and policy enforcement.

---

## 🎯 Objectives  
- Deploy and configure Active Directory Domain Services (AD DS)  
- Create and manage users, groups, and Organizational Units (OUs)  
- Configure and apply Group Policy Objects (GPOs)  
- Join client machines to the domain  
- Test authentication and access control  

---

## 🛠️ Technologies Used  
- Windows Server 2025  
- Active Directory Domain Services (AD DS)  
- DNS  
- Group Policy Management  
- PowerShell  
- VMware  
- Windows 11 Pro  
- Shared Network Files  

---

## 🧭 Architecture Diagram  

[ Admin ]  
    │  
    ▼  
[ Domain Controller (Server-01) ]  
    ├── Manages Active Directory (Users & Groups)  
    ├── Handles DNS Resolution  
    ├── Applies Group Policy (GPOs)  
    ├── Maps Shared Network Resources  
    │  
    ▼  
[ Client Machine (Client-01) ]  
    ├── Authenticates to Domain  
    ├── Receives Security Policies  
    └── Accesses Network Resources  

---

## ⚙️ Setup Process  

### 1. Server Configuration  
- Installed Windows Server and Update | [Windows Server Update](Server-Configuration/windows-update.png)
- Configured static IP address | [Static IP Setup](Server-Configuration/static-ip.png)
- Renamed server to Server-01
- Configured DNS  | [DNS Configure](Server-Configuration/dns-configure.png) | [DNS Verify](Server-Configuration/dns-verify.png)

### 2. Active Directory Setup  
- Installed AD DS role  | [Domain Controller Configuration](Server-Configuration/DC.png)
- Promoted server to Domain Controller  
- Created new forest: homelab.local  

### 3. User & Group Management  
- Created Organizational Units (OUs)  | [OU and User Creation](Server-Configuration/User-Management/user-ou.png)
- Added users and security groups | [Security Group Creation and Assignment](Server-Configuration/User-Management/group-creation.png)
- Assigned users to appropriate groups | [Access Control](Server-Configuration/User-Management/access-shared.png) 

### 4. Group Policy Configuration  
- Configured password policies  
- Enforced security settings  
- Applied policies to specific OUs  | [Group Policies](Server-Configuration/User-Management/GPO/default-gpo.png)
- Network Mapping | [Network Map Drive](Server-Configuration/User-Management/GPO/network-map-drive.png)
- Redirect Client Workstation to OU | [Redirect Workstation](Server-Configuration/User-Management/GPO/redirect-client.png)

### 5. Client Machine Setup  
- Installed Windows 11 Pro 
- Joined machine to domain  
- Logged in with domain user account  | [User Domain Login](Server-Configuration/User-Management/Client-Workstation/login.php)
- Tested network file sharing  | [User Domain Login](Server-Configuration/User-Management/Client-Workstation/network-attempt.png)

---

## 🚧 Challenges & Solutions  

- Issue: IT group was not receiving Local Admin Privileges 
  Fix: Change Secruity filtering on the policy to Domain Computers  

- Issue: GPO not applying  
  Fix: Ran gpupdate /force and verified OU linkage  

---

## 📚 Key Takeaways  
- Learned how Active Directory manages users and devices  
- Gained hands-on experience with Group Policy and security controls  
- Improved troubleshooting skills in a Windows domain environment  

---

## 🚀 Future Improvements  
- Implement roaming profiles  
- Automate user creation with PowerShell scripts  
- Expand lab with network firewall and FileShare servers  
- Add monitoring tools and logging
- Create Internal network and connect via VPN 

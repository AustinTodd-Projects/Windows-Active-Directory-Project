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
- Installed Windows Server  
- Configured static IP address  [Link to Screenshot](Server-Configuration/static-ip.png)
- Renamed server to Server-01  
- Configured DNS  

### 2. Active Directory Setup  
- Installed AD DS role  
- Promoted server to Domain Controller  
- Created new forest: homelab.local  

### 3. User & Group Management  
- Created Organizational Units (OUs)  
- Added users and security groups  
- Assigned users to appropriate groups  

### 4. Group Policy Configuration  
- Configured password policies  
- Enforced security settings  
- Applied policies to specific OUs  

### 5. Client Machine Setup  
- Installed Windows 11 Pro  
- Joined machine to domain  
- Logged in with domain user account  
- Tested network file sharing  

---

## 🚧 Challenges & Solutions  

- Issue: Client could not join domain  
  Fix: Corrected DNS settings to point to Domain Controller  

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
- Expand lab with multiple domain controllers for redundancy  
- Add monitoring tools and logging  

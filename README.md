
# Active Directory Simulation – CyberTech Solutions

This project is the deployment of a Windows Server Domain Controller (Active Directory) for a company called **CyberTech Solutions**. It includes domain setup, client configuration, OU design, group policies, and access control in an enterprise environment.

---

## Company Structure

**CyberTech Solutions** is a small IT services firm with the following structure:

- 1 x Windows Server (AD Domain Controller)
- 1 x Windows 8 Client PC (Account Department)
- 1 x Windows 7 Client PC (Legacy Software)

---

## Project Objectives

- Configure an AD Domain Controller on Windows Server
- Join client PCs to the domain
- Create Organizational Units (OUs)
- Implement basic Group Policies for access control
- Simulate a centralized IT environment

---

## Network Design

```
Internet
   ↓
Router (Gateway: 10.0.5.1)
   ↓
Switch
 ┌──────┬─────────────┬──────────────┐
 │      │             │              │
Server  PC1 (Win 8)   PC2 (Win 7)
```

| Device        | IP Address      | Role                        |
|---------------|----------------|-----------------------------|
| Windows Server| 10.0.5.5  | AD Domain Controller (DC)   |
| Windows 8 PC  | DHCP    | Client (Accounts)           |
| Windows XP PC | DHCP    | Legacy Client               |

---

## Domain Configuration

- **Domain Name**: `cybertech.local`
- **Server Name**: `CYBERTECH`
- **Static IP**: `10.0.5.4`
- **AD Roles Installed**: AD DS, DNS (DHCP)

---

## Organizational Units (OUs)

Created using **Active Directory Users and Computers**:

```
CyberTech.local
├── OU: IT Department
│   └── Users: Dominic.IT
    

├── OU: HR
│   └── Users: Martins.HR
```

---

## Group Policy (GPO)

Created and linked using **Group Policy Management Console (gpmc.msc)**:

- **GPO Name**: `DisableRemovableDrives`
- **Linked to**: OU: IT Department
- **Policy Configured**:
  - `Computer Configuration` > `Administrative Templates` > `System` > `Removable Storage Access`
  - Set **"All Removable Storage classes: Deny all access"** to **Enabled**

Result: USB and external drives are disabled for all users in the **Accounts OU**.

- **GPO Name**: `DisablePoweroffRestartoptions`
- **Linked to**: OU: HR Department
- **Policy Configured**:
  - `Computer Configuration` > `Administrative Templates` > `System` > `Removable Storage Access`
  - Set **"Remove ans prevent all acess to shutdown, restart and hibernate commands"** to **Enabled**

Result: commans disabled for all users in the **HR and IT OU**.
---

## Screenshots

- [AD Domain Structure](https://github.com/namecheap-tech/Active-Directory-Simulation-CyberTech-Solutions/blob/main/Screenshots/OUs_Groups_Users.png)
- [GPO Editor Screenshot](https://github.com/namecheap-tech/Active-Directory-Simulation-CyberTech-Solutions/blob/main/Screenshots/Group_policy_management.png)
- [PC joined to domain](https://github.com/namecheap-tech/Active-Directory-Simulation-CyberTech-Solutions/blob/main/Screenshots/windows_machine_connection.png)
- [Result of denied shutdown command access](https://github.com/namecheap-tech/Active-Directory-Simulation-CyberTech-Solutions/blob/main/Screenshots/Access_denied.png)

---

## Key Takeaways

- Gained practical experience with Windows Server roles and domain setup
- Implemented centralized access control using Group Policy
- Learned how to structure users and departments with OUs
- Applied IAM concepts in a real-world simulated environment

---

## Author

**Aliu B. Sanusi**  
Cybersecurity Analyst  

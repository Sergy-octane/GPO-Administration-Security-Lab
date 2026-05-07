# GPO-Administration-Security-Lab
This project demonstrates the implementation of **Group Policy Objects (GPO)** to control user behavior and enhance network security within a Windows Server 2022 environment.


## 🎯 Objectives
* Implement centralized security policies.
* Restrict unauthorized hardware (USB) and system access.
* Enforce strong password standards.

## 🛠️ Configurations Implemented

### 1. Password Security Policy
Configured the **Default Domain Policy** to ensure all users follow enterprise security standards:
* **Minimum length:** 8 characters.
* **Complexity requirements:** Enabled (Uppercase, numbers, symbols).
* **Expiration:** 30 days.
  <img width="781" height="562" alt="contraseña_1" src="https://github.com/user-attachments/assets/5bf46edb-c575-4968-be04-1b19b2ffd4d1" />


### 2. Hardware Restriction (USB Block)
Created a GPO to prevent data theft and malware infections by denying access to all removable storage devices.
* **Path:** Computer Configuration > Administrative Templates > System > Removable Storage Access.

<img width="787" height="552" alt="usb_bloqueadas" src="https://github.com/user-attachments/assets/70eb452d-43f6-4f04-8a17-d69348e740d5" />

### 3. Control Panel Restriction
Prevented standard users from modifying critical system settings.
* **Path:** User Configuration > Administrative Templates > Control Panel.
  <img width="785" height="559" alt="Panel_Bloqueado" src="https://github.com/user-attachments/assets/48a5d122-2a31-4fc5-a08e-ca511783080f" />


## 🧪 Verification & Results
After applying the policies, I performed a forced update on the client machine (**Windows 10**) using:
`gpupdate /force`

### Evidence:
<img width="928" height="495" alt="Restriccion" src="https://github.com/user-attachments/assets/d57c2fec-eaae-4d41-b6bc-6af366f2cda2" />


*Figure 1: Access denied message when a restricted user tries to open the Control Panel.*

## 🧠 Key Learnings
* Difference between **Computer Configuration** (applies to the machine) and **User Configuration** (follows the person).
* Troubleshooting GPO propagation in a domain environment.
* Importance of having the **Domain Controller (DC)** online for policy synchronization.

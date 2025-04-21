<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

# Creating Domain Users and Allowing Remote Access

This lab focuses on two key administrative tasks within Active Directory: allowing remote desktop access to domain users and bulk creation of multiple employee accounts using PowerShell scripting.

---

## 🧰 Technologies Used

- Microsoft Azure (Virtual Machine Hosting)
- Windows Server 2022 (Domain Controller)
- Windows 10 Pro (Client)
- PowerShell ISE
- Active Directory Users and Computers (ADUC)

---

## 🎯 Lab Objectives

- Grant domain users access to Remote Desktop on Client-1  
- Use PowerShell to create multiple domain user accounts  
- Verify the creation and login of non-administrative users on Client-1  

---

## 🖥️ Step-by-Step Walkthrough

### 🔐 Step 1: Allow Domain Users Remote Access to Client-1

<p align="center">
  <img src="https://github.com/Herkamal/creating-users/blob/main/domain_users.png?raw=true" width="80%"/>
</p>

Log in to **Client-1** as `mydomain.com\jane_admin`.  
Open **System Properties > Remote Desktop** and allow **Domain Users** access to Remote Desktop.  

This enables non-admin users within the domain to remotely log in to Client-1.

---

### 👤 Step 2: Bulk Create Domain Users via PowerShell

<p align="center">
  <img src="https://github.com/Herkamal/creating-users/blob/main/create-users.png?raw=true" width="80%"/>
</p>

Log in to **DC-1** as `mydomain.com\jane_admin` and open **PowerShell ISE as Administrator**.  
Create a new script file and paste in the contents of [this script](https://github.com/joshmadakor1/AD_PS/blob/master/Generate-Names-Create-Users.ps1).  
Run the script to automatically generate multiple domain user accounts.

The script generates multiple employee accounts and places them in the `_EMPLOYEES` Organizational Unit (OU).

---

### ✅ Step 3: Verify Users and Log In

Once the script completes, open **Active Directory Users and Computers (ADUC)** to verify the new users exist in the `_EMPLOYEES` OU.

Then, log in to **Client-1** using one of the new accounts. This confirms both account creation and remote login access were successful.

> 🔐 *Note: The password used in the script will be required to log in — typically something like `Cyberlab123!` unless otherwise specified.*

---

## 📌 Summary

This lab demonstrated how to:
- Enable remote desktop access for domain users  
- Use PowerShell to automate user account creation  
- Confirm access by logging in from a domain-joined client machine  

These are essential tasks for any IT administrator managing users at scale.

---

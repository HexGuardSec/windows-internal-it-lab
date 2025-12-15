# 🧪 Scenario 02 – Local Users & Privileges Audit

## 🏢 Context

This Windows workstation represents a standard corporate endpoint used by employees in an enterprise environment.

As part of an Internal IT security audit, a review of **local user accounts and privilege assignments** was conducted to ensure:
- proper access control
- compliance with least privilege principles
- reduced attack surface on the workstation

This scenario focuses specifically on **local users and local group management**, using both **GUI-based tools and PowerShell**, which reflects real-world Internal IT operations.

---

## 🎯 Audit Scope

The audit covers:
- Local user accounts
- Local group memberships
- Privileged group: `Administrators`
- Standard user group: `Users`

> NTFS file permissions are intentionally **out of scope** for this scenario and will be addressed in a dedicated lab.

---

## 📋 Baseline Audit (Before Changes)

An initial audit was performed before any modification to establish a baseline state.

### 🔍 Actions Performed
- Reviewed all existing local user accounts
- Reviewed membership of:
  - `Administrators`
  - `Users`

### 📸 Screenshots
- `baseline-local-users.png` – List of existing local users  
- `baseline-group-administrators.png` – Members of the Administrators group  
- `baseline-group-users.png` – Members of the Users group  

---

## 👤 User Management Simulation

To simulate realistic Internal IT tasks, two new local user accounts were created using different administrative approaches.

---

### 🖥️ User 1 – GUI-Based Account Creation

- **Username:** `user_gui`
- **Full Name:** User GUI
- **Description:** Standard employee account (created via GUI)
- **Creation Method:** Local Users and Groups
- **Initial Privileges:** Standard user

This simulates a typical helpdesk workflow where user accounts are created using graphical administration tools.

### 📸 Screenshots
- `user-gui-created.png` – Confirmation of user creation  
- `user-gui-in-users-group.png` – Account properties  

---

### 💻 User 2 – PowerShell-Based Account Creation

- **Username:** `user_ps`
- **Full Name:** User ps
- **Description:** Standard employee account (created via PS)
- **Creation Method:** PowerShell (run as Administrator)
- **Initial Privileges:** Standard user

This demonstrates command-line administration skills commonly required for automation and advanced IT operations.

### 📸 Screenshots
- `powershell-user-ps-created.png` – User creation via PowerShell  

---

## 🧩 PowerShell Commands Used (Explanation)

### 🔐 Secure Password Input

```powershell
$password = Read-Host -AsSecureString
````

This command prompts the administrator to enter a password securely:

* the password is not displayed on screen
* the value is stored encrypted in memory

This approach prevents password exposure and avoids hardcoding credentials in scripts.

---

### ➕ Local User Creation via PowerShell

```powershell
New-LocalUser -Name user_ps -FullName "User ps" -Description "Standard employee account (created via PS)" -Password $password
```

This command creates a new local user account:

* `-Name user_ps` defines the username
* `-FullName` provides a descriptive identifier
* `-Description` documents the business purpose of the account
* `-Password` assigns the securely entered password

Using PowerShell allows scalable and repeatable user provisioning.

---

### 👥 Adding the User to the Standard Users Group

```powershell
Add-LocalGroupMember -Group Users -Member user_ps
```

This command adds `user_ps` to the `Users` group, ensuring the account has **standard, non-privileged access**.

Group-based privilege management is a core best practice in enterprise environments.

---

## 🧱 Group Membership Configuration

### ✅ Standard User Assignment

Both `user_gui` and `user_ps` were added to the `Users` group.

This ensures:

* limited privileges
* reduced risk of accidental or malicious system changes

### 📸 Screenshots

* `user-gui-in-users-group.png` – `user_gui` member of Users
* `powershell-user-ps-added-users.png` – `user_ps` added to Users via PowerShell

---

### ⚠️ Simulated Misconfiguration – Temporary Administrative Access

To simulate a **common enterprise misconfiguration**, `user_gui` was temporarily added to the `Administrators` group.

**Context:**

> Administrative privileges were temporarily granted for troubleshooting purposes.

`user_ps` was intentionally **not** granted administrative privileges to demonstrate correct PowerShell-based provisioning.

### 📸 Screenshots

* `user-gui-in-administrators-group.png` – `user_gui` added to Administrators

---

## 🔎 Post-Change Audit

A post-change audit was conducted to assess the impact of the privilege modification.

### 📌 Findings

* A standard user account (`user_gui`) had administrative privileges
* Temporary admin access was not technically restricted or time-bound
* This represents a realistic and high-risk misconfiguration scenario

### 📸 Screenshots

* `postchange-group-administrators.png` – Administrators group after change
* `postchange-group-users.png` – Users group after change

---

## 🚨 Risk Analysis

### ❗ Risk 1 – Excessive Local Administrator Privileges

Granting administrative privileges to standard users significantly increases the attack surface.
If compromised, such accounts provide full system control.

---

### ⏳ Risk 2 – Temporary Privileges Becoming Permanent

Temporary admin access is frequently forgotten, leading to long-term security policy violations.

---

### 📄 Risk 3 – Lack of Formal Privilege Review Process

Without structured review and documentation, privilege changes may remain unnoticed.

---

## 🛠️ Remediation Actions

To mitigate the identified risks, the following actions were taken:

* Removed `user_gui` from the `Administrators` group (via GUI)
* Verified that `user_ps` remained a standard user
* Confirmed both accounts are members of the `Users` group only

### 📸 Screenshots

* `remediation-user-gui-removed-admins.png` – Admin rights revoked

---

## ✅ Final Validation

A final audit confirmed:

* Only authorized IT accounts remain in the `Administrators` group
* Both simulated employee accounts operate with standard privileges
* Least privilege principles are enforced
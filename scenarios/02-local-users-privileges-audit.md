# 🧪 Scenario 02 – Local Users & Privileges Audit

![Platform](https://img.shields.io/badge/Platform-Windows-blue)
![Focus](https://img.shields.io/badge/Focus-Internal%20IT%20Audit-informational)
![Level](https://img.shields.io/badge/Level-Junior-yellow)
![Skills](https://img.shields.io/badge/Skills-User%20Management%20%7C%20PowerShell%20%7C%20Privilege%20Audit-lightgrey)

---

## 🏢 Context

This Windows workstation represents a standard corporate endpoint used by employees in an enterprise environment.

As part of an **Internal IT security audit**, a review of **local user accounts and privilege assignments** was conducted to ensure:

* proper access control
* compliance with least privilege principles
* reduction of the workstation attack surface

This scenario focuses on **local users and local group management**, using both **GUI-based tools and PowerShell**, reflecting real-world Internal IT operations.

---

## 🧾 Executive Summary

The audit identified a realistic and common privilege misconfiguration:
a standard user account was temporarily granted **local administrative privileges** without technical restriction or expiration.

While no active compromise was detected, this configuration significantly increases the attack surface and could lead to **full system compromise** if the account were abused.

Corrective actions were applied to restore least-privilege access and validate system integrity.

---

## 🎯 Audit Scope

The audit covers:

* Local user accounts
* Local group memberships
* Privileged group: `Administrators`
* Standard group: `Users`

> NTFS file permissions are intentionally **out of scope** for this scenario and will be addressed in a dedicated lab.

---

## 📋 Baseline Audit (Before Changes)

An initial audit was performed before any modification to establish a baseline state.

### 🔍 Actions Performed

* Reviewed all existing local user accounts
* Reviewed group membership for:

  * `Administrators`
  * `Users`

### 📸 Screenshots

* `baseline-local-users.png` – Existing local users
* `baseline-group-administrators.png` – Administrators group members
* `baseline-group-users.png` – Users group members

---

## 👤 User Management Simulation

To simulate realistic Internal IT tasks, two new local user accounts were created using different administrative approaches.

---

### 🖥️ User 1 – GUI-Based Account Creation

* **Username:** `user_gui`
* **Full Name:** User GUI
* **Description:** Standard employee account (created via GUI)
* **Creation Method:** Local Users and Groups
* **Initial Privileges:** Standard user

This simulates a typical **helpdesk workflow**, where accounts are created using graphical administration tools.

### 📸 Screenshots

* `user-gui-created.png` – User creation confirmation
* `user-gui-in-users-group.png` – Group membership

---

### 💻 User 2 – PowerShell-Based Account Creation

* **Username:** `user_ps`
* **Full Name:** User PS
* **Description:** Standard employee account (created via PowerShell)
* **Creation Method:** PowerShell (run as Administrator)
* **Initial Privileges:** Standard user

This demonstrates command-line administration skills commonly required for **automation and advanced IT operations**.

### 📸 Screenshots

* `powershell-user-ps-created.png` – User creation via PowerShell

---

## 🧩 PowerShell Commands Used

### 🔐 Secure Password Input

```powershell
$password = Read-Host -AsSecureString
```

* Password is not displayed on screen
* Stored securely in memory
* Prevents credential exposure

---

### ➕ Local User Creation

```powershell
New-LocalUser -Name user_ps -FullName "User PS" -Description "Standard employee account (created via PS)" -Password $password
```

This command ensures:

* clear user identification
* documented business purpose
* secure password handling

---

### 👥 Group Assignment

```powershell
Add-LocalGroupMember -Group Users -Member user_ps
```

Group-based privilege management enforces **least privilege** and simplifies audits.

---

## 🧱 Group Membership Configuration

### ✅ Standard User Assignment

Both `user_gui` and `user_ps` were assigned to the `Users` group only.

This ensures:

* limited privileges
* reduced risk of accidental or malicious changes

### 📸 Screenshots

* `user-gui-in-users-group.png`
* `powershell-user-ps-added-users.png`

---

### ⚠️ Simulated Misconfiguration – Temporary Admin Access

To simulate a **common enterprise misconfiguration**, `user_gui` was temporarily added to the `Administrators` group.

**Context:**

> Administrative privileges were granted temporarily for troubleshooting purposes.

`user_ps` was intentionally **not** granted administrative access to demonstrate correct PowerShell-based provisioning.

### 📸 Screenshots

* `user-gui-in-administrators-group.png`

---

## 🔎 Post-Change Audit

A post-change audit assessed the impact of the privilege modification.

### 📌 Findings

* A standard user had administrative privileges
* No technical restriction or expiration existed
* Represents a **high-risk misconfiguration**

### 📸 Screenshots

* `postchange-group-administrators.png`
* `postchange-group-users.png`

---

## 🚨 Risk Analysis

### ❗ Excessive Local Administrator Privileges

If compromised, a local admin account provides **full system control**, enabling malware installation, persistence, and lateral movement.

---

### ⏳ Temporary Privileges Becoming Permanent

Temporary access is frequently forgotten, leading to long-term policy violations.

---

### 📄 Lack of Formal Privilege Review

Without structured reviews, misconfigurations may remain undetected indefinitely.

---

## 🏢 Internal IT / SOC Perspective

From an Internal IT and SOC Tier 1 perspective, this scenario highlights a frequent operational risk:

* Troubleshooting-driven privilege escalation
* No expiration or automation
* Missing review checkpoints

Such situations represent **high-value targets** for attackers.

---

## 🛠️ Remediation Actions

The following actions were applied:

* Removed `user_gui` from the `Administrators` group
* Verified `user_ps` remained a standard user
* Confirmed group memberships were compliant

### 📸 Screenshots

* `remediation-user-gui-removed-admins.png`

---

## 📜 Best Practice Recommendations

* Enforce time-bound administrative access
* Document all privilege escalations
* Perform regular local admin audits
* Favor PowerShell-based provisioning for traceability

---

## ✅ Final Validation

A final audit confirmed:

* Only authorized IT accounts remain administrators
* All employee accounts operate with standard privileges
* Least privilege principles are enforced

---

## 🧠 Conclusion

This scenario demonstrates the importance of continuous privilege auditing on Windows endpoints.

Through structured investigation, risk assessment, and remediation, the system was returned to a compliant and secure state.

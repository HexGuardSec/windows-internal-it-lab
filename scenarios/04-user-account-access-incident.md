![Platform](https://img.shields.io/badge/Platform-Windows-blue)
![Category](https://img.shields.io/badge/Category-Internal%20IT%20Support-informational)
![Level](https://img.shields.io/badge/Level-L1%20%2F%20L2-yellow)
![Type](https://img.shields.io/badge/Type-Incident%20Response-orange)

# 🧪 Scenario 04 – User Account Access Issue (Local Account Disabled)


## 🏢 Context

This Windows workstation represents a standard corporate endpoint used by employees in an enterprise environment.

As part of daily Internal IT support operations, user authentication issues are a common occurrence.
One of the most frequent causes is a **disabled user account**, either due to administrative actions, security measures, or misconfiguration.

This scenario simulates a **realistic Level 1 / Level 2 support incident** where a user reports being unable to log in to their workstation.

The investigation and remediation follow a **standard Internal IT troubleshooting workflow**, using built-in Windows administrative tools.

---

## 🎯 Incident Scope

The incident investigation covers:

* Local user account status
* Account enablement state
* Basic authentication troubleshooting
* Use of administrative tools for validation and remediation

> Active Directory, centralized authentication, and enterprise IAM solutions are **out of scope** for this scenario.

---

## 📋 Initial Situation

A user reports the following issue:

> “I am unable to log in to my workstation this morning.”

At the time of the investigation:

* The workstation is operational
* The IT administrator has local administrative access
* The affected user account exists on the system

---

## 🔍 Initial Account Verification (Baseline)

Before making any changes, the local user account status was verified to confirm its existence and current state.

### 🔧 Actions Performed

* Queried local user accounts using PowerShell
* Verified the enablement status of the affected user account

### 📸 Screenshots

* `screenshots/01-user-status-before.png` – Local user account enabled (baseline state)

---

## ⚠️ Incident Simulation – Account Disabled

To reproduce the reported issue in a controlled manner, the affected local user account was intentionally disabled.

Disabling a local account is a common administrative action and prevents the user from authenticating on the system.

### 🔧 Actions Performed

* Opened Local Users and Groups (`lusrmgr.msc`)
* Disabled the affected user account

### 📸 Screenshots

* `screenshots/02-user-disabled.png` – User account marked as disabled

> When a local account is disabled, Windows may prevent it from appearing on the login screen.
> This behavior is expected and does not indicate that the account has been deleted.

---

## 🔎 Investigation Findings

After disabling the account, the user’s inability to log in was investigated from an IT administrator perspective.

### 🔍 Observations

* The user account still exists on the system
* The account status is set to **Disabled**
* Disabled local accounts cannot authenticate on Windows systems

### 🔧 Verification

The account status was confirmed using PowerShell.

### 📸 Screenshots

* `screenshots/03-user-status-disabled.png` – Local user account shown as disabled via PowerShell

---

## 🧠 Root Cause Analysis

### ❗ Root Cause – Disabled Local User Account

The user was unable to log in because their local account was disabled.
Windows enforces authentication restrictions on disabled accounts, preventing access until the account is re-enabled.

---

## 🛠️ Remediation Actions

To resolve the incident, the account was re-enabled using administrative privileges.

### 🔧 Actions Performed

* Re-enabled the local user account using PowerShell
* Ensured the account status returned to an enabled state

### 📸 Screenshots

* `screenshots/04-user-enabled.png` – Local user account successfully re-enabled

---

## ✅ Result

After remediation:

* The user account is enabled
* Authentication restrictions are removed
* The user can successfully log in to the workstation

---

## 📝 IT Support Note

Disabled local accounts may not appear on the Windows login screen, which is normal behavior.
When investigating login issues, verifying account status via administrative tools is a critical first step before performing further troubleshooting.

---

## 📌 Key Takeaways

* Local account status directly impacts authentication
* PowerShell is an effective tool for validating user account state
* Simple configuration issues can cause significant user disruption
* Clear documentation improves support efficiency and traceability
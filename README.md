# 🪟 Windows Internal IT Lab

![OS](https://img.shields.io/badge/OS-Windows%2010%20%2F%2011-blue)
![Category](https://img.shields.io/badge/Category-Internal%20IT-lightgrey)
![Level](https://img.shields.io/badge/Level-Junior-informational)
![Focus](https://img.shields.io/badge/Focus-User%20Management%20%7C%20Services%20%7C%20Logs-success)

---

## 🧩 Overview

This repository contains a collection of **realistic Internal IT lab scenarios** conducted on a Windows workstation.

The labs simulate daily tasks commonly handled by:
- Internal IT Engineers
- IT Support / System Administrators
- SOC Tier 1 analysts (Windows visibility & basic investigation)

The objective is to demonstrate **practical Windows administration skills** in a corporate environment, with a strong focus on:
- security awareness
- audit methodology
- clear and professional documentation

---

## 📁 Scenarios

### 🔹 01. Basic Internal IT Audit on Windows

An initial Internal IT audit performed on a standalone Windows workstation.

This scenario provides a global overview of the system and establishes a baseline.

**Covered topics:**
- Local user and group overview
- Service inspection and status review
- Event Viewer log analysis (System & Security)
- Administrator vs standard user separation

📂 Documentation:
```

scenario-01-basic-internal-it-audit/

```

---

### 🔹 02. Local Users & Privileges Audit

An in-depth audit focused on **local user accounts and privilege management**.

This scenario simulates common Internal IT tasks related to user provisioning, privilege review, and misconfiguration remediation.

**Covered topics:**
- Baseline local user and group audit
- Local user creation via GUI and PowerShell
- Standard vs administrative privilege assignment
- Detection of excessive privileges
- Remediation and final validation
- Least privilege principles

📂 Documentation:
```

scenario-02-local-users-privileges-audit/

```

---

### 🔹 03. Scheduled Task Abuse Audit

A security-oriented audit scenario focusing on **abuse of Windows Scheduled Tasks** as a persistence mechanism.

This lab follows a realistic Internal IT / Blue Team investigation workflow.

**Covered topics:**
- Task Scheduler baseline review
- Identification of a suspicious scheduled task
- Analysis of task triggers, actions, execution context, and history
- Risk assessment related to persistence mechanisms
- Remediation through task removal
- Final validation and system stability check

📂 Documentation:
```

scenario-03-scheduled-task-abuse/

```

---

## 🛠️ Tools & Components Used

- Local Users and Groups (`lusrmgr.msc`)
- Windows PowerShell
- Services Manager (`services.msc`)
- Task Scheduler (`taskschd.msc`)
- Event Viewer (`eventvwr.msc`)
- Windows Local Accounts
- Administrative privileges

---

## 🎯 Purpose

This lab portfolio complements Linux-focused projects by demonstrating the ability to operate in a **mixed Linux / Windows Internal IT environment**, which is extremely common in real enterprises.

It is designed to serve as a **practical and professional portfolio** for junior-level:
- Internal IT Engineers
- System Administrators
- SOC Tier 1 analysts

with an emphasis on:
- operational mindset
- security awareness
- structured documentation
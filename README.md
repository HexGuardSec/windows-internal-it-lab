# 🪟 Windows Internal IT Lab

![OS](https://img.shields.io/badge/OS-Windows%2010%20%2F%2011-blue)
![Category](https://img.shields.io/badge/Category-Internal%20IT-lightgrey)
![Level](https://img.shields.io/badge/Level-Junior-informational)
![Focus](https://img.shields.io/badge/Focus-User%20Management%20%7C%20Services%20%7C%20Logs-success)

---

## 🧩 Overview

This lab simulates **Internal IT operations on a Windows workstation**, focusing on tasks commonly handled by:

- Internal IT Engineers
- IT Support / System Administrators
- SOC Tier 1 (Windows visibility & basic log analysis)

The goal is to demonstrate **hands-on Windows administration skills** in a corporate environment, with an emphasis on:
- security awareness
- audit methodology
- clear documentation

---

## 📁 Scenarios

### 🔹 01. Basic Internal IT Audit on Windows

A first internal IT audit performed on a standalone Windows system.

Covered topics:
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

An in-depth audit focused on **local user accounts and privilege management** on a Windows workstation.

This scenario simulates realistic Internal IT tasks, including:
- baseline user and group audit
- local user creation via GUI and PowerShell
- standard vs administrative privilege assignment
- detection of privilege misconfiguration
- remediation and final validation

Covered topics:
- Local Users and Groups (`lusrmgr.msc`)
- Administrators vs Users groups
- Least privilege principles
- PowerShell-based user provisioning
- Internal IT audit documentation

📂 Documentation:
```

scenario-02-local-users-privileges-audit/

```

---

## 🛠️ Tools & Components Used

- Local Users and Groups (`lusrmgr.msc`)
- Windows PowerShell
- Services Manager (`services.msc`)
- Event Viewer (`eventvwr.msc`)
- Windows Local Accounts
- Administrative privileges

---

## 🎯 Purpose

This lab complements Linux-focused projects by demonstrating the ability to operate in a **mixed Linux / Windows internal IT environment**, which is extremely common in real enterprises.

It is designed to serve as a **practical portfolio** for junior-level Internal IT or System Administration roles, emphasizing:
- operational mindset
- security awareness
- structured documentation

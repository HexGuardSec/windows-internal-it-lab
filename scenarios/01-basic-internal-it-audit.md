# 🧪 Scenario 01 — Basic Internal IT Audit on Windows

**Category:** Internal IT / System Administration  
**Level:** Junior  
**Environment:** Windows 11 (Standalone VM)

---

## 🎯 Objective

Perform a basic Internal IT audit on a Windows workstation to verify:

- Local user configuration
- Separation between administrator and standard users
- Service visibility and configuration
- Availability of system and security logs

This scenario simulates a **first-day audit task** for a junior Internal IT / IT Support Engineer.

---

## 1️⃣ Local User & Privilege Review

The system was reviewed using **Local Users and Groups** to identify:

- Administrator account (`it-admin`)
- Standard employee account (`employee01`)

This separation ensures that daily users do not operate with elevated privileges.

📸 Evidence:
- Local Users and Groups overview

---

## 2️⃣ Services Inspection

The **Services Manager (`services.msc`)** was used to:

- Review running and stopped services
- Identify critical system services (Windows Update, Security Center, Remote Desktop Services)
- Verify startup types and service status

This step ensures no unnecessary or suspicious service is running.

📸 Evidence:
- Services overview

---

## 3️⃣ Event Log Review

The **Event Viewer (`eventvwr.msc`)** was inspected:

- `Windows Logs → System`
- `Windows Logs → Security`

Recent warnings, errors, and login-related events were reviewed to ensure proper logging is enabled.

📸 Evidence:
- Event Viewer overview
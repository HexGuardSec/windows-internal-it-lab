# 🧪 Scenario 05 – Windows Service Startup Failure Investigation

![OS](https://img.shields.io/badge/OS-Windows%2010%20%2F%2011-blue)
![Category](https://img.shields.io/badge/Category-Internal%20IT-lightgrey)
![Level](https://img.shields.io/badge/Level-Junior-informational)
![Focus](https://img.shields.io/badge/Focus-Services%20%7C%20Logs%20%7C%20Troubleshooting-success)

---

## 🏢 Context

This Windows workstation represents a standard corporate endpoint used by employees in an enterprise environment.

Following a system reboot, users reported potential system time synchronization issues.  
As part of an **Internal IT incident investigation**, a review of Windows services was conducted to identify and resolve a **service startup failure**.

This scenario simulates a **realistic L1/L2 Internal IT ticket**, focusing on structured troubleshooting, log analysis, remediation, and validation.

---

## 🎯 Incident Scope

The investigation focuses on:
- Windows service startup behavior
- Service configuration and startup type
- System logs related to service failures
- Root cause identification and remediation
- Post-remediation validation

> Advanced monitoring tools and centralized logging solutions are **out of scope** for this scenario.

---

## 📋 Baseline Observation

Before the incident simulation, a baseline check was performed to confirm normal service behavior.

### 🔍 Actions Performed
- Reviewed the status of the **Windows Time (w32time)** service
- Verified startup type and running state

### 📸 Screenshots
- `screenshots/05-windows-service-stratup-failure/01-baseline-windows-time-service-running` – Windows Time service running with automatic startup

---

## ⚠️ Incident Detection

After a system reboot, the Windows Time service failed to start as expected.

### 🔍 Observations
- The service was found in a **Stopped** state
- Manual start attempt failed
- Startup type was set to **Disabled**

### 📸 Screenshots
- `screenshots/05-windows-service-stratup-failure/02-incident-windows-time-failed-to-start` – Service startup failure observed

---

## 🔎 Log Analysis

To identify the root cause, system logs were reviewed using Event Viewer.

### 🔍 Actions Performed
- Opened **Event Viewer**
- Reviewed **System** logs
- Filtered events from **Service Control Manager**
- Identified errors related to the Windows Time service

### 📸 Screenshots
- `screenshots/05-windows-service-stratup-failure/03-logs-windows-time-service-error` – Service Control Manager error details

---

## 🧠 Root Cause Analysis

Based on service configuration and log analysis, the following root cause was identified:

- The **Windows Time service was disabled**
- A disabled service cannot start automatically or be started manually
- The service failure was caused by **misconfiguration**, not by corruption or system instability

---

## 🛠️ Remediation Actions

To resolve the incident, the following actions were taken:

- Startup type of the Windows Time service was changed from **Disabled** to **Automatic**
- The service was started successfully
- No system restart was required at this stage

> No remediation screenshot was captured, as the configuration change and service start were immediately validated during the final verification step.

---

## ✅ Final Validation

A system reboot was performed to confirm that the remediation was effective.

### 🔍 Validation Results
- The Windows Time service started automatically after reboot
- No new service-related errors were observed in Event Viewer

### 📸 Screenshots
- `screenshots/05-windows-service-stratup-failure/04-remediation-windows-time-service-restored` – Service running successfully after reboot

---

## 🚨 Risk Assessment

### ❗ Risk – Service Misconfiguration

Incorrect service startup configuration can lead to:
- System functionality degradation
- Time synchronization issues
- Authentication and logging inconsistencies in enterprise environments

---

## 🎯 Conclusion

This scenario demonstrates a **complete Internal IT troubleshooting workflow**, including:

- Incident detection
- Log-based investigation
- Root cause identification
- Service remediation
- Post-fix validation

It reflects real-world **L1/L2 Internal IT responsibilities** and emphasizes the importance of structured diagnostics and verification in enterprise Windows environments.
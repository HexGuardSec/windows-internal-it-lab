# 🧪 Scenario 03 – Scheduled Task Abuse

## 🏢 Context

This Windows workstation represents a standard corporate endpoint used by employees in an enterprise environment.

As part of an Internal IT security audit, a review of **Windows Scheduled Tasks** was conducted to identify potential persistence mechanisms and unauthorized automated executions.

Scheduled Tasks are commonly used for legitimate administrative purposes but can also be abused by attackers or misconfigured users to maintain persistence on a system.

This scenario focuses on **auditing, identifying, and remediating a suspicious scheduled task**, following a realistic Internal IT investigation workflow.

---

## 🎯 Audit Scope

The audit covers:
- Scheduled Tasks within the Task Scheduler Library
- Task triggers and execution frequency
- Actions executed by scheduled tasks
- User context under which tasks are executed

> Advanced monitoring solutions and centralized logging are **out of scope** for this scenario.

---

## 📋 Baseline Observation

An initial review of the Task Scheduler was performed to establish a baseline.

### 🔍 Actions Performed
- Reviewed existing scheduled tasks
- Identified standard Microsoft and system-related tasks
- Observed task naming conventions and execution patterns

### 📸 Screenshots
- `screenshots/audit/audit-task-library-overview.png` – Task Scheduler Library overview  
- `screenshots/baseline-legit-task.png` – Example of a legitimate scheduled task  

---

## ⚠️ Suspicious Task Identification

During the audit, a scheduled task was identified that did not clearly align with standard enterprise usage.

### 🔍 Observations
- The task had a generic and non-descriptive name
- It was configured to run at regular intervals
- The task executed a command without clear business justification
- It was created and executed under a **standard user context**

### 📸 Screenshots
- `screenshots/suspicious/suspicious-task-created.png` – Task creation evidence  
- `screenshots/audit/audit-suspicious-task-identified.png` – Suspicious task highlighted  
- `screenshots/audit/audit-suspicious-task-general.png` – General properties  
- `screenshots/audit/audit-suspicious-task-triggers.png` – Trigger configuration  
- `screenshots/audit/audit-suspicious-task-actions.png` – Action details  
- `screenshots/audit/audit-suspicious-task-history.png` – Execution history  

---

## 🔎 Audit Findings

Based on the task configuration and behavior, the following findings were documented:

- The task runs automatically without user interaction
- Execution frequency is higher than expected for a standard user task
- No business or operational justification could be identified
- The task represents a potential persistence mechanism

---

## 🚨 Risk Analysis

### ❗ Risk 1 – Persistence Mechanism via Scheduled Task

Scheduled Tasks are a common persistence technique used to execute code repeatedly without user interaction.  
If abused, they allow long-term presence on a compromised system.

---

### ❗ Risk 2 – Abuse by Compromised Standard User Account

The task was created and executed under a standard user context.  
If the account is compromised, an attacker could leverage scheduled tasks to maintain access without requiring administrative privileges.

---

### ❗ Risk 3 – Lack of Scheduled Task Monitoring

Without regular audits or monitoring of scheduled tasks, unauthorized or malicious tasks may remain active for extended periods, increasing attacker dwell time.

---

## 🛠️ Remediation Actions

Based on the findings, the following remediation actions were taken:

- The suspicious scheduled task was **deleted**
- No legitimate business justification was identified for its existence
- Removing the task eliminates the persistence mechanism

### 📸 Screenshots
- `screenshots/remediation/remediation-task-delete-confirmation.png` – Deletion confirmation  
- `screenshots/remediation/remediation-task-removed.png` – Task removed from library   
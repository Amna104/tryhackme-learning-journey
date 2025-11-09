# TryHackMe: SOC L1 Alert Reporting

**Learn how to properly report, escalate, and communicate about high-risk SOC alerts.**

🕒 **Estimated Time:** 60 minutes 

---

## 🧩 Task 1: Introduction

During or after alert triage, L1 analysts may sometimes be uncertain about how to classify an alert. This may require senior support or system owner input. L1s also face real cyberattacks that need immediate escalation and remediation.

This room introduces three essential SOC concepts:
- **Alert Reporting**
- **Escalation**
- **Communication**

### 🎯 Learning Objectives
- Understand the importance of SOC alert reporting and escalation  
- Learn how to write proper alert comments and case reports  
- Explore escalation procedures and communication best practices  
- Apply this knowledge in a simulated environment  
- Build confidence for SOC Simulator and SAL1 certification  

### 📚 Prerequisites
- Completion of the **SOC L1 Alert Triage** room  
- Basic understanding of common attacks  
- Awareness of SOC L1 analyst responsibilities  

### 🖥️ SOC Dashboard
Use the SOC Dashboard to practice reporting and escalation skills.  
Access is granted via the provided link in the TryHackMe room.

---

## 🧩 Task 2: Alert Funnel

The **Alert Funnel** represents how alerts move through different SOC levels:

1. **L1 Analysts** receive and triage alerts using SIEM, EDR, or ticketing tools.  
2. **Most alerts** are closed as false positives or handled at the L1 level.  
3. **True Positive alerts** are escalated to **L2 analysts** for further investigation.  
4. **Severe incidents** may require **DFIR (Digital Forensics and Incident Response)** intervention.

### Key Concepts
- **Alert Reporting:** Documenting investigation details and evidence before closure or escalation.  
- **Alert Escalation:** Passing alerts to L2 for deeper analysis and action.  
- **Communication:** Coordinating with other departments (IT, HR, etc.) for confirmation or context.

---

## 🧩 Task 3: Reporting Guide

Writing reports is essential for documentation, communication, and knowledge sharing within a SOC.

### 🧠 Why L1 Analysts Should Write Reports
| Purpose | Explanation |
|----------|--------------|
| Provide context for escalation | Helps L2 analysts quickly understand and continue the investigation. |
| Save findings for records | Alerts are kept indefinitely; storing context ensures clarity in the future. |
| Improve investigation skills | Writing reports helps analysts think clearly and explain findings effectively. |

### 📝 Recommended Report Format — *The Five Ws*
1. **Who:** The user or entity performing the activity  
2. **What:** Actions or events observed (commands, logins, downloads)  
3. **When:** The exact timeline of the activity  
4. **Where:** The affected system, IP, or platform  
5. **Why:** Reasoning for the final conclusion or verdict  

Use these five elements in every report to ensure clarity and completeness.

---

## 🧩 Task 4: Escalation Guide

After investigation and reporting, the next step is to decide whether to **escalate** the alert.

### 🔼 When to Escalate
- The alert indicates a major cyberattack or requires DFIR involvement.  
- Remediation is needed (e.g., malware removal, host isolation, password reset).  
- Communication with stakeholders (management, legal, customers) is required.  
- The alert is unclear or requires senior input.

### 🔄 Escalation Steps
1. Write your alert report and mark it **In Progress**.  
2. Assign the alert to the **L2 analyst on shift**.  
3. Notify L2 via chat or ticketing system.  
4. L2 reviews, validates, and proceeds with remediation or incident response.

### 💬 Requesting L2 Support
If you’re unsure about an alert, it’s always better to ask for help than to close it prematurely.  
Use your SOC’s preferred communication channels to request assistance.

---

## 🧩 Task 5: SOC Communication

Effective communication ensures SOC operations remain smooth during critical events.

### ⚠️ Communication Scenarios & Best Practices
- **Critical alert, L2 unavailable:** Call L2 directly, then L3 or manager if unresponsive.  
- **Compromised communication channel:** Use alternate methods (e.g., phone, email).  
- **Alert surge:** Prioritize critical alerts and inform L2 immediately.  
- **Missed malicious action:** Notify L2 as soon as you identify the mistake.  
- **Log issues:** Investigate what’s possible, then report to L2 or SOC engineer.

### 🧩 Communication Flow Example
L1 → Escalates data leak alert → L2 → Initiates DFIR & notifies legal/PR departments  

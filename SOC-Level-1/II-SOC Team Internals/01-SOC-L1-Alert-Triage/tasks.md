# 🧠 SOC Level 1 – Alert Triage

## 🧩 Task 1 — Introduction
**Summary:**  
This room introduces SOC alerts, their lifecycle, and the importance of alert triage. L1 analysts are the first line of defense, reviewing alerts to detect potential breaches.

**Learning Objectives:**  
- Understand SOC alerts and their properties  
- Learn how to triage alerts efficiently  
- Prepare for SOC workflows and SAL1 certification  

**Prerequisites:**  
- Basic understanding of attacks on Windows, Linux, and networks  
- Knowledge of SOC L1 roles and duties  

---

## 🧩 Task 2 — Events and Alerts
**Summary:**  
Events are system occurrences (logins, process launches, file downloads) that generate alerts through SIEM/EDR systems. Alerts allow SOC analysts to focus on suspicious activity instead of millions of raw logs.

**Key Points:**  
- Alerts come from SIEM, EDR/NDR, SOAR, or ITSM platforms  
- SOC L1 analysts review alerts, distinguish bad from good, and escalate real threats  
- L2 analysts and engineers support the process  

**Questions & Answers:**  
- *Number of alerts seen on the dashboard:* 5  
- *Name of the most recent alert:* *(record your current alert name here)*  

---

## 🧩 Task 3 — Alert Properties
**Summary:**  
Alerts have key fields that L1 analysts must understand before triage.

**Properties Include:**  
1. **Alert Time** – creation time  
2. **Alert Name** – summary of activity  
3. **Severity** – Low, Medium, High, Critical  
4. **Status** – New, In Progress, Closed  
5. **Verdict** – True Positive or False Positive  
6. **Assignee** – responsible analyst  
7. **Description** – logic and reason for alert  
8. **Fields** – additional info for triage  

**Questions & Answers:**  
- *Verdict for "Unusual VPN Login Location":* False Positive  
- *User mentioned in the alert:* *(record user here)*  

---

## 🧩 Task 4 — Alert Prioritisation
**Summary:**  
Alerts must be prioritized to ensure timely detection of critical threats. L1 analysts usually:  
1. Filter alerts (ignore duplicates or handled alerts)  
2. Sort by severity (Critical → Low)  
3. Sort by time (oldest first)  

**Questions & Answers:**  
- *Should you first prioritise medium over low severity alerts?* → Yea  
- *Should you first take newest alerts before older ones?* → Nay  

---

## 🧩 Task 5 — Alert Triage
**Summary:**  
Review assigned alerts carefully and apply L1 knowledge to determine legitimacy. Use playbooks or manuals if available.

**Steps:**  
1. Assign alert to yourself → move to In Progress  
2. Understand affected system/user and suspicious activity  
3. Analyze surrounding events and logs  
4. Decide on **True Positive** or **False Positive**  
5. Comment and close alert  

**Flags Received:**  
- First-priority alert: `THM{looks_like_lots_of_zoom_meetings}`  
- Second-priority alert: `THM{how_could_this_user_fall_for_it?}`  
- Third-priority alert: *(record flag once completed)*  

---

## 🧰 Tools & Skills Practiced
- SIEM/EDR dashboards  
- Alert investigation and triage  
- Prioritization and workflow management  
- Incident documentation  

---

## 🧾 TryHackMe Profile
🔗 [View My Public TryHackMe Profile](https://tryhackme.com/p/yourusername)

---

## 💼 Author
**Amna Arshad**  
Junior Security Analyst (in training) | MERN Stack Developer | Cybersecurity Enthusiast

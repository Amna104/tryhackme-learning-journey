# 🧠 SOC Level 1 — Introduction to SIEM  
Learned the fundamentals of **Security Information and Event Management (SIEM)** — the central security solution used in a Security Operations Center (SOC).  
Explored how logs are collected, normalized, correlated, and analyzed to detect and respond to threats efficiently.

---

## 🧩 Task 1 — Introduction  
**Summary:**  
Introduced the purpose of SIEM in modern SOC environments — collecting logs from various sources, correlating them, and helping analysts identify malicious activities.  

**Learning Objectives:**  
- Understand different log sources  
- Identify limitations of isolated logs  
- Recognize the importance of centralized log management  
- Explore key SIEM features and alert processes  

---

## 🧩 Task 2 — Logs Everywhere, Answers Nowhere  
**Summary:**  
Explored challenges of working with scattered logs from multiple devices across a network.  

**Log Source Types:**  
1. 🖥 **Host-Centric Logs** — Windows, Linux, Servers (file access, process creation, PowerShell execution)  
2. 🌐 **Network-Centric Logs** — Firewalls, IDS/IPS, Routers (SSH, VPN, FTP, HTTP traffic)  

**Challenges Identified:**  
- Numerous log sources generating hundreds of events/second  
- No centralization (logs stored on separate devices)  
- Limited context without correlation  
- Manual analysis impractical  
- Different log formats across sources  

**Takeaway:**  
A centralized, automated system is required to handle massive log data — introducing the need for SIEM.  

---

## 🧩 Task 3 — Why SIEM?  
**Summary:**  
SIEM centralizes, normalizes, and correlates logs to detect malicious activity and improve visibility.  

**Core Features:**  
- 🗂 **Centralized Log Collection:** Collects all logs in one place  
- ⚙️ **Normalization & Parsing:** Converts diverse logs into a consistent format  
- 🔗 **Correlation:** Finds relationships between events across systems  
- ⏰ **Real-time Alerting:** Detects threats using pre-built or custom rules  
- 📊 **Dashboards & Reporting:** Visualizes security data for quick insights  

**Example Scenario:**  
User “Haris” logs in via an unknown IP, accesses shared files, runs PowerShell, and connects externally — correlated logs reveal a **data exfiltration attempt**.  

---

## 🧩 Task 4 — Log Sources and Ingestion  
**Summary:**  
Learned how various devices generate logs and how SIEM solutions collect and process them.  

**Common Log Sources:**  
- 🪟 **Windows:** Event Viewer (`Event ID 4624`, `4688`, etc.)  
- 🐧 **Linux:** `/var/log/auth.log`, `/var/log/cron`, `/var/log/kern`  
- 🌐 **Web Servers:** `/var/log/apache/` or `/var/log/httpd/` for access logs  

**Log Ingestion Methods:**  
- 🧩 **Agent / Forwarder** — Lightweight tool (e.g., Splunk Forwarder)  
- 📨 **Syslog** — Common protocol for log forwarding  
- 📁 **Manual Upload** — Importing offline logs for analysis  
- 🔌 **Port Forwarding** — Listening ports to receive live data  

---

## 🧩 Task 5 — Alerting Process and Analysis  
**Summary:**  
Explored how SIEM triggers alerts using **detection rules** and how analysts investigate them.  

**Detection Rule Examples:**  
- 5 failed logins in 10 seconds → _Multiple Failed Login Attempts_  
- Successful login after failures → _Potential Brute-Force_  
- USB insertion → _Policy Violation_  
- Outbound traffic > 25 MB → _Possible Data Exfiltration_  

**Use Case 1:**  
If `EventID = 104` in `WinEventLog` → “Event Log Cleared” alert  

**Use Case 2:**  
If `EventID = 4688` and `NewProcessName` contains `whoami` → “Whoami Command Execution Detected”  

**Alert Analysis Workflow:**  
- 🟢 False Positive → Tune rule  
- 🔴 True Positive → Investigate further  
- 📞 Contact asset owner  
- 💻 Isolate host / block IP  

---

## 🧩 Task 6 — Lab Work  
**Scenario:**  
Monitored a simulated SIEM dashboard. Detected a suspicious process and investigated triggered alerts.  

**Findings:**  
| Question | Answer |
|-----------|--------|
| Process causing alert | `cudominer.exe` |
| Responsible user | `chris` |
| Hostname | `HR_02` |
| Term matching rule | `miner` |
| Alert type | `True Positive` |
| Flag | `THM{000_SIEM_INTRO}` |

---

## 🧩 Task 7 — Conclusion  
Learned how SIEM acts as the **heart of a SOC**, collecting, normalizing, correlating, and alerting on log data to identify potential threats in real time.

---

## 🧰 Tools & Skills Practiced  
- SIEM dashboards (Splunk example)  
- Log ingestion & normalization  
- Correlation rule creation  
- Alert investigation workflow  
- Detection of True/False positives  
- Threat analysis and host isolation  

---

## 🧾 TryHackMe Profile  
🔗 [View My Public TryHackMe Profile](https://tryhackme.com/p/yourusername)

---

## 💼 Author  
**Amna Arshad**  
Junior SOC Analyst (in training) | MERN Stack Developer | Cybersecurity Enthusiast  

# 🧠 SOC Level 1 — Introduction to EDR  
Learned the fundamentals of Endpoint Detection and Response (EDR), its architecture, telemetry, detection methods, and response capabilities used in real-world SOC environments.

---

## 🧩 Task 1 — Introduction
**Summary:**  
Introduces the concept of Endpoint Detection and Response (EDR) — a modern security solution designed to monitor, detect, and respond to advanced threats on endpoints.

**Learning Objectives:**
- Understand EDR basics and how it works  
- Differentiate between EDR and Antivirus  
- Explore EDR architecture and telemetry  
- Learn detection and response capabilities  
- Investigate a realistic alert within an EDR console  

---

## 🧩 Task 2 — What is an EDR?
**Summary:**  
EDR continuously monitors endpoints to detect threats that traditional antivirus tools miss, especially in remote or distributed environments.

**Core EDR Features (3 Pillars):**
1. 🔍 **Visibility:** Deep process, file, registry, and user activity monitoring  
2. 🚨 **Detection:** Signature-based + behavior-based analysis with ML  
3. 🛡️ **Response:** Remote containment actions (isolate, kill, quarantine)

**Example Tools:**  
CrowdStrike Falcon, SentinelOne, Microsoft Defender for Endpoint, OpenEDR, Symantec EDR  

**Answer:** The feature providing full context for detections is **Visibility** ✅  

---

## 🧩 Task 3 — EDR vs Antivirus  
**Analogy:**  
- **Antivirus:** Like immigration officers checking passports against a blacklist  
- **EDR:** Like security guards inside the airport watching behavior and cameras  

**Comparison Summary:**
| Step | AV Response | EDR Response |
|------|--------------|--------------|
| File download | Signature check | Logs and monitors |
| Macro runs PowerShell | Often misses | Flags unusual parent-child behavior |
| Memory injection | Missed | Detects process injection |
| Network connection | Missed | Flags outbound traffic |
| Final Result | May miss threat | Provides full attack chain |

**Conclusion:**  
EDR offers behavior-level protection and endpoint visibility beyond signature-based antivirus tools.  

---

## 🧩 Task 4 — How an EDR Works  
**Components:**
- 🧠 **EDR Console:** Centralized brain for data correlation and analysis  
- 👂 **EDR Agents (Sensors):** Deployed on each endpoint to collect data  
- 📊 **Telemetry:** Logs and sends real-time activity (processes, files, registry, etc.)

**Workflow:**
1. Agent monitors endpoint behavior  
2. Sends data to EDR console  
3. Machine learning detects anomalies  
4. Analyst reviews severity and takes action  

**Integration:**  
EDR integrates with other tools (Firewall, SIEM, DLP, IAM) for a unified defense ecosystem.  

---

## 🧩 Task 5 — EDR Telemetry  
**Definition:**  
Telemetry = Real-time data collected from endpoints to detect and investigate threats.  

**Collected Telemetry:**
- Process executions and terminations  
- Network connections  
- Command-line activity  
- File and folder changes  
- Registry modifications  

**Purpose:**  
Helps analysts reconstruct attack timelines and distinguish normal vs. malicious behavior.  

---

## 🧩 Task 6 — Detection and Response Capabilities  
**Detection Techniques:**
- Behavioral Detection  
- Anomaly Detection  
- IOC Matching  
- MITRE ATT&CK Mapping  
- Machine Learning Algorithms  

**Response Capabilities:**
- 🧱 Isolate Host  
- 🔪 Terminate Process  
- 🧰 Quarantine File  
- 💻 Remote Access (RTR)  
- 📦 Collect Artifacts (Memory dumps, logs, registry hives)

**Takeaway:**  
EDR provides both automated and manual response controls for rapid incident containment.  

---

## 🧩 Task 7 — Investigating Alerts  
**Scenario:**  
Analyzed alerts in a simulated EDR dashboard as a SOC analyst at TECH THM.  
Learned how to triage detections, understand severity, and explore visibility within the EDR interface.

---

## 🧰 Tools & Skills Practiced
- EDR dashboards (CrowdStrike Falcon examples)  
- Threat detection and triage  
- Behavioral and anomaly-based analysis  
- Host isolation and process termination  
- Telemetry investigation  
- MITRE ATT&CK mapping  

---

## 🧾 TryHackMe Profile  
🔗 [View My Public TryHackMe Profile](https://tryhackme.com/p/yourusername)

---

## 💼 Author  
**Amna Arshad**  
Junior SOC Analyst (in training) | MERN Stack Developer | Cybersecurity Enthusiast  

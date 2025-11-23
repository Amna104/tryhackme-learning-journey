# 🛡️ TryHackMe — File and Hash Threat Intel  
**Room Objective:**  
Learn how to enrich file and hash artefacts using threat intelligence tools like **VirusTotal**, **MalwareBazaar**, and **sandbox analysis**.

---

## 🧩 Task 1 — Introduction

Security Operations Centers (SOCs) work inside alert queues and follow three core steps:

1. **Verify**  
2. **Enrich**  
3. **Decide**

This room focuses on step **Enrich**, especially using **filepaths, filenames, and hashes** to determine whether a file is **benign, bait, or malicious**.

### 🎯 Learning Objectives
After completing this room, you can:

- Interpret suspicious filepaths and filenames  
- Generate and validate cryptographic hashes  
- Enrich files using **VirusTotal** & **MalwareBazaar**  
- Extract behaviour from sandboxes  
- Map behaviour to **MITRE ATT&CK**

### 📌 Scenario
It’s Monday. Your EDR flags several binaries on user workstations.  
As an **L1 SOC Analyst**, you receive a triage package.  
Within **60 minutes**, you must determine if files are **benign or malicious**.

---

## 🧩 Task 2 — Filenames and Paths

Filepaths and filenames act like **crime scene clues**. They reveal attacker behaviour and intent.

### 🔎 Filepath Analysis
Common attacker techniques:

- **C:\ (system drive)** → persistence, privileged areas  
- **C:\Users\Public** → cross-user access  
- **C:\Windows\Temp** → temporary payload staging  
- **C:\ProgramData** → writable system directory used for stealth  

### 🧠 Filename Heuristic Indicators
Watch out for these red flags:

- **Double extensions** → `invoice.pdf.exe`  
- **System process impersonation** → `scvhost.exe`  
- **High entropy random names** → `jf82hd.exe`  
- **Masquerading** → `backup-2300.exe`, or 1-letter substitution  

These do NOT prove malware alone, but they **strongly justify deeper investigation**.

---

## 🧩 Task 3 — File Hash Lookup

Attackers constantly rename malware.  
**Hashes remain the same** even when filenames change.

### 🔐 Generating SHA256 Hashes

**Windows CMD**
certutil -hashfile bl0gger.exe SHA256

**PowerShell**
Get-FileHash -Algorithm SHA256 bl0gger.exe

**Linux**
sha256sum bl0gger.exe


### 📝 Analyst Guidelines
- Store hashes in **lowercase**  
- Hash **everything that matters** (zip file + extracted binary)  
- Never store a hash without **context** (where/when found)  
- Any byte change → new hash  

---

### 🔍 VirusTotal Analysis

VirusTotal helps you determine:

- **Maliciousness score**  
- **Threat family names**  
- **YARA/heuristic rules**  
- **Infrastructure (IPs, domains)**  
- **Dropped files**  
- **File properties**  

#### 📊 What to Check

| Section | Key Question | Red Flags | Analyst Notes |
|--------|--------------|-----------|---------------|
| Detection Score | How many vendors detect it? | 5+ solid detections | New malware may have low initial detections |
| Upload Time | When was it first submitted? | Recent upload + high detections | Check again after 24–48 hrs |
| Signatures | Is it signed? | Invalid/missing cert | Certificates can be stolen |
| Properties | Any anomalies? | Odd compile time, high entropy | Compare w/ known-good versions |
| Relations | What does it connect to? | Known bad IPs/domains | Check infra on Shodan |
| Behaviour | What does it do? | Registry edits, process injection | Correlate w/ endpoint logs |

---

### 🔍 Cross-Reference: MalwareBazaar

MalwareBazaar is used to reinforce VirusTotal findings.

#### Features:
- Upload malware samples  
- Search by SHA256 → `sha256:<hash>`  
- Malware family tagging  
- YARA rules for hunting  
- Threat actor/campaign tags → `#TA551`  

Helpful for:
- Confirming family attribution  
- Downloading samples for sandboxing  
- Gathering related IOCs  

---

## 🧩 Task 4 — Sandbox Analysis

Static analysis identifies **what the file is**.  
Sandboxing identifies **what the file does**.

Sandboxes = isolated VMs that capture:

- Process execution  
- Registry changes  
- Network behaviour  
- Dropped payloads  
- MITRE ATT&CK mapping  

### ⚙️ Tools Used
- **Hybrid Analysis** → fast behavioural summary + MITRE heatmap  
- **Joe Sandbox** → deep-dive (syscalls, memory dumps, strings)  

### 🔥 Example Finding (Hybrid Analysis)
- Threat Score: **100/100** (malicious)  
- Shows MITRE ATT&CK techniques  
- Shows executed processes, domains contacted, dropped files, mutexes, etc.

---

### 🚫 Sandboxing Limitations

Attackers often evade sandboxes using:

#### **1. Sandbox Evasion**
- VM/environment checks  
- Anti-debugging  
- CPU/memory fingerprinting  

#### **2. Limited Execution Time**
Sandboxes typically run **2–5 minutes**, so multi-stage payloads remain undetected.

#### **3. Encrypted/Obfuscated Traffic**
- HTTPS traffic hides payloads  
- DNS tunneling may bypass visibility  

#### **4. Fileless & Living-off-the-Land Malware**
- PowerShell  
- WMI  
- Registry-based persistence  

These may **not appear** in traditional sandbox logs.

---

# ✔️ Room Completed  
This room taught critical SOC techniques for file and hash enrichment:

- Heuristic filename/path analysis  
- Hash fingerprinting  
- VirusTotal and MalwareBazaar enrichment  
- Sandbox dynamic behaviour mapping  
- MITRE ATT&CK alignment  

---

## ✍️ Author  
**Amna Arshad**  
Junior SOC Analyst (in training) | MERN Stack Developer | Cybersecurity Enthusiast  
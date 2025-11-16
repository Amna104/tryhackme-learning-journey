# 🌐 TryHackMe — Web Security Essentials  

**Objective:** Learn how the web works, identify common website security risks, and implement protections for a safer internet.  
**Duration:** ~60 min  
**Users Completed:** 9,779  

---

## 🧩 Task 1 — Introduction  

**Overview:**  
- Web applications are prime targets for attackers because of their widespread availability and connectivity to sensitive systems.  
- Understanding web operations and security measures is essential for defending web applications or investigating incidents.  

**Learning Objectives:**  
- Understand the shift from desktop to web applications.  
- Learn why web apps are common targets.  
- Explore web infrastructure and security tools.  
- Apply security measures to harden a web application.  

**Prerequisites:**  
- Basics of web applications.  
- HTTP fundamentals: requests, responses, and status codes.  

---

## 🧩 Task 2 — Why Web?  

**Shift from Desktop to Web:**  
- 1990s: Desktop apps dominated due to connectivity limits.  
- 2000s: Rise of dynamic web apps (email, banking, social media).  
- 2010s: Cloud computing & SaaS made web apps mainstream.  

**Security Perspective:**  
- Advantages: accessibility, faster updates, browser-based functionality.  
- Risks: web apps are always online, exposed, and often linked to backend systems.  

**Web App Owner vs User Risks:**  

| Web App Owner | Web App User |
|---------------|--------------|
| App is always online | Data stored on app, potentially insecure |
| Must secure users' data | Browser compromise risks all accounts |
| Stay updated with threats | Identity theft, financial loss possible |

**Real-World Breaches:**  
- **Equifax (2017):** Apache vulnerability exposed 150M users’ data.  
- **Capital One (2019):** Misconfigured WAF exposed 100M users’ sensitive info.  

---

## 🧩 Task 3 — Web Infrastructure  

**Request-Response Cycle:**  
1. Browser sends a request to a web server.  
2. Server processes request and responds (webpage, data, etc.).  

**Components of a Web Service:**  
- **Application:** Code, images, styles, and UI.  
- **Web Server:** Hosts the application and handles requests.  
- **Host Machine:** Underlying OS running server & app (Linux/Windows).  

**Common Web Servers:**  
- **Apache:** Popular for simple websites and WordPress.  
- **Nginx:** High-performance apps (Netflix, GitHub).  
- **IIS:** Microsoft server for enterprise environments.  

---

## 🧩 Task 4 — Protecting the Web  

**Security Measures:**  

**Application:**  
- Secure coding & error handling.  
- Input validation and sanitization.  
- Access control based on user roles.  

**Web Server:**  
- Logging of requests (access logs).  
- Web Application Firewall (WAF) to filter/block harmful traffic.  
- Content Delivery Network (CDN) to reduce exposure.  

**Host Machine:**  
- Least privilege principle.  
- System hardening and port management.  
- Antivirus for endpoint protection.  

**Additional Tips:**  
- Strong authentication for code/admin panels.  
- Patch management for apps, servers, and OS.  

**Access Logs Example:**  
- `GET /index.html` → homepage visit.  
- `GET /login.html` → login page access.  
- `POST /login.html` → credentials submitted.  
- `GET /myaccount.html` → account page viewed.  

---

## 🧩 Task 5 — Defense Systems  

**Content Delivery Network (CDN):**  
- Stores cached content on edge servers near users.  
- Security benefits: IP masking, DDoS protection, enforced HTTPS, integrated WAF.  

**Web Application Firewall (WAF):**  
- Inspects HTTP requests, blocks suspicious traffic.  
- Types: Cloud-based (reverse proxy), Host-based, Network-based.  
- Detection methods: Signature-based, Heuristic, Anomaly, Location/IP reputation.  

**Antivirus (AV):**  
- Protects endpoints from malware.  
- Detects malicious uploads or web shells.  
- Works as part of a layered defense strategy.  

---

## 🧩 Task 6 — Practice Scenario  

**Scenario:**  
- Site: **Secure-A-Site** is under development.  
- Goal: Secure the web application, web server, and host machine.  

**Practice Areas:**  
- **Web Application:** Apply input validation, access controls, secure coding.  
- **Web Server:** Enable logging, deploy WAF, leverage CDN.  
- **Host Machine:** Use least privilege, system hardening, antivirus.  

**Hands-On:**  
- Open the site and implement security measures.  
- Claim flags and answer questions to complete tasks.  

---

## 🧰 Key Takeaways  

- Web apps are always online, making them prime attack vectors.  
- Security requires a layered approach across **application, server, and host**.  
- Tools like **WAF, CDN, AV**, and **logging** are essential for detection and mitigation.  
- Practical exercises reinforce theoretical knowledge and incident response skills.

# 🛡️ TryHackMe — Network Traffic Basics

# Task 1 & 2 - Network Traffic Analysis (NTA)

## What is Network Traffic Analysis?
Network Traffic Analysis is the process of monitoring, inspecting, and analyzing data moving through a network.  
Think of it like **watching cars on a highway** to see where they go, how fast, and what they carry.

## Purpose of Network Traffic Analysis
- **Monitor network performance** – detect slowdowns or spikes.  
- **Detect abnormal activity** – find unusual behavior in systems.  
- **Inspect suspicious communication** – check for data exfiltration, malware, or command and control (C2) traffic.  
- **Support SOC operations** – verify alerts, reconstruct attacks, and detect threats.

## Example: DNS Tunneling
- A host (`WIN-016`) sends many DNS queries to `malicious-tld.com` with different subdomains.
- Logs alone show `who`, `when`, and `where`.
- Traffic inspection reveals **hidden commands** in TXT records, e.g., `SSBsb3ZlIHlvdXIgY3VyaW91c2l0eQ==`.

## Information Gathered from Traffic
1. Query and query type (A, TXT, etc.)  
2. Subdomain and TLD (check maliciousness using VirusTotal/AbuseDB)  
3. Host IP (source system)  
4. Destination IP (verify if malicious)  
5. Timestamp (for building a timeline)

## Real-Life Scenarios
1. Suspicious HTTP download detected through traffic inspection.  
2. Data exfiltration via DNS tunneling discovered by analyzing DNS traffic.

## Key Takeaway
Network Traffic Analysis is critical to **understand network behavior, detect threats, and investigate attacks**. Logs are helpful, but analyzing traffic content gives the full picture.


## Questions & Answers
**Q:** What is the name of the technique used to smuggle C2 commands via DNS?  
**A:** DNS tunneling

--------------------


# Task 3 – What Network Traffic Can We Observe?

## Understanding the TCP/IP Stack
Network traffic can be observed at different layers of the TCP/IP model.  
Each layer adds its own header containing important information.  
Logs typically show **only parts** of these headers, but full packet captures reveal **everything**, which is essential for detecting attacks.

---

## 1. Application Layer
This layer contains:
- **Application headers** (e.g., HTTP, DNS, SMTP)
- **Application data (payload)**

Example (HTTP GET request):
- Logs show the filename requested and server response.
- Logs do NOT show the contents of the ZIP file.
- Packet captures allow us to inspect the actual ZIP bytes.

---

## 2. Transport Layer
This layer breaks data into smaller segments.

Logs usually show:
- Source port
- Destination port
- TCP flags (SYN, ACK)

Logs do NOT show:
- TCP **sequence numbers**
- TCP **acknowledgement numbers**

These fields help detect session hijacking.  
Example:
- A packet with an abnormal sequence number jump can indicate an attacker injecting packets.

---

## 3. Internet Layer (IP Layer)
This layer adds IP addresses and handles fragmentation.

Logs usually show:
- Source IP
- Destination IP
- TTL

Packet captures allow inspection of:
- Fragment offset
- Total length
- Overlapping fragments

Attackers can perform **fragmentation attacks** to evade IDS systems.

---

## 4. Link Layer
This layer includes MAC addresses.

Logs show:
- Source MAC
- Destination MAC

Full packet captures reveal:
- ARP spoofing attempts
- Gratuitous ARP storms
- Conflicting MAC address claims

Example:
- An attacker responds to ARP requests with a fake MAC to perform ARP poisoning.

---

# Questions & Answers

### **1. What is the size of the ZIP attachment included in the HTTP response?**  
**Answer:** `10485760 bytes`

### **2. Which attack do attackers use to try to evade an IDS?**  
**Answer:** `Fragmentation`

### **3. What field in the TCP header can we use to detect session hijacking?**  
**Answer:** `Sequence number`

-----------------------------

# Task 4 – Network Traffic Sources and Flows

## 1. Network Traffic Sources

There are two main categories of network traffic sources:

---

### **Intermediary Sources**
Devices through which traffic *passes*. They generate low amounts of traffic.

Examples:
- Firewalls
- Switches
- Routers
- Web proxies
- IDS/IPS
- Access points
- Wireless controllers

Types of traffic they generate:
- Routing protocols (OSPF, BGP, EIGRP)
- Management protocols (SNMP, ICMP/Ping)
- Logging (Syslog)
- Network services (ARP, DHCP, STP)

---

### **Endpoint Sources**
Devices where traffic originates and ends.

Examples:
- Servers
- Workstations
- Printers
- IoT devices
- Mobile devices
- Virtual machines
- Cloud-hosted systems

**Endpoints generate the majority of network traffic.**

---

## 2. Network Traffic Flows

Traffic in a corporate network can be classified into two categories:

---

### **North–South (NS) Traffic**
Traffic going **in and out** of the internal network (LAN ↔ WAN).

Examples:
- HTTPS
- DNS
- RDP
- VPN
- SMTP
- SSH

This traffic always passes through a firewall and is monitored closely.

---

### **East–West (EW) Traffic**
Traffic that stays **inside** the LAN.

Examples:
- Active Directory & Kerberos
- SMB file sharing
- Internal application communication
- Database connections
- Backup & replication
- Monitoring & management services

EW traffic is important for detecting lateral movement by attackers.

---

## 3. Flow Examples

### **HTTPS with TLS Inspection**
- Client connects to a web proxy/firewall
- Proxy establishes a second connection to the web server
- Two sessions exist:  
  1. Client ↔ Proxy  
  2. Proxy ↔ Server  
- Proxy inspects encrypted data before passing it to the client

---

### **External DNS Flow**
1. Host sends DNS query to internal DNS server  
2. Internal DNS checks cache  
3. If unresolved, forwards query outward via firewall  
4. Response returns to internal DNS, which forwards it to the host

---

### **SMB with Kerberos Authentication**
Steps:
1. User logs in and receives a Ticket Granting Ticket (TGT)  
2. Host requests a service ticket from the KDC  
3. Host uses the service ticket to authenticate with the file server  
4. SMB session is established

---

# Questions & Answers

### **1. Which category of devices generates the most traffic in a network?**  
**Answer:** Endpoint devices

### **2. Before an SMB session can be established, which service needs to be contacted first for authentication?**  
**Answer:** Kerberos (Key Distribution Center)

### **3. What does TLS stand for?**  
**Answer:** Transport Layer Security

-----------------------------------





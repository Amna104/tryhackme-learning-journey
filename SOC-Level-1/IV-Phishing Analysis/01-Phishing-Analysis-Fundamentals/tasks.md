# 🧠 SOC Level 1 — Phishing Analysis

Learned the fundamentals of **email security analysis**, focusing on spam, phishing, and malicious emails. Explored email components, protocols, headers, bodies, attachments, and types of phishing attacks.  

---

## 🧩 Task 1 — Introduction  
**Summary:**  
- Spam and phishing are common **social engineering attacks**, primarily delivered via email.  
- Even with layered defenses, a single unsuspecting user can allow attackers into a network.  
- Analysts must know how to **analyze emails**, determine if they are malicious or benign, and gather intelligence to prevent future attacks.  
- Deployed virtual machines simulate real email analysis environments.  

---

## 🧩 Task 2 — The Email Address  
**Summary:**  
- Email invented by **Ray Tomlinson** in the 1970s for ARPANET.  
- An email address consists of:  
  - **User mailbox** (username)  
  - `@` symbol  
  - **Domain**  
- Example: `billy@johndoe.com` → `billy` is the mailbox, `johndoe.com` is the domain.  
- Analogy: mailbox = house number, domain = street.  

---

## 🧩 Task 3 — Email Delivery  
**Protocols Involved:**  
1. **SMTP (Simple Mail Transfer Protocol)** — sending emails  
2. **POP3 (Post Office Protocol)** — downloads emails to a single device  
3. **IMAP (Internet Message Access Protocol)** — syncs emails across multiple devices  

**Email Journey Overview:**  
1. Sender composes email in client → hits SEND.  
2. SMTP server queries **DNS** for recipient domain info.  
3. Email routed across Internet through SMTP servers.  
4. Email reaches recipient’s **POP3/IMAP server**.  
5. Recipient downloads (POP3) or syncs (IMAP) email.  

**Default Ports Example:**  
- SMTP: 25 (commonly used)  
- POP3: 110  
- IMAP: 143  

---

## 🧩 Task 4 — Email Headers  
**Purpose:** Understand email metadata for manual analysis.  

**Two Main Parts of an Email:**  
- **Header** — information about email routing, sender, and recipient  
- **Body** — content of the email (text/HTML)  

**Header Fields of Interest:**  
- `From` — sender’s address  
- `Subject` — subject line  
- `Date` — sent date  
- `To` — recipient  
- `X-Originating-IP` — sending IP  
- `Reply-To` — address for responses  

**Resource:** [Email Header Analysis Guide](https://web.archive.org/web/20221219232959/https://mediatemple.net/community/products/all/204643950/understanding-an-email-header)  

---

## 🧩 Task 5 — Email Body  
**Summary:**  
- **Plain text** vs **HTML emails** (HTML allows images, hyperlinks, attachments).  
- **Attachments:**  
  - `Content-Type` (e.g., `application/pdf`)  
  - `Content-Disposition` (`attachment`)  
  - `Content-Transfer-Encoding` (e.g., `base64`) → can decode and save attachments safely.  
- Always handle attachments carefully to avoid accidental execution.  

---

## 🧩 Task 6 — Types of Phishing  
**Common Malicious Emails:**  
- **Spam** — unsolicited bulk email; `MalSpam` = malicious spam  
- **Phishing** — pretends to be trusted entity to steal information  
- **Spear Phishing** — targeted to specific individuals/orgs  
- **Whaling** — targets high-level executives (CEO, CFO)  
- **Smishing** — SMS-based phishing  
- **Vishing** — voice call-based phishing  

**Characteristics of Phishing Emails:**  
- Spoofed sender email  
- Urgent subject lines (Invoice, Suspended, etc.)  
- HTML body mimicking trusted entity  
- Poorly formatted or generic text (Dear Sir/Madam)  
- Malicious hyperlinks (defanged: e.g., hxxp[://]www[.]suspiciousdomain[.]com)  
- Attachments posing as legitimate documents  

**Reminder:** Always **defang links and attachments** before investigation.  

**Lab Exercise:**  
- Analyze `email3.eml` in the VM.  
- Alexa = victim, Billy = analyst.  

---

## 🧰 Tools & Skills Practiced  
- Email header and body analysis  
- Protocol understanding (SMTP, POP3, IMAP)  
- Attachment and link inspection  
- Phishing classification and defense  
- Defanging suspicious URLs  

---

## 💼 Author  
**Amna Arshad**  
Junior SOC Analyst (in training) | MERN Stack Developer | Cybersecurity Enthusiast  

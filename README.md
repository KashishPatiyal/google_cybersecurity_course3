# Network Traffic Analysis and Attack Investigation

This repository contains two structured case studies related to cybersecurity network traffic analysis. Each case demonstrates the identification and analysis of network-level issues using packet inspection tools, aiding in incident detection and response.

## 📁 1. DNS & ICMP Unreachable Error Analysis (`dns-icmp-unreachable-analysis`)

### 🧠 Summary
A DNS request was sent to resolve the domain `www.yummyrecipesforme.com`, but users consistently encountered the error: **"destination port unreachable"**. Using `tcpdump`, ICMP responses were captured, revealing that UDP packets to port 53 (DNS) were met with the ICMP error "udp port 53 unreachable".

### 🔍 Key Findings
- The affected protocol: **UDP (DNS service)**.
- The triggered error response: **ICMP "Port Unreachable"**.
- Root cause: **No DNS service was listening on port 53 of the target server**.
- Timestamped packet analysis confirmed that the DNS resolution was the failure point, causing the web access issue.

### 💡 Takeaways
This incident underscores the importance of proper DNS server configuration and shows how ICMP responses can provide crucial clues during network troubleshooting.

---

## 📁 2. SYN Flood DoS Attack Response (`syn-flood-dos-attack-response`)

### 🧠 Summary
A travel agency’s website became inaccessible, with a connection timeout error. Packet analysis revealed a **flood of TCP SYN requests** from a suspicious IP, suggesting a **SYN Flood Denial-of-Service (DoS)** attack.

### 🔍 Key Findings
- Attack type: **SYN Flood Attack**.
- Symptoms: **Web server overwhelmed by incomplete TCP handshakes**.
- Temporary fix: **Blocked offending IP via firewall and took the server offline to stabilize**.
- Persistent threat: **IP spoofing** means attackers can bypass IP-based filtering.

### 💡 Takeaways
This case study demonstrates the impact of DoS attacks on service availability and the need for stronger solutions like rate limiting, SYN cookies, or intrusion prevention systems (IPS).

---

## 📦 Repository Structure

```bash
.
├── dns-icmp-unreachable-analysis.pdf
├── syn-flood-dos-attack-response.pdf
└── README.md

### **Step 5: Learn How Data Moves Through a Network (Packet Flow & Protocols)**

Now that you understand routing, switching, and IP addressing, it’s time to focus on **how data actually flows across a network**, and how **protocols** at different OSI layers interact. This is essential for analyzing traffic, detecting anomalies, and understanding cyberattacks.

---

### 🔹 **Step 5: Understand Packet Flow and Network Protocols**

#### 📘 Topics to Study:

##### 🧩 **Packet Flow in Action**:
- What happens when you type a URL in a browser? Understand the full journey:
  - DNS lookup (resolves domain to IP)
  - TCP 3-way handshake
  - HTTP/HTTPS request
  - Routing across networks
  - Response back from the server

##### 🛰️ **Important Protocols to Know**:
- **TCP vs UDP**:
  - TCP = connection-oriented (e.g., HTTPS, SSH)
  - UDP = faster but no guarantee (e.g., DNS, video streaming)
- **DNS** – Resolves domain names to IPs
- **ARP** – Resolves IP addresses to MAC addresses
- **ICMP** – Used for diagnostics (e.g., `ping`)
- **HTTP/HTTPS** – Web traffic
- **FTP, SSH, Telnet** – File transfer and remote access
- **DHCP** – Dynamically assigns IP addresses

##### 📡 **OSI & TCP/IP Models (Again)**:
- Reinforce how each protocol fits into the OSI model (especially Layers 3–7).
- Know how data is **encapsulated** and **decapsulated** as it moves through layers.

---

### 🧠 How to Study:
- **Wireshark Labs**: Capture real packet flows (e.g., open a webpage and inspect DNS, TCP handshakes, HTTP requests).
- **Protocol Deep-Dives**: Use resources like:
  - [Wireshark’s free capture samples](https://wiki.wireshark.org/SampleCaptures)
  - [PacketLife.net cheatsheets](https://packetlife.net/library/cheatsheets/)
- **Interactive Tools**:
  - Use [Packet Tracer] to simulate traffic
  - Use `ping`, `traceroute`, `nslookup`, `netstat`, and `tcpdump` in a terminal

---

### 🛡️ Cybersecurity Connection:
- Many attacks are visible in packet captures: **port scans**, **DNS spoofing**, **MITM**, **injection attacks**, etc.
- Analyzing packets helps you detect and prevent:
  - Suspicious connections
  - Misconfigured protocols
  - Malicious payloads (malware C2, etc.)

### **Step 7: Learn Common Network Attacks and How to Detect Them**

Now that you’ve built a lab and have hands-on experience with network tools, it’s time to **shift into the offensive and defensive mindset**. This step focuses on learning **how networks are attacked**, and how to **detect and prevent** these attacks — a core skill in cybersecurity.

---

### 🔹 **Step 7: Study Network-Based Cyber Attacks**

#### 🧨 Common Network Attacks You Must Know:
| Attack | Description | Tool Examples |
|--------|-------------|----------------|
| **Port Scanning** | Discover open ports and services on hosts | Nmap |
| **IP Spoofing** | Faking the source IP to appear trusted | Scapy |
| **MAC Spoofing** | Changing the MAC address to impersonate devices | macchanger |
| **Man-in-the-Middle (MITM)** | Intercepting traffic between devices | ARP spoofing with `ettercap`, `bettercap` |
| **DNS Spoofing** | Redirecting DNS queries to malicious IPs | dnsspoof |
| **ARP Poisoning** | Redirecting LAN traffic through attacker’s machine | arpspoof |
| **DoS/DDoS** | Flooding a target to disrupt service | LOIC, hping3 |
| **Packet Sniffing** | Capturing data on the network | Wireshark, tcpdump |
| **Rogue DHCP Server** | Attacker assigns wrong IP/Gateway to clients | Yersinia |

---

### 🧠 How to Study:
- **Simulate these attacks** in your home lab:
  - Use Kali Linux to perform basic scans, ARP poisoning, or DNS spoofing
  - Capture the traffic in Wireshark to understand what the attack looks like
- **Watch Real Attack Demos**:
  - YouTube channels: IppSec, The Cyber Mentor, LiveOverflow
- **Understand the Packet-Level Signatures** of attacks
  - Learn how an ARP spoof looks in Wireshark
  - What does a port scan look like? SYN packets to multiple ports

---

### 🛡️ Detection and Defense:
- Use **Wireshark** to build detection patterns
- Use **Snort or Suricata** to try real-time intrusion detection
- Learn how to read logs from **firewalls and routers**
- Practice writing **iptables/ufw** rules to block attacks

---

### 💡 Why This Step Is Crucial:
If you understand how an attack works at the packet and protocol level, you can:
- Detect it in real-time
- Write defensive rules
- Perform forensics after a breach

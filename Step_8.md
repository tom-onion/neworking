### **Step 8: Learn Network Monitoring and Intrusion Detection Systems (NIDS)**

Now that you’ve studied network attacks, the next step is learning how to **monitor networks and detect intrusions automatically** using professional-grade tools. This is a critical defensive skill in cybersecurity operations.

---

### 🔹 **Step 8: Set Up and Use Network Monitoring & IDS Tools**

#### 🧠 Core Concepts:
- **Network Monitoring**: Continuously inspecting traffic for performance, anomalies, or threats.
- **Intrusion Detection System (IDS)**: Detects suspicious traffic and alerts (e.g., Snort, Suricata).
- **Intrusion Prevention System (IPS)**: Detects and **blocks** malicious traffic (e.g., Suricata in IPS mode, pfSense with IDS/IPS).

---

#### 🛠️ Tools to Learn:
| Tool | Purpose | Description |
|------|---------|-------------|
| **Wireshark** | Manual monitoring | Visual packet inspection |
| **Snort** | IDS | Signature-based detection of known attacks |
| **Suricata** | IDS/IPS | Advanced, multi-threaded with protocol parsing |
| **Zeek (formerly Bro)** | IDS/monitor | Focuses on network behavior and logs |
| **pfSense** | Firewall + IDS/IPS | Complete network security appliance |
| **ELK Stack (Elasticsearch, Logstash, Kibana)** | Log analysis | Visualize alerts and logs from IDS systems |

---

#### ⚙️ Hands-On Lab Ideas:
1. **Set up Snort or Suricata** on a Linux VM.
2. Configure it to **monitor another VM’s traffic**.
3. Launch an attack from Kali Linux (e.g., port scan or MITM).
4. Watch the IDS **generate an alert**.
5. Visualize the logs using **Kibana** or simple log files.

---

#### 🧩 Learn Detection Techniques:
- Signature-based detection (matches patterns)
- Anomaly-based detection (detects deviation from normal)
- Behavior-based (long-term analysis like Zeek)

---

### 💡 Why This Matters:
In real-world cybersecurity roles (Blue Team), **IDS/IPS systems are your first alert** that something is wrong. Without visibility, you can’t defend the network.

---

### **Step 4: Understand Routing and Switching**

Now that you’ve got a solid grasp of IP addressing and subnetting, it’s time to dive into **routing** and **switching**, which are at the core of how data moves through networks. Understanding these concepts will help you as you learn to defend or attack networks in cybersecurity scenarios.

---

### 🔹 **Step 4: Master Routing and Switching**

#### 📘 Topics to Study:

- **Routing Basics**:
  - **What is Routing?**: Learn how routers determine the best path to send packets from one network to another.
  - **Static vs Dynamic Routing**:
    - **Static Routing**: Manually configured routes.
    - **Dynamic Routing**: Uses protocols like **RIP**, **OSPF**, **EIGRP** to automatically update routes based on network changes.
  - **Routing Tables**: How routers use routing tables to make forwarding decisions.
  - **Default Gateway**: Understand the role of the gateway as the path to reach external networks (like the internet).

- **Switching Basics**:
  - **What is Switching?**: Switches work at Layer 2 of the OSI model (Data Link Layer) to send data within a local network.
  - **MAC Address Table**: Switches maintain a MAC address table to know where to send frames within a network.
  - **VLANs (Virtual Local Area Networks)**: Understand how VLANs segment networks for better performance and security.
  - **Trunking**: Learn how switches communicate across VLANs using trunk ports (802.1Q tagging).

- **Advanced Routing Protocols**:
  - **OSPF (Open Shortest Path First)**: A more advanced routing protocol used in larger networks.
  - **BGP (Border Gateway Protocol)**: The protocol used for routing between different autonomous systems (AS) on the internet.

#### 🧠 How to Study:
- **Hands-on Lab**: Set up simple networks in Cisco Packet Tracer or GNS3. Start with routers and switches, and practice routing between different subnets.
- **YouTube Channels**: Look for tutorials on routing and switching from experts like NetworkChuck or CBT Nuggets.
- **Textbooks**: Books like *"Routing and Switching Essentials"* by Cisco are excellent for beginners.

#### 🛠️ Practical Tools:
- **Ping & Traceroute**: Use these to verify routing functionality and trace the path of packets through a network.
- **Wireshark**: Capture and analyze the data sent between routers and switches to understand how data flows.
- **NAT (Network Address Translation)**: Understand how NAT allows multiple devices on a private network to access the internet using a single public IP.

#### Why This Matters in Cybersecurity:
- **Routing**: Knowing how routing works helps you in securing network traffic and understanding how attacks like **Man-in-the-Middle (MITM)** or **IP Spoofing** can occur.
- **Switching**: Understanding VLANs and switches is crucial for defending against attacks like **VLAN hopping** and ensuring proper network segmentation.

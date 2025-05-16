
# Master Routing and Switching

---

## 🛰️ **Routing Basics**

### ✅ What is Routing?

Routing is the process of **moving packets between networks**.
Routers examine the **destination IP address** and forward packets along the best path.

---

### 🔀 Static vs Dynamic Routing

| Feature       | Static Routing                    | Dynamic Routing                             |
| ------------- | --------------------------------- | ------------------------------------------- |
| Configuration | Manually set by admin             | Automatically learned via routing protocols |
| Adaptability  | Doesn’t adjust to network changes | Adapts to topology changes                  |
| Use Case      | Small networks, simple configs    | Large or complex networks                   |
| Protocols     | None                              | RIP, OSPF, EIGRP, BGP                       |

---

### 📘 Routing Tables

A **routing table** is a list of known networks and the next hop to reach them.

**Example Entry:**

| Destination | Next Hop    | Interface | Metric |
| ----------- | ----------- | --------- | ------ |
| 10.0.0.0/24 | 192.168.1.1 | eth0      | 1      |

Routers consult this table to decide **where to send a packet**.

---

### 🌐 Default Gateway

* The **default gateway** is the IP address of the router your device sends data to **when the destination is outside your local network**.
* Set on every device (PC, phone, etc.)
* Acts as the "exit door" to the internet.

---

## 🔄 **Switching Basics**

### 📶 What is Switching?

Switching is the method of **sending data within a local network (LAN)**.
Switches operate at **Layer 2** of the OSI model and forward **Ethernet frames** based on **MAC addresses**.

---

### 🧠 MAC Address Table (CAM Table)

Switches learn which devices are connected to which ports by building a **MAC address table**.

| MAC Address         | Port |
| ------------------- | ---- |
| AA\:BB\:CC:11:22:33 | 1    |
| 00:11:22:33:44:55   | 2    |

Switches use this table to **forward frames only to the intended recipient**, unlike hubs that broadcast to all.

---

### 🧩 VLANs (Virtual LANs)

* **VLANs** logically divide a network into segments on the same switch.
* Devices in different VLANs **can’t communicate without a router** or Layer 3 switch.

**Example VLAN Setup:**

| VLAN ID | Department |
| ------- | ---------- |
| 10      | Sales      |
| 20      | HR         |
| 30      | IT         |

---

### 🧵 Trunking (802.1Q)

* Trunk ports **carry traffic for multiple VLANs** between switches or between a switch and a router.
* Tags are added to Ethernet frames to **identify the VLAN** (via **802.1Q** tagging).

---

## 🚀 Advanced Routing Protocols

### 📍 OSPF (Open Shortest Path First)

* **Link-state routing protocol**
* Uses **Dijkstra’s algorithm** to calculate shortest paths
* Fast convergence, good for medium to large enterprise networks
* Uses **areas** to segment routing and reduce overhead

---

### 🌍 BGP (Border Gateway Protocol)

* Used for **routing between ISPs or large networks (Autonomous Systems)**
* **Path-vector protocol**, not concerned with shortest path but **policy-based routing**
* Foundation of the **global internet routing system**

**Example:**
When your ISP needs to find a path to YouTube’s servers, it uses BGP to choose the best AS-path.

---

## 🧠 Summary Table

| Concept           | Key Idea                                                                |
| ----------------- | ----------------------------------------------------------------------- |
| Routing           | Moves data **between** networks                                         |
| Static Routing    | Manual, fixed routes                                                    |
| Dynamic Routing   | Auto-updates via RIP, OSPF, EIGRP, BGP                                  |
| Routing Table     | Map of destinations and next hops                                       |
| Default Gateway   | Device’s path to external networks                                      |
| Switching         | Moves data **within** a LAN based on MAC addresses                      |
| MAC Address Table | Tracks device-port mappings on a switch                                 |
| VLANs             | Logically segmented LANs                                                |
| Trunking          | Sends multiple VLANs over one link using tags                           |
| OSPF              | Link-state, fast convergence, enterprise use                            |
| BGP               | Internet-wide routing between autonomous systems (ISPs, large networks) |

---

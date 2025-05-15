# Networking Devices and Their Roles

---
# **ROUTERS**
---

## 🧭 **What Does a Router Do?**

A router **receives a packet**, looks at its **destination IP address**, and decides **where to send it** — either to a device in your local network or out to the internet.

## 📦 **How Routers Forward Packets – Step-by-Step**

### 🔁 **1. Device Sends a Packet**

* Your phone or laptop sends a packet (e.g., visiting a website like `example.com`)
* The packet contains:

  * Source IP: your device’s **private IP** (e.g., `192.168.1.10`)
  * Destination IP: the **public IP** of the website (e.g., `93.184.216.34`)


### 🌐 **2. Router Uses NAT (Network Address Translation)**

* Your router replaces your **private IP** with its **public IP**
* It records this change in a **NAT table** so it knows how to forward the response back to the right device

| Before NAT         | After NAT                              |
| ------------------ | -------------------------------------- |
| From: 192.168.1.10 | From: 203.0.113.5 (router’s public IP) |
| To: 93.184.216.34  | To: 93.184.216.34                      |

### 🧭 **3. Router Looks at the Routing Table**

* The router checks its **routing table** to decide where to send the packet
* If it’s going outside the network (like to the internet), it forwards the packet to the **default gateway** (usually your ISP)

### 📶 **4. Packet Travels Across the Internet**

* The packet hops through **multiple routers** on the internet
* Each one reads the **destination IP** and sends it closer to its destination

### 📩 **5. Web Server Responds**

* The web server sends a response **back to your router’s public IP**
* Your router checks the **NAT table** to see which device on your LAN requested it

### 🏠 **6. Router Forwards Packet to Device**

* The router **rewrites the destination IP** back to your device’s **private IP** (e.g., `192.168.1.10`)
* The data is delivered to your device


## 🔍 **Key Concepts Involved**

| Term                | What It Means                                  |
| ------------------- | ---------------------------------------------- |
| **NAT**             | Allows multiple devices to share one public IP |
| **Routing Table**   | Tells the router where to send packets         |
| **Default Gateway** | Where to send traffic that’s not local         |
| **Private IP**      | Only valid within your home network            |
| **Public IP**       | Unique address used on the internet            |

## 🧠 Simple Diagram (Text Version)

```
[Your Laptop] --(Private IP)--> [Router] --(Public IP via NAT)--> [Internet] --> [Web Server]
                                                 ↑
                                                 NAT Table tracks the translation
```


![image](https://raw.githubusercontent.com/tom-onion/tom-onion.github.io/refs/heads/main/router-visual-rep.png)
<br><br>
---

# **SWITCHES**

---

## 🔄 **What is a Switch?**

A **switch** is a device that connects multiple devices (computers, printers, etc.) within a **Local Area Network (LAN)** and **forwards data only to the device it’s meant for**.


## 🧩 **How Switches Operate: Step-by-Step**

### 1. **Learning MAC Addresses**

* When a device sends data, the switch looks at the **source MAC address** and notes which port it came from.
* It builds a **MAC address table** mapping devices to specific switch ports.


### 2. **Forwarding Frames**

* When a device sends data to another device, the switch looks at the **destination MAC address**.
* It checks its MAC table:

  * **If the address is known:** the switch sends the data only to the port linked to that MAC.
  * **If unknown:** it broadcasts the data to all ports (except the sender’s) — this is called **flooding**.


### 3. **Filtering Traffic**

* Switches prevent unnecessary traffic by only sending data where it’s needed.
* This reduces collisions and improves network efficiency compared to older devices like hubs.


## 📊 **Key Points About Switches**

| Feature            | Description                                |
| ------------------ | ------------------------------------------ |
| Operates at        | Layer 2 (Data Link) of OSI model           |
| Uses               | MAC addresses to forward frames            |
| Learns             | Source MAC addresses dynamically           |
| Traffic Type       | Forwards frames between devices            |
| Network Efficiency | Reduces unnecessary traffic and collisions |


## 🧠 Simple Analogy

Imagine a switch as a **smart mail sorter** in an office:

* It remembers which desk (port) each employee (MAC address) is at.
* When a letter (data) arrives for an employee, it sends it directly to their desk instead of handing it to everyone.


![image](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcT6fiuDUmAJmoaY0OzTaeYhvfRbe-JpoAeUiuOdoDCXPCbeA2CGDcBSfqNUjTEOraI37SQ&usqp=CAU)
<br><br>
---

# **FIREWALL**

---

## 🔥 **What is a Firewall?**

A **firewall** is a **security system** — hardware, software, or both — that **monitors and controls incoming and outgoing network traffic** based on a set of predefined security rules.

Its job: **Allow safe traffic and block potentially dangerous traffic**.


## 🛡️ **How Firewalls Filter Network Traffic**

### 1. **Packet Filtering**

* Inspects each packet’s **IP address**, **port number**, and **protocol**.
* Blocks or allows packets based on rules like “block all incoming traffic on port 23 (Telnet).”

### 2. **Stateful Inspection**

* Tracks the **state of active connections**.
* Allows only packets that are part of a legitimate ongoing connection.

### 3. **Proxy Service**

* Acts as an intermediary between your device and the internet.
* Receives requests, filters them, then sends safe traffic on behalf of your device.

### 4. **Next-Generation Firewalls (NGFW)**

* Include advanced features like **intrusion detection**, **application awareness**, and **deep packet inspection**.


## 🔍 **Firewall Roles in Cybersecurity**

| Role                         | Explanation                                                           |
| ---------------------------- | --------------------------------------------------------------------- |
| **Block Malicious Traffic**  | Stops attacks like hacking attempts, malware, and unauthorized access |
| **Enforce Network Policies** | Allows or denies traffic based on company or personal rules           |
| **Monitor Traffic**          | Logs network activity for analysis and alerts                         |
| **Prevent Data Leaks**       | Stops sensitive information from leaving the network                  |
| **Protect Devices**          | Shields computers, servers, and networks from threats                 |


## 🧠 **Firewall Deployment Types**

| Type                    | Where It’s Used                              | Description                         |
| ----------------------- | -------------------------------------------- | ----------------------------------- |
| **Network Firewall**    | At the boundary between two or more networks | Filters traffic between LAN and WAN |
| **Host-Based Firewall** | Installed on individual devices              | Protects a single computer          |
| **Cloud Firewall**      | Protects cloud-based infrastructure          | Managed via cloud service providers |


## 🛠️ **Common Firewall Rules Examples**

* Allow HTTP/HTTPS traffic (ports 80, 443) outbound
* Block all incoming traffic except responses to outgoing requests
* Block all traffic from suspicious IP addresses
* Restrict access to certain websites or services


## 🧠 Simple Analogy

A firewall is like a **security guard at a building’s entrance**:

* Checks IDs (packets)
* Lets in only authorized visitors
* Keeps out troublemakers

![image](http://www.researchgate.net/publication/333654196/figure/fig2/AS:767163430338561@1559917423381/How-Firewall-works-9.png)

<br><br>
---

# **Access Points (APs)**

---


## 📡 **What is a Wireless Access Point (AP)?**

An **Access Point (AP)** is a device that allows **wireless devices (like laptops, phones, tablets)** to connect to a **wired network** using Wi-Fi.

## 🧩 **How Wireless Networks Work**

1. **Wireless devices communicate using radio waves** on specific frequency bands (e.g., 2.4 GHz or 5 GHz).
2. The AP **receives wireless signals** from these devices.
3. The AP **converts wireless signals into wired Ethernet signals** and sends them through the wired LAN.
4. It also works in reverse: converting wired signals back into wireless signals for devices.


## 🔄 **AP’s Role in a Network**

| Step                            | Description                                            |
| ------------------------------- | ------------------------------------------------------ |
| Device connects wirelessly      | Using Wi-Fi, device connects to AP                     |
| AP receives data                | AP listens on wireless channels for device traffic     |
| Data forwarded to switch/router | AP sends data via Ethernet cable into the wired LAN    |
| Network communication           | Router forwards data to the internet or other networks |


## 📊 **Key Features of APs**

| Feature                   | Description                               |
| ------------------------- | ----------------------------------------- |
| Provides Wi-Fi coverage   | Allows wireless connectivity over an area |
| Connects wireless devices | Links Wi-Fi devices to wired LAN          |
| Handles multiple clients  | Supports many devices simultaneously      |
| Security                  | Supports Wi-Fi encryption (WPA2, WPA3)    |


## 🧠 Simple Analogy

Think of an AP as a **wireless bridge**:

* Wireless devices "talk" to the AP via radio waves.
* AP "translates" wireless signals into wired signals.
* This connects wireless devices to the rest of the network.

![image](https://datasave.qsfptek.com/upload/2023-10-27/1698388294233.jpg)
<br><br>
---

# **Network Interface Cards (NICs)**

---

## 💻 What is a Network Interface Card (NIC)?

A **Network Interface Card (NIC)** is a **hardware component** inside a computer or device that enables it to **connect to a network**.

* It can be **built-in** (integrated into the motherboard) or an **expansion card** you plug in.
* It works for both **wired connections** (Ethernet) and **wireless connections** (Wi-Fi).


## 🔧 What Does a NIC Do?

| Function                       | Description                                                   |
| ------------------------------ | ------------------------------------------------------------- |
| **Physical Connection**        | Provides a physical port or wireless radio for network access |
| **Data Link Layer Operations** | Packages data into frames and handles error detection         |
| **Addressing**                 | Has a unique **MAC address** to identify the device on a LAN  |
| **Sending & Receiving Data**   | Converts digital data to electrical signals and vice versa    |


## 🛠️ Types of NICs

| Type             | Description                      | Example Use                                    |
| ---------------- | -------------------------------- | ---------------------------------------------- |
| **Ethernet NIC** | Connects via Ethernet cable      | Desktop computers, servers                     |
| **Wireless NIC** | Connects via Wi-Fi radio signals | Laptops, smartphones                           |
| **Fiber NIC**    | Uses fiber optic cables          | High-speed data centers                        |
| **USB NIC**      | External NIC via USB port        | Adding network to devices without built-in NIC |


## 🧠 Simple Analogy

Think of a NIC as your device’s **network passport and translator**:

* The **MAC address** is like an ID card unique to your device.
* The NIC translates your computer’s data into signals the network understands and vice versa.

![image](https://resource.fs.com/mall/generalImg/HDUobq9gtof9RExpKF2czXygnkb.jpeg)

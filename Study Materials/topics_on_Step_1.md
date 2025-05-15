# What is a network? (LAN, WAN, internet)

A **network** is a group of interconnected devices (such as computers, servers, phones, and printers) that can communicate and share resources (like files, internet access, or printers). Networks can vary in size and scope, and they are typically classified into different types based on their scale and purpose. The three most common types are:

---

### 1. **LAN (Local Area Network)**

* **Definition**: A LAN is a network that covers a small geographic area, like a home, office, or school.
* **Example**: Your Wi-Fi network at home connecting your laptop, smartphone, and printer.
* **Characteristics**:

  * High speed
  * Private ownership
  * Limited to a single building or campus

---

### 2. **WAN (Wide Area Network)**

* **Definition**: A WAN spans a large geographic area and connects multiple LANs together.
* **Example**: A corporation's offices in different cities connected via leased communication lines.
* **Characteristics**:

  * Slower than LANs (typically)
  * Public or private ownership
  * Can span cities, countries, or even continents

---

### 3. **Internet**

* **Definition**: The internet is a **global network of networks**—it connects millions of private, public, academic, business, and government networks.
* **Example**: When you browse a website or send an email, you're using the internet.
* **Characteristics**:

  * Largest WAN
  * Open and public
  * Uses standard protocols like TCP/IP

---

### Summary Table:

| Type     | Full Form          | Scope              | Ownership      | Speed    |
| -------- | ------------------ | ------------------ | -------------- | -------- |
| LAN      | Local Area Network | Small/local area   | Private        | Fast     |
| WAN      | Wide Area Network  | Large/geographical | Private/Public | Slower   |
| Internet | -                  | Global             | Public         | Variable |


# What is an IP address? (IPv4 vs IPv6)

An **IP address** (Internet Protocol address) is a unique identifier assigned to each device connected to a network. It allows devices to find and communicate with each other over the internet or a local network.

---

## 📌 **What is an IP Address?**

* Think of it like a **home address** for your device on a network.
* It helps route data to the correct destination (e.g., when you open a website).

---

## 📖 **Types of IP Addresses**

There are two main versions of IP addresses:

---

### **1. IPv4 (Internet Protocol version 4)**

* **Format**: `192.168.1.1` (four numbers separated by dots)
* **Each number** ranges from 0 to 255
* **Bit length**: 32-bit
* **Total addresses**: About **4.3 billion**
* **Most commonly used** today

✅ **Example**: `172.16.254.1`
❗ **Limitation**: Running out of unique addresses due to the growth of the internet

---

### **2. IPv6 (Internet Protocol version 6)**

* **Format**: `2001:0db8:85a3:0000:0000:8a2e:0370:7334` (eight groups of four hexadecimal digits)
* **Bit length**: 128-bit
* **Total addresses**: **340 undecillion** (that’s 340 trillion trillion trillion!)
* **Designed to replace IPv4**

✅ **Advantages**:

* Much **larger address space**
* **Better security and efficiency**
* **No need for NAT** (Network Address Translation)

---

## 🧠 Summary Table

| Feature       | IPv4           | IPv6                           |
| ------------- | -------------- | ------------------------------ |
| Format        | 192.168.1.1    | 2001:0db8:85a3::8a2e:0370:7334 |
| Length        | 32-bit         | 128-bit                        |
| Address Space | \~4.3 billion  | \~340 undecillion              |
| Common Use    | Widely used    | Growing adoption               |
| Notation      | Decimal (dots) | Hexadecimal (colons)           |

---

# MAC address vs IP address

Both **MAC addresses** and **IP addresses** are used to identify devices on a network, but they serve different purposes and work at different levels in the networking model.

---

## 📡 **MAC Address vs IP Address**

| Feature         | **MAC Address**                                  | **IP Address**                                |
| --------------- | ------------------------------------------------ | --------------------------------------------- |
| **Full Form**   | Media Access Control Address                     | Internet Protocol Address                     |
| **Purpose**     | Identifies a device on a **local network**       | Identifies a device on a **network globally** |
| **Assigned By** | Manufacturer (burned into the device's hardware) | Network or ISP (can be dynamic or static)     |
| **Level**       | Layer 2 (Data Link Layer in OSI model)           | Layer 3 (Network Layer)                       |
| **Format**      | `00:1A:2B:3C:4D:5E` (hexadecimal, 6 pairs)       | IPv4: `192.168.1.1`, IPv6: `2001:db8::1`      |
| **Changeable?** | Usually **fixed**, but can be spoofed            | **Changeable**, often dynamically assigned    |
| **Scope**       | Local network only                               | Used for global communication across networks |

---

### ✅ **MAC Address** – Think "Device ID"

* Unique to each **network interface card (NIC)**
* Used for communication **within** a local area network (LAN)
* Often called the **physical address**

🧠 **Example**: When a router sends data to a laptop in your home, it uses the MAC address to deliver it directly.

---

### ✅ **IP Address** – Think "Location on the Network"

* Used to **route** traffic between networks and over the internet
* May change depending on the network (e.g., Wi-Fi at home vs. café)

🧠 **Example**: When you access a website, your IP address is used to send and receive information between your device and the web server.

---

### 📦 How They Work Together

* When your computer wants to send data, it uses the **IP address** to find the destination and the **MAC address** to actually deliver it on the local network.
* This is handled through a protocol called **ARP** (Address Resolution Protocol).

---


# What is DNS, DHCP?

**DNS** and **DHCP** are essential services that make modern networking—especially the internet—work smoothly, even if we don’t see them in action.

---

## 🌐 **DNS (Domain Name System)**

### ✅ What it does:

**DNS translates domain names (like `www.google.com`) into IP addresses (like `142.250.190.68`)** so computers can locate and connect to each other.

### 🧠 Analogy:

Think of DNS as the **internet's phone book**:

* You remember the name (`google.com`)
* DNS tells your device the number (IP address) to call

### 🔧 Example:

When you type `www.facebook.com` in your browser:

1. Your computer asks the DNS server: "What's the IP address of facebook.com?"
2. DNS replies: "It’s 157.240.1.35"
3. Your browser connects to that IP address

### 📍 Key Points:

* Saves you from having to remember numeric IP addresses
* DNS servers can be public (like Google’s `8.8.8.8`) or private (used in internal networks)

---

## 📦 **DHCP (Dynamic Host Configuration Protocol)**

### ✅ What it does:

**DHCP automatically assigns IP addresses and other network settings to devices on a network.**

### 🧠 Analogy:

DHCP is like a **host at a hotel**:

* You show up (connect to a network)
* The host (DHCP server) gives you a room (IP address), key (gateway), and rules (DNS info)

### 🔧 Example:

When your phone connects to Wi-Fi:

1. It sends a DHCP request: “Can I get an IP address?”
2. The DHCP server replies: “Sure, here’s 192.168.1.25”
3. Your phone uses this info to join the network

### 📍 Key Points:

* Makes it **easy to connect new devices** without manual configuration
* Can also assign **subnet mask**, **default gateway**, and **DNS server**

---

## 🧾 Summary Table

| Feature     | **DNS**                               | **DHCP**                                      |
| ----------- | ------------------------------------- | --------------------------------------------- |
| Full Form   | Domain Name System                    | Dynamic Host Configuration Protocol           |
| Purpose     | Converts domain names to IP addresses | Assigns IP addresses to devices automatically |
| Works Like  | Phone book for websites               | Hotel host handing out room numbers           |
| Typical Use | Typing a website URL                  | Connecting your phone to Wi-Fi                |

---


# OSI Model (7 layers) 

Let's break down the **OSI Model** with a focus on the most important layers for networking: **Layer 2 (Data Link), Layer 3 (Network), and Layer 4 (Transport)**.

---

## 📦 OSI Model – The 7 Layers (Overview)

From bottom to top:

1. **Physical** – cables, connectors, voltage
2. **Data Link** – MAC addresses, switches
3. **Network** – IP addresses, routing
4. **Transport** – end-to-end communication (TCP/UDP)
5. **Session** – managing sessions between applications
6. **Presentation** – data translation/encryption
7. **Application** – what the user interacts with (e.g., browser)

---

## 🔍 FOCUS: Key Layers

---

### **🔁 Layer 2: Data Link Layer**

#### ✅ What it does:

* Handles **direct communication between devices** on the same local network (LAN)
* Uses **MAC addresses** to identify devices
* Responsible for **framing**, **error detection**, and **flow control**

#### 🧱 Key components:

* **Switches**
* **MAC addresses**
* **Ethernet frames**

#### 📌 Example:

When your laptop sends a file to your printer on the same Wi-Fi, the Data Link layer ensures it goes to the **correct MAC address**.

---

### **🌍 Layer 3: Network Layer**

#### ✅ What it does:

* Responsible for **routing** packets across multiple networks
* Uses **IP addresses** to identify devices
* Determines the **best path** to reach the destination

#### 🧱 Key components:

* **Routers**
* **IP addresses (IPv4/IPv6)**
* **Packets**

#### 📌 Example:

When you visit a website, Layer 3 decides **how your request travels across the internet** to reach the web server, using the server’s IP address.

---

### **🚚 Layer 4: Transport Layer**

#### ✅ What it does:

* Provides **reliable or fast delivery** of data between devices
* Ensures **end-to-end communication** between applications
* Manages **data segmentation**, **flow control**, and **error recovery**

#### 🧱 Key protocols:

* **TCP (Transmission Control Protocol)** – reliable, ordered, error-checked (e.g., web browsing, email)
* **UDP (User Datagram Protocol)** – fast, no guarantee of delivery or order (e.g., video streaming, gaming)

#### 📌 Example:

When you stream a video:

* **TCP** is used if you need every bit (like downloading the file)
* **UDP** is used if speed matters more than perfect delivery

---

## 🧠 Summary Table

| Layer | Name      | Function                   | Examples                |
| ----- | --------- | -------------------------- | ----------------------- |
| 4     | Transport | End-to-end communication   | TCP, UDP                |
| 3     | Network   | Routing across networks    | IP, Routers             |
| 2     | Data Link | Local device communication | MAC addresses, Switches |

---


# What is a port? What is a protocol?

Understanding **ports** and **protocols** is key to making sense of how computers communicate over networks like the internet.

---

## 🔌 **What is a Port?**

### ✅ Definition:

A **port** is a **virtual doorway** on a device that helps direct network traffic to the right service or application.

Think of it as a **channel number** that a computer listens to for specific types of communication.

### 🧠 Analogy:

* Your IP address is like your **home address**
* A port is like the **room number** inside your house — it tells data **where** to go once it arrives

### 📍 Common Port Numbers:

| Port | Service            | Protocol |
| ---- | ------------------ | -------- |
| 80   | HTTP (websites)    | TCP      |
| 443  | HTTPS (secure web) | TCP      |
| 25   | SMTP (email)       | TCP      |
| 53   | DNS                | UDP/TCP  |
| 22   | SSH                | TCP      |
| 110  | POP3 (email)       | TCP      |

---

## 🌐 **What is a Protocol?**

### ✅ Definition:

A **protocol** is a **set of rules** that defines **how data is formatted, transmitted, and processed** between devices.

Protocols ensure that different systems can understand and respond to each other correctly — like speaking the same language.

### 🧱 Common Network Protocols:

| Protocol | Purpose                         | Transport Layer |
| -------- | ------------------------------- | --------------- |
| HTTP     | Web traffic                     | TCP             |
| HTTPS    | Secure web traffic              | TCP             |
| FTP      | File transfer                   | TCP             |
| DNS      | Domain name resolution          | UDP/TCP         |
| SMTP     | Sending emails                  | TCP             |
| TCP      | Reliable communication          | —               |
| UDP      | Fast, lightweight communication | —               |

---

## 🧠 Summary:

| Concept      | What It Does                      | Example                   |
| ------------ | --------------------------------- | ------------------------- |
| **Port**     | Routes traffic to specific apps   | Port 80 = web browser     |
| **Protocol** | Sets rules for data communication | HTTP, TCP, UDP, DNS, etc. |

---


# Common protocols: TCP, UDP, HTTP, HTTPS, FTP, ICMP, ARP

Here’s a clear breakdown of the **most common network protocols** you mentioned, including what they do, how they work, and where they’re used.

---

## 🌐 **Common Network Protocols**

| Protocol  | Full Name                      | Purpose                                     | Transport Layer     | Reliable? |
| --------- | ------------------------------ | ------------------------------------------- | ------------------- | --------- |
| **TCP**   | Transmission Control Protocol  | Reliable, ordered delivery of data          | Yes (Layer 4)       | ✅ Yes     |
| **UDP**   | User Datagram Protocol         | Fast, connectionless transmission           | Yes (Layer 4)       | ❌ No      |
| **HTTP**  | HyperText Transfer Protocol    | Web browsing (unencrypted)                  | Uses TCP            | ✅ Yes     |
| **HTTPS** | HTTP Secure                    | Secure web browsing (encrypted with TLS)    | Uses TCP            | ✅ Yes     |
| **FTP**   | File Transfer Protocol         | Uploading/downloading files between systems | Uses TCP            | ✅ Yes     |
| **ICMP**  | Internet Control Message Prot. | Diagnostic messages (e.g., ping, errors)    | Network Layer (3)   | N/A       |
| **ARP**   | Address Resolution Protocol    | Resolves IP addresses to MAC addresses      | Data Link Layer (2) | N/A       |

---

### 🔍 Protocol Descriptions

---

### **1. TCP (Transmission Control Protocol)**

* Ensures **reliable**, **ordered**, and **error-checked** delivery
* Used for email, web, file transfer
* **Connection-oriented**: must establish a connection before sending data
* Example: Browsing a website with HTTP/HTTPS

---

### **2. UDP (User Datagram Protocol)**

* **Faster**, but less reliable (no error checking or retransmission)
* Ideal for real-time applications: **video calls**, **gaming**, **streaming**
* **Connectionless**

---

### **3. HTTP (HyperText Transfer Protocol)**

* Used for **loading websites**
* Sends data in plain text (not secure)
* Port: **80**
* Based on TCP

---

### **4. HTTPS (HTTP Secure)**

* Same as HTTP, but **encrypted** using TLS/SSL
* Keeps web communication **private and secure**
* Port: **443**
* Also uses TCP

---

### **5. FTP (File Transfer Protocol)**

* Used for **transferring files** between computers on a network
* Can require authentication (username/password)
* Port: **21**
* Uses TCP

---

### **6. ICMP (Internet Control Message Protocol)**

* Used for **network diagnostics**
* Sends messages like:

  * "Destination unreachable"
  * "Time exceeded"
* Example: `ping` and `traceroute` commands

---

### **7. ARP (Address Resolution Protocol)**

* Translates an **IP address to a MAC address**
* Works on a local network (LAN)
* Crucial for sending data over Ethernet

---

## 🧠 Summary Table (at a glance):

| Protocol | Use Case              | Secure | Reliable | Layer       |
| -------- | --------------------- | ------ | -------- | ----------- |
| TCP      | General data transfer | No     | ✅ Yes    | Transport   |
| UDP      | Streaming, gaming     | No     | ❌ No     | Transport   |
| HTTP     | Web browsing          | No     | ✅ Yes    | Application |
| HTTPS    | Secure web browsing   | ✅ Yes  | ✅ Yes    | Application |
| FTP      | File transfer         | No     | ✅ Yes    | Application |
| ICMP     | Ping, diagnostics     | N/A    | N/A      | Network     |
| ARP      | IP-to-MAC resolution  | N/A    | N/A      | Data Link   |

---


---

# 🌐 **IP Addressing Basics**

### 📌 **1. IPv4 Address**

An **IPv4 address** is a 32-bit number written in **dotted decimal format**, like:

```
192.168.1.1
```

* Composed of 4 **octets** (each 8 bits), separated by dots.
* Each octet ranges from **0 to 255**.
* Example: `192.168.1.1` = `11000000.10101000.00000001.00000001` (binary)


### 📌 **2. Subnet Masks**

A **subnet mask** divides an IP address into:

* **Network portion** (which network it belongs to)
* **Host portion** (which specific device within that network)

**Common Subnet Mask:**

```
255.255.255.0  →  11111111.11111111.11111111.00000000
```

Used with IP: `192.168.1.10`
Means:

* **Network**: `192.168.1.0`
* **Host** range: `.1` to `.254`
* `.0` is network ID, `.255` is broadcast address


### 📌 **3. Public vs Private IP Addresses**

| Type        | Purpose                      | Example Ranges                                 | Routable on Internet? |
| ----------- | ---------------------------- | ---------------------------------------------- | --------------------- |
| **Private** | Used in internal LANs        | 192.168.x.x, 10.x.x.x, 172.16.x.x – 172.31.x.x | ❌ No                  |
| **Public**  | Assigned for internet access | Any IP outside private ranges                  | ✅ Yes                 |

Private IPs are **reused** in homes and offices, but require **NAT** (Network Address Translation) to connect to the internet via a **public IP**.


### 📌 **4. CIDR Notation (Classless Inter-Domain Routing)**

**CIDR** simplifies IP and subnet representation using a **slash** and number of network bits.

Example:

```
192.168.1.0/24
```

* `/24` means the **first 24 bits** are the network portion.
* Equivalent to subnet mask: `255.255.255.0`
* Leaves **8 bits** for host addresses → 2⁸ - 2 = **254 usable hosts**

**CIDR Notation Examples:**

| CIDR | Subnet Mask     | Hosts Available |
| ---- | --------------- | --------------- |
| /24  | 255.255.255.0   | 254             |
| /25  | 255.255.255.128 | 126             |
| /30  | 255.255.255.252 | 2               |


## ✅ Summary

| Term          | Description                                                                 |
| ------------- | --------------------------------------------------------------------------- |
| IPv4 Address  | 32-bit address in dotted decimal format (e.g., 192.168.1.1)                 |
| Subnet Mask   | Defines which portion of IP is network vs host                              |
| Private IP    | Used in LANs, not routable on the internet                                  |
| Public IP     | Unique, routable on the internet                                            |
| CIDR Notation | Shorthand to represent IP address + subnet mask (e.g., /24 = 255.255.255.0) |

---

# 🌐 What Is Subnetting?

**Subnetting** is the process of **dividing a large network into smaller logical subnetworks (subnets)** by adjusting the **subnet mask**.

This helps:

* **Reduce broadcast traffic**
* **Improve performance**
* **Enhance security**
* Efficiently **use IP addresses**


## 📘 How Subnetting Works

You **borrow bits** from the **host portion** of an IP address to create **more network portions** (subnets).

Example starting network:

```
192.168.1.0/24   → 255.255.255.0
```

* Total hosts = 2⁸ - 2 = **254 hosts**
* You can split it into:

  * Two /25 subnets (126 hosts each)
  * Four /26 subnets (62 hosts each), etc.


## ✏️ Subnetting Calculation Practice

### 🔹 Step 1: Determine Your Requirements

> Example: You need **4 subnets**, each supporting up to **50 hosts**.

### 🔹 Step 2: Calculate Needed Host Bits

* To support 50 hosts:
  2⁶ = 64 (−2 for network and broadcast) → ✅
* So you need **6 host bits**
* Since IPv4 has 32 bits, network bits = 32 - 6 = **/26**

Result:
Each subnet is `/26` = `255.255.255.192`


### 🧠 Quick Reference Table

| CIDR | Subnet Mask     | Subnets (from /24) | Hosts per Subnet |
| ---- | --------------- | ------------------ | ---------------- |
| /25  | 255.255.255.128 | 2                  | 126              |
| /26  | 255.255.255.192 | 4                  | 62               |
| /27  | 255.255.255.224 | 8                  | 30               |
| /28  | 255.255.255.240 | 16                 | 14               |
| /29  | 255.255.255.248 | 32                 | 6                |

> Formula for **hosts per subnet**:
> `2^(32 - subnet bits) - 2`


## 🛠️ Subnetting Techniques

1. **FLSM (Fixed Length Subnet Masking)**

   * All subnets are the same size.
   * Easy to manage, simple design.

2. **VLSM (Variable Length Subnet Masking)**

   * Subnets of **different sizes** based on needs.
   * Saves IPs, but requires more planning.
   * Common in enterprise routing.

3. **CIDR (Classless Inter-Domain Routing)**

   * Allows arbitrary prefix lengths (e.g., /22, /28).
   * Improves IP allocation on the internet.


## 🧩 Example Breakdown: Subnetting a /24

Original: `192.168.1.0/24`

Split into `/26`:

```
Subnet 1: 192.168.1.0/26     → 192.168.1.1–62     (Broadcast: 192.168.1.63)
Subnet 2: 192.168.1.64/26    → 192.168.1.65–126   (Broadcast: 192.168.1.127)
Subnet 3: 192.168.1.128/26   → 192.168.1.129–190  (Broadcast: 192.168.1.191)
Subnet 4: 192.168.1.192/26   → 192.168.1.193–254  (Broadcast: 192.168.1.255)
```

Each subnet supports **62 hosts** (with network and broadcast reserved).


## ✅ Summary

| Concept          | Description                                                   |
| ---------------- | ------------------------------------------------------------- |
| Subnetting       | Splits large networks into smaller subnets using subnet masks |
| Host Calculation | `2^(32 - subnet bits) - 2`                                    |
| CIDR Notation    | Shorthand for network + subnet mask (e.g., /26)               |
| FLSM             | Equal-size subnets                                            |
| VLSM             | Subnets of varying size, IP-efficient                         |

---

# 🏷️ **Classful IP Addressing**

Before **CIDR (Classless Inter-Domain Routing)**, IP addresses were divided into **classes** (A, B, C, D, E) based on **first octet value**. Each class had a fixed **network/host division**.


### 📚 **Main Classes (A, B, C)**

| Class | First Octet Range | Default Subnet Mask | # of Networks    | Hosts per Network      | Example IP  |
| ----- | ----------------- | ------------------- | ---------------- | ---------------------- | ----------- |
| **A** | 1 – 126           | 255.0.0.0 (/8)      | 128 (2⁷)         | \~16 million (2²⁴ − 2) | 10.0.0.1    |
| **B** | 128 – 191         | 255.255.0.0 (/16)   | 16,384 (2¹⁴)     | \~65,534 (2¹⁶ − 2)     | 172.16.0.1  |
| **C** | 192 – 223         | 255.255.255.0 (/24) | 2 million+ (2²¹) | 254 (2⁸ − 2)           | 192.168.1.1 |

> ⚠️ First octet 127 is reserved for **loopback (127.0.0.1)**, not Class A use.


### 🔸 **Special Classes**

| Class | Range   | Purpose                 |
| ----- | ------- | ----------------------- |
| **D** | 224–239 | Multicast               |
| **E** | 240–255 | Experimental / Research |


## 🧠 Key Takeaways

* **Class A** = Few networks, many hosts (used by large orgs)
* **Class B** = Medium networks, medium hosts (used by universities, ISPs)
* **Class C** = Many networks, few hosts (used in most LANs)
* **Class D & E** = Not used for standard host addressing


## ✅ Example Classification

| IP Address    | Class | Subnet Mask   | Use Case                 |
| ------------- | ----- | ------------- | ------------------------ |
| 10.0.0.1      | A     | 255.0.0.0     | Private org network      |
| 172.16.5.1    | B     | 255.255.0.0   | Medium-sized enterprise  |
| 192.168.1.100 | C     | 255.255.255.0 | Home or small office LAN |


## 📌 Why It’s Mostly Historical Now

* Classful addressing was **inefficient** — led to wasted IPs.
* **CIDR** replaced it by allowing **flexible subnet sizes** using `/` notation.
* Still useful for understanding legacy systems and **default routing behavior**.

---

# 🔒 **Private IP Address Ranges**

**Private IP addresses** are reserved IP blocks **not routable on the internet**. They’re used **within internal networks** (like homes, offices, or enterprises).

These ranges were defined by [RFC 1918](https://datatracker.ietf.org/doc/html/rfc1918).


### 📌 **Reserved Private IP Ranges**

| Range                           | Class | Number of Addresses  | Common Usage                 |
| ------------------------------- | ----- | -------------------- | ---------------------------- |
| `10.0.0.0 – 10.255.255.255`     | A     | \~16.7 million (2²⁴) | Large enterprises            |
| `172.16.0.0 – 172.31.255.255`   | B     | \~1 million (2²⁰)    | Medium-sized networks        |
| `192.168.0.0 – 192.168.255.255` | C     | \~65,536 (2¹⁶)       | Home networks, small offices |


### 💡 Key Points

* Devices using **private IPs can communicate with each other** within the same local network.
* To **access the internet**, private IPs are **translated** into a **public IP** using **NAT (Network Address Translation)** — usually done by a **router**.


### 🧠 Example in a Home Network:

| Device       | Private IP            |
| ------------ | --------------------- |
| Your laptop  | 192.168.0.101         |
| Your phone   | 192.168.0.102         |
| Your printer | 192.168.0.150         |
| Your router  | 192.168.0.1 (Gateway) |

> All of these devices share one **public IP** when communicating with the internet, via **NAT**.


### ❗ Why Use Private IPs?

✅ Avoids IP conflicts on the internet
✅ Enhances security (not directly reachable from outside)
✅ Conserves public IP addresses


## 🌍 Public vs Private IP Summary

| Type        | Used In                 | Routable on Internet? | Managed By  |
| ----------- | ----------------------- | --------------------- | ----------- |
| **Private** | LANs, internal networks | ❌ No                  | Local admin |
| **Public**  | Internet-wide           | ✅ Yes                 | ISP / IANA  |

---

# 🔹 What Is a VLAN?

A **VLAN (Virtual LAN)** is a **logical** (not physical) subdivision of a LAN that allows you to **group devices together**, even if they’re on different physical switches — as if they’re on the same network.


## 🎯 Purpose of VLANs

VLANs allow you to:

* **Segment network traffic** for performance and security.
* **Isolate departments** (e.g., HR, Finance, Engineering).
* Control broadcast domains (each VLAN = separate broadcast domain).
* Reduce congestion and limit unnecessary traffic.


## 📦 How VLANs Work

Without VLANs:

* One switch = one large broadcast domain.
* All devices receive all broadcast traffic.

With VLANs:

* Switch ports are **assigned to specific VLANs**.
* Devices on **different VLANs can’t communicate** directly (unless routed via a **Layer 3 device** like a router).


### 💡 VLAN Example:

| Department | Devices      | VLAN ID | Subnet          |
| ---------- | ------------ | ------- | --------------- |
| HR         | PC1, PC2     | 10      | 192.168.10.0/24 |
| IT         | PC3, Server1 | 20      | 192.168.20.0/24 |
| Guest      | Laptop1      | 30      | 192.168.30.0/24 |

* HR traffic stays on VLAN 10.
* IT can’t access Guest VLAN without routing.
* VLANs are enforced by the **managed switch**.


## 🔌 VLAN Trunking (802.1Q)

* A **trunk port** allows traffic for **multiple VLANs** to pass over a single link (e.g., between switches).
* It uses **802.1Q tagging** to mark which VLAN each frame belongs to.
* Essential for inter-switch VLAN communication.


## 🔐 VLAN Benefits

✅ Improved security (isolation)
✅ Better bandwidth usage
✅ Easier administration
✅ Scalable and flexible
✅ Supports BYOD and guest networks


## 🧠 Key Concepts Summary

| Term               | Meaning                                                  |
| ------------------ | -------------------------------------------------------- |
| VLAN ID            | Numeric ID (1–4094) used to identify VLANs               |
| Access Port        | Port assigned to a single VLAN                           |
| Trunk Port         | Port that carries traffic for multiple VLANs (with tags) |
| Inter-VLAN Routing | Routing between VLANs using Layer 3 switch or router     |
| Broadcast Domain   | Each VLAN creates a separate one                         |

---


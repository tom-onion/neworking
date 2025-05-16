
# Master IP Addressing and Subnetting

---

## 🌐 **IP Addressing**

### ✅ IPv4 Address

* Format: `xxx.xxx.xxx.xxx` (e.g., `192.168.1.1`)
* Each "xxx" is an **octet** (8 bits), total = **32 bits**
* Used to **identify devices** on a network

---

### 🎯 Subnet Masks

* Define which part of the IP is **network** and which is **host**
* Common example: `255.255.255.0` → `/24` CIDR
* Helps routers know **which subnet** an IP belongs to

**Example:**

| IP Address   | Subnet Mask   | Network Address |
| ------------ | ------------- | --------------- |
| 192.168.1.10 | 255.255.255.0 | 192.168.1.0     |

---

### 🔐 Private vs Public IPs

| Type    | Used Where           | Routable on Internet? | Example              |
| ------- | -------------------- | --------------------- | -------------------- |
| Private | Home, office LAN     | ❌ No                  | 192.168.0.1          |
| Public  | Internet-facing apps | ✅ Yes                 | 8.8.8.8 (Google DNS) |

**Private IP Ranges:**

* `10.0.0.0 – 10.255.255.255`
* `172.16.0.0 – 172.31.255.255`
* `192.168.0.0 – 192.168.255.255`

---

### 🧮 CIDR Notation (Classless Inter-Domain Routing)

* **Format:** `IP/NetworkBits` → e.g., `192.168.1.0/24`
* `/24` means: First **24 bits = network**, last **8 bits = host**
* Replaces class-based addressing for **more flexible subnetting**

---

## 🔧 **Subnetting**

### 📚 What is Subnetting?

Dividing a network into **smaller segments (subnets)** to:

* Improve performance
* Enhance security
* Manage IPs more efficiently

---

### ✂️ How to Divide a Network

**Steps:**

1. Choose how many **subnets** or **hosts per subnet** you need
2. Adjust subnet mask/CIDR to fit

| CIDR | Subnet Mask     | # Hosts/Subnet |
| ---- | --------------- | -------------- |
| /24  | 255.255.255.0   | 254            |
| /26  | 255.255.255.192 | 62             |
| /30  | 255.255.255.252 | 2              |

> Formula:
> Hosts = `2^H - 2` (where H = host bits)

---

### 🧠 Subnetting Example:

`192.168.1.0/24` → Want 4 subnets:

* Borrow 2 bits → `/26`
* Subnet ranges:

  * `192.168.1.0/26` → Hosts .1–.62
  * `192.168.1.64/26` → Hosts .65–.126
  * `192.168.1.128/26` → Hosts .129–.190
  * `192.168.1.192/26` → Hosts .193–.254

---

## 🏷️ **Classful Addressing**

| Class | Range (First Octet) | Default Subnet Mask | Hosts per Network |
| ----- | ------------------- | ------------------- | ----------------- |
| A     | 1–126               | 255.0.0.0 (/8)      | \~16 million      |
| B     | 128–191             | 255.255.0.0 (/16)   | \~65,534          |
| C     | 192–223             | 255.255.255.0 (/24) | 254               |

> Modern networks now use **CIDR** instead of class-based rules.

---

## 🧩 **VLANs (Virtual LANs)**

### 🧠 What is a VLAN?

A **Virtual LAN** logically segments a physical network:

* Devices on the same VLAN behave as if on the same switch—even if they are not physically connected
* Used for **traffic separation, security, and organization**

### 🏢 Use Case Example:

* VLAN 10 = HR
* VLAN 20 = IT
* VLAN 30 = Guests

Even if they use the same switch, **VLANs isolate traffic** between these groups.

---

## ✅ Summary

| Concept             | Key Idea                                        |
| ------------------- | ----------------------------------------------- |
| IPv4                | 32-bit address to identify devices on a network |
| Subnet Mask         | Defines network vs. host parts of an IP         |
| Private IP          | Used internally, not routable                   |
| Public IP           | Unique, used on the internet                    |
| CIDR Notation       | Compact IP + subnet mask format                 |
| Subnetting          | Splits network into smaller pieces              |
| Classful Addressing | Legacy method of IP classification              |
| VLANs               | Logical separation of networks on same hardware |

---

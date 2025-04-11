# IP Address

A client doesn’t magically know where a server is — it needs an **address** to locate and communicate with it.

On the internet, computers identify each other using **IP addresses**, which are like **phone numbers** for servers.

When a client wants to access a service (like a website or API), it needs the server’s **IP address** to send a request. This usually happens through **DNS (Domain Name System)**, which translates human-friendly names (like `example.com`) into machine-readable IP addresses (like `93.184.216.34`).

### 🔹 What is an IP Address?

An **IP address (Internet Protocol address)** is a unique identifier assigned to each device connected to a computer network that uses the Internet Protocol for communication.

---

### 🔸 Types of IP Addresses

### 1. **IPv4 (Internet Protocol version 4)**

- Format: `xxx.xxx.xxx.xxx` (e.g., `192.168.0.1`)
- 32-bit address
- Supports ~4.3 billion unique addresses
- Most commonly used

### 2. **IPv6 (Internet Protocol version 6)**

- Format: `xxxx:xxxx:xxxx:xxxx:xxxx:xxxx:xxxx:xxxx` (e.g., `2001:0db8:85a3:0000:0000:8a2e:0370:7334`)
- 128-bit address
- Supports trillions of addresses
- Designed to replace IPv4 due to address exhaustion

---

### 🔸 Classification of IPv4 Addresses

| Class | Range | Used For |
| --- | --- | --- |
| A | 1.0.0.0 to 126.255.255.255 | Large networks |
| B | 128.0.0.0 to 191.255.255.255 | Medium networks |
| C | 192.0.0.0 to 223.255.255.255 | Small networks |
| D | 224.0.0.0 to 239.255.255.255 | Multicasting |
| E | 240.0.0.0 to 255.255.255.255 | Reserved for future use |

---

### 🔸 Types by Use

1. **Public IP Address**
    - Accessible over the internet
    - Assigned by your Internet Service Provider (ISP)
2. **Private IP Address**
    - Used within a local network (e.g., home Wi-Fi)
    - Examples: `192.168.x.x`, `10.x.x.x`, `172.16.x.x` – `172.31.x.x`
3. **Static IP Address**
    - Manually assigned and does not change
4. **Dynamic IP Address**
    - Automatically assigned by DHCP and can change over time

---

### 🔸 Components of an IP Address

For IPv4:

- **Network part**: Identifies the specific network.
- **Host part**: Identifies the device on that network.

Example:

- IP: `192.168.1.10`
- Subnet Mask: `255.255.255.0`
- Network: `192.168.1.0`
- Host: `.10`

---

### 🔸 How to Find Your IP Address

- **Linux/macOS**:

```makefile
ifconfig or ip a
```

- **External IP** (public):
    
    Visit websites like `whatismyip.com`
    

## 🔧 How IPs Are Assigned to Devices

### ✅ **1. Automatically via DHCP (Dynamic Host Configuration Protocol)**

This is the **most common method**.

- When a device connects to a network (Wi-Fi or LAN), the **router** or a **DHCP server** assigns an IP address automatically.
- Example: Your phone joins Wi-Fi → router assigns it an available IP like `192.168.0.5`.

### 👉 Benefits:

- Easy setup
- No manual work
- IPs are recycled and reused efficiently

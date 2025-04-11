# Domain Name System

**DNS (Domain Name System)** — the phonebook of the internet.

## 🔍 What is DNS?

**DNS** (Domain Name System) is like the **address book** of the internet. It translates **human-friendly domain names** (like `www.google.com`) into **IP addresses** (`142.250.190.4`) that computers use to identify each other on the network.

Without DNS, you’d have to remember IP addresses for every website you want to visit — which is impractical.

## 🧠 How DNS Works (Step-by-Step)

When you type `www.example.com` in a browser:

### 1. **Check Local Cache**

- Your computer first checks if it already knows the IP address (from previous queries).
- If found, it uses it directly — super fast.

### 2. **Query the Recursive DNS Resolver**

- If not in cache, it asks a **recursive resolver** (usually provided by your ISP or Google DNS like `8.8.8.8`).

### 3. **Ask the Root Server**

- The resolver asks a **Root DNS server** (there are 13 logical root servers).
- Root server responds: "I don't know `example.com`, but I know where `.com` servers are."

### 4. **Ask the TLD Server**

- The resolver then queries the **TLD (Top-Level Domain)** server for `.com`.
- TLD server says: "I know where `example.com` lives, ask the authoritative name server."

### 5. **Ask the Authoritative DNS Server**

- The resolver asks the **authoritative server** for `example.com`.
- It returns the IP address.

### 6. **Return the IP**

- The resolver gives the IP address back to your browser.
- Your browser connects to the server and loads the website.

🔁 The resolver caches the result for a time (defined by TTL) to speed up future requests.

## 🧩 Key DNS Components

| Component | Description |
| --- | --- |
| **DNS Resolver** | Intermediary between client and DNS servers. Does the heavy lifting. |
| **Root Server** | Knows where all the TLD servers are. First step in resolution. |
| **TLD Server** | Knows where domain-specific (e.g., `.com`, `.org`) authoritative servers are. |
| **Authoritative Server** | Has the final answer (IP address or resource record). |
| **Cache** | Temporary storage to avoid repeating resolution process. |

![image.png](Domain%20Name%20System%201d01fec92daa802b9492fe5c4f239b25/image.png)

![DNS.png](Domain%20Name%20System%201d01fec92daa802b9492fe5c4f239b25/DNS.png)

## 📄 DNS Record Types (VERY Important)

| Record Type | Purpose | Example |
| --- | --- | --- |
| **A** | Maps domain to **IPv4 address** | `example.com → 192.0.2.1` |
| **AAAA** | Maps domain to **IPv6 address** | `example.com → ::1` |
| **CNAME** | Canonical name; alias for another domain | `www → example.com` |
| **MX** | Mail exchange, email routing | `example.com → mail server` |
| **NS** | Name servers for domain | `NS1.exampledns.com` |
| **TXT** | Text data; used in verification (SPF, DKIM) | `v=spf1 include:_spf.google.com` |
| **PTR** | Reverse DNS lookup (IP → domain) | Used by email servers |
| **SRV** | Service location (used in VoIP, etc.) | `_sip._tcp.example.com` |
| **SOA** | Start of Authority, meta info | TTL, admin email, etc. |

---

## ⏱️ TTL (Time To Live)

- Defines how long a DNS response is cached.
- Lower TTL = frequent updates (but more load).
- Higher TTL = faster lookups (but slower updates).

## 💡 Visual Recap

```
[You] (e.g., New York)
 ↓
Recursive Resolver (e.g., Google DNS in NYC)
 ↓
Root Server (nearest Anycast root node, maybe DC or NYC)
 ↓
TLD Server for .com (Verisign's node, maybe nearby)
 ↓
Authoritative Server (e.g., Google's own server)

```

## Summary Table (with Use Cases)

| Record | Purpose | When You Use It |
| --- | --- | --- |
| A | Map to IPv4 | Hosting a website |
| AAAA | Map to IPv6 | IPv6-enabled site |
| CNAME | Alias to domain | Point subdomain to main domain |
| MX | Email delivery | Setting up email (Google, Outlook) |
| NS | Delegation | Who manages your DNS |
| TXT | Email security, site verification | Google/SSL/SPF/DKIM |
| PTR | IP → Hostname (reverse) | Spam prevention, server validation |
| SRV | Service discovery | VoIP, chat, LDAP |
| SOA | Zone authority + timing | DNS replication logic |

[Root Server Technical Operations Association](https://root-servers.org/)

[What is DNS? | How DNS works | Cloudflare](https://www.cloudflare.com/learning/dns/what-is-dns/)

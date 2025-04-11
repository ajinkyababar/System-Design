# Proxy

## 🔹 What is a Proxy Server?

A **proxy server** acts as an **intermediary** between a client (like your browser) and another server (like a website). When a client makes a request, it goes to the proxy, which then forwards it to the destination server. The response returns through the proxy as well.

Think of it like a **middleman**.

![updated-proxy-diagram.svg](Proxy%201d01fec92daa80cba051d97aaf094dba/updated-proxy-diagram.svg)

## 🔹 Types of Proxy Servers

### 1. **Forward Proxy**

**Location**: Between client and internet

- The client knows it's using a proxy.
- The destination server doesn't know who the real client is.

**Use Case**: Client-side privacy, content filtering, bypassing geoblocks.

**Example**:

- A company uses a forward proxy to control and log employee internet usage.
- A user in a restricted country accesses blocked content via a forward proxy.

### 2. **Reverse Proxy**

**Location**: Between internet and web server

- The client is unaware it's using a proxy.
- The proxy decides which server should handle the request.

**Use Case**: Load balancing, SSL termination, caching, hiding backend details.

**Example**:

- Netflix uses reverse proxies to manage load and serve content efficiently.
- NGINX or Apache as reverse proxies in front of backend APIs.

## 🔹 Key Differences: Forward vs Reverse Proxy

| Feature | Forward Proxy | Reverse Proxy |
| --- | --- | --- |
| Sits between | Client and Server | Server and Client |
| Used by | Clients | Servers |
| Purpose | Hide clients, restrict/filter access | Hide servers, balance load, enhance security |
| Seen by origin | Server sees proxy (not client) | Client sees proxy (not server) |
| Examples | Squid, Tor | NGINX, HAProxy, Cloudflare |

## 🔹 Common Uses

### ✅ Forward Proxy Uses:

- 🔒 Anonymous browsing
- 🌍 Bypass geo-restrictions
- 🛡️ Content filtering in organizations
- 📊 Monitor employee/student usage

### ✅ Reverse Proxy Uses:

- ⚖️ Load balancing
- ⚡ Speed via caching
- 🛡️ DDoS protection
- 🔐 TLS/SSL termination
- 🎯 Route to microservices

## 🔹 Real-World Examples

| Tool/Service | Type | Description |
| --- | --- | --- |
| Squid | Forward Proxy | Caching and filtering for clients |
| Tor | Forward Proxy | Anonymous internet usage |
| NGINX | Reverse Proxy | Web server + load balancer |
| Cloudflare | Reverse Proxy | DDoS protection, CDN |
| AWS ELB | Reverse Proxy | Routes traffic to EC2 containers |

## 🔹 **Forward Proxy – Common Uses (Client-side Proxy)**

### 1. **Anonymous Browsing**

- Hides your IP address from the websites you visit.
- Example: Use a proxy to access a website without revealing your identity.

### 2. **Bypassing Geo-Restrictions**

- Access websites/services blocked in your country (like Netflix US from abroad).
- Example: Use a US-based forward proxy while traveling in Europe to access American content.

### 3. **Content Filtering**

- Used by schools or companies to block access to certain websites (e.g., social media, gaming).
- Example: Employees can’t access YouTube at work.

### 4. **Internet Usage Monitoring**

- Logs and monitors traffic for compliance or security.
- Example: A company tracks all web traffic going out of its network.

### 5. **Caching Content**

- Stores web content to speed up repeated requests.
- Example: Reduces bandwidth by caching static web pages.

---

## 🔹 **Reverse Proxy – Common Uses (Server-side Proxy)**

### 1. **Load Balancing**

- Distributes client requests across multiple backend servers.
- Example: Balances traffic between app servers to handle high load.

### 2. **Caching**

- Stores responses to reduce repeated requests hitting the backend.
- Example: Caches homepage content to serve faster.

### 3. **SSL Termination**

- Handles HTTPS encryption/decryption to offload work from backend.
- Example: NGINX decrypts HTTPS and forwards plain HTTP to internal servers.

### 4. **Security / Anonymizing Backend**

- Hides backend server details, preventing direct access.
- Example: Prevents attackers from directly targeting your app server.

### 5. **Compression & Optimization**

- Compresses responses (like Gzip) before sending to clients.
- Example: Reduces payload size to improve performance.

### 6. **Routing Requests (API Gateway)**

- Routes requests to different microservices based on path or headers.
- Example: `/api/users` goes to user service, `/api/orders` to order service.

| Proxy Type | Example | Main Role |
| --- | --- | --- |
| Forward Proxy | Squid, Tor | Hides the **client**, filters requests |
| Reverse Proxy | NGINX, Cloudflare | Hides the **server**, balances load, caches |

## 🔹 What is a VPN?

A **VPN (Virtual Private Network)** encrypts **all your internet traffic** and routes it through a remote server, masking your IP and location.

🛡️ **Works at the operating system level**, not just your browser.

---

## 🔍 Key Differences

| Feature | **Proxy** | **VPN** |
| --- | --- | --- |
| **Traffic Scope** | Only selected apps (usually browser) | All traffic (entire device) |
| **Encryption** | ❌ Usually no encryption | ✅ Strong encryption (AES-256) |
| **Anonymity** | Moderate (depends on provider) | High (with no-logs VPNs) |
| **Speed** | Usually faster, less secure | Slightly slower due to encryption |
| **Cost** | Often free or cheaper | Usually paid ($5–10/month) |
| **Use Case** | Geo-bypass, scraping, light traffic routing | Privacy, secure access on public Wi-Fi, torrenting |
| **Security Level** | Low to medium | High |
| **Setup** | Simple browser or app settings | Requires VPN app or OS-level configuration |


# What is DNS?

**DNS** stands for **Domain Name System**.

When you type a website like `google.com` or `lakshmireddy.site` in your browser, DNS translates the domain name into an IP address. This is how your computer knows where to connect.

**Example:**
```
google.com          → .com is the TLD (Top-Level Domain)
lakshmireddy.site   → .site is the TLD
```

---

## 🔁 Step-by-Step: What Happens When You Type a Domain in the Browser

```
You type → lakshmireddy.site
        ↓
1. Browser Cache
        ↓
2. Operating System (OS)
        ↓
3. OS Cache
        ↓
4. DNS Resolver (usually by your ISP)
        ↓
5. Root Servers
        ↓
6. TLD Servers (.site)
        ↓
7. Name Server (holds actual records)
        ↓
8. Returns IP Address
```

### 🧩 Components Explained:

#### ✅ OS:
If the browser doesn’t know the IP, your **Operating System** (Windows, macOS, Linux) checks its own cache to see if it remembers the IP address.

#### ✅ DNS Resolver:
If not found, your system asks a **DNS Resolver** (usually from your ISP). This resolver does all the querying work for you.

#### ✅ Root Servers:
The resolver now asks the **Root DNS Servers**: “Where can I find info about `.site` domains?” There are **13 root server systems** globally.

#### ✅ TLD Servers (Top-Level Domain):
These servers are in charge of specific domain extensions like `.com`, `.org`, `.in`, `.site`, etc. The resolver contacts the `.site` TLD server.

#### ✅ Authoritative Name Server:
The TLD server directs the resolver to the **name server** that holds DNS records for `lakshmireddy.site`. These records include the **IP address**.

#### ✅ Get the IP Address:
The name server replies:  
> “The IP address for `lakshmireddy.site` is `123.89.0.0`”  
The browser uses this IP to connect to the site.

---

## 🔑 Key Parts of DNS:

- **Domain Name**: e.g., `google.com`
- **Name Server**: Special servers that store DNS records.
- **DNS Record**: Instructions stored on name servers to direct traffic.

---

## 🧾 Common DNS Record Types:

### 📌 A Record (Address Record)
- Maps a domain name to an **IPv4 address**.
- Used to tell browsers where to find a website.

**Example:**
```
lakshmireddy.in → 123.89.0.0
```

---

### 📌 CNAME Record (Canonical Name)
- Points a domain/subdomain to **another domain**, not an IP.
- Often used for subdomains.

**Example:**
```
www.lakshmireddy.in → lakshmireddy.in → 123.89.0.0
```

> ⚠️ CNAME must point to a domain (not an IP) and **cannot be used on root domains** — only subdomains.

---

### 📌 MX Record (Mail Exchange)
- Used to route **emails** to mail servers for the domain.

---

### 📌 TXT Record (Text Record)
- Holds **text information** for verification (e.g., Google, Microsoft).
- Also used for **email security policies** like SPF, DKIM, and DMARC.

---


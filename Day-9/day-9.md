
# What is DNS?

**DNS** stands for **Domain Name System**.

### Example:
When you type a website like `google.com` into your browser, the DNS translates the domain name into an IP address. This is how your computer connects to the correct server hosting the website.

---

## 🔑 Key Parts of DNS:

- **Domain Name**: e.g., `google.com`
- **Name Server**: Special servers that hold DNS records.
- **DNS Record**: Instructions stored in the name servers that tell how to handle requests for a domain.

---

## 📄 Common DNS Record Types:

### 1. **A Record (Address Record)**  
- Points a domain name to an IPv4 address.  
- Tells browsers where to find the website.

**Example:**
```
lakshmireddy.in ➝ 123.89.0.0
```

---

### 2. **CNAME Record (Canonical Name)**  
- Points one domain to another domain name (not directly to an IP address).  
- Commonly used for subdomains.

**Example:**
```
www.lakshmireddy.in ➝ lakshmireddy.in ➝ 123.89.0.0
```

> ⚠️ **Note**: A CNAME must always point to another domain name, not an IP address.  
> CNAME records **cannot** be used for root domains — only subdomains.

---

### 3. **MX Record (Mail Exchange Record)**  
- Used to specify mail servers for a domain.  
- Directs email traffic to the correct server.

---

### 4. **TXT Record (Text Record)**  
- Used for domain verification and other purposes such as SPF, DKIM, and DMARC records.

```
Example uses:
- Verifying domain ownership for services like Google
- Setting email security policies
```

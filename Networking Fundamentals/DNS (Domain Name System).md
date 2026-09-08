## DNS Resolution

**What it is:** Translates domain names to IP addresses and Vice Versa

**How it works:**

- **Browser checks cache** → then asks your **Recursive Resolver** (your ISP or 8.8.8.8)
- Resolver asks a **Root Nameserver** → returns address of the **.com TLD nameserver** (TLD - Top Level Domain)
- Resolver asks the **.com TLD nameserver** → returns address of **Google's Authoritative Nameserver**
- Resolver asks **Google's Authoritative NS** → gets the actual IP → sends it back to you

**Recursive Resolver** = the detective. Makes multiple separate queries (Root → TLD → Auth NS) on your behalf, caches the result, returns IP to you. Does all the legwork.

**Authoritative NS** = just a database. Holds the actual DNS records for a domain. When asked, it simply replies "google.com = 142.250.x.x" — that's it. It doesn't query anyone or close connections back through the chain

**SOC angle:** DNS abuse = common C2 channel (DNS tunneling)

**My gap:** No return chain through Root/TLD — resolver sends IP directly to client

**Example:** typing google.com → resolver finds 142.250.x.x


Anchor's : 
- Recursive Resolver does all the legwork
- Queries Root → TLD → Authoritative NS in order
- Returns IP to client, caches it
- Resolver = asks questions & Authoritative NS = has the answers.

TIP :
What is the type of log that has a destination port number of 52567 and a source IP address of 8.8.8.8?  
  
Answer Format: logtype
Answer : DNS
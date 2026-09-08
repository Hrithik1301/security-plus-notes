
They are designed to control the flow of traffic between two points, and we might be able to control the traffic flowing in or out of the network using firewalls. we can have firewalls in home, office, built into Operating Systems etc

Functionalities

     1. corporate control of outbound & inbound data (sensitive materials)
     2. control of inappopriate content (NSFW, Parental controls)
     3. protection against evils like virus & malware

Network based firewalls filter traffic by port no. (OSI Layer 4) or application (OSI Layer 7)

A. **Traditional FireWalls** 

1. control traffic based on OSI Layer 4 wiz port no. i.e., either a TCP port no. or a UDP port no.

Unified Threat Management Device (UTM)

older firewalls with additional functionalities
also called as  Web Security Gateway
URL filter/content inspection
malware inspection
spam filter
csu/dsu
router, switch
firewall
IDS/IPS
Bandwidth shaper
VPN endpoint

but with a lot of features the performance is compromised


B. **Next Generation FireWalls (NGFW's)**

1. control traffic based on OSI Layer 7 wiz application layer
2. used to make Forwarding decisions based on the applications that are being used on the network
3. also called by different name such as application layer gateway, stateful multilayer inspection, deep packet inspection 
4. Requires some advanced decodes such as every packet must be analyzed and categorized before a security (forwarding) decision is determined
5. controls traffic flows based on applications
6. intrusion prevention systems(IPS) i.e., identify the application, and apply application specific vulnerability signatures to the traffic
7. content filtering such as URL filters, control website traffic by category.

Quick addition: NGFW also does **deep packet inspection, IPS (intrusion prevention), URL filtering, and app identification** — so it can block YouTube or allow SSH but block port scanners on the same port. Not just layer 7 awareness but full visibility into what the traffic actually is.


**C. WEB Application FireWall (WAF)**

1. not like a normal firewall, applies rules to HTTP/HTTPS conversations
2. allow or deny based on explicit input i.e., unexpected input is a common method of exploiting an application
3. SQL injection i.e., add your own command's to an application's SQL Query
4. A major focus on Payment Card Industry Data Security Standard (PCI DSS)

Firewalls can also encrypt traffic i., VPN
most firewalls can be layer 3 devices i.e., Routers
which also has a functionality of Network Addr translation (NAT)
Authenticate Dynamic Routing Communication


What's the difference between a **stateful** and **stateless** (packet filtering) firewall?

**Stateless (packet filtering):**  
Checks each packet individually — source IP, destination IP, port, protocol. No memory of previous packets. Simple and fast but easy to fool.

**Stateful:**  
Tracks the full connection state. Knows if a packet is part of an established session or a new/suspicious one. Much smarter — can block packets that look valid but don't belong to any known connection.

**SOC angle:** Stateless = easier to bypass. Stateful = baseline expectation on modern networks.

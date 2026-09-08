
| OSI Layer                                                       | TCP/IP Layer       | Key Protocols                         | Port / Hardware Addresses                                              | Common Usage / Purpose                                                                       | Protocol Data Unit(PDU) |
| --------------------------------------------------------------- | ------------------ | ------------------------------------- | ---------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- | ----------------------- |
| **7. Application**  <br>**6. Presentation**  <br>**5. Session** | **Application**    | HTTP, HTTPS, FTP, SMTP, DNS, DHCP     | HTTP (80), HTTPS (443), FTP (20/21), SMTP (25), DNS (53), DHCP (67/68) | Interacts directly with software applications. Handles formatting, encryption, and sessions. | Data                    |
| **4. Transport**                                                | **Transport**      | TCP, UDP                              | _Uses Port Numbers_                                                    | Ensures reliable data transfer and flow control between hosts.                               | Segments                |
| **3. Network**                                                  | **Internet**       | IP (IPv4/IPv6), ICMP                  | _Uses IP Addresses_  (Router's)                                        | Handles logical addressing and routing packets across networks.                              | Packets                 |
| **2. Data Link**                                                | **Network Access** | Ethernet, Wi-Fi (802.11), PPP, Switch | _Uses MAC Addresses_ (NIC's)                                           | Groups data into frames. Handles physical addressing and error detection.                    | Frames                  |
| **1. Physical**                                                 | **Network Access** | Cables (Cat6, Fiber), Hubs, Repeaters | _No addresses (Uses Bits/Signals)_                                     | Transmits raw binary data over physical wires, fiber optics, or radio waves.                 | BITS                    |



![[tcp-ip vs osi.jpg]]


**Hardware and Devices by Layer**

```
[ Transport Layer ] --------> HOSTS (PC, Server, Smartphone)
       │                      (Handles end-to-end software connection)
       ▼
[ Network Layer ] ----------> ROUTER (or Layer 3 Switch)
       │                      (Moves data between different networks)
       ▼
[ Data Link Layer ] --------> SWITCH / NIC / Bridge
       │                      (Moves data within the local network)
       ▼
[ Physical Layer ] ---------> HUB / Repeater / Cables
                              (Moves raw electrical or light signals)
```


**SOC angle** — e.g. "Firewalls operate at Layer 4 (stateless) or Layer 7 (NGFW). IDS/IPS sits at Layer 3–7 depending on type."
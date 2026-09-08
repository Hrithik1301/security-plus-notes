
- **A port is a logical number (0–65535) that identifies a specific service or process on a host.** It exists so that multiple services can run on the same IP address simultaneously — the OS uses the port number to know which application gets the incoming traffic, a port is not just a "communication medium"
- Example: IP gets you to the machine, port 80 gets you to the web server on that machine.


**Ports & Protocols — key ones to know:**

| Port | Protocol | Use                    |
| ---- | -------- | ---------------------- |
| 22   | SSH      | Secure remote access   |
| 23   | Telnet   | Insecure remote access |
| 25   | SMTP     | Email sending          |
| 53   | DNS      | Name resolution        |
| 80   | HTTP     | Web (unencrypted)      |
| 443  | HTTPS    | Web (encrypted)        |
| 3389 | RDP      | Windows remote desktop |

**FTP (File Transfer protocol) 

Transfers files between systems, not specific to os
tcp/20 ---> active mode data
tcp/21 ---> control
authenticates with username & password
encrypted network communication for file transfer happens on tcp/22 which uses ssh ftp


**SSH (Secure Shell)**

tcp/22 ---> encrypted communication link i.e., console to a remote device
text based console-communication
- SSH on a non-standard port (like 2222) is a red flag because attackers often move services to unusual ports to **evade firewall rules or detection tools** that only watch port 22. It could also mean someone set up an unauthorized backdoor.
- Rule of thumb: **unexpected port = investigate why.**


**Telnet (Telecommunication Network)*

tcp/23
Non-encrypted form of console communication
similar to ssh, but without encryption, so the communication channel runs data in plain text even the usernames and passwords, so anyone can see it/steal it


**SMTP (Simple Mail Transfer Protocol)**

server to server Email Transfer
tcp/25 ---> SMTP using plain text
tcp/587 ---> SMTP using TLS encryption
also used to send email from a device to a mail server
other protocols are used for clients to receive emails like POP3 & IMAP


**DNS (Domain Name System)**

converts domain name to IP addr's ---> udp/53
**Why UDP?** DNS queries are tiny and speed matters more than reliability. No need for a full TCP handshake just to resolve a domain name.

(Side note: DNS uses TCP/53 for large responses like zone transfers — worth knowing for Security+.)


**DHCP (Dynamic Host Configuration Protocol)**

Automatic configuration of IP addr, Subnet mask & other options
udp/67 & udp/68
to use DHCP we need to have a DHCP server
server, appliance, integrated into a SOHO router
IP Addr's are assigned in real time from a pool
Addr's are assigned by MAC addr in the DHCP server


**TFTP (Trivial File Transfer Protocol)**

udp/69
very simple file transfer application, NO authentication
useful when starting a system to transfer config files etc


**HTTP & HTTPS** **(HyperText Transfer Protocol)**

communication in the browser
HTTP ---> tcp/80 ---> Web - server communication
HTTPS ---> tcp/443 ---> Web - server communication with Encryption
HTTPS uses either ssl (Secure sockets layer)(old version) / tls(Transport layer security) (new version)


**NTP (Network Time Protocol)**

Switches, Routers, Firewalls, Workstations, Servers
Every device has its own clock
Synchronization of clock becomes critical (log files, authentication info, outage details)
very accurate & flexible


**SNMP (Simple Network Management Protocol)**

udp/161 ---> Gather statistics from network devices


**LDAP/LDAPS (Lightweight Directory Access Protocol / Secure)**

LDAP ---> tcp/389 ---> Store & retrieve info. in a network directory
LDAPS ---> tcp/636 ---> a non-standard implementation of LDAP over ssl


**SYSlog**

udp/514 ---> Standard for message logging (Diverse system, consolidated log)
usually a central log collector 
integrated into security info & event management (SIEM)


**RDP (Remote Desktop Protocol)**

tcp/3389 ---> Share a desktop from a remote location
connect to an entire desktop or just an application
os independent


**SIP (Session Initiation Protocol)**

Voice over IP-Signaling (VoIP)
tcp/5060 & tcp/5061
setup & manage VoIP Sessions
Extend voice communication to video conferencing, file transfer, instant messaging etc


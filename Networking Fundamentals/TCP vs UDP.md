**What it is:** tcp (transmission control protocol) uses 3 way hand-shake for connection establishment, and data is shared after the connection is established, most reliable where as udp(user datagram protocol) directly sends data without connection establishment (i., connectionless), not reliable but fast

**How it works:** TCP - 3-way Handshake
UDP : Directly shoots data packets to a target instead of connection establishment like TCP

**Why it matters (SOC angle):** 
- SYN flood attack = attacker sends thousands of SYN packets, never completes handshake → exhausts server resources (DoS)
- Half-open connections in logs = sign of a SYN scan (Nmap default)
- UDP used in amplification DDoS attacks (DNS, NTP amplification)

**My confusion / gap:** 3-way Handshake = **seq numbers + ACK only.** Ports are already known before the handshake starts.

**Example:** TCP : web browsing (HTTP/HTTPS), email, file transfers, SSH
UDP : Gaming, Video calls, phone calls, streaming

3 Way Handshake : 

client  sends SYN packet with seq no. to server
server sends SYN + ACK packets to client
Client sends ACK packet to server 
connection established
data transfer

NOTE : 
SYN - Synchronization packet
ACK - Acknowledgement packet

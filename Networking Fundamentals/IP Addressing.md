
**What it is:** IP addresses are used to uniquely identify devices on a network

Every IP addr is 32 bits with 4 octets(8 bits in each octet)

**How it works:** there are two types of classifying the IP Addr's
1. classfull 
2. classless Inter domain routing (CIDR) 

Classfull

here we have 5 classes of networks namely A, B, C, D, E

Class A (1 - 126)  
2^31 ip addr's in total 
1st octet starts with 0
8 bits network ID part & 24 bits host ID part
total 2^7 networks & 2^24 IP Addr's possible in each network
configurable hosts in each network 2^24 - 2


Class B (128 - 191)
2^30 ip addr's in total 
1st octet starts with 10
16 bits network ID part & 16 bits host ID part
total 2^14 networks & 2^16 IP Addr's possible in each network
configurable hosts in each network 2^16 - 2



Class C (192 - 223)
2^29 ip addr's in total 
1st octet starts with 110
24 bits network ID part & 8 bits host ID part
total 2^21 networks & 2^8 IP Addr's possible in each network
configurable hosts in each network 2^8 - 2



Class D  (224–239)
2^28 ip addr's in total 
1st octet starts with 1110
Used for multicasting

Class E  (240 - 255)
2^28 ip addr's in total 
1st octet starts with 1111
Reserved

Class D & E do not have nid and hid part

NOTE : we do not assign 1st & last ip addr for configuring a host, bcos we use the first ip addr as the Network ID & the last IP addr as the Directed broadcast Addr 


- Private IP ranges: 10.x.x.x, 172.16–31.x.x, 192.168.x.x
- Loopback address: 127.0.0.1
- APIPA range: 169.254.x.x (appears when DHCP fails — common SOC log entry)


CIDR

there is no flexibility in the no. of ip's we can choose in classfull classification, i.e., we cannot customize the no. of ip addr's we want in classfull classification, but in CIDR we can choose the no. of IP Addr's we want but there are a few limitations as follows 
1. the IP Addr's must be continuous
2. the no. of IP Addr's must be a power of 2 i.e., 2^n
3. First IP Addr in the block must be evenly divisible by the size of the block

Example : 

100.1.2.32
100.1.2.33
........
.......
100.1.2.47

is this block a CIDR block ?

1. since the ip addr's are continuous i.e., 32, 33, 34, ........ 47 the first condition satisfies
2.  32, 33, ......47 are nothing but 16 IP Addr's which is 2^4 = 16, i.e., 2^n rule is also satisfied
3. first IP Addr must be evenly divisible by the size of the block i.e., 100.1.2.32 which is nothing but 100.1.2.0010**0000**  and the size of the block is 2^n = 2^4, so the least significant 4 bits of the 1st ip must be zero, which also satisfies. 
so, as all the 3 conditions are satisfied the given block is a CIDR block

NOTE : a CIDR block is represented as follows
100.1.2.40 / 20
where 100.1.2.40 can be any ip addr from the cidr block and 20 is the no of bits in the Netwrok ID part and Host ID part no.of bits is calculated by HID = 32-NID, wiz, HID = 32-20= 12 is the no. of bits in the HID part in the CIDR block


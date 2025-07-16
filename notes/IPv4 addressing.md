When working with IPv4 addresses, writing out subnet masks in dotted decimal form (like 255.255.255.0) can be long and repetitive. To make this easier, there is an alternative called the prefix length.

🌟 What is a Prefix Length?
The prefix length tells us how many bits in the subnet mask are set to 1. It is written using slash notation, which means placing a forward slash / after the IPv4 address, followed by the number of 1 bits.

For example:

A subnet mask of 255.255.255.0 in binary is:

Copy
Edit
11111111.11111111.11111111.00000000
Here, there are 24 bits set to 1.

So instead of writing 192.168.10.10 255.255.255.0, you write:

Copy
Edit
192.168.10.10/24
This shorthand makes it quicker to represent both the IP address and its subnet mask.

📌 Why is it Called a Prefix?
In networking, the part of the address covered by the 1s in the subnet mask is called the network prefix. It identifies the network portion of the IP address, while the remaining 0s represent the host portion (specific devices in that network).

So, the prefix length simply indicates how much of the address is reserved for the network.

📊 Example Table: Subnet Masks and Prefix Lengths
Subnet Mask	Binary Representation	Prefix Length
255.0.0.0	11111111.00000000.00000000.00000000	/8
255.255.0.0	11111111.11111111.00000000.00000000	/16
255.255.255.0	11111111.11111111.11111111.00000000	/24
255.255.255.128	11111111.11111111.11111111.10000000	/25
255.255.255.252	11111111.11111111.11111111.11111100	/30

This table shows how subnet masks can be written more compactly using prefix length.

✅ Key Takeaways:

The prefix length is the number of 1 bits in the subnet mask.

It uses slash notation (e.g., /24 for 255.255.255.0).

It simplifies how we write IP addresses and subnet information.

✅ Logical AND in Networking (Explained Clearly)
The logical AND is one of the three basic Boolean operations (the others are OR and NOT). In digital logic:

1 = True

0 = False

AND only gives 1 (True) when both inputs are 1.

Input A	Input B	A AND B
1	1	1
1	0	0
0	1	0
0	0	0

So: both bits must be 1 for the result to be 1.

📌 Why is AND Used in IPv4?
To find the network address of a host, the host’s IPv4 address is ANDed bit by bit with its subnet mask.

This process determines:

The network portion of the address (bits where the subnet mask has 1s).

Sets the host portion to 0 (bits where the subnet mask has 0s).

📝 Example: Find the Network Address
Host IPv4 Address: 192.168.10.10
Subnet Mask: 255.255.255.0 (/24)

Step 1: Convert both to binary

Address	Binary Representation
192.168.10.10	11000000.10101000.00001010.00001010
255.255.255.0	11111111.11111111.11111111.00000000

Step 2: Perform bitwise AND

Copy
Edit
11000000.10101000.00001010.00001010 (Host Address)
AND
11111111.11111111.11111111.00000000 (Subnet Mask)
=
11000000.10101000.00001010.00000000 (Network Address)
Step 3: Convert result back to decimal
Result:

scss
Copy
Edit
192.168.10.0 (/24)
This is the network address for the host.

🌟 Key Takeaways
✔ Logical AND finds the network portion of an IPv4 address.
✔ Only 1 AND 1 gives 1; any other combination gives 0.
✔ ANDing host address with subnet mask zeros out the host bits, leaving only the network bits.
✔ Example:
192.168.10.10 AND 255.255.255.0 = 192.168.10.0
This tells the host it belongs to the 192.168.10.0/24 network.


✅ IPv4 Transmission Types: Unicast, Broadcast, Multicast
📌 1. Unicast – One-to-One Communication
Definition: Unicast is when one device sends a packet directly to one specific device.

Destination IP: A unique unicast address for a single recipient.

Source IP: Always unicast since it comes from one device.

Address Range: IPv4 unicast addresses are 1.0.0.1 to 223.255.255.255 (excluding special/reserved addresses).

Example:

Host 172.16.4.1 sends a packet to printer 172.16.4.253.

Switch forwards the packet directly to 172.16.4.253.

💡 All IPv4 communications in this course are unicast unless stated otherwise.

📌 2. Broadcast – One-to-All Communication
Definition: Broadcast sends a packet to all devices in the same network.

Destination IP: All 1s in host bits. Two types:

Limited Broadcast: 255.255.255.255 – sent to all hosts in the local network (not forwarded by routers).

Directed Broadcast: Highest address in a subnet (e.g., 192.168.1.255 for 192.168.1.0/24) – routers forward it only to the target network.

Example:

Host 172.16.4.1 sends a limited broadcast to 255.255.255.255.

Switch forwards the packet to all connected devices.

⚠️ Broadcasts use network resources heavily since every device must process them.

🔒 Routers block broadcasts by default, and Cisco IOS disables directed broadcasts for security (starting IOS 12.0).

📌 3. Multicast – One-to-Many (Selected) Communication
Definition: Multicast sends a single packet to multiple selected devices that are members of a multicast group.

Destination IP: Reserved multicast range 224.0.0.0 to 239.255.255.255.

How it Works:

Devices subscribe to a multicast group to receive packets addressed to that group.

Other devices ignore the packet.

Example:

Host 172.16.4.1 sends a multicast packet to 224.10.10.5.

Switch forwards the packet, but only group members process it.

📦 Use Case: Protocols like OSPF use multicast (224.0.0.5) so only OSPF-enabled routers process the packets.

🌟 Key Takeaways
Transmission	Destination	Sent To
Unicast	Single IP Address	One specific device
Broadcast	All 1s in host bits	All devices in the broadcast domain
Multicast	224.0.0.0–239.255…	Only subscribed multicast clients

Unicast = One-to-One

Broadcast = One-to-All

Multicast = One-to-Many (Selected)




📌 Public IPv4 Addresses
Definition: Public IPv4 addresses are globally unique and routable on the Internet.

They are assigned by ISPs and used for devices that need direct access to the internet.

Example: A website’s server or an ISP router uses public IPv4 addresses.

📌 Private IPv4 Addresses
Definition: Private IPv4 addresses are not routable on the Internet.

They are meant for use inside private networks (like homes, offices, or organizations).

Devices with private addresses communicate internally and use NAT (Network Address Translation) to access the Internet through a public IP.

🌟 Why Private Addresses Were Introduced
In the mid-1990s, rapid growth of the Internet caused IPv4 address exhaustion.

RFC 1918 defined private address blocks to conserve public IPv4 space.

Private addresses are not unique globally; any organization can use them internally.

💡 Long-term solution to IPv4 depletion: the adoption of IPv6.

📊 Private IPv4 Address Ranges (RFC 1918)
Private Block	Address Range	Subnet Mask
Class A	10.0.0.0 – 10.255.255.255	255.0.0.0 (/8)
Class B	172.16.0.0 – 172.31.255.255	255.240.0.0 (/12)
Class C	192.168.0.0 – 192.168.255.255	255.255.0.0 (/16)

🌟 Key Points
✅ Public addresses are globally routable; private addresses are for internal use only.

✅ Private addresses must use NAT to reach the Internet.

✅ Defined in RFC 1918 (often called “RFC 1918 address space”).

✅ IPv6 was designed as the long-term fix for IPv4 exhaustion.


Private IPv4 Addresses and NAT (Network Address Translation)
📌 Why Private IPv4 Addresses Need NAT
Private IPv4 addresses (like 10.0.0.0/8, 172.16.0.0/12, and 192.168.0.0/16) are not globally routable.

When a device on a private network sends a packet to the Internet:

The source IP is private.

The destination IP is public.

Routers and ISPs cannot forward packets with private source IPs. They must first be translated to public IPs using NAT.

🌟 What is NAT?
Network Address Translation (NAT) translates private IPv4 addresses into public IPv4 addresses.

This allows multiple devices in a private network (intranet) to share a single or a few public IPv4 addresses for Internet access.

NAT is usually done on the router connecting the internal network to the ISP.

📊 Example Scenario
Network 1 (10.0.0.0/8), Network 2 (172.16.0.0/16), and Network 3 (192.168.0.0/24) send packets to the Internet.

Each packet’s private source IP (e.g., 10.0.0.5) is translated by the ISP router into a public IP before forwarding.

The reverse happens for incoming traffic—public IPs are translated back to private IPs.

🔥 Special Case: DMZ (Demilitarized Zone)
DMZ is a part of the network where resources like web servers are placed.

Devices in the DMZ use public IPv4 addresses so they’re accessible from the Internet.

The router connecting the Intranet, DMZ, and Internet acts as:

A NAT device (for translating private IPs).

A firewall (for security, controlling traffic between zones).

⚠️ Important Notes
Private IPv4 addresses cannot be accessed directly from the Internet.

NAT does not provide security by itself. The IETF considers it a workaround for IPv4 exhaustion, not a security feature.

For educational labs, private IPv4 addresses are often used to avoid interfering with real-world public IPs.

✅ Special Use IPv4 Addresses
IPv4 includes addresses reserved for specific purposes, some of which cannot be assigned to hosts, and others that are assigned but with restrictions.

📌 1. Loopback Addresses (127.0.0.0/8)
Range: 127.0.0.1 to 127.255.255.254 (commonly known as 127.0.0.1).

Purpose: Used by a device to send traffic to itself for testing TCP/IP configuration.

Example:

ping 127.0.0.1 verifies that TCP/IP is working on the local machine.

Any address in 127.0.0.0/8 loops back to the local host.

📝 These addresses never appear on the network—they are handled internally by the host.

📌 2. Link-Local Addresses (169.254.0.0/16)
Range: 169.254.0.1 to 169.254.255.254

Purpose: Assigned automatically when a device fails to get an IP from a DHCP server (APIPA in Windows).

Usage: Limited to local communication between devices (peer-to-peer).

📝 Not routable and not commonly used beyond self-assignment.

✅ Legacy Classful Addressing (RFC 790)
📌 Classful IPv4 Ranges
Class	Range	Prefix	Hosts per Network	Purpose
A	0.0.0.0 – 127.255.255.255	/8	~16.7 million	Very large networks
B	128.0.0.0 – 191.255.255.255	/16	~65,000	Medium networks
C	192.0.0.0 – 223.255.255.255	/24	254	Small networks
D	224.0.0.0 – 239.255.255.255	N/A	Multicast only	Multicast groups
E	240.0.0.0 – 255.255.255.255	N/A	Experimental use	Research/Experimental

📌 Problems with Classful Addressing
Class A and B networks had too many unused addresses.

Led to inefficient use of IPv4 space.

💡 Solution: In the mid-1990s, classful addressing was replaced with Classless Inter-Domain Routing (CIDR), which allocates addresses based on need, ignoring rigid class boundaries.

✅ Assignment of IP Addresses
📌 Public IPv4 Addresses
Globally unique and routable on the Internet.

Managed and allocated by:
IANA (Internet Assigned Numbers Authority) → Regional Internet Registries (RIRs) → ISPs → Organizations.

📌 Regional Internet Registries (RIRs)
RIR	Region Covered
AfriNIC	Africa
APNIC	Asia/Pacific
ARIN	North America
LACNIC	Latin America & some Caribbean Islands
RIPE NCC	Europe, Middle East, Central Asia

Organizations can request IP addresses from their RIR or get them from their ISP.

🌟 Key Takeaways
✔ Loopback: For self-testing (127.0.0.1).
✔ Link-Local: Self-assigned if no DHCP (169.254.x.x).
✔ Classful Addressing: Obsolete, replaced by CIDR.
✔ Public IPs: Unique and managed globally by IANA → RIRs → ISPs.


To accomplish end-to-end communications across network boundaries, network layer protocols perform four basic operations:

Addressing end devices - End devices must be configured with a unique IP address for identification on the network.
Encapsulation - The network layer encapsulates the protocol data unit (PDU) from the transport layer into a packet. The encapsulation process adds IP header information, such as the IP address of the source (sending) and destination (receiving) hosts. The encapsulation process is performed by the source of the IP packet.
Routing - The network layer provides services to direct the packets to a destination host on another network. To travel to other networks, the packet must be processed by a router. The role of the router is to select the best path and direct packets toward the destination host in a process known as routing. A packet may cross many routers before reaching the destination host. Each router a packet crosses to reach the destination host is called a hop.
De-encapsulation - When the packet arrives at the network layer of the destination host, the host checks the IP header of the packet. If the destination IP address within the header matches its own IP address, the IP header is removed from the packet. After the packet is de-encapsulated by the network layer, the resulting Layer 4 PDU is passed up to the appropriate service at the transport layer. The de-encapsulation process is performed by the destination host of the IP packet.



IP ENCAPSULATION
The IP header is examined by Layer 3 devices (i.e., routers and Layer 3 switches) as it travels across a network to its destination. It is important to note, that the IP addressing information remains the same from the time the packet leaves the source host until it arrives at the destination host, except when translated by the device performing Network Address Translation (NAT) for IPv4.

These are the basic characteristics of IP:

Connectionless - There is no connection with the destination established before sending data packets.
Best Effort - IP is inherently unreliable because packet delivery is not guaranteed.
Media Independent - Operation is independent of the medium (i.e., copper, fiber-optic, or wireless) carrying the data.

IP HEADER FIELDS
✅ Version – 4 bits set to 0100 to identify IPv4.
✅ Differentiated Services (DS) – 8 bits for packet priority; includes DSCP (6 bits) and ECN (2 bits).
✅ Time to Live (TTL) – 8 bits to limit packet lifetime; decremented by routers. If it reaches 0, the packet is dropped and an ICMP error is sent.
✅ Protocol – 8 bits indicating payload type (e.g., ICMP=1, TCP=6, UDP=17).
✅ Header Checksum – Detects errors in the IPv4 header.
✅ Source IPv4 Address – 32 bits specifying the sender’s IP (unicast).
✅ Destination IPv4 Address – 32 bits specifying the recipient’s IP (unicast, multicast, or broadcast).

LIMITATIONS OF IPv4
✅ IPv4 address depletion – The ~4 billion IPv4 addresses are not enough for the growing number of devices, always-on connections, and global internet expansion.

✅ Lack of end-to-end connectivity – NAT allows multiple devices to share one public IPv4 address, but it hides internal IPs, which breaks direct end-to-end communication needed by some technologies.

✅ Increased network complexity – NAT prolongs IPv4’s use but adds complexity, latency, and makes troubleshooting harder.


improvements that IPv6 provides include the following:

Increased address space - IPv6 addresses are based on 128-bit hierarchical addressing as opposed to IPv4 with 32 bits.
Improved packet handling - The IPv6 header has been simplified with fewer fields.
Eliminates the need for NAT - With such a large number of public IPv6 addresses, NAT between a private IPv4 address and a public IPv4 is not needed. This avoids some of the NAT-induced problems experienced by applications that require end-to-end connectivity.

IPv6 header field

✅ Version – 4 bits set to 0110 to identify IPv6.
✅ Traffic Class – 8 bits, same as IPv4 Differentiated Services (DS) field.
✅ Flow Label – 20 bits to mark packets for special router handling.
✅ Payload Length – 16 bits indicating the size of the payload (not the 40-byte IPv6 header).
✅ Next Header – 8 bits, same as IPv4 Protocol field; identifies the upper-layer protocol.
✅ Hop Limit – 8 bits replacing IPv4 TTL; decremented at each router, no header checksum needed.
✅ Source IPv6 Address – 128 bits identifying the sender.
✅ Destination IPv6 Address – 128 bits identifying the receiver.

HOST FORWARDING DECISION
✅ Packets are created at the source host, which uses its own routing table to direct packets to the destination.

✅ The network layer directs packets to:

Itself – Uses loopback address (127.0.0.1 for IPv4, ::1 for IPv6) to test the TCP/IP stack.

Local host – Destination is on the same network (same network address).

Remote host – Destination is on a different network (different network address).

✅ The source device decides if a destination is local or remote:

IPv4 – Uses its IP address, subnet mask, and the destination IP.

IPv6 – Relies on the local router to advertise the network prefix.

✅ Local hosts (same network) communicate directly via a switch or WAP without needing a router.

✅ Remote hosts (different network) require routing. The packet is sent to the default gateway (router) to find the best path to the destination.

DEFAULT GATEWAY
On a network, a default gateway is usually a router with these features:

It has a local IP address in the same address range as other hosts on the local network.
It can accept data into the local network and forward data out of the local network.
It routes traffic to other networks.


HOST ROUTING TABLES
On a Windows host, the route print or netstat -r command can be used to display the host routing table. Both commands generate the same output. The output may seem overwhelming at first, but is fairly simple to understand.

The figure displays a sample topology and the output generated by the netstat -r command.


ROUTER PACKET FORWARDING DECISION
✅ Hosts and routers both use routing tables to decide where to send packets.

✅ If a host sends a packet to a remote network, it forwards it to the default gateway (usually a router).

✅ When a router receives a packet:

It checks the destination IP address.

Searches its routing table for the best (longest match) route.

Forwards the packet to the next hop or destination based on that route entry.


✅ A router’s routing table lists all known network destinations and contains three types of entries:

Directly-connected networks – Networks directly attached to the router’s active interfaces (e.g., 192.168.10.0/24).

Remote networks – Networks learned from other routers via manual configuration or dynamic routing protocols (e.g., 10.1.1.0/24).

Default route – A gateway of last resort used when no specific route matches the destination.
STATIC ROUTING
✅ Static routes are manually configured entries in a router’s routing table.

✅ Example: On R1, a static route to reach network 10.1.1.0/24 via R2 is set using:




R1(config)# ip route 10.1.1.0 255.255.255.0 209.165.200.226
10.1.1.0 255.255.255.0 = remote network

209.165.200.226 = next hop router’s IP

✅ Limitation: Static routes do not adjust automatically to topology changes. If the path to 10.1.1.0/24 via R2 fails, R1 must be reconfigured to use an alternative path (e.g., via R3).

DYNAMIC ROUTING
✅ Dynamic routing protocols allow routers to:

Automatically learn about remote networks (including default routes).

Share routing information with other routers.

Adjust to topology changes without manual reconfiguration.

✅ Example:

R1 and R2 use OSPF to exchange information about their connected networks.

If the link between R1 and R2 fails, OSPF automatically finds a new best path through R3.

✅ Features of dynamic routing protocols:

Discover remote networks.

Keep routing tables up to date.

Select the best path to destinations.

Automatically reroute traffic if paths fail.

✅ Common protocols: OSPF, EIGRP.

✅ Note: Networks often use a mix of static routes and dynamic routing for flexibility.


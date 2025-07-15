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
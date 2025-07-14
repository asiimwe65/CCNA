Ethernet operates in the data link layer and the physical layer. It is a family of networking technologies defined in the IEEE 802.2 and 802.3 standards. Ethernet supports data bandwidths of the following:

10 Mbps
100 Mbps
1000 Mbps (1 Gbps)
10,000 Mbps (10 Gbps)
40,000 Mbps (40 Gbps)
100,000 Mbps (100 Gbps)

Ethernet is defined by data link layer and physical layer protocols.
Ethernet uses the data link subayers as well.

ny frame less than 64 bytes in length is considered a “collision fragment” or “runt frame” and is automatically discarded by receiving stations. Frames with more than 1500 bytes of data are considered “jumbo” or “baby giant frames”.

If the size of a transmitted frame is less than the minimum, or greater than the maximum, the receiving device drops the frame. Dropped frames are likely to be the result of collisions or other unwanted signals. They are considered invalid. Jumbo frames are usually supported by most Fast Ethernet and Gigabit Ethernet switches and NICs.


ETHERNET FRAME FIELDS
Start Frame: used for synchronization and btn sending and receiving of messages./ to get attention of the receiving nodes.
Destination MAC address field : It is used to determine if a frame is addressed to them and if it is matching.
Source MAC address field : identifies the originating NIC or interface of the frame.
TYPE/LENGTH: identifies the upper layer protocols encapsulated in the frame.
Data field: contains the encapsulated data from from the higher layers. All  frames must be 64 bits long. If it is too small additional bits are added called a pad.
FRAME CHECK: This one id used to check  for errors in the sequence check.



MAC ADDRESS AND HEXADECIMAL
An Ethernet MAC address consists of a 48-bit binary value. Hexadecimal is used to identify an Ethernet address because a single hexadecimal digit represents four binary bits. Therefore, a 48-bit Ethernet MAC address can be expressed using only 12 hexadecimal values.
When using hexadecimal, leading zeroes are always displayed to complete the 8-bit representation. For example, the binary value 0000 1010 is shown in hexadecimal as 0A.
You may have to convert between decimal and hexadecimal values. If such conversions are required, convert the decimal or hexadecimal value to binary, and then to convert the binary value to either decimal or hexadecimal as appropriate.

In an Ethernet LAN, every network device is connected to the same, shared media. The MAC address is used to identify the physical source and destination devices (NICs) on the local network segment
MAC addressing provides a method for device identification at the data link layer of the OSI model.

All MAC addresses must be unique to the Ethernet device or Ethernet interface. To ensure this, all vendors that sell Ethernet devices must register with the IEEE to obtain a unique 6 hexadecimal (i.e., 24-bit or 3-byte) code called the organizationally unique identifier (OUI).

When a vendor assigns a MAC address to a device or Ethernet interface, the vendor must do as follows:

Use its assigned OUI as the first 6 hexadecimal digits.
Assign a unique value in the last 6 hexadecimal digits.

lt is the responsibility of the vendor to ensure that none of its devices be assigned the same MAC address. However, it is possible for duplicate MAC addresses to exist because of mistakes made during manufacturing, mistakes made in some virtual machine implementation methods, or modifications made using one of several software tools. In any case, it will be necessary to modify the MAC address with a new NIC or make modifications via software.

Frame Processing
Sometimes the MAC address is referred to as a burned-in address (BIA) because the address is hard coded into read-only memory (ROM) on the NIC. This means that the address is encoded into the ROM chip permanently.

Note: On modern PC operating systems and NICs, it is possible to change the MAC address in software. This is useful when attempting to gain access to a network that filters based on BIA. Consequently, filtering or controlling traffic based on the MAC address is no longer as secure.

When the computer boots up, the NIC copies its MAC address from ROM into RAM. When a device is forwarding a message to an Ethernet network, the Ethernet header includes these:

Source MAC address - This is the MAC address of the source device NIC.
Destination MAC address - This is the MAC address of the destination device NIC.
Note: Ethernet NICs will also accept frames if the destination MAC address is a broadcast or a multicast group of which the host is a member.


UNICAST MAC ADDRESS
 For a unicast packet to be sent and received, a destination IP address must be in the IP packet header. A corresponding destination MAC address must also be present in the Ethernet frame header. The IP address and MAC address combine to deliver data to one specific destination host.

 The process that a source host uses to determine the destination MAC address associated with an IPv4 address is known as Address Resolution Protocol (ARP). 

 The process that a source host uses to determine the destination MAC address associated with an IPv6 address is known as Neighbor Discovery (ND).

BROADCAST MAC ADDRESS

 An Ethernet broadcast frame is received and processed by every device on the Ethernet LAN. The features of an Ethernet broadcast are as follows:

It has a destination MAC address of FF-FF-FF-FF-FF-FF in hexadecimal (48 ones in binary).
It is flooded out all Ethernet switch ports except the incoming port.
It is not forwarded by a router.

If the encapsulated data is an IPv4 broadcast packet, this means the packet contains a destination IPv4 address that has all ones (1s) in the host portion. This numbering in the address means that all hosts on that local network (broadcast domain) will receive and process the packet.

 the source host sends an IPv4 broadcast packet to all devices on its network. The IPv4 destination address is a broadcast address, 192.168.1.255. When the IPv4 broadcast packet is encapsulated in the Ethernet frame, the destination MAC address is the broadcast MAC address of FF-FF-FF-FF-FF-FF in hexadecimal (48 ones in binary).

DHCP for IPv4 is an example of a protocol that uses Ethernet and IPv4 broadcast addresses.

MULTICAST MAC ADDRESS 
The features of an Ethernet multicast are as follows:

There is a destination MAC address of 01-00-5E when the encapsulated data is an IPv4 multicast packet and a destination MAC address of 33-33 when the encapsulated data is an IPv6 multicast packet.
There are other reserved multicast destination MAC addresses for when the encapsulated data is not IP, such as Spanning Tree Protocol (STP) and Link Layer Discovery Protocol (LLDP).
It is flooded out all Ethernet switch ports except the incoming port, unless the switch is configured for multicast snooping.
It is not forwarded by a router, unless the router is configured to route multicast packets.

The range of IPv4 multicast addresses is 224.0.0.0 to 239.255.255.255


MAC ADDRESS TABLE
The switch dynamically builds the MAC address table by examining the source MAC address of the frames received on a port. The switch forwards frames by searching for a match between the destination MAC address in the frame and an entry in the MAC address table.

🌟 1. What is an Ethernet Switch?
An Ethernet switch is a device that connects multiple devices (PCs, printers, servers, etc.) on a Local Area Network (LAN) and allows them to communicate efficiently.
It works at Layer 2 (Data Link Layer) of the OSI model and uses MAC addresses to make decisions.

🔥 2. Switch Learning (MAC Address Learning)
When a switch is powered on, its MAC address table (or CAM table) is empty.
Here’s what happens step by step:

📦 Step 1: A frame arrives at the switch

The switch checks the frame’s source MAC address and the port it came from.

📝 Step 2: The switch records this information

It stores the MAC address and associates it with the port in its MAC address table.

Example:

MAC Address	Port
00:11:22:33:44:55	1
AA:BB:CC:DD:EE:FF	3

🎯 Now the switch knows where that device is.

📤 3. Switch Forwarding (Frame Forwarding)
When the switch receives a frame it must deliver:

✅ If the destination MAC address is in the MAC table:

The switch forwards the frame directly to the associated port.
This is called unicast forwarding.
📌 Efficient: Only the target device receives the frame.

❌ If the destination MAC address is NOT in the MAC table:

The switch floods the frame out of all ports except the one it arrived on.
📌 This is because the switch doesn’t yet know where the destination is.

🚀 Frame Forwarding Methods on Cisco Switches
There are three main methods:

1️⃣ Store-and-Forward Switching
✅ How it works:

The switch receives the entire frame, including the trailer (CRC).

It checks for errors using the Cyclic Redundancy Check (CRC).

If the frame has no errors, it forwards it.

If the frame has errors, it discards it.

📌 Key features:

Performs error checking (CRC).

Supports Quality of Service (QoS) because the full frame is available for inspection.

Introduces a small latency since it waits for the whole frame.

🎯 Use case: Default on Cisco switches (modern models).

2️⃣ Cut-Through Switching
✅ How it works:

The switch starts forwarding the frame as soon as it reads the destination MAC address (first 6 bytes of the frame header).

It does not wait for the entire frame or check for errors.

📌 Key features:

Very low latency (ideal for high-speed networks).

No error checking – corrupted frames are forwarded.

Faster but less reliable compared to store-and-forward.

🎯 Use case: Environments where speed is more critical than error checking (like high-performance computing).

3️⃣ Fragment-Free Switching (Modified Cut-Through)
✅ How it works:

The switch waits to read the first 64 bytes of the frame before forwarding.

Why 64 bytes? Because most Ethernet collisions and errors occur in the first 64 bytes.

Helps avoid forwarding frames damaged during collisions.

📌 Key features:

Balances speed and reliability.

Checks for collision fragments but not full CRC.

🎯 Use case: Older Cisco switches or networks prone to collisions.


🧠 What is Memory Buffering in Switching?
When multiple frames arrive at a switch faster than it can process or forward them, they are temporarily stored in memory buffers.

📦 Why?
To avoid dropping frames when:
✅ Incoming traffic exceeds outgoing link speed.
✅ Multiple frames arrive at once for the same destination port.

So buffering gives the switch time to handle congestion.

🔥 Types of Memory Buffering in Switches
There are two main buffering techniques used in Cisco switches:

1️⃣ Port-Based Memory Buffering (Port-Based or Static Buffering)
✅ How it works:

Each port on the switch gets its own dedicated memory buffer.

Frames arriving on a port are stored in that port’s buffer if the outgoing port is busy.

📌 Key Characteristics:

Simple design.

A busy destination port causes frames for that port to wait in each source port’s buffer.

⚠️ Limitation: If a high-speed port sends traffic to a low-speed port, frames can pile up and overflow the source port’s buffer (head-of-line blocking).

2️⃣ Shared Memory Buffering (Dynamic Buffering)
✅ How it works:

All ports share a common memory buffer pool.

Any port can use as much buffer space as needed (depending on traffic load).

Frames are stored in the shared buffer, and the switch keeps track of which frames belong to which ports.

📌 Key Characteristics:

Efficient use of memory—no unused buffer space.

Solves head-of-line blocking problem.

Better for high-performance switches handling bursty traffic.

📘 Summary Table
Feature	                          Port-Based Buffering	                                      Shared Memory Buffering
Memory Allocation	             Fixed per port	                                             Dynamic (shared among ports)
Efficiency	                     Less efficient	                                             More efficient
Head-of-Line Blocking	         Possible	                                                 Reduced/avoided
Complexity	                     Simple	                                                      More complex 
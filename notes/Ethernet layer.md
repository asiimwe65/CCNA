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


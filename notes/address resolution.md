
DESTINATION ON THE SAME NETWORK
✅ When a host knows only the IP address of a destination on the same network, it uses address resolution to find the MAC address of that device.

✅ Devices have:

MAC address (Layer 2) – For NIC-to-NIC communication on the same Ethernet LAN.

IP address (Layer 3) – For identifying devices across networks.

✅ On the same network, the destination MAC address is the MAC of the destination device.

✅ Example: PC1 (192.168.10.10, MAC aa-aa-aa) sends a packet to PC2 (192.168.10.11, MAC 55-55-55):

Ethernet Frame (Layer 2):

Destination MAC: 55-55-55 (PC2)

Source MAC: aa-aa-aa (PC1)

IP Packet (Layer 3):

Source IP: 192.168.10.10

Destination IP: 192.168.10.11
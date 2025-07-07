UTP-unshilded Twisted Pair used in ethernet networks
Ethernet standards are defined in IEEE(in other words protocols and technologies)

SPEED               COMMON-NAME             IEEE-STANDARD       INFORMAL-NAME         MAX-LENGTH
10Mbps               Ethernet               802.3i              10 Base-T               100m
100Mbps             fast-ethernet           802.3u              100 Base-T              100m
1Gbps               Gigabit ethernet        802.3ab             1000 Base-T             100m
10Gbps              10Giga-ethernet                             10GBase-t               100m

.                               UTP CABLES
 NOTE:   we use straight through cables when we are connecting that are not the same and cross over cables when you are connecting
devices that are the same.

Examples of devices and their connecting points(pins or ports)
             receive                     transmit
PC            3&6                         1&2
FIREWALL      3&6                         1&2
ROUTER        3&6                         1&2
SWITCH        1&2                         3&6

Auto-MDIX feature is a modern one that is used to detect data and enable switching for receiving and transmitting of data.
(1000BASE-T AND 10GBASE-T)- these cables are bi-directional (can receive and transmit data)

.                             FIBER CABLES
The fiber glass core : To send and receive data
The cladding core    : To reflect light
The outer jacket     : To protect the cable

<   
the fiber cables send and transmit data in this format
>
 The fiber cables are in multimode and singlemode.  The multimode has a wider glass core than the singlemode.
 The singlemode allows connection to further distances than the multimode.
 

  Dispersion refers to the spreading out of a light pulse over time. Increased dispersion means increased loss of signal strength. MMF has a greater dispersion than SMF. That is why MMF can only travel up to 500 meters before signal loss.
  Some switches and routers have ports that support fiber-optic connectors through a small form-factor pluggable (SFP) transceiver. Search the internet for various types of SFPs.


  WIRELESS MEDIA

  These are the wireless standards:

Wi-Fi (IEEE 802.11) - Wireless LAN (WLAN) technology, commonly referred to as Wi-Fi. WLAN uses a contention-based protocol known as carrier sense multiple access/collision avoidance (CSMA/CA). The wireless NIC must first listen before transmitting to determine if the radio channel is clear. If another wireless device is transmitting, then the NIC must wait until the channel is clear. Wi-Fi is a trademark of the Wi-Fi Alliance. Wi-Fi is used with certified WLAN devices based on the IEEE 802.11 standards.
Bluetooth (IEEE 802.15) - This is a wireless personal area network (WPAN) standard, commonly known as “Bluetooth.” It uses a device pairing process to communicate over distances from 1 to 100 meters.
WiMAX (IEEE 802:16) - Commonly known as Worldwide Interoperability for Microware Access (WiMAX), this wireless standard uses a point-to-multipoint topology to provide wireless broadband access.
Zigbee (IEEE 802.15.4) - Zigbee is a specification used for low-data rate, low-power communications. It is intended for applications that require short-range, low data-rates and long battery life. Zigbee is typically used for industrial and Internet of Things (IoT) environments such as wireless light switches and medical device data collection.
Note: Other wireless technologies such as cellular and satellite communications can also provide data network connectivity. However, these wireless technologies are out of scope for this module.
A common wireless data implementation is enabling devices to connect wirelessly via a LAN. In general, a WLAN requires the following network devices:

Wireless Access Point (AP) - These concentrate the wireless signals from users and connect to the existing copper-based network infrastructure, such as Ethernet. Home and small business wireless routers integrate the functions of a router, switch, and access point into one device, as shown in the figure.
Wireless NIC adapters - These provide wireless communication capability to network hosts.
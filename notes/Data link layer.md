 The data link layer is responsible for network interface card (NIC) to network interface card communications.


THE ROLE OF THE DATA LINK LAYER
 Enables upper layers to access the media. The upper layer protocol is completely unaware of the type of media that is used to forward the data.
Accepts data, usually Layer 3 packets (i.e., IPv4 or IPv6), and encapsulates them into Layer 2 frames.
Controls how data is placed and received on the media.
Exchanges frames between endpoints over the network media.
Receives encapsulated data, usually Layer 3 packets, and directs them to the proper upper-layer protocol.
Performs error detection and rejects any corrupt frame.




a node is a device that can receive, create, store, or forward data along a communications path.

 IEEE 802 LAN/MAN Data Link Sublayers
IEEE 802 LAN/MAN standards are specific to Ethernet LANs, wireless LANs (WLAN), wireless personal area networks (WPAN) and other types of local and metropolitan area networks. The IEEE 802 LAN/MAN data link layer consists of the following two sublayers:

Logical Link Control (LLC) - This IEEE 802.2 sublayer communicates between the networking software at the upper layers and the device hardware at the lower layers. It places information in the frame that identifies which network layer protocol is being used for the frame. This information allows multiple Layer 3 protocols, such as IPv4 and IPv6, to use the same network interface and media.
Media Access Control (MAC) - Implements this sublayer (IEEE 802.3, 802.11, or 802.15) in hardware. It is responsible for data encapsulation and media access control. It provides data link layer addressing and it is integrated with various physical layer technologies.

The MAC sublayer provides data encapsulation:

Frame delimiting - The framing process provides important delimiters to identify fields within a frame. These delimiting bits provide synchronization between the transmitting and receiving nodes.

Addressing - Provides source and destination addressing for transporting the Layer 2 frame between devices on the same shared medium.
Error detection - Includes a trailer used to detect transmission errors.

The MAC sublayer also provides media access control, allowing multiple devices to communicate over a shared (half-duplex) medium. Full-duplex communications do not require access control.


PROVIDING ACCESS TO MEDIA
 a router performs the following Layer 2 functions:

Accepts a frame from a medium
De-encapsulates the frame
Re-encapsulates the packet into a new frame
Forwards the new frame appropriate to the medium of that segment of the physical network

TOPOLOGIES

POINT-TO-POINT
This is the simplest and most common WAN topology. It consists of a permanent link between two endpoints.

HUB AND SPOKE
This is a WAN version of the star topology in which a central site interconnects branch sites through the use of point-to-point links. Branch sites cannot exchange data with other branch sites without going through the central site.

MESH
This topology provides high availability but requires that every end system is interconnected to every other system. Therefore, the administrative and physical costs can be significant. Each link is essentially a point-to-point link to the other node.

Note: A point-to-point connection over Ethernet requires the device to determine if the incoming frame is destined for this node.

LAN TOPOLOGIES
 An extended star extends this topology by interconnecting multiple Ethernet switches. The star and extended topologies are easy to install, very scalable (easy to add and remove end devices), and easy to troubleshoot. Early star topologies interconnected end devices using Ethernet hubs.

 Legacy LAN Topologies

Early Ethernet and legacy Token Ring LAN technologies included two other types of topologies:

Bus - All end systems are chained to each other and terminated in some form on each end. Infrastructure devices such as switches are not required to interconnect the end devices. Legacy Ethernet networks were often bus topologies using coax cables because it was inexpensive and easy to set up.
Ring - End systems are connected to their respective neighbor forming a ring. The ring does not need to be terminated, unlike in the bus topology. Legacy Fiber Distributed Data Interface (FDDI) and Token Ring networks used ring topologies.


Half-duplex communication

Both devices can transmit and receive on the media but cannot do so simultaneously. WLANs and legacy bus topologies with Ethernet hubs use the half-duplex mode. Half-duplex allows only one device to send or receive at a time on the shared medium. 

Full-duplex communication

Both devices can simultaneously transmit and receive on the shared media. The data link layer assumes that the media is available for transmission for both nodes at any time. Ethernet switches operate in full-duplex mode by default, but they can operate in half-duplex if connecting to a device such as an Ethernet hub

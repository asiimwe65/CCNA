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
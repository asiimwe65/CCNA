Protocols must account for the following requirements to successfully deliver a message that is understood by the receiver:

An identified sender and receiver
Common language and grammar
Speed and timing of delivery
Confirmation or acknowledgment requirements


Common computer protocols include the following requirements:

Message encoding
Message formatting and encapsulation
Message size
Message timing
Message delivery options

 Encoding is the process of converting information into another acceptable form, for transmission. Decoding reverses this process to interpret the information

 When a message is sent from source to destination, it must use a specific format or structure. Message formats depend on the type of message and the channel that is used to deliver the message.

  when a long message is sent from one host to another over a network, it is necessary to break the message into smaller pieces

  Message timing is also very important in network communications. Message timing includes the following:

Flow Control - This is the process of managing the rate of data transmission. Flow control defines how much information can be sent and the speed at which it can be delivered. For example, if one person speaks too quickly, it may be difficult for the receiver to hear and understand the message. In network communication, there are network protocols used by the source and destination devices to negotiate and manage the flow of information.
Response Timeout - If a person asks a question and does not hear a response within an acceptable amount of time, the person assumes that no answer is coming and reacts accordingly. The person may repeat the question or instead, may go on with the conversation. Hosts on the network use network protocols that specify how long to wait for responses and what action to take if a response timeout occurs.
Access method - This determines when someone can send a message. Click Play in the figure to see an animation of two people talking at the same time, then a "collision of information" occurs, and it is necessary for the two to back off and start again. Likewise, when a device wants to transmit on a wireless LAN, it is necessary for the WLAN network interface card (NIC) to determine whether the wireless medium is available.
The animation shows a woman and a man speaking at the same time. The woman says What time is the movie? and the man says When are we meeting for dinner?. Because they spoke simultaneously, neither understood the other and they both say Sorry? I did not understand you.


Network

Network communications has similar delivery options to communicate. As shown in the figure, there three types of data communications include:

Unicast - Information is being transmitted to a single end device.
Multicast - Information is being transmitted to a one or more end devices.
Broadcast - Information is being transmitted to all end devices.


Network communication protocols are responsible for a variety of functions necessary for network communications between end devices. For example, in the figure how does the computer send a message, across several network devices, to the server?

functions include addressing flow control, sequencing,reliability and interface plus error detection


Hypertext Transfer Protocol (HTTP) - This protocol governs the way a web server and a web client interact. HTTP defines the content and formatting of the requests and responses that are exchanged between the client and server. Both the client and the web server software implement HTTP as part of the application. HTTP relies on other protocols to govern how the messages are transported between the client and server.
Transmission Control Protocol (TCP) - This protocol manages the individual conversations. TCP is responsible for guaranteeing the reliable delivery of the information and managing flow control between the end devices.
Internet Protocol (IP) - This protocol is responsible for delivering messages from the sender to the receiver. IP is used by routers to forward the messages across multiple networks.
Ethernet- This protocol is responsible for the delivery of messages from one NIC to another NIC on the same Ethernet local area network (LAN).


PROTOCOLS 
A protocol suite is a set of protocols that work together to provide comprehensive network communication services.



Application Layer

Name System

DNS - Domain Name System. Translates domain names such as cisco.com, into IP addresses.
Host Config

DHCPv4 - Dynamic Host Configuration Protocol for IPv4. A DHCPv4 server dynamically assigns IPv4 addressing information to DHCPv4 clients at start-up and allows the addresses to be re-used when no longer needed.
DHCPv6 - Dynamic Host Configuration Protocol for IPv6. DHCPv6 is similar to DHCPv4. A DHCPv6 server dynamically assigns IPv6 addressing information to DHCPv6 clients at start-up.
SLAAC - Stateless Address Autoconfiguration. A method that allows a device to obtain its IPv6 addressing information without using a DHCPv6 server.
Email

SMTP - Simple Mail Transfer Protocol. Enables clients to send email to a mail server and enables servers to send email to other servers.
POP3 - Post Office Protocol version 3. Enables clients to retrieve email from a mail server and download the email to the client's local mail application.
IMAP - Internet Message Access Protocol. Enables clients to access email stored on a mail server as well as maintaining email on the server.
File Transfer

FTP - File Transfer Protocol. Sets the rules that enable a user on one host to access and transfer files to and from another host over a network. FTP is a reliable, connection-oriented, and acknowledged file delivery protocol.
SFTP - SSH File Transfer Protocol. As an extension to Secure Shell (SSH) protocol, SFTP can be used to establish a secure file transfer session in which the file transfer is encrypted. SSH is a method for secure remote login that is typically used for accessing the command line of a device.
TFTP - Trivial File Transfer Protocol. A simple, connectionless file transfer protocol with best-effort, unacknowledged file delivery. It uses less overhead than FTP.
Web and Web Service

HTTP - Hypertext Transfer Protocol. A set of rules for exchanging text, graphic images, sound, video, and other multimedia files on the World Wide Web.
HTTPS - HTTP Secure. A secure form of HTTP that encrypts the data that is exchanged over the World Wide Web.
REST - Representational State Transfer. A web service that uses application programming interfaces (APIs) and HTTP requests to create web applications.


Transport layer

Connection-Oriented

TCP - Transmission Control Protocol. Enables reliable communication between processes running on separate hosts and provides reliable, acknowledged transmissions that confirm successful delivery.
Connectionless

UDP - User Datagram Protocol. Enables a process running on one host to send packets to a process running on another host. However, UDP does not confirm successful datagram transmission.

 INTERNET LAYER
 IPv4: internet protocol version 4. turns segments it packets needed for delivery of messages or data. (32 bits)
 IPv6: 128 bits
 NAT: Network Address Translation. Translates IPv4 address from a private network into globally unique public IPv4 address

 MESSAGING
  ICMPv4-Internet control message protocol for the IPv4. Provides feedback to the source host from destination about any errors
  ICMPv6
  ICMPv6 ND:""Neigbour Discovery [detect address resolution and duplicate address detection]

  ROUTING PROTOCOLS
  OSPF - Open Shortest Path First. Link-state routing protocol that uses a hierarchical design based on areas. OSPF is an open standard interior routing protocol.
EIGRP - EIGRP - Enhanced Interior Gateway Routing Protocol. An open standard routing protocol developed by Cisco that uses a composite metric based on bandwidth, delay, load and reliability.
BGP - Border Gateway Protocol. An open standard exterior gateway routing protocol used between Internet Service Providers (ISPs). BGP is also commonly used between ISPs and their large private clients to exchange routing information.






.STANDARDS 
                  Research Networking Standards
Who is Jonathan B. Postel and what is he known for?
Jonathan B. Postel was an American computer scientist known for his pioneering work on the development of the Internet. He was the editor of the Request for Comments (RFC) series and played a key role in the development of protocols such as TCP/IP and DNS.

Which two related organizations are responsible for managing the top-level domain name space and the root Domain Name System (DNS) name servers on the internet?

ICANN (Internet Corporation for Assigned Names and Numbers)

IANA (Internet Assigned Numbers Authority)

Vinton Cerf has been called one of the main fathers of the internet. What internet organizations did he chair or help found? What internet technologies did he help to develop?
Vinton Cerf co-founded the Internet Society (ISOC) and served as chair of the Internet Architecture Board (IAB). He co-developed the TCP/IP protocols, which form the core of internet communication.

What organization is responsible for publishing Request for Comments (RFC)?
The Internet Engineering Task Force (IETF).

What do RFC 349 and RFC 1700 have in common?
Both are related to assigning and documenting protocol numbers and standards. RFC 1700 was a list of assigned numbers; RFC 349 was an update to that concept and procedure.

What RFC number is the ARPAWOCKY? What is it?
RFC 527. It is a humorous RFC—a parody of Jabberwocky by Lewis Carroll, written in internet jargon.

Who founded the World Wide Web Consortium (W3C)?
Tim Berners-Lee.

Name 10 World Wide Web (WWW) standards that the W3C develops and maintains:

HTML

CSS

XML

SVG

WCAG (Web Content Accessibility Guidelines)

DOM (Document Object Model)

RDF (Resource Description Framework)

SPARQL

SOAP

WebAssembly

Where is the Institute of Electrical and Electronics Engineers (IEEE) headquarters located and what is the significance of its logo?
Located in Piscataway, New Jersey, USA. The logo features a diamond-shaped kite symbol from Benjamin Franklin’s experiments, symbolizing innovation and electrical engineering.

What is the IEEE standard for the Wi-Fi Protected Access 2 (WPA2) security protocol?
IEEE 802.11i

Is the Wi-Fi Alliance a non-profit standards organization? What is their goal?
Yes, it is a non-profit. Its goal is to promote Wi-Fi technology and ensure interoperability and security of wireless networking products through certification.

Who is Hamadoun Touré?
He is a former Secretary-General of the International Telecommunication Union (ITU), serving from 2007 to 2014.

What is the International Telecommunication Union (ITU) and where is it headquartered?
It is a UN specialized agency responsible for issues related to information and communication technologies. Headquarters: Geneva, Switzerland.

Name the three ITU sectors:

ITU-R (Radiocommunication)

ITU-T (Telecommunication Standardization)

ITU-D (Telecommunication Development)

What does the RS in RS-232 stand for and which organization introduced it?
RS stands for Recommended Standard. It was introduced by the Electronic Industries Association (EIA).

What is SpaceWire?
A high-speed communication protocol developed by the European Space Agency (ESA) for use in spaceflight systems.

What is the mission of the ISOC and where are its headquarters located?
ISOC (Internet Society) works to ensure the open development, evolution, and use of the Internet. Headquarters: Reston, Virginia, USA and Geneva, Switzerland.

What organizations does the IAB oversee?
The IETF (Internet Engineering Task Force) and the IRTF (Internet Research Task Force).

What organization oversees the IAB?
The Internet Society (ISOC).

When was the ISO founded and where are its headquarters located?
Founded in 1947. Headquarters: Geneva, Switzerland.

 Reflection on Internet and Networking Experiences
How do the internet standards allow for greater commerce? What potential problems could we have if we did not have the IEEE?
Internet standards ensure interoperability, security, and reliability across global networks—essential for e-commerce, banking, and digital transactions. Without the IEEE, there would be no standardization for physical and wireless network technologies like Ethernet and Wi-Fi, causing compatibility issues and slowed innovation.

What potential problems could we have if we did not have the W3C?
Without the W3C, web development would be inconsistent across platforms and browsers. There would be no unified standards for HTML, CSS, and accessibility, leading to poor user experiences and compatibility issues.

What can we learn from the example of the Wi-Fi Alliance with regard to the necessity of networking standards?
The Wi-Fi Alliance shows the importance of certification and interoperability. With standardized testing and security protocols like WPA2, users can trust that devices from different manufacturers will work reliably together—supporting global connectivity.




Electronic and Communications Standards
Other standards organizations have responsibilities for promoting and creating the electronic and communication standards used to deliver the IP packets as electronic signals over a wired or wireless medium.

These standard organizations include the following:

Institute of Electrical and Electronics Engineers(IEEE, pronounced “I-triple-E”) - Organization of electrical engineering and electronics dedicated to advancing technological innovation and creating standards in a wide area of industries including power and energy, healthcare, telecommunications, and networking. Important IEEE networking standards include 802.3 Ethernet and 802.11 WLAN standard. Search the internet for other IEEE network standards.
Electronic Industries Alliance (EIA) - Organization is best known for its standards relating to electrical wiring, connectors, and the 19-inch racks used to mount networking equipment.
Telecommunications Industry Association (TIA) - Organization responsible for developing communication standards in a variety of areas including radio equipment, cellular towers, Voice over IP (VoIP) devices, satellite communications, and more.
International Telecommunications Union-Telecommunication Standardization Sector (ITU-T) - One of the largest and oldest communication standards organizations. The ITU-T defines standards for video compression, Internet Protocol Television (IPTV), and broadband communications, such as a digital subscriber line (DSL).
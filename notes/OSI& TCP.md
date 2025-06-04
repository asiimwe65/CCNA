Network model provides structure for networking protocols and  standards
OSI- Open Systems  Interconnection Model
.                                 OSI LAYERS
7.Application layer
6.Presentation layer
5.session layer
4.Transport layer
3.Network layer
2.Datalink layer
1.Physical layer

.                                  Application layer
-interacts with software applications

.                                  Presentation LAYER
-Data in application is translated to a different format to be sent over a network.

.                                  Session layer
-Controls sessions or dialogues

.                                  Transport layer(segment)
- Breaks large segments to smaller ones to enable transmission with no issues.
NOTE: From layer 4 downwards each segment is added with a header

.                                    Network layer(packet)
Provides connectivity between end host on different networks(provides IP address)
routers
path selection
.               FROM 4(SEGMENT) TO 3 IT BECOMES A PACKET

.                                    Data link layer(frame)
Node to node connectivity(direct connectivity between PC and switch)
How data is formatted for transmission over a physical medium like copper utp cables
Detects and corrects physical layer errors 

NOTE : ON THIS PART A TRAILER IS ADDED
            
.                                     Physical layer
Defines physical characteristics of the medium used to transfer data between devices eg voltage levels, maximum transmission



encapsulation happens when data moves from 7 to 1 and the opposite is de-encapsulation


.                                  TCP/IP suite
same structure as the OSI but less layers
4.Application
3.Transport
2.Internet(where the ip address is found)
1.Link(encapusation)

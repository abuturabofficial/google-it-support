<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**

- [The Transport Layer](#the-transport-layer)
  - [Dissection of a TCP Segment](#dissection-of-a-tcp-segment)
    - [TCP segment](#tcp-segment)
    - [TCP Header](#tcp-header)
  - [TCP Control Flags and the Three-way Handshake](#tcp-control-flags-and-the-three-way-handshake)
    - [TCP Control Flags](#tcp-control-flags)
    - [The Three-way Handshake](#the-three-way-handshake)
    - [The Four-way Handshake](#the-four-way-handshake)
  - [TCP Socket States](#tcp-socket-states)
    - [Socket](#socket)
    - [Instantiation](#instantiation)
    - [Socket States](#socket-states)
  - [Connection-oriented and Connectionless Protocols](#connection-oriented-and-connectionless-protocols)
    - [Connection-oriented Protocol](#connection-oriented-protocol)
    - [Connectionless Protocol](#connectionless-protocol)
  - [System Ports vs Ephemeral Ports](#system-ports-vs-ephemeral-ports)
  - [Firewalls](#firewalls)
- [The Application Layer](#the-application-layer)
  - [The Application Layer and the OSI Model](#the-application-layer-and-the-osi-model)
    - [Session Layer](#session-layer)
    - [Presentation Layer](#presentation-layer)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# The Transport Layer

  "Allows traffic to be directed to specific network applications"

- It handles multiplexing and demultiplexing through ports

![De/multiplexing](./images/de-multiplexer.png) 

- Port
  
  > A 16-bit number that's used to direct traffic to specific services running on a networked computer

  ![Port Number](./images/socket_port.png) 

  ![A Small Company Network Hosted on a Single Server](./images/small_company_network.png) 

## Dissection of a TCP Segment

- IP datagram encapsulate TCP segment

### TCP segment

  "Made up of a TCP header and a data section"

### TCP Header

![A TCP Header](./images/tcp_header.png) 

- Destination port

  > The port of the service the traffic is intended for.

- Source port

  > A high-numbered port chosen from a special section of ports known as ephemeral ports.

- Sequence number

  > A 32-bit number that's used to keep track of where in a sequence of TCP segments this one is expected to be.

- Acknowledgement number

  > The number of the next expected segment.

- Data offset field

  > A 4-bit number that communicates how long the TCP header for this segment is.

- Control Flag (See next part)

- TCP window

  > Specifies the range of sequence numbers that might be sent before an acknowledgement is required.

- TCP checksum

  > Operates just like the checksum fields at the IP and Ethernet level.

- Urgent pointer field

  > Used in conjunction with one of the TCP control flags to point out particular segments that might be more important than others. (No real world adoption of this TCP feature)

- Options field

  > It is sometimes used for more complicated flow control protocols. (rarely used in real world)

- Padding

  > Just a sequence of zeros to make sure data payload section starts at the expected location.

## TCP Control Flags and the Three-way Handshake

### TCP Control Flags

Not in strict order;

- URG (urgent)

  > A value of one here indicates that the segment is considered urgent and that the urgent pointer field has more data about this. (No particular real world use for this flag)

- ACK (acknowledged)

  > A value of one in this field means that the acknowledgement number field should be examined.

- PSH (push)

  > The transmitting device wants the receiving device to push currently-buffered data to the application on the receiving end asap.

- RST (reset)

  > One the sides in a TCP connection hasn't been able to properly recover from a series of missing or malformed segments.

- SYN (synchronize)

  > It's used when first establishing a TCP connection and makes sure the receiving end knows to examine the sequence number field.

- FIN (finish)

  > When this flag is set to one, it means the transmitting computer doesn't have any more data to send and the connection can be closed.

### The Three-way Handshake

- Handshake

  > "A way for two devices to ensure that they're speaking the same protocol and will be able to understand each other."

![A Three-way Handshake](./images/three_way_handshake.png) 

![A TCP Handshake](./images/tcp_handshake.png) 

### The Four-way Handshake

- Not very common

- TCP connection when finishes sending data it sends **FIN** to request the port closure.

- Then receiving end responds with **ACK** flag and connection closes

- Even though port on one end, can simply remain open and the connection ends without closing it

![A Four-way Handshake](./images/four_way_handshake.png) 

## TCP Socket States

### Socket

  "The instantiation of an end-point in a potential TCP connection."

### Instantiation

  "The actual implementation of something defined elsewhere."

### Socket States

- LISTEN
  
  > A TCP socket is ready and listening for incoming connection.

- SYN_SENT

  > A synchronization request has been sent, but the connection has not been established yet.

- SYN-RECEIVED

  > A socket previously in a **LISTEN** state has received a synchronization request and sent a **SYN/ACK** back.

- ESTABLISHED

  > The TCP connection is in working order and both sides are free to send each other data.

- FIN_WAIT

  > A **FIN** has been sent, but the corresponding **ACK** from the other end hasn't been received yet.

- CLOSE_WAIT

  > The connection has been closed at the TCP layer, but the application that opened the socket hasn't yet released its hold on the socket yet.

- CLOSED

  > The connection has been fully terminated and that no further communication is possible.

## Connection-oriented and Connectionless Protocols

### Connection-oriented Protocol

  "Established a connection, and uses this to ensure that all data has been properly transmitted."

![A lossless TCP Transfer](./images/lossless_tansfer.png) 

![A Packet loss during TCP Transfer](./images/packet_loss.png) 

### Connectionless Protocol

- The most common one is UDP

- Used where data integrity is not super important i.e. video streaming

## System Ports vs Ephemeral Ports

- **Port 0** isn't in use for network traffic, but sometimes used in communications taking place between different programs on the same computer

- **Ports 1-1024** are referred as **system ports** or sometimes as **well-known ports**. These ports represent the official ports for the most well-known network services
  
  + i.e. HTTP uses port-80, FTP uses port-21
  + Admin level access is needed to listen on these port in mos OSs

- **Ports 1024-49151** are known as **registered ports**. These ports are used for lots of other network services that might not be quite as common as the ones that are on system ports.

  + i.e. Port-3306 is used for many Databases listen on
  + Some of these ports are registered with **IANA** but not always

- **Ports 49152-65535** are known as **Private or ephemeral ports**. Ephemeral ports can't be registered with the **IANA** and are generally used for establishing outbound connections.

  + When a client wants to communicate with a server, the client will be assigned an ephemeral port to be used for just that one connection, while the server listen on a static system or registered port
  + Not all OSs follow the ephemeral port recommendation of the IANA

## Firewalls

  "A device that blocks traffic that meets certain criteria."

# The Application Layer

  "Allows network applications to communicate in a way they understand."

![The TCP Five-Layered Model](./images/tcp_model.png) 

- Too many protocols in use at application layer, a hassle to list them all.
 
  + i.e. HTTP, SMTP, etc.

## The Application Layer and the OSI Model

### Session Layer
  
  "Facilitating the communication between actual applications and the transport layer."

- Takes application layer data and hands it off to the presentation layer

### Presentation Layer

  "Responsible for making sure that the un-encapsulated application layer data is able to be understood by the application in question."

![The OSI 7-Layer Model](./images/osi_model.png) 


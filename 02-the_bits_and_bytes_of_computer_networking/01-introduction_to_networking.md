<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**

- [Introduction to Computer Networking](#introduction-to-computer-networking)
  - [Protocol](#protocol)
  - [Computer Networking](#computer-networking)
- [The Basics of Networking Devices](#the-basics-of-networking-devices)
  - [Cables](#cables)
  - [Hubs and Switches](#hubs-and-switches)
    - [Hub](#hub)
    - [Network Switch](#network-switch)
  - [Routers](#routers)
  - [Servers and Clients](#servers-and-clients)
    - [Servers](#servers)
- [The TCP/IP Five-Layer Network Model](#the-tcpip-five-layer-network-model)
  - [1) Physical Layer](#1-physical-layer)
    - [Twisted-Pair Cabling and Duplexing](#twisted-pair-cabling-and-duplexing)
    - [Network Ports and Patch Panels](#network-ports-and-patch-panels)
  - [2) Data Link Layer](#2-data-link-layer)
    - [Ethernet and MAC Addresses](#ethernet-and-mac-addresses)
    - [Uni-cast, Multicast and Broadcast](#uni-cast-multicast-and-broadcast)
    - [Dissecting an Ethernet Frame](#dissecting-an-ethernet-frame)
  - [3) Network Layer](#3-network-layer)
    - [Inter-network](#inter-network)
  - [4) Transport Layer](#4-transport-layer)
  - [5) Application Layer](#5-application-layer)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# Introduction to Computer Networking

## Protocol

  A defined set of standards that computers must follow in order to communicate properly.

## Computer Networking

  The name we've given to the full scope of how computer communicate with each other.

- TCP/IP five layered network model

# The Basics of Networking Devices

## Cables

"Connect different devices to each other, allowing data to be transmitted over them."

- Copper Cables

  + Change voltage to get binary data
  + The most common forms of copper twisted-pair cables used in networking are **Cat5, Cat5e, and Cat6** cables
  ![Types of Twisted-Pair Copper Cables](./images/copper_cables.png) 

> **Crosstalk**: "When an electrical pulse on one wire is accidentally detected on another wire."

- Fiber Optic Cables

> Contain individual optical fibers, which are tiny tubes made out of glass about the width of a human hair.

- Unlike copper cables, fibers use light pulses to send 1s and 0s

## Hubs and Switches

### Hub

> A physical layer device that allows for connections from many computers at once.

![Hubs's Working](./images/hubs.png)

- Layer 1 device
- **Collision domain:** A network segment where only one device can communicate at a time.
- If multiple systems try sending data at the same time, the electrical pulses sent across the cable can interfere with each other

![Data Collision](./images/data_collision.png)

### Network Switch

- Layer 2 device
- Can direct traffic to particular node on network, so reduces Collision Domain

## Routers

- The primary devices used to connect computers on a single network, usually referred to as a **LAN or local area network**

> A device that knows how to forward data between independent networks

- Layer 3 (network) device
- Core ISP routers(More complex than home routers) form the backbone of the internet.

## Servers and Clients

### Servers

> Provide data to some client, requesting it

- Vague definition, as individual programs running on the computer can also act a server

# The TCP/IP Five-Layer Network Model

## 1) Physical Layer

  Represents the physical devices that interconnect computers.

- 10 Base T, 802.11
- Bits
  > **Bits:** The smallest representation of data that a computer can understand; it's a one or zero

- 1s and 0s are sent across network using modulation

  > **Modulation:** A way of varying the voltage of charge moving across the cables

- When using modulation in computer networks, it's called **Line coding**

### Twisted-Pair Cabling and Duplexing

- Most common
- Twisted-Pair avoid interference & crosstalk

> **Duplex Communication:** The concept that information can flow in both directions across the globe

> **Simplex Communication:** This is unidirectional

![Simplex and Duplex Communication](./images/simplex_duplex.png)

### Network Ports and Patch Panels

- Twisted-Pair Cables end with the plug which takes the wires and act as a connector
- The most common plug **RJ45**

![Plugs and Connector](./images/plugs.png) 

> **Network Ports:** They are generally directly attached to the devices that make up a computer network

- Most network ports have two small LEDs

> **Activity LED:** Would flash when data actively transmitted across the cable

> **Link LED:** Lit when cable properly connected to two devices that are both powered on

- Sometimes a network port isn't connected directly to a device.
Instead, there might be network ports mounted on a wall or underneath your desk.
These ports are generally connected to the network via cables,
run through the walls that eventually end at a patch panel. 

> **Patch Panel:** A device containing many network ports. But it does no other work.

## 2) Data Link Layer

Responsible for defining a common way of interpreting these signals so network devices can communicate.

- Ethernet: The Ethernet standards also define a protocol responsible for getting data to nodes on the same network.
- WI-FI
- Frames
- Mac-Address

### Ethernet and MAC Addresses

- Ethernet is the most common means of sending data
- Ethernet solves Collision domain by using a technique known as **carrier sense multiple access with collision detection (CSMA/CD)**.

> **CSMA/CD:** Used to determine when the communications channels are clear, and when device is free to transmit data

> **MAC Address:** A globally unique identifier attached to an individual network interface

  + It's a 48- bit number normally represented by six groupings of two hexadecimal numbers
  + **Hexadecimal:** A way to represent numbers using 16 digits

  ![Hexadecimal Numbers](./images/hexadecimal_numbers.png) 

  + Another way to represent MAC Address is Octet
  + **Octet:** In computer networking, any number can be represented by 8 bits
  + MAC-Address is split in two categories

  > **1) Organizationally Unique Identifier(OUI):** The first three octets of a MAC address

  > **2) Vendor Assigned(NIC Cards, Interfaces):** Last three octets are assigned by the vendor, depending upon their preferences.

  ![MAC Address Types](./images/mac_addresses.png) 

  + Ethernet uses MAC addresses to ensure that the data it sends has both an address for the machine that sent the transmission, and the one the transmission was intended for.

### Uni-cast, Multicast and Broadcast

- Uni-cast
  > A uni-cast transmission is always meant for just one receiving address

  ![Unicast](./images/unicast.png) 

  + It's done by looking at specific bit in the destination MAC address
  + If the least significant bit in the first octet of a destination address is set to **zero**, it means that Ethernet frame is intended for **only the destination address**. 
  + If the least significant bit in the first octet of a destination address is set to **one**, it means you're dealing with a **Multicast frame**

  ![Multicast](./images/multicast.png) 

- Broadcast

> An Ethernet Broadcast is sent to every single device on a LAN

  + This is accomplished by special address known as Broadcast address
  + Ethernet broadcast are used, so devices can learn more about each other
  + Ethernet broadcast address used is `FF:FF:FF:FF:FF:FF:FF` 

  ![Broadcast](./images/broadcast.png) 

### Dissecting an Ethernet Frame

- Data Packet

  > An all-encompassing term that represents any single set of binary data being sent across a network link

- Ethernet Frame

  > A highly structured collection of information presented in a specific order
  
  ![Ethernet Frame](./images/ethernet_frame.png) 

  + First part of Ethernet frame is called a preamble.

  > **Preamble:** 8 bytes (or 64 bits) long, and can itself split into two sections

  + Preamble can split into two part of 1 byte of series of 1s and 0s
  + Last frame in preamble is called Start frame delimiter (SFD)
  
  > Signals to a receiving device that the preamble is over and that the actual frame contents will now follow

  + Next is Destination MAC address

  > The hardware address of the intended recipient

  + Followed by Source Address
  + The next part of Ethernet Frame is EtherType field

  > 16 bits long and used to describe the protocol of the contents of the frame

  + WE can use VLAN header in place of EtherType field

  > Indicates that the frame itself is what's called a VLAN frame

  + If a VLAN header is present, the EtherType field follows it.
  > **Virtual LAN (VLAN):** A technique that lets you have multiple logical LANs operating on the same physical equipment
  + VLANs, use to segregate different type of network traffic

  ![Vlan Network](./images/vlan.png) 
  
  + The next part of Ether frame is payload

  > In networking terms, is the actual data being transported, which is everything that isn't a header.

  + Following payload is, Frame Check Sequence (FCS)

  > A 4-byte (or 32-bit) number that represents a checksum value for the entire frame

    + This **checksum value** is calculated by performing what's known as a cyclical redundancy check against the frame.

    > **Cyclic Redundancy Check (CRC):** An important concept for data integrity, and is used all over computing, not just network transmissions



## 3) Network Layer

Allows different networks to communicate with each other through devices know as routers.

-   IP: IP is the heart of the Internet and smaller networks around the world.
-   Datagram
-   IP Address

### Inter-network

A collection of networks connected together through routers, the most famous of these being the Internet.

## 4) Transport Layer

Sorts out which client and server programs are supposed to get that data.

-   TCP/UDP
-   Segment
-   Ports

## 5) Application Layer

There are lots of different protocols at this layer, and as you might have guessed from the name, they are application-specific. Protocols used to allow you to browse the web or send receive email are some common ones.

-   HTTP, SMTP etc.
-   Messages


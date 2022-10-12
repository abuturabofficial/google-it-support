<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Physical Layer](#physical-layer)
- [Data link Layer](#data-link-layer)
- [Network Layer](#network-layer)
- [Transport Layer](#transport-layer)
  - [Multiplexing and Demultiplexing](#multiplexing-and-demultiplexing)
- [MAC Address](#mac-address)
- [IP Address](#ip-address)
    - [**1) IPv4 address:**](#1-ipv4-address)
    - [2) IPv6 Addresses](#2-ipv6-addresses)
- [TCP Port](#tcp-port)
- [Checksum Check](#checksum-check)
- [Routing Table](#routing-table)
    - [Entries of an IP Routing Table:](#entries-of-an-ip-routing-table)
    - [1) Network ID:](#1-network-id)
  - [2) Subnet Mask:](#2-subnet-mask)
    - [3) Next Hop:](#3-next-hop)
    - [4) Outgoing Interface:](#4-outgoing-interface)
    - [5) Metric:](#5-metric)
- [TTL](#ttl)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# Physical Layer

This layer describes that how devices connect to each other at the physical level. On this level, twisted-pair cables and duplexing is used.

Duplex communication has two types;

1) Half-duplex: Communication is possible only in one direction at a time.

2) Full-Duplex/Duplex: The information can flow in the both direction at the same time.

The information travels in the form of bits in the Physical layer.

  

#  Data link Layer

Responsible for defining a common way of interpreting signals coming from the physical layer, so network devices can communicate with each other.

It consists of following protocols;

1) Wi-Fi

2) Ethernet

The data sent in this layer in the form of frames. We can identify devices working at the Physical layer by their MAC addresses.

# Network Layer

This layer corresponds to the combination of Data Link Layer and Physical Layer of OSI Model. It looks out for hardware addressing and the protocols present in this layer allows for the physical transmission of data.

This layer includes

-   IP addressing
    
-   Encapsulation
    

The unit of data in the network layer is **datagram**.

# Transport Layer

Transport layer is the second layer in TCP/IP model. It is an end-to-end layer used to deliver messages to a host. It is termed an end-to-end layer because it provides a point-to-point connection rather of hop-to-hop, between the source host and destination host to deliver the services reliably. The unit of data in the transport layer is a segment.

## Multiplexing and Demultiplexing

Multiplexing allows simultaneous use of different applications over a network that is running on a host. The transport layer provides this mechanism, which enables us to send packet streams from various applications simultaneously over a network. The transport layer accepts these packets from different processes, differentiated by their port numbers, and passes them to the network layer after adding proper headers. Similarly, Demultiplexing is required at the receiver side to obtain the data coming from various processes. Transport receives the segments of the data from the network layer and delivers it to the appropriate process running of the receivers’ machine.

#  MAC Address

A globally unique identifier attached to the individual network interfaces. It is a 48-bits number, normally represented by 6 groups of 2 hexadecimal numbers.

MAC addresses split up into two categories;

  

**1) Organizationally Unique Identifier (UIO):**

  

The first three groups represent the UIO of the device, which is unique to every organization issuing it. I.e., for Cisco, UIO is 00 60 2F.

  

**2) Vendor Assigned(NIC Cards, interfaces):**

  

The last three octets are assigned by the vendor, depending upon their preferences. Which tells us about that particular device it's assigned for.

  

#  IP Address

An IP address, or Internet Protocol address, is a series of numbers that identifies any device on a network. Computers use IP addresses to communicate with each other, both over the internet and on other networks.

  

An IP address consists of 4 octets of 8 bits, so it has 32-bits in total. There are two types of IP addresses;

  

### **1) IPv4 address:**

IPv4 addresses consist of 4 octets of decimal numbers, each octet range from 0-255. There are only 4 billion IPv4 addresses to use for us, so we need some other way to assign IPs to the devices to overcome the shortage of IP addresses.

IPv4 addresses are further divided into three major classes;

**a) Class-A Addresses:** These have only the first octet for network ID, and the rest for the host IDs.

**b) Class-B Addresses:** These have the first 2 octets for network IDs, and the rest for the host IDs.

**c) Class-C addresses:** These have first 3 octets for Network IDs, and the only last one for host IDs.

### 2) IPv6 Addresses

IPv6 addresses has 132-bit of hexadecimal numbers, it has 2^128 IP addresses, which solves our problem of IP address shortage.

# TCP Port

A 16-bit number that's used to direct traffic to specific services running on a networked computer.

  

There are almost, 65535 ports available to use which are categorized as follows;

  

> Port 0 used for internal traffic between different programs on the same computer.

  

> Ports 1-1024 are called system ports or well known ports. These are used for some well known services such HTTP, FTP, SMTP and require admin level privileges for the port to be accessed.

  

> Ports 1025-49151 are called registered ports. They are used for the services not well known as used by system ports. They don't require admin level access for the port to be accessed.

  

> Ports 49152-65535 are called ephemeral ports. They are used for establishing outbound connections.

#  Checksum Check

A checksum is a value that represents the number of bits in a transmission message and is used by IT professionals to detect high-level errors within data transmission.

The common algorithm used for checksum is **MD5, SHA-2** etc

#  Routing Table

A routing table is a set of rules, often viewed in table format, that is used to determine where data packets traveling over an Internet Protocol (IP) network will be directed. All IP-enabled devices, including routers and switches, use routing tables.

| Destination | Subnet mask | Interface |
|:--------------:|:----------:|:--------:|
| 128.75.43.0 | 255.255.255.0 | Eth0 |
| 128.75.43.0 | 255.255.255.128 |Eth1 |
| 192.12.17.5 | 255.255.255.255 | Eth3 |
| default | | Eth2 |


### Entries of an IP Routing Table:

A routing table contains the information necessary to forward a packet along the best path toward its destination. Each packet contains information about its origin and destination. The routing table provides the device with instructions for sending the packet to the next hop on its route across the network.

Each Entry in the routing table consists of the following route.

  
  

### 1) Network ID:

The network ID or destination corresponding to the route.

## 2) Subnet Mask:

The mask that is used to match a destination IP address to the network ID.

### 3) Next Hop:

The IP address to which the packet is forwarded.

### 4) Outgoing Interface:

Outgoing interface the packet should go out to reach the destination network.

### 5) Metric:

A common use of the metric is to indicate the minimum number of hops (routers crossed) to the network ID.

Routing table entries can be used to store the following types of routes:

-   Directly Attached Network IDs
    
-   Remote Network IDs
    
-   Host Routes
    
-   Default Routes
    
-   Destination
    

#  TTL

Time-to-live (TTL) in networking refers to the time limit imposed on the data packet to be in-networking before being discarded. It is an 8-bit binary value set in the header of Internet Protocol (IP) by sending the host. The Purpose of a TTL is to prevent data packets from being circulated forever in the network. **The maximum TTL value is 255, while the commonly used one is 64.**
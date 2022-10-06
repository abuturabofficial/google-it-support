# Introduction to Troubleshooting and the Future of Networking

## Introduction to Troubleshooting and the Future of Networking

- After every possible safeguard in place, misconfiguration happens and:

  + Error still pop-up

  + Misconfiguration occur

  + Hardware breaks down

  + System incompatibilities come to light

### Error-detection

"The ability for a protocol or program to determine that something went wrong."

### Error-recovery

"The ability for a protocol or program to attempt to fix it."


# Verifying Connectivity

## Ping: Internet Control Message Protocol (ICMP)

### ICMP Message

- ICMP packet is sent to troubleshoot network issues.

- Make-up of ICMP packet is pretty simple, it has a HEADER and DATA section.

- The ICMP HEADER has the following fields:

  + **TYPE**: 8-bits long, which specifies what type of data is being delivered. Like, destination unreachable or time exceeded.

  + **CODE**: 8-bits long, which indicates more specific reason than just a type. I.e. destination unreachable type, there are different cods for destination network unreachable or destination port unreachable.

  + **Checksum**: 16-bits checksum, that work like every other checksum field.

  + **Rest of Header** 32-bits long, this field is optionally used by some specific codes and types to send more data.

- Data Payload section for ICMP

  + The payload for an ICMP packet exists entirely so that the recipient of the message knows which of their transmissions caused the error being reported.

  + It contains entire IP Header, and the first 8-bytes of the data payload section of the offending packet.

- ICMP isn't developed for the humans to interact with.

![ICMP Message](./images/icmp.png) 

### Ping

Ping lets you send a special type of ICMP message called an **Echo Request**.

- Echo Request just asks, hi, are your there?

- If the destination is up and running and able to communicate on the network, it'll send back an ICMP **Echo Reply** message type.

## Traceroute

"A utility that lets you discover the path between two nodes, and gives you information about each hop along the way."

![Traceroute](./images/traceroute.png) 

- Two similar tools to traceroute are:

  + mtr - Linux/MacOS

  + pathping - Windows

## Testing Port Connectivity

- Sometimes, you need to know if things working at transport layer.

- There two powerful tools for this at your disposal:
  
  + netcat - Linux/MacOS

  + Test-NetConnection - Windows

# Digging into DNS

## Name Resolution Tools

- Most common tool is **nslookup**.

- Available on all OSs.

## Public DNS Servers

- An ISP almost always gives you access to a **recursive name server** as part of the service it provides.

- Many businesses run their own name servers. To give names to the Printers, computers etc instead of referring them with their IPs.

![A Private Name server](./images/private_name_server.png) 

- Another option is using **DNS as a service** provider. It is becoming more popular.

- Some organizations run Public DNS servers, like Google's **8.8.8.8**, cloudflare's **1.1.1.1**, quad9's **9.9.9.9** etc.

- Some level 3 DNS provider also provide free public DNS servers, but not advertised by them. I.e. 4.2.2.3 etc.

  + Name servers specifically set up so that anyone can use them, for free.

  + Most public DNS servers are available globally through anycast.

- One should be careful when using Public DNS server, hijacking outbound DNS query, and redirecting the traffic to malicious website is a common intrusion technique.

- Always make sure the name server is run by a reputable company, and try to use the name servers provided by your ISP outside of troubleshooting scenarios.

![DNS Hi-jacking](./images/dns_hijacking.png) 

## DNS Registration and Expiration

### Registrar

An organization responsible for assigning individual domain names to other organizations or individuals.

- Originally, there was only one company **Network Solutions INC** responsible for domain Registration.

- Network Solutions Inc. and USA government came to an agreement to let other companies also sell domain names.

## Hosts Files

- The original way that numbered network addresses were correlated with words was through **hosts files**.

- Most modern system, like computers and Mobile phones still hosts files.

- Hosts files are a popular way for the computer viruses to disrupt and redirect users' traffic.

### Hosts File

"A flat file that contains, on each line, a network address followed by the host name it can be referred to as."

### Loopback Address

A way of sending network traffic to yourself.

- Loopback IP for IPv4 is 127.0.0.1

- Almost every hosts file in existence will, in the very least, contain a line that reads **127.0.0.1 localhost**, most likely followed by **::1 localhost**, where **::1** is the loopback address for IPv6.

# The Cloud

## What is The Cloud?

- Not a single technology, it's a technique.

### Cloud Computing

"A technological approach where computing resources are provisioned in a shareable way, so that lots of users get what they need, when they need it."

Or

"A new model in computing where large clusters of machines let us use the total resources available in a better way."

- Hardware virtualization is at the heart of cloud computing.

- Hardware virtualization platforms deploy what's called a hypervisor.

### Virtualization

"A single physical machine, called a host, could run many individual virtual instances, called guests."

### Hypervisor

"A piece of software that runs and manages virtual machines, while also offering these guests a virtual operating platform that's indistinguishable from an actual hardware."

![A Hypervisor](./images/hypervisor.png)

### Public Cloud

A large cluster of machines run by another company.

### Private Cloud

Used by a single large corporation and generally physically hosted on its own premises.

### Hybrid Cloud

A term used to describe situations where companies might run thing like their most sensitive proprietary technologies on a private cloud, while entrusting their less-sensitive servers to a public cloud.

## Everything as a Service

- X as a Service, where X can mean many things.

### Infrastructure as a Service (IaaS)

You shouldn't have to worry about building your own network or your own servers.

### Platform as a Service (PaaS)

A subset of cloud computing where a platform is provided for customers to run their services.

### Software as a Service (SaaS)

A way of licensing the use of software to others while keeping that software centrally hosted and managed.

  + Gmail for Business

  + Office 365 Outlook

## Cloud Storage

- Operate in different geographic region.

- Pay as you use

- Good for backup

# IPv6

## IPv6 Addressing and Subnetting

- IPv4 was run out of new IPs

- IPv5 was an experimental protocol that introduced the concept of connections.

- IPv6 = 128 bits, written as 8 groups of 16-bits each. Each one of these groups is further made up of **four** hexadecimal numbers.

- Full IPv6 address looks like this

![An IPv6 Address](./images/full_ipv6.png) 

- Reserved IPv6 range is as follows, for education, documentation, books, courses etc.

![Reserved IPv6 Addresses](./images/reserved_ipv6.png) 

### Shortening of an IPv6 address

Two rules

- Remove any leading zeros from a group

- Any number of consecutive groups composed of just zeros can be replaced with two colon **::**.

- Any IPv6 address begins with **FF00::** is used for **multicast**.

- Any IPv6 address begins with **FE80::** is used for **Link-local unicast**.

- First 32-bits of IPv6 are network ID, and last are host ID.

- IPv6 uses same CIDR notation for subnet mask.


### Multicast

A way of addressing groups of hosts all at once.

### Link-local unicast

Allow for local network segment communication and are configured based upon a host's MAC address.

## IPv6 Headers

- Header much simpler than IPv4 header.

- IPv6 header has following components:

  + Version field

  > A 4-bit field that defines what version of IP is in use.

  + Traffic class field

  > An 8-bit field that defines the type of traffic contained within the IP datagram, and allows for different classes of traffic to receive different priorities.

  + Flow Label Field

  > A 20-bit field that's used in conjunction with the traffic class field for routers to make decisions about the quality of service level for a specific datagram.

  + Payload length field

  > A 16-bit field that defines how long the data payload section of the datagram is.

  + Next header field

  > A unique concept of IPv6, and needs a little extra explanation. It defines what header is up next after that. To help reduce the problems with additional data that IPv6 addresses impose on the network, the IPv6 header was built to be a short as possible. One way to do that is to take all of the optional fields and abstract them away from the IPv6 header itself. The next header field defines what kind of header is immediately after this current one. These additional headers are optional, so they're not required for a complete IPv6 datagram. Each of these additional optional headers contain a next header field and allow for
a chain of headers to be formed if there's a lot of optional configuration. 

  + Hop limit

  > An 8-bit field that's identical in purpose to TTL field in an IPv4 header.

  + Source Address : 128-bits

  + Destination Address : 128-bits
  
  + Data Payload section

![An IPv6 Header](./images/ipv6_header.png) 

## IPv6 and IPv4 harmony

- Not possible for whole Internet to switch to IPv6 in no time.

- So, IPv6 and IPv4 traffic need to coexist during the transition period.

- This is possible with **IPv4 mapped address space**. The IPv6 specifications have set aside a number of addresses that can be directly correlated to an IPv4 address.

![IPv4 mapped address space](./images/mapped_addr.png) 

- More important is IPv6 traffic needs to travel to IPv4 servers.

- This is done through **IPv6 tunnels**.

### IPv6 tunnels

Servers take incoming IPv6 traffic and encapsulate it within traditional IPv4 datagram.

- They consist of IPv6 tunnel servers on either end of a connection. These IPv6 tunnel servers take incoming IPv6 traffic and encapsulate it within traditional IPv4 datagrams. This is then delivered across the IPv4 Internet space where it's received by another IPv6 tunnel server. That server performs the de-encapsulation and passes the IPv6 traffic further along in the network.

![IPv6 tunneling](./images/ipv6_tunneling.png) 

### IPv6 tunnel broker

Companies that provide IPv6 tunneling endpoints for you, so you don't have to introduce additional equipment to your network. 

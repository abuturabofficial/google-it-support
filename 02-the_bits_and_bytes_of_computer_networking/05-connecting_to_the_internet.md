<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**

- [POTS and Dial-up](#pots-and-dial-up)
  - [Dial-up, Modems and Point-to-Point Protocols](#dial-up-modems-and-point-to-point-protocols)
    - [Dial-up](#dial-up)
    - [Baud rate](#baud-rate)
- [Broadband Connections](#broadband-connections)
  - [What is broadband?](#what-is-broadband)
  - [T-carrier technologies](#t-carrier-technologies)
  - [Digital Subscriber Lines (DSL)](#digital-subscriber-lines-dsl)
  - [Cable Broadband](#cable-broadband)
    - [Cable modems](#cable-modems)
    - [Cable modem termination system (CMTS)](#cable-modem-termination-system-cmts)
  - [Fiber Connections](#fiber-connections)
    - [Optical Network Terminator (ONT)](#optical-network-terminator-ont)
- [WANs](#wans)
  - [Wide Area Network Technologies](#wide-area-network-technologies)
    - [Local Loop](#local-loop)
  - [Point-to-Point VPNs](#point-to-point-vpns)
- [Wireless Networking](#wireless-networking)
  - [Introduction to Wireless Networking Technologies](#introduction-to-wireless-networking-technologies)
    - [Frequency band](#frequency-band)
    - [Wireless access point](#wireless-access-point)
  - [Wireless Network Configuration](#wireless-network-configuration)
    - [Ad-hoc Network](#ad-hoc-network)
    - [Wireless LAN (WLAN)](#wireless-lan-wlan)
    - [Mesh Network](#mesh-network)
  - [Wireless Channels](#wireless-channels)
    - [Collision domain](#collision-domain)
  - [Wireless Security](#wireless-security)
    - [Wired Equivalent Privacy (WEP)](#wired-equivalent-privacy-wep)
    - [MAC filtering](#mac-filtering)
  - [Cellular Networking](#cellular-networking)
  - [Mobile Device Networks](#mobile-device-networks)
  - [IoT Wireless network protocols at the physical layer](#iot-wireless-network-protocols-at-the-physical-layer)
    - [Wi-Fi](#wi-fi)
    - [IEEE 802.15.4](#ieee-802154)
    - [ZigBee](#zigbee)
    - [Thread](#thread)
    - [Z-Wave](#z-wave)
    - [Wireless mesh network (WMN)](#wireless-mesh-network-wmn)
    - [Bluetooth](#bluetooth)
    - [Near-Field Communication (NFC)](#near-field-communication-nfc)
    - [Long Range Wide Area Network (LoRaWAN)](#long-range-wide-area-network-lorawan)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# POTS and Dial-up

## Dial-up, Modems and Point-to-Point Protocols

- In late 1970s two graduate students of Duke University were trying to come up with a better way to connect computers at further distances.

- They realized basic infrastructure in the form of telephone lines already existed.

- The **Public Switched Telephone Network** or **PSTN** also referred as the **Plain Old Telephone Service** or **POTS**.

- System they built was called **USENET**, which was precursor for Dial-up.

### Dial-up

A dial-up connection uses **POTS** for data transfer, and gets its name because the connection is established by actually dialing a phone number.

![A Dial-up](./images/dial-up.png) 

- Transferring data on dial-ups is done through **Modems**, stands for **Modulator/Demodulator**.

![A Modem In Practice](./images/modems.png) 

- Early modems have very low **Baud rate**

- By late 1950s, computers can generally send data at the rate of **110bps**.

- When **USENET** was developed, this rate was increased to **300bps**

- In early 1990s, when the dial-up access to the Internet became a household commodity, this rate was increased to **14.4kbps**.

### Baud rate

"A measurement of how many bits can be passed across a phone line in a second."

# Broadband Connections

## What is broadband?

"Any connectivity technology that isn't dial-up Internet."

- In late 1990s, it was become common for most businesses to use **T-carrier technologies**.

- T-carrier technologies require dedicated line, so are used by mainly only businesses.

- Other solutions and technologies also available for businesses and normal consumers:

  + DSL

  + Cable broadband

  + Fiber connections

## T-carrier technologies

"Originally invented by **AT&T** in order to transmit multiple phone calls over a single link."

- Before **Transmission System 1** or short **T1** each phone call require its own copper cable to transmit.

- With **T1** AT&T invented way to carry **24 phone calls** simultaneously over a single copper cable.

- Few years later, **T1** technology was repurposed for data transfers.

![T1 technology at play](./images/t1_tech.png) 

- Over the years, the phrase **T1** has come to mean any **twisted pair copper connection** capable of speeds of **1.544mbps**, even if they doesn't strictly follow the original **Transferring System 1** specifications.

- Initially **T1** lines were used to connect telecommunication channels only

- But as the Internet grew, many businesses and companies paid to have **T1** cables installed for faster connectivity.

- Improvements were made by developing a way for multiple **T1s** to act as a single link.

- **T3** line was invented which has 28 **T1** lines combined, and total speed of **44.736mbps**.

- Now for small businesses and companies, Fiber connection are more common as they cheaper.

- For **inner-ISP** communications different Fiber technologies have all replaced older copper-based ones.

## Digital Subscriber Lines (DSL)

- DSL made possible the occurrence of phone calls and data transfer at the same line, and at the same time.

- DSL uses their own modems called **Digital Subscriber Line Access Multiplexers (DSLAMs)**.

- Just like dial-up modems, these devices establish data connections across phone lines, but unline dial-up connections, they're usually long-running.

- Two most common DLSs are:

  + ADSL (Asymmetric Digital Subscriber Line)
  
    + Feature different speed of outbound and inbound data. It means faster download speeds and slower Upload.

  + SDSL (Symmetric Digital Subscriber Line)

    + Same as ADSL, but upload and download speeds are the same.

    + Most SDSLs have an upper cap of speed, **1.544mbps**.

- Further developments in SDSL technology have yielded things like:
  
  + HDSL (High Bit-rate Digital Subscriber Lines)

    + These provision speeds above **1.544mbps**.

![A DSL connection](./images/dsl.png) 

## Cable Broadband

- The history of both computer and telephone tells a story that started with all communications being wired, but the recent trend is moving towards more traffic as wireless.

- But television followed the opposite path. Originally, all television broadcast were wireless, sent out by giant television towers and received by smaller antennas in people's houses.

- You had to be in range of that towers to receive signals, like today you've to be in range cellular tower for cellular communications.

- Late 1940s, first television technology was developed.

- In 1984, **Cable Communications Policy Act** deregulated the television industry, started booming, rest of world soon followed suit.

![Cable and DSL](./images/cable_dsl.png) 

- Cable connections are managed by **Cable modems**.

### Cable modems

The device that sits at the edge of a consumer's network and connects it to the cable modem termination system, or CMTS.

### Cable modem termination system (CMTS)

Connects lots of different cable connections to an ISPs core network.

## Fiber Connections

- Fiber achieve higher speed, no degradation in signal transfer.

- An electrical signal can only travel few hundred meters before degradation in copper cable.

- While light signal in fiber cables can travel many, many KMs before degradation.

- Producing and laying fibers a lot more expensive than copper cables.

- Fiber connection to the end consumers, varies tons due to tons of implications.

- That's why phrase **FTTX** or **fiber to the X** was developed.

  + **FTTN**: Fiber to the Neighbourhood

  + **FTTB**: Fiber to the Building, FTTB is a setup where fiber technologies are used for data delivery to an individual building.

  + **FTTH**: Fiber to the Home

  + **FTTB** and **FTTH** both may also refer to as **FTTP** or Fiber to the Premises

- Instead of modem, the demarcation point for Fiber technologies is known as **Optical Network Terminator** or **ONT**.

![Fiber to the X](./images/fttx.png) 

### Optical Network Terminator (ONT)

Converts data from protocols, the fiber network can understand, to those that more traditional, twisted-pair copper networks can understand.

# WANs

## Wide Area Network Technologies

"Acts like a single network, but spans across multiple physical locations."

- It works at Data Link Layer.

- WANs are built to be super fast.

- Some of the technologies used in WANs:

  + Frame Relay

  > Frame Relay is a standardized wide area network (WAN) technology that specifies the **Physical & Data Link Layer** of digital telecommunications channels using a **packet switching** methodology. Originally designed for transport across **Integrated Services Digital Network (ISDN)** infrastructure, it may be used today in the context of many other network interfaces.

  + High-Level Data Link Control (HDLC)

  > HDLC is a bit-oriented code-transparent synchronous **data link layer protocol** developed by the **International Organization for Standardization (ISO)**. The standard for HDLC is **ISO/IEC 13239:2002**.

    + HDLC provides both connection-oriented and connectionless service.

  + Asynchronous Transfer Mode (ATM)

  > A standard defined by **American National Standards Institute (ANSI) and **ITU-T** for digital transmission of multiple types of traffic.

    + ATM was developed to meet the needs of the **Broadband Integrated Services Digital Network (BISDN)** as defined in late 1980s.

### Local Loop

"In a WAN, the area between a demarcation point and the ISP's core network is called Local Loop."

## Point-to-Point VPNs

- A popular alternative to WAN technologies

- Companies are moving cloud for services such as Email, Cloud Storage. So, expensive cost of WANs is often outnumbered.

- They maintain their secure connection to these cloud solutions through **Point-to-Point VPNs**.

- Point-to-Point VPN often called **Site-to-Site VPN**.

![Point-to-Point VPNs](./images/ptop_vpn.png) 

# Wireless Networking

## Introduction to Wireless Networking Technologies

"A way to network without wires."

- **IEEE 802.11 Standards** or **802.11 family** define the most common workings of Wireless networks.

- Wireless devices communicate via radio waves.

- Different 802.11 generally use the same basic protocol but different frequency bands.

- In North America, FM radio transmissions operate between **88 and 108 MHz**. This specific frequency band is called **FM Frequency Band**.

- **Wi-Fi** works at **2.4GHz and 5GHz** bands.

- There are many 802.11 specifications, but common ones, you might run into are: (In order of when were introduced)

  + 802.11b

  + 802.11a

  + 802.11g

  + 802.11n

  + 802.11ac

- 802.11 = physical and data link layers

- All specifications operate with the same basic data link protocol. But, how they operate at the 88physical layer** varies.

- 802.11 frame has a number of fields.

  + Frame control field

  > Is 16-bits long and contains a number of subfields that are used to describe how the frame itself should be processed.

  + Duration field

  > It specifies how long the total frame is, so the receiver knows how long it should expect to have to listen to this transmission.

  + Rest are 4 address fields. 6 bytes long.

    + Source address field

    + Intended destination

    + Receiving address

    + Transmitter address

  + Sequence control field

  > Is 16-bits long and mainly contains a sequence number used to keep track of the ordering of frames.

  + Data payload

  > Has all the data of the protocols further up the stack.

  + Frame check sequence field

  > Contains a checksum used for a cyclical redundancy check, just like how Ethernet does it.

- The most common wireless setup includes **wireless access point**.

![802.11 Data Frame](./images/802-11_frame.png) 

### Frequency band

"A certain section of the radio spectrum that's been agreed upon to be used for certain communications."

### Wireless access point

"A device that bridges the wireless and wired portions of a network."

## Wireless Network Configuration

- There are few ways wireless networks can be configured

  + Ad-hoc networks: Nodes speak directly to each other.

  + Wireless LANS (WLANS): Where one or more access point act as a bridge between a wireless and a wired network.

  + Mesh Networks: Hybrid of the former two.

### Ad-hoc Network

- Simplest of the three

- In an ad-hoc network, there isn't really any supporting network infrastructure.

- Every device on the network speaks directly to every other device on the network.

- Used in smartphones, Warehouses

- Important tool during disaster like earthquake, the relief workers, can communicate via ad-hoc network.

![Ad-hoc Network](./images/ad-hoc.png) 

### Wireless LAN (WLAN)

- Most common in business settings

![Wireless LAN](./images/wlan.png) 

### Mesh Network

- Most mesh networks are only made up of wireless access points. And are still connected to the wired network.

![Mesh Network](./images/mesh.png) 

## Wireless Channels

"Individual, smaller sections of the overall frequency band used by a wireless network."

- Channels solve problem of collision domain.

![2.4 GHz band and Wireless Channels](./images/2-4band.png) 

### Collision domain

"Any one of the network segment where one computer can interrupt another."

## Wireless Security

- Data packets sent in the air via radio waves need to be protected.

- Wired Equivalent Privacy (WEP) was invented to encrypt data packets.

- WEP uses only 40-bits for its encryption keys, which could easily be compromised with modern and fast computers.

- So, WEP was quickly replaced in most places with **WPA or Wi-Fi Protected Access**.

- WPA, by-default uses **128-bits** key.

- Nowadays, the most common wireless encryption method used is **WPA2**, an update to the original **WPA**

- **WPA2** uses **256-bits** key.

- Another common way of securing wireless traffic is **MAC filtering**.

### Wired Equivalent Privacy (WEP)

"An encryption technology that provides a very low level of privacy."

### MAC filtering

You configure your access points to only allow for connections from a specific set of MAC addresses belonging to devices you trust.

## Cellular Networking

- Cellular networks have lot in common with 802.11 networks.

- Just like Wi-Fi, they also operate on radio waves.

- There are cellular frequency bands reserved for Cellular communications.

- Phone frequency waves can travel several KMs.

![Cellular Networking](./images/cellular_comms.png) 

## Mobile Device Networks

- Mobile devices use wireless networks to communicate with the Internet and with other devices.

- Depending on the device, it might use:

  + Cellular networks

  + Wi-Fi

  + Bluetooth

  + Internet of Things (IoT) network protocols

## IoT Wireless network protocols at the physical layer

- IoT devices can use both wired and wireless connections.

- Most IoT devices can use at least one of the following network protocols:

### Wi-Fi

+ Wireless Fidelity (Wi-Fi): IEEE 802.11 Standard
+ Wi-Fi 6 can support up-to **500mbps**

+ The 2.4 GHz frequency extends to 150 feet (45 meters) indoors, and 300 feet (92 meters) outdoors.

+ 2.4 GHz may feel congestion due to limited number of channels and high interference from other devices.

+ 5.0 GHz provide stronger signal and has more channels to handle more traffic. The drawback is limited range of 50 feet (12 meter) indoors and 100 feet (30.6 meter) outdoors.

### IEEE 802.15.4

+ An inexpensive, low-power wireless access technology intended for IoT devices that operate on battery power.

+ IEEE 802.15.4 uses 2.4 GHz or lower frequencies

+ IEEE 802.15.4 is normally used for **low-rate wireless personal area networks (LR-WPANs)** and uses a **128-bits** encryption.

### ZigBee

+ **ZigBee** is an LR-WPANs intended for smart home use. Also adopted globally for commercial use. ZigBee LR-WPAN networks can be accessed through Wi-Fi or Bluetooth.

### Thread

+ **Thread: a low latency wireless mesh network protocol based on IPv6**.

+ Don't use proprietary gateways or translators, making them inexpensive and easier to implement and maintain than other wireless technologies.

+ Thread is used by **Google Nest Hub Max**.

### Z-Wave

+ **Z-Wave**: An interoperable, wireless mesh protocol that is based on low powered radio frequency **(RF)** communications.

+ The Z-Wave protocol uses an RF signal on the **908.2MHz* frequency and extends to **330 feet**.
+ Z-Wave is inexpensive, reliable, and simple to use. The Z-Wave protocol supports a closed network for security purposes.

+ Over 3300 types and models of home and business IoT devices are certified to use Z-Wave technology, with more than 100 million devices in use worldwide.

### Wireless mesh network (WMN)

Mesh networks are used by many popular wireless IoT network protocols, like Zigbee and Z-Wave, for device communication. Wireless mesh networks use less power than other wireless connectivity options. Wireless mesh is a decentralized network of connected wireless access points (WAP), also called nodes. Each WAP node forwards data to the next node in the network until the data reaches its destination. This network design is “self-healing,” meaning the network can recover on its own when a node fails. The other nodes will reroute data to exclude the failed node. Wireless mesh is a good option for high reliability and low power consumption, which is better for battery powered IoT devices. Wireless mesh networks can be configured to be full or partial mesh:

- **Full mesh network**: Every node can communicate with all the other nodes in the network. 

- **Partial mesh network**: Nodes can only communicate with nearby nodes.

### Bluetooth

Bluetooth is a widely used wireless network that operates at a 2.45 GHz frequency band and facilitates up to 3 Mbps connections among computing and IoT devices. Bluetooth has a range of up to 100 feet (30.6 meters) and can accommodate multiple paired connections. It is a good choice for creating a short distance wireless connection between Bluetooth enabled devices. Bluetooth is often used by computing devices to manage, configure, control, and/or collect small amounts of data from one or more close range IoT devices. For example, Bluetooth may be used to control smart home lighting or thermostat IoT devices from a smartphone.

### Near-Field Communication (NFC)

NFC is a short-range, low data, wireless communication protocol that operates on the 13.56 MHz radio frequency. NFC technology requires a physical chip (or tag) to be embedded in the IoT device. NFC chips can be found in credit and debit cards, ID badges, passports, wallet apps on smartphones (like Google Pay), and more. A contactless NFC scanner, like a Point-of-Sale (PoS) device, is used to read the chip. This scanner communication connection often requires the IoT device to be within 2 inches (6 cm) of the scanner, but some NFC chips have an 8 inch (20 cm) range. This short-distance range helps to limit wireless network security threats. However, criminals can carry a portable NFC scanner into a crowded area to pick up NFC chip data from items like credit cards stored inside purses and wallets. To protect against this type of data theft, the cards should be placed inside special NFC/RFID sleeves that make the chips unreadable until they are removed from the sleeves. NFC technology may also be used in the pairing process for Bluetooth connections.

### Long Range Wide Area Network (LoRaWAN)

LoRaWan is an open source networking protocol designed to connect battery powered, wireless IoT devices to the Internet for widely dispersed networks.

---
layout: post
title: "Network Switch"
tagline: "An Introduction to Network Switch"
categories: Networking
author: "Pasan Jayathunga"
---

**A network switch** (also called switching hub, bridging hub, officially MAC bridge) is a computer networking device that connects devices together on a computer network by using packet switching to receive, process, and forward data to the destination device.

A network switch is a multiport network bridge that uses hardware addresses to process and forward data at the data link layer (layer 2) of the OSI model. Some switches can also process data at the network layer (layer 3) by additionally incorporating routing functionality. Such switches are commonly known as layer-3 switches or multilayer switches.

Switches for Ethernet are the most common form of network switch. The first Ethernet switch was introduced by Kalpana in 1990.] Switches also exist for other types of networks including Fibre Channel, Asynchronous Transfer Mode, and InfiniBand.

Unlike less advanced repeater hubs, which broadcast the same data out of each of its ports and let the devices decide what data they need, a network switch forwards data only to the devices that need to receive it.

## Overview

A switch is a device in a computer network that connects together other devices. Multiple data cables are plugged into a switch to enable communication between different networked devices. Switches manage the flow of data across a network by transmitting a received network packet only to the one or more devices for which the packet is intended. Each networked device connected to a switch can be identified by its network address, allowing the switch to direct the flow of traffic maximizing the security and efficiency of the network.   
A switch is more intelligent than an Ethernet hub, which simply retransmits packets out of every port of the hub except the port on which the packet was received, unable to distinguish different recipients, and achieving an overall lower network efficiency. 

An Ethernet switch operates at the data link layer (layer 2) of the OSI model to create a separate collision domain for each switch port. Each device connected to a switch port can transfer data to any of the other ports at any time and the transmissions will not interfere. Because broadcasts are still being forwarded to all connected devices by the switch, the newly formed network segment continues to be a broadcast domain. Switches may also operate at higher layers of the OSI model, including the network layer and above. A device that also operates at these higher layers is known as a multilayer switch.

Segmentation involves the use of a switch to split a larger collision domain into smaller ones in order to reduce collision probability, and to improve overall network throughput. In the extreme case (i.e. micro-segmentation), each device is located on a dedicated switch port. In contrast to an Ethernet hub, there is a separate collision domain on each of the switch ports. This allows computers to have dedicated bandwidth on point-to-point connections to the network and also to run in full-duplex mode. Full-duplex mode has only one transmitter and one receiver per collision domain, making collisions impossible.
The network switch plays an integral role in most modern Ethernet local area networks (LANs). Mid-to-large sized LANs contain a number of linked managed switches. Small office/home office (SOHO) applications typically use a single switch, or an all-purpose device such as a residential gateway to access small office/home broadband services such as DSL or cable Internet. In most of these cases, the end-user device contains a router and components that interface to the particular physical broadband technology. User devices may also include a telephone interface for Voice over IP (VoIP).
 
## Role of switches in a network

Switches are most commonly used as the network connection point for hosts at the edge of a network. In the hierarchical internetworking model and similar network architectures, switches are also used deeper in the network to provide connections between the switches at the edge.

In switches intended for commercial use, built-in or modular interfaces make it possible to connect different types of networks, including Ethernet, Fibre Channel, RapidIO, ATM, ITU-T G.hn and 802.11. This connectivity can be at any of the layers mentioned. While the layer-2 functionality is adequate for bandwidth-shifting within one technology, interconnecting technologies such as Ethernet and token ring is performed more easily at layer 3 or via routing. Devices that interconnect at the layer 3 are traditionally called routers, so layer 3 switches can also be regarded as relatively primitive and specialized routers.

Where there is a need for a great deal of analysis of network performance and security, switches may be connected between WAN routers as places for analytic modules. Some vendors provide firewall, network intrusion detection, and performance analysis modules that can plug into switch ports. Some of these functions may be on combined modules.

Through port mirroring, a switch can create a mirror image of data that can go to an external device such as intrusion detection systems and packet sniffers.
A modern switch may implement power over Ethernet (PoE), which avoids the need for attached devices, such as a VoIP phone or wireless access point, to have a separate power supply. Since switches can have redundant power circuits connected to uninterruptible power supplies, the connected device can continue operating even when regular office power fails.
 
## Layer-specific functionality

Modern commercial switches use primarily Ethernet interfaces. The core function of an Ethernet switch is to provide a multiport layer 2 bridging function. Many switches also perform operations at other layers. A device capable of more than bridging is known as a multilayer switch. Switches may learn about topologies at many layers and forward at one or more layers.

- Layer 1
A layer 1 network device transfers data , but does not manage any of the traffic coming through it, an example is Ethernet hub. Any packet entering a port is repeated to the output of every other port except for the port of entry. Specifically, each bit or symbol is repeated as it flows in. A repeater hub can therefore only receive and forward at a single speed. Since every packet is repeated on every other port, packet collisions affect the entire network, limiting its overall capacity.

By the early 2000s, there was little price difference between a hub and a low-end switch. Hubs remained useful for a time for specialized applications, such supplying a copy of network traffic to a packet analyzer. A network tap may also be used for this purpose and many network switches now have a port mirroring feature that provides the same functionality.

- Layer 2

A layer 2 network device is a multiport device that uses hardware addresses, MAC address, to process and forward data at the data link layer (layer 2)
A switch operating as a network bridge may interconnect devices in a home or office. The bridge learns the MAC address of each connected device. Bridges also buffer an incoming packet and adapt the transmission speed to that of the outgoing port. While there are specialized applications, such as storage area networks, where the input and output interfaces are the same bandwidth, this is not always the case in general LAN applications. In LANs, a switch used for end user access typically concentrates lower bandwidth and uplinks into a higher bandwidth.

Interconnect between switches may be regulated using spanning tree protocol (STP) that disables links so that the resulting local area network is a tree without loops. In contrast to routers, spanning tree bridges must have topologies with only one active path between two points. Shortest path bridging is a layer 2 alternative to STP allows all paths to be active with multiple equal cost paths.

- Layer 3

A layer-3 switch can perform some or all of the functions normally performed by a router. Most network switches, however, are limited to supporting a single type of physical network, typically Ethernet, whereas a router may support different kinds of physical networks on different ports.
A common layer-3 capability is awareness of IP multicast through IGMP snooping. With this awareness, a layer-3 switch can increase efficiency by delivering the traffic of a multicast group only to ports where the attached device has signalled that it wants to listen to that group.
Layer-3 switches typically support IP routing between VLANs configured on the switch. Some layer-3 switches support the routing protocols that routers use to exchange information about routes between networks.

- Layer 4

While the exact meaning of the term layer-4 switch is vendor-dependent, it almost always starts with a capability for network address translation, and may add some type of load distribution based on TCP sessions or advanced QoS capabilities.The device may include a stateful firewall, a VPN concentrator, or be an IPSec security gateway

- Layer 7

Layer-7 switches may distribute the load based on uniform resource locators (URLs), or by using some installation-specific technique to recognize application-level transactions. A layer-7 switch may include a web cache and participate in a content delivery network (CDN)
 
## Types of switches

1. Form factors

Switches are available in many form factors, including stand-alone, desktop units which are typically intended to be used in a home or office environment outside a wiring closet; rack-mounted switches for use in an equipment rack or an enclosure; DIN rail mounted for use in industrial environments; and small installation switches, mounted into a cable duct, floor box or communications tower, as found, for example, in fibre to the office infrastructures.
Rack-mounted switches may be standalone units, stackable switches or large chassis units with swappable line cards

2. Configuration options

Unmanaged switches have no configuration interface or options. They are plug and play. They are typically the least expensive switches, and therefore often used in a small office/home office environment. Unmanaged switches can be desktop or rack mounted.

Managed switches have one or more methods to modify the operation of the switch. Common management methods include: a command-line interface (CLI) accessed via serial console, telnet or Secure Shell, an embedded Simple Network Management Protocol (SNMP) agent allowing management from a remote console or management station, or a web interface for management from a web browser. Examples of configuration changes that one can do from a managed switch include: enabling features such as Spanning Tree Protocol or port mirroring, setting port bandwidth, creating or modifying virtual LANs (VLANs), etc. Two sub-classes of managed switches are smart and enterprise managed switches.
Smart (or intelligent) switches are managed switches with a limited set of management features. Likewise "web-managed" switches are switches which fall into a market niche between unmanaged and managed. For a price much lower than a fully managed switch they provide a web interface (and usually no CLI access) and allow configuration of basic settings, such as VLANs, port-bandwidth and duplex.

Enterprise managed (or fully managed) switches have a full set of management features, including CLI, SNMP agent, and web interface. They may have additional features to manipulate configurations, such as the ability to display, modify, backup and restore configurations. Compared with smart switches, enterprise switches have more features that can be customized or optimized, and are generally more expensive than smart switches. Enterprise switches are typically found in networks with larger number of switches and connections, where centralized management is a significant savings in administrative time and effort. A stackable switch is a version of enterprise-managed switch.

### Typical switch management features

- Enable and disable ports
- Link bandwidth and duplex settings
- Quality of service configuration and monitoring
- MAC filtering and other access control list features
- Configuration of Spanning Tree Protocol (STP) and Shortest Path Bridging (SPB)   features
- Simple Network Management Protocol (SNMP) monitoring of device and link health
  Port mirroring for monitoring traffic and troubleshooting
- Link aggregation configuration to set up multiple ports for the same connection to achieve higher data transfer rates and reliability
- VLAN configuration and port assignments including IEEE 802.1Q tagging
- Network Access Control features such as IEEE 802.1X
- IGMP snooping for control of multicast traffic

### Traffic monitoring on a switched network

Unless port mirroring or other methods such as RMON, SMON or sFlow are implemented in a switch, it is difficult to monitor traffic that is bridged using a switch because only the sending and receiving ports can see the traffic. These monitoring features are rarely present on consumer-grade switches
Two popular methods that are specifically designed to allow a network analyst to monitor traffic are:

- Port mirroring – the switch sends a copy of network packets to a monitoring network connection.

- SMON – "Switch Monitoring" is described by RFC 2613 and is a protocol for controlling facilities such as port mirroring.

Another method to monitor may be to connect a layer-1 hub between the monitored device and its switch port. This will induce minor delay, but will provide multiple interfaces that can be used to monitor the individual switch port.

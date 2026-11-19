+++
title = 'Computer Science Principles Unit 2 Review D'
date = 2026-11-19T11:57:17-06:00
author = "Roy  Alvarez"
draft = false
+++

## Overview
In this section, we will learn about how the internet uses packets to transfer data to other computing devices.
We will also become familiar with how the packets get transfered over the internet.
Finally, we will understand how the internet as a system manages to not  fail when things go wrong.


### Sending Messages over the Internet
When we send data over the internet, such as checking the status of another device or fetching a webpage, the data is broken up into smaller bits of data called packets.

While a computer can store all the data in its memory at once,  transfering the data across networks is much more limited in its capacity. Thus the computer follows the Internet Protocol in order to break the data into chunks.

### Defining IP Packets
IP Packets are a structure which ccontain pieces of data to be sent over a network.

The structure is defined by the Internet Protocol, and it has two componentss:
* header
* payload (data)

#### Header
The header can contain up to 24 bytes of data or 16,777,216 bits.

It is responsible for containing all the routing information to get to the destination.

#### Payload
The payload has a variable-length size.

It is responsible for storing the actual data, such as a file, video, or status indicator.

### Routing packets 
We are now familiar with the thing that gets sent over the internet, packets. Lets understand how the packets find there way through the evergrowing internet.

The internet Protocol also describes how to route the packet from one device to the other on the internet. It is  a process of sending packets to network routers, and they proceed forward to eventually send the packet to its target destination.

Lets analyze this process into 4 parts:
1. the packet is sent to initial router.
2. the router acquires the packet.
3. router forwards the packet.
4. final router sends the packet to destination.

#### A) Packet Sent to Initial Router
The computing device sends the packet to the nearest router. The router is another computing device utilized in computer networks to forward packets along.

#### B) Router Acquires Packet
The router upon requiring the packet, looks at the packet header. It focuses on the destination field holding an     IP address to see where the packet wants to go.

Header fields include:
* source IP address
* destination IP address
* version

Describes the IP version in use.
* time to live (ttl)

Describes how long the packet remains active and useable before expiring.
* and more fields...

#### C) Router Forwards Packet
There are a many of paths that the router can send the packet, for example, another router closer to the destination, or even further away from its destination.

To decide which path to send the packet, the router relies on a forwarding table. The forwarding table stores IP address prefixes, and because IP addresses are hierarchical, these prefixes represent networks and or subnets which decrease data storage in the forwarding table.

The router looks up the most specific IP address prefix matching the destination IP address, and the router then forwards the packet onward.

#### D) Final Router sends Packet to Destination
IF there were no failures so far, the packet will eventually be at a router which knows where the destination IP address is exactly.

That destination can be a server or a computer. In whatever computing device it is, the router sends the  packet to it.

### Defining Redundancy System Design
Redundancy is the practice of having backup components in the system so that when a failure occurs, the system can continue living and will not crash as the backup components will save it.

The system design of redundancy improves reliability and availability.

#### Routing with Redundancy
The routing architecture uses a redundancy design to transfer packets from source to destination. Packets have many paths that they can move through in order to arrive at the place of interest. This is especially important for when one router or network goes down, the packets can just use a different path to arrive at the same location.

### Defining Fault Tolerant System
A fault tolerant sysetem is a system that can experience an  error or errors in its components, but still operate as normal.

One way to achieve  this type of system is by using redundancy during the design period. The architects find single points of failure in the system, that is a point that ccan crash the entire system, and use redundancy at the point to have backup components that can save the system.



## Summary
The Internet Protocol defines the packet structure, which allows the transmission of information across the internet. Packets have headers to help with routing, and payloads to store the content.
Packets are transferred through the internet by routers.  This ensures packets arrive to their target destination. With the help of the Internet Protocol and forwarding tables, the process is scalable.
Routing Packets can rely on the fact that the internet is a fault tolerant system to successfully arrive to its intended destination.





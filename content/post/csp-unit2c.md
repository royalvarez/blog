+++
title = 'Computer Science Principles Unit 2 Review C'
date = 2026-11-16T20:02:43-06:00
draft = false
author = "Roy Alvarez"
+++

## Overview
IN this section, we will explore the protocol that makes sending and recieving data in computer networks possible, and how our devices at home get connected to the network.
We will also become familiar with the hierarchy of an IP address, subnetworks, and how the the computer stores the address in memory.

### Defining the Internet Protocol
The internet protocol (IP for short) describes the utilization of IP addresses to identify unique computing devices connected to the internet.

It is responsible for all communication on the internet and handles addressing and routing.

When devices are communicating with each other, both devices need to know where to send the data. The protocol requires the sender (the initiator) to send over the receiver's IP address along with its IP address, so that the receiver can know where to send a response.

There are two main versions  of the internet protocol used today.
* IPv4

The Internet Protocol version 4 was was the first to be used on the internet.

* IPv6

The Internet Protocol version 6 is backwards compatible with  IPv4, and solves a problem in IPv4.

#### The Internet Protocol Version 4
When using IPv4, IP addresses look like the following:
* 74.125.20.113

This sequence of numbers is known as an address scheme.

You can enter the ip address into your choice of browser like you would any other website, and you would be taken to google.ccom.

##### Breaking down the IP address
In the IPv4, we can break down the IP address sequence into 4 distinct numbers, whereby each number ranges from 0 to 255 inclusive.

As humans we use the numbers 0 to 255, but computers use the corresponding binary representation.

Each number is 8 bits wide and again represent 2 to the 8th power individgally. This is where the term octet really gets used in speech.

Lets now calculate the number of unique IP addresses that IPv4 can support.

To calculate the total number of unique IP addresses, we take each 8 bit wide instance, and in IPv4 we have 4 numbers, so that is 8 bits times 4 or 32 bits wide. We can then compute the total possible connected devices on IPv4, 2 raised to the 32nd power minus 1 or 4,294,967,295 unique devices.

Just  under 4 billion and 300 million devices. And what is the current population of the world? It is around 8.3 billion. That is quite problematic for half the the people.

So I guess 1 out of 2 people get the internet, right? Well, no, thanks to IPv6.

#### The Internet Protocol version 6
When using IPv6, IP addresses look like the following:
* 2001:0db8:0000:0042:0000:8a2e:0370:7334

Notice that this schema uses 8 numbers.

##### Breaking down the IP address
The human readable version uses hexadecimal to shorten the visual representation of each number. But in the computer, each number is 16 bits wide.

If the number is 16 bits wide, then the number can range from 0 to 2 raised to the 16th power- 1 or 65,535.

Lets now calculate the number of unique IP addresses that IPv6 can support.

To calculate the total number of unique IP addresses, we take each 16 bit wide instance, and in IPv6 we have 8 numbers, so that is 16 bits times 8 or 128 bits wide. We can then compute the total possible connected devices on IPv6, 2 raised to the 128th power  minus 1 or 4,294,967,340,282,366,920,938,463,463,374,607,431,768,211,455 unique devices.

The number is so large that it is not even in my screen readers vocabulary. The IPv6 can support just under 340 undecillion connected devices.

#### Static and Dynamic IP Addresses
There are two kinds of addresses that a device can be:
* static

Static addresses stay the same.

* dynamic

Dynamic addresses change over time.

Most devices like yours and mine have dynamic IP addresses - they change throughout the day. But devices that act as servers often have static IP addresses.

The reason servers have static IP addresses is because it makes sending data more efficient. We need not to bother checking each time if the IP address that we want to send data to has changed since the last time we used it.

The people responsible for giving out IP addresses are the internet service providers (ISPs). They have a unique  range of IP addresses that they can give to their customers in their network.

#### Public and Private IP Addresses 
Your computer and my computer most likely have 2 IP addresses.

* Public IP address

A public address is the address that the external world sees like servers or your ISP.

* Private IP address

A private IP address is unique to your device, and the only one that is aware of it is the router.

The public IP address is one address that gets assigned to many devices in a network. Take  a home for example, each device connected to the home network is assigned a single public IP address to communicate to the world wide web.

If you grew up in the days of gaming where people would boot you offline, your console in the home would not be the only device that could nott connect to the network. You would get grounded because your parents had to get up from the counch as a result of a block of text that reads, "cannot connect to network." All devices in the  home were subjected to the DDOS attack because of this public IP address.

### Defining IP Address Hierarchy
By now we know what a IP address is, so what is a hierarchy? The initial meaning of hierarchy comes from the Christian religion, describing the structure or ranks of angels.

Now lets combine the two terms.

The IP address uses a specific schema, 4 numbers in IPv4, and 8 in IPv6. Each number in the schema holds some meaning. This is what we call the IP address hierarchy.

Lets use the IPv4 to understand the address hierarchy further.

#### IPv4 Address Hierarchy
* 0.123.45.67

The 4 numbers in the IPv4 address schema can be segragated into 2 sections.
1. Network administrator.
2. The home device.

The first 2 octets represent the network admin or the parent, and the last 2 octets represent a device connected to that network or a child of the parent.

Having the IP address hierarchy makes routing packets much more easier by getting source packets to its target destination. A hand wavey process looks like the following:
1. send packet to network (the first 2 octets).
2. a network router then sends the packet to the target device (the final 2 octets).

#### Subnets
Subnetworks (subnets for short) are the further splitting of the octets in the schema, and the network admin can control whether if any is present in the IP address.

Lets take the following number to express subnets:
* 141.213.127.13

This IP address can be split into 3 sections:

1. 141.213
2. 127
3. 13

The first section (2 octets) is the entire network. The next octet is a subnetwork. The last octet is the connected device.

Having more levels to the network can improve routing in the network.

#### How the computer splits octets
Recall that in the IPv4 schema, each number is 8 bits wide and there are 4 numbers in total.

The computer usually splits the 32 bits (the 4 octets) in half. Lets use the previous IP address.
1. 10001101 (141)
2. 11010101 (213)
3. 01111111 (127)
4. 00001101 (13)

They combine into this 32 bit wide sequence:
* 10001101110101010111111100001101

* The first 16 bits can be the entire network:1000110111010101
* the next 2 bits  can be the subnet: 01
* and the last 14 bits can be the connected devices: 11111100001101.

This means that there are 2 raised to the 2nd power or 4 subnets in the network, and 2 raised to the 14th or 16384 devices.

## Summary
The internet protocol is an addressing scheme that makes sending and recieving data efficient. It labels a unique address to networks and devices connected to the network. There are 2 main versions in use today, IPv4 and IPv6. Each address has a static or dynamic property, and a public and private property.
Additionally, IP addresses use a hierarchy to assign more context to the octets, which then improves routing. Depending on the network, octets can represent subnetworks for even more specificity in the network.
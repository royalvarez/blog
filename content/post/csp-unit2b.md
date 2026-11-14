+++
title = 'Computer Science Principles Unit 2 Review B'
date = 2026-11-13T21:05:35-06:00
author = "Roy Alvarez"
draft = false
+++

## Overview
In this section, we will begin to understand what we mean by a network, the physical connections in a network, and how data gets exchange through a network.

## defining computer network
  A computer network is any interconnected computing devices with the ability to send or receive data.

  Whereby a computational device is a device that can run a program.
* The internet is the largest computer network

### Constructing a Network
  All networks have a topology, "study of a particular place." In other words, there is a layout composing the network.

  For the most basic computer network, there can exist at most 2 interconnected computing devices.
This topology has only 2 problems to solve:
* physical connection
* sending data to one another in a format understood by both devices

Lets add one more device to our network shall we?
When there is 3 or more devices a new problem arises in addition to the previous 2:
* when sending data, which computer is met to recieve it?

  This can be solved via an address scheme, whereby each computer is given a unique name.

#### Popular Network topologies
1. Ring topology

  A hexagon model, whereby each device is connected to 2 devices at any given point.

2. Bus topology

  All surrounding devices only connect to one central device.

3. Tree topology

  There lies one device that is the tip of the tree, and devices that branch further out. Each branch can contain a left and right child.


Deciding a network's topology is a game of tradeoffs.
Imagine that you are a piece of data being sent over a network. What route is most optimal  to get to the targeted destination?

### Types of Networks
  Networks can be be identified based on their size and characteristics.
Lets explore three:
1. Local area network
2. Wide area network
3. data center network

#### A) Local Area Network
Local area network (LAN for short) covers very little ground. It is the most common network.
Some examples include:
* home, school

#### B) Wide Area Network
Wide area network (WAN for short) covers a large ground. It is so large in fact that it is composed of many local area networks, connected by leased telecommunication lines from a myriad of companies. This is the largest network type.
Some examples include:
* cities, countries

#### C) Data Center Network
Data center network (DCN for short) spans a building. The defining feature is that its main priority is to exchange data with minimal delay.

### Networking Protocols
When computing devices are connected to a network, they require protocols to be able to exchange data to one another.

There are many kinds of protocols solving different problems, but the main protocols that will be learning is the internet protocols during this unit.

## The Physical connections of Networks
Lets now explore the  underlying connections of networks.

### Copper cables
The first internet connections used copper cables to connect to computing devices and is still present today.

A popular copper cable is the twisted pair cable.
Twisted pair cables send data through the network by using electricity. Each pulse transmits binary information.

The receiver must understand the incoming transmission from the copper cables. In order to achieve this, they follow the ethernet standards. Hence the name ethernet cable.

Networks  that use copper cables include:
* LAN, WAN

### Fiber optic cables
Fiber optic cables cconsist of optical fiber, which allows light to transmit binary information through the network.

Like copper cables, fiber optic cables mainly follow the ethernet standards so that other computing devices can interpret the data.
  However, They are also able to transmit more data per second compared  to copper cables.

Most fiber optic cables are used in networks that are connected across the ocean.

### Wireless
Wireless connections are cards inside the computing device that transmits binary information by way of radio waves into the air.

Because radio waves are unable to travel long distances, there are wireless access points that pick up the radio waves that convert the waves back into binary information.
These wireless access points are physically connected to the network.

### Copper cable, Optic Fiber cable, and Wireless
IN reality, all of these connections work together to power the internet.
* we use wifi to connect to our home router
* the home router uses ethernet cables to connect to the city network
* and the city network uses optic fiber cables to connect to the data center networks located across the ocean

Each connection has its pros and cons.
1. copper cable
sends electricity, up to 330 feet, a bandwidth of 1 gb per second, and interference is likely.
2. optic fiber cable
sends light, up to 50 miles, a bandwidth of 26 tb per second, and can be costly.
3. wireless
sends radio waves, up to 100 feet, a bandwidth of 1.3 gb per second, and is slow.


## How streams of binary get sent over the Network
All the computational devices on the internet use electromagnetic signals to send streams of binary information.
Lets see how the binary is sent and how quickly  it can send the data.

In a greater sized Earth, computers could have plenty of wires that can represent giant numbers.
If we wanted to send the number 10, we would need a computer with 4 wires to represent the binary 1010. This requires the 1st and 3rd wire to indicate "on."

Unfortunately, the real world is small, and human space must be micro-managed.
Computers are limited on wires and thus a new way of sending data must be explored.

Instead  of using more wires, computers use a period of time to send and receive data.
For example, lets take the number 10 again. For both the compueter sender and reciever, they must both agree on a time period in order to exchange data. Lets agree on seconds.
To send 1010, we need 4 seconds. Each second will either have an electromagnetic signal or not. For when the case has a signal, 1 is sent over. When no signal is present dering the short second, 0 is sent over.

Depending on the kind of connection, the thing that models the signal is different.
* For connections that rely on electricity, like the ethernet cable, the signal is a current or voltage.
* For connections that rely on light, like fiber optic cables, the signal is the light's intensity.

The technical term for turning binary data into a time dependent signal is line coding.
We used a duration of a second as our line coding scheme, but there are many more. It just depends on what the connection calls for.

### Defining Bit Rate
Bit rate is a ratio describing the relationship between the number of bits being sent each second.
It tells us how fast bits are being sent through the connection.

While the term uses bits, there are many other groupings in use.
This is often the case since technological advances have been made since  the internet's debute in the 70s.

The most common unit to send data over the internet is megabites. Not to be confused with megabytes.

A settle but important distincction is that megabites is used to denote bit rate, ande megabytes is a unit denoting a measure of computer storage.
These units follow the metric standard, not the byte sized computer processes.
* bit = 1.
* killabite = 1000.
* megabite = 1000000.
* gigiabite = 1000000000.
* and so forth...

### defining bandwidth
Bandwidth is the maximum bit rate of the connection.
For example, say the sender sends 5 bits, 3 bits the next second, and 1 bit the last second.
In this example the bandwidth is 5 bits per second, because that was the maximum number of bits in the 3 second signal.

A term that you might here in the wild is broadband internet. It is an internet connection with a bandwidth of 256 kbs.
This kind of internet connection provides the most basic access like reading websites and writing emails. But because an average video or music file is on average 3 to 4 mbs, these mediums cannot be accessed with broadband internet.

### Defining latency
Latency is the measure of time between sending and recieving data. Its units are measured in milliseconds.

The process  is the total time of one device sending data through  the connection, the recieving device acquires the data, and then the  recieving device sends back a response to the sender.
If we send a request to my website, my website recieves the request 10 milliseconds later, and our device recieves a response 20 milliseconds after, then the latency is 30 milliseconds.

What determines latency is a myriad of factors.
* the type of connection.
* the distance between the sender and the reciever.
* the congestion ( or busyness) of the network.

The main limiting factor to latency is light. Speed of light can travel 1 foot per nanosecond.

So then, how can we improve latency?
The only things we can do when it comes to light carrying data is to:
* improve pdysical connections.
* and reduce congestions in the network.

#### Determining Internet speed
The internet speed is dependent on both bandwidth and latency.

Computers store data in packets before sending information over a network. Each request containing a packet can only be sent once the previous request was recieved.
Despite a computer having a high bandwidth, the speed of sending and recieving data is still dependent on latency.

It is common for your Internet Server Provider (ISP for short) to give a higher download speed than upload speed, as the nature of most users are not uploading data all the time.

## Summary
Computer networks are connected by various  cables. Every computer in the network follows some agreed upon standard so that data can be exchanged.

The amount of data exchange that happens per second is the bit rate of the cconnection to the network. Two Important characters that play a role in the calculation of the bit rate are bandwidth and latency.
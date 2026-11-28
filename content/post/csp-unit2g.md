+++
title = 'Computer Science Principles Unit 2 Review G'
date = 2026-11-27T18:09:06-06:00
author = "Roy Alvarez"
draft = false
+++

## Overview
In this section, we will define what a scalable system is, how the internet and the services on top of the internet use scalability, and the real world implications of this design.

### Defining Scalable System Design
A system which has been designed to be scalable is one that handles increasing data  traffic through improving resource capacity. All the while, performance is still good.

You can learn more about scalable design here: [what is scalability](https://www.geeksforgeeks.org/system-design/what-is-scalability/).

#### Scaling the Internet
Lets now see how the internet is designed to be scalable.
* Any computing device can join the internet and send data as long as they follow the protocols.
* The number of computing devices that can be connected to the internet using IPv6 is well over the amount of 8 billion users and organizations.
* Any routeing device at any time can connect to a network and assist in moving data.

##### Threats to the Internet Scalablity
Assume every person on the internet decides to download the same movie, Waum Waum goes to Earth. What could happen to the internet?

* Congestion in traffic. Network cconnections have a limited bandwidth (number of bits per second that can be sent). Networks with higher bandwidth may not be affected, but networks with smaller bandwidth may experience packet loss or severe delay.
* Limited throughput  in routers (the amound of data that can be forward per second). A consumer router like mine and yours has an average of 1GPS throughput, while a business router can have on average has up to 10 GPS throughput. If Waum Waum takes anywhere from 1 GB to 10 GB to download, it will be a bottleneck in the network.
* Wireless routers have a limit of how many devices can be connected at once to it - and 250 is usually the cap.

#### web Application Scalability
Every app on the web is running on a server somewhere. It could be Timmy's sister's basement, an underground military base, or a data center that your council brokered a deal with.

In any case, these servers are responsible for ensuring data traffic connections. If the server cannod handle 30 million people, and your app happens to be a video game with 30 million husers logging on, then most users will receive a lost connection to server message. Or, Timmy might just be sitting in front of the TV on a loading screen thanks to latency (the round trip in ms for the client to send and receive a response from the server).

#### Load Testing
Load testing is a simulation of sending high amounts of traffic in a short period of time to a system in order to evaluate how well the system performs, if at all.

The outcome also can reveal any bottlenecks or hard coded limits within the system.

#### Scaling Systems Reality Check
No system can infinitely scale. Or to say it differently, all systems have a limited capacity.

Some systems are made to not scale, and the capacity of data is set and stone.

Meanwhile, other systems are scalable and do. But the scaling capacity varies. For example, one system may be able  to scale twice as much data traffic, while another may be able to scale 200x.

When designing a system, it is important to understand the reach. Is it local, global? This will help determine a wise approach in implementing scalability into the system.

## Summary
A scalable design allows for a flexible system that can handle lots of data without any major hits to performance. The internet is a scalable system, and web services atop of the internet are also scalable. Systems that are scalable still have a capacity limit though, it is just much larger than what everyday traffic brings.
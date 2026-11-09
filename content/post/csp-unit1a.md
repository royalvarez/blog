+++
title = 'Computer Science Principles Unit 1 Review A'
date = 2026-10-27T12:36:58-05:00
author = "Roy Alvarez"
draft = true
+++

## Overview
Unit 1 is the introduction to the Computer Science Principles course offered by the great people at Khan Academy. You can start the course [here](https://www.khanacademy.org/computing/ap-computer-science-principles).
The main theme of unit 1 is to begin to understand how real world information gets transformed so that a computer can process the incoming data.
It's segregated into 8 distinct sections:
bits and bytes, binary numbers, limitation of storing numbers, storing text in binary, converting analog data to binary, lossless compression, lossy compression, and lastly, digital copyright and licenses.

## It's just bits all the way down
The first section covers how computers visualize the digital data; it's just bits all the way down.

Inside the computer, we have wires and circuits. These components are barrels of data.
Imagine a sink with a faucet that only contains one lever. You can either pull up and water comes out, or leave it down and no water comes out.
The state of the faucet has at most two options.
When the lever is being pulled up, there is an underlying mechanism signaling to another, requesting water to come through.
When the lever is down, the same mechanism is signaling and requesting no more water.

Similarly, the wires inside a computer has the same on or off state depending on the flow of electricity. This on and off state is known as a bit, short for binary digit. A bit is the smallest information stored in a computer.
A bit can either be one, which represents the electricity flows through the wire, and zero for no electricity flowing through the same wire.
But what if we had two knobs instead of a lever on the faucet, or many wires instead of just one wire? We can store many more kinds of information.

Computers don't just have one wire. Computers have a great many of wires. This is how come computers can display a character, a number, a pixel, and a sample for sound.
And finally, the barrel mentioned previously is analogous to electromechanical transistors. The job of these transistors are to store bits, and to map electrical signals to the on or off state.

However, there is one more unit to know about. While computers do store only bits, many computers process data  8 bits at a time. This grouping of 8 bits is called a byte.
A byte can contain information of a letter, number, a pixel belonging to an image, a program instruction, or a section of an audio clip. It just depends on the context.

## Summary
The fundamental idea is that ones and zeros is the language of a computer.  Each 1 and 0 is just a bit. As bits increase, the kinds of data possible to store and process also increase.
And processing information happens in byte size sequences.

[Go to next section]({{% relref "/post/csp-unit1b.md" %}})
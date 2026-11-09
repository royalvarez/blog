+++
title = 'Computer Science Principles Unit 1 Review F'
date = 2026-11-01T12:11:00-05:00
author = "Roy Alvarez"
draft = false
+++

## Overview
In this section, we will explore the concept of compression. We will begin to understand what goes on under the hood wehn are file sizes dramatically decrease after zipping it and sending it over to our programming friend.

## Storage units
Lets first talk about all the important units of measurement in computers.
1. Bit  
A bit is exactly equal to one bit.
2. Byte  
A byte is exactly equal to 8 bits. It is sometimes called a octet. A computer processes information in byte sizes.
3. Kilobyte  
A kilobyte is equal to 1024 bytes, but you may also hear 1000 bytes. It is the smallest unit of memory measurement that all modern files and programs use. As programmers, its 1024 bytes because we think in powers of 2 like the computer. 1000 pleases the metric system and those who manufactured the hard drives. 2 raised to the power of 10 = 1024 bytes.
4. Megabyte  
A megabyte is 1024 kilobytes or (2 raised to the 20) bytes.
5. Gigabyte  
A gigabyte is 1024 megabytes or (2 raised to the 30) bytes.
6 Terabyte  
A terabyte is 1024 gigabytes or (2 raised to the 40) bytes.

## Cracking Down on File Sizes
My current computer storage capacity is 1.82 terabytes. But when computers first became available to personally own, 5 megabytes was as good as you were going to get. The small storage capacity led people to invent compression algorithms which would dramatically decrease file sizes.

## The Types of Compression Algorithms
There are two types of compression algorithms, lossless and lossy - or "Tweedledum and Tweedledee."
1. Lossless  
A lossless algorithm compresses a file without losing any details. When it comes to reconstruction, the file is able to regain 100% of the information back. Think of text files and simple graphics.
2. Lossy  
A lossy algorithm compresses size noticably, but it can only do this by throwing away smaller details. Meaning, the reconstruction is never a one-to-one exact match. think of high resolution videos and audio files.

## Compressing Text Files with the Lossless Algorithm
Computers can analyze text, determine distinct repeating sequences, and replace those sequences with a shorter representation in bytes. But in order to reconstruct the text file later, the computer will need to store the mapping of values in a table to lookup.
This additional storage can cause the file size to increase if there were few sequences.
However in almost every senario, text contains various repeating character sequences. Thus compression will assist in decreasing file sizes.

## Compressing Images with the Lossless Algorithm
Lets begin by encoding an image with no compression into binary.
Imagine a black and white graphic of a plus sign. The graphic is 5 by 5.
Now take a grid and overlay it atop of the graphic.
Each square on the grid represents one pixel. There are 5 rows, and each row has 5 columns.
A pixel in this case can either be white or black. Therefore in the encoding process, we can represent white as 0, and black as 1.
This binary mapping to a pixel is called a bitmap.
The encoding would appear in binary as the following:
1. 00100
2. 00100
3. 11111
4. 00100
5. 00100

### Run Length Encoding Algorithm
IN the plus sign binary encoding example, humans would probably read the bits like 2 zeros, one one, two zeros, etc, to relay the encoding faster.
Similarly, computers can do the same, and the algorithm is named Run Length Encoding (RLE).
In RLE, the white color  is  represented first, then black is represented. For instance, the plus sign in LRE would be:
2, 1, 2
2, 1, 2
0, 5
2, 1, 2
2, 1, 2
ON average the higher dimensions of an image, will result in a better compressed file size.
But what if we were to encode an image that has a different color for each pixel? Another algorithm would have to be used since RLE only handles black and white images.
That is not to say the algorithm is dead, for example some image extensions like jpeg still use RLE, but only as final touches. Other compression algorithms have been made to better suit modern day images.

## Compressing bits with the Lossless Algorithm
We have explored text files and images, but lets talk about the underlying bit that stores all files and how its compressed.

### The Huffman Encoding Algorithm
The Huffman algorithm is the result of looking at individual characters in bit form, seeing which character appears most and least frequent, and reducing the bit representation of the more frequent characters.
This algorithm is still in use in modern day compressions. For example, fax machines and png images.

## Summary
There are two types of compression algorithms to reduce file sizes, lossless and lossy.
Lossless reconstructs files as they were before compression. Popular Lossless algorithms include RLE and Huffman encoding.

[Go to previous section]({{% relref "/post/csp-unit1e.md" %}})
[Go to next section]({{% relref "/post/csp-unit1g.md" %}})
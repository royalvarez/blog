+++
title = 'Computer Science Principles Unit 1 Review C'
date = 2026-10-30T11:28:01-05:00
author = "Roy Alvarez"
draft = false
+++

## Overview
In this section, we will learn about some of the limitations when it comes to storing numbers. You will understand number overflow and rounding errors.

## Computers are not perfect
Say we want to store a number in a programming language.
```
var halloweenNumber int
halloweenNumber = 13
```
The computer must  represent the number 13 somewhere in memory. Depending on the type of the number, whether it is an integer or floating number, the strategy in order to store the number can vary.
But say we have a number which is greater than what are computer memory can handle. The computer program will either do one of two things, throw an error, or the number will wrap back around.

## Integer and Float types
All computer programs have some concept of an integer type and float type. So what are they?
An integer type is any number without a fraction (or without a decimal point). And the float is the opposite. It is any number with a fraction (or decimal point).

## Overflow
An overflow is a common error in programming. It even has its own website named after it, [StackOverflow](https://stackoverflow.com/questions). An overflow is simply something exceeding the max boundary. For example, say a computer can only store 2 bits (the largest possible number is 3). We then store the number 4. Depending on the programming language, we will receive an overflow error, a strict enforced boundary whereby any number greater than 3 gets set to three, or wrap to zero.
Overflows are just one of those bugs where if you are not careful, [a rocket may just explode](https://en.wikipedia.org/wiki/Ariane_flight_V88).

## Roundoff
Roundoff errors only occur when we are computing floating numbers. let's take the famous repeating sequence of pi. Computers cannot store an infinite sequence in memory, so the number is rounded to the nearest  floating number. Even what we think of as easy to manage numbers like the decimal 0.4 can be difficult for the computer to store accurately. For example, the computation of 0.4 * 3 gets stored as 1.2000000000000002.

## Summary
Computers store numbers as either an integer number, or a floating number. When numbers get too big, or infinitely long, we can have unexpected behavior in our computations.

[Go to previous section]({{% relref "/post/csp-unit1b.md" %}})
[Go to next section]({{% relref "/post/csp-unit1d.md" %}})
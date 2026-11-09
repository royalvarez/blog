+++
title = 'Computer Science Principles Unit 1 Review B'
date = 2026-10-29T10:48:55-05:00
author = "Roy Alvarez"
draft = false
+++

## Overview
In this section, unit 1 will cover the basics of binary numbers. You will be able to understand the base 2 numbering system, converting from base 10 to base 2, and common patterns when working in the binary system.

## A peak behind the bit
Binary numbers can only represent a sequence of ones and zeroes. This is because binary is in base 2.

If all we have is one and zero, how the hell can we represent 2, 3 or 10? We must first back up and look back at our younger days when we were first learning to count. We humans use the base 10 numbering system. All the numbers include 0, 1, 2, 3, 4, 5, 6, 7,  8, and 9. But of course we have 10s of numbers, 100s of numbers, etc. These are placeholder values, the ones place, tenths place, hundredth place, etc. We get to these place holders by taking the base number (10) and multiplying it to the nth power - 10 ^ (raised to the) n. For instance, 10 raised to the zero power equals 1. In fact, any base raised to the zero power is 1. 10 raised to the 1st power is 10. and 10 raised to the 2nd power is 100.

We can use the same formula for binary, with the simple swapping of the base number. 2 raised to the 0 is 1 and that is the ones place. To raised to the 1st power is 10 and that is the twos place. And 2 raised to the third power is 100 and that is the fourth's place. You will notice a constant pattern, 2 keeps doubling. The next place holder would be 4 * 2 (or 8).
Please visit the unit on Khan Academy to [learn more](https://www.khanacademy.org/computing/ap-computer-science-principles).

## Strategy to convert from base 10 to base 2
A quick strategy to convert base 10 into base 2 is to determine what number are we having to convert. If the number is less than 16 2 raised to the 4th power, then write only 4 bits. If the number is less than 255 2 raised to the 8th power, write only 8 bits.
We can then start at the leftmost bit,, and compare the number with the placeholder. If the number is greater than or equal to the place holder, then the bit is equal to one. Then go ahead and subtract the number to that place holder value. Keep going until the number becomes zero. I like to call this the Bigger one cascade (Boc).

## Only a glance
It takes a glance to determine whether or not a binary number represents an even or odd number. Whenever the rightmost digit is one, the binary number is odd. And when the rightmost digit is zero, the binary number is even.
Moreover, to determine the biggest number that a binary sequence can represent, you can simply count all the digits and plug the number into the base 2 raised to the nth power and subtract 1. For example, 000, 2 raised to the third power is 8. Subtract one, and we get 7. Therefore a binary sequence with the length of 3 can at most evaluate to 7.

Wit the same pattern, and a binary sequence of all ones, the resulting number which the binary represents is the same. Taking the previous example, 111, a length of three in binary. We have the ones place filled in, the twos place filled in, and the third place filled in. That is one + 2 + 4 which evaluates to 7, the same number we got from 2 raised to the 3rd power minus 1.

## Summary
Converting to binary is the simple process of swapping bases, and realizing how the nth power factors into what place holders truly mean for when it comes time to conversion.

[Go to previous section]({{% relref "/post/csp-unit1a.md" %}})
[Go to next section]({{% relref "/post/csp-unit1c.md" %}})
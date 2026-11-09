+++
title = 'Computer Science Principles Unit 1 Review D'
date = 2026-10-30T12:47:05-05:00
author = "Roy Alvarez"
draft = false
+++

## Overview
IN this section, we will explore how computers store text, the difference gbetween a character set and character encoding, and the dominant character set and encoding used today.

## Let's Colab some Encodings
For computers to store text, it needs some help from its masters. we humans contrive meaning to the binary sequence. We can mutually agree that the sequence 100 represents the letter m. WE can then continue  this process for every character in the word mouse. M, o, u, s, and e, are all encodings of some binary sequence. In other words, these characters map to a binary number. We can give another programmer a table describing the encoding, and they can understand our insane binary speak by decoding the bits.

## Character set versus Character encoding
An important distinction to keep in mind is a character set is not the same as a character encoding. Early on in the history of encoding, these two concepts were tightly intertwine. But no longer is that the case in modern day thinking.
A character set is an encoding system which tells the computer how the character is to be stored in memory.
A character encoding takes those bytes and provides a mapping to text, essentially acting as  an interpreter to  the character set.
The same sequence of bytes can be interpreted in many different ways thanks to character encoding.

## The invention of Unicode
Unicode is a universal character set. In the set, each character gets assigned a code point and a name. A code point is just some number in base 16 that begins with U+. For example, B is assigned the code point U+0042 and its name is latin capital letter  B.
Unicode is convenient as it can unify characters across languages and thus saving memory space. This is common for eastern languages. [You can read about it here](https://en.wikipedia.org/wiki/Han_unification).

## UTF-8: our lord and savior
Remember that unicode is just a character set. A computer needs a way to interpret that character set. Here comes the holy UTF-8 encoding. UTF-8 is able to describe every single character from the [unicode standard](https://www.unicode.org/standard/standard.html). In memory, these characters are stored in sequences of 1 to 4 bytes.
For example, when we are reading a UTF-8 encoded file in a computer program, the computer can determine the number of bytes a character is based on the leading bits.
1. If the leading bit is 0, the encoding character is one byte long and belongs to the [ASCII characters](https://www.ascii-code.com/) and the 7 remaining bits determine the character.
2. If the leading 2 bits are one,  the encoding character  is 2 bytes long and belongs to the latin based languages not covered in the ASCII character set.
3. If the leading three bits are ones, the encoding character is 3 bytes long and belongs to the Asian languages.
4. If the leading 4 bits are ones, the encoding character is 4 bytes long and belongs to esoteric, ancient  characters and everyday emojis.

## Summary
Text can be represented by computers through human cooporation. There are two components to the operation of storing characters in a computer, first the character set, and then the character encoding. A popular modern character set used today is unicode, and the character encoding we use to interpret unicode is with UTF-8.

[Go to previous section]({{% relref "/post/csp-unit1c.md" %}})
[Go to next section]({{% relref "/post/csp-unit1e.md" %}})
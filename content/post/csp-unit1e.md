+++
title = 'Computer Science Principles Unit 1 Review E'
date = 2026-10-31T01:00:09-05:00
author = "Roy Alvarez"
draft = true
+++

## Overview
In this section, we will understand how continuous data gets converted into a finite sequence of bits. These  bits can then be represented by a computer. It only takes three steps: sampling, quantization, and binary encoding!

## Sampling
Let's represent a sound as data. Imagine a Cartesian bord with an x and y axis. The x axis represents time in milliseconds, and the y axis represents volts.
On the board, we overlay a sine wave since that is the graph represented by sound.
The sampling process is as easy as defining a time interval. How many milliseconds per sample? We then use the sample and obtain the points by liining up the x and y axis on where they intersect on the sine wave.
The sample rate is the inverse the sample internval - just a fancy flip of a fraction. Because we are using milliseconds, the sampling rate is per second. therefore the formula to compute the sampling rate is milliseconds (1000)/ whatever the defined time interval is.
A good sample rate is twice or more than the highest frequency of the specific signal.
Frequency is the number of cycles per second. In a sound wave, this is one full period, or a full circle. For example, a frequency of 400 hertz (frequency is measured in hertz), a good sample rate is 800 hertz or more.
Hertz is just a unit of measurement denoting a thing happening periodically.

## Quantization
The second step in the process is quantization. It takes the define intervals from sampling and begins to round the values iin volts. The process is much like the sampling but instead of focusing on x primarily, we are focusing on y.
Due to the computer's finite capabilities, there is bound to be some precision errors in the end result.

## Binary  Encoding
Now iits time to communicate to the computer. The computer has a strategy in converting the y values we got from quantization into even smaller values. It is essentially an alias reducing the amount of bits needed to store the values.
Once the computer finishes  the conversion, it will encode the sequence into binary.

The last step is telling how  the computer should read that data, so programmers can use it. The computer needs to know how we sampled the data, and how the data was encoded into binary. As in, how many bits represent each sample. This is called the bit depth.

## Replaying the Sound
When the computer needs to convert the digitalized data (bits) back into the continuous data modeling real world sound, it will use the description given during the encoding process to provide the original sound.
For the sound wave described above, the computer can estimate a smooth curve going through the points produced in the quantization step.
In order to obttain a closer approximation to the initial continuous sound, the sampling interval must be decreased (meaning more points will be present, increasing the sample rate) and lower the quantization error in a similar fashion (increasing   the bit depth, increasing storage).

## Summary
The three steps to convert continuous data into a finite sequence are: sampling, the process of turning an infinite range into a finite range, quantization, the smoothing over the values by approximation, and encoding the   dissected data. And lastly, the more accurate representaation requires a decreased sampling interval and increased storage capacity.

### Special Message
Happpy Halloween y'all. Trick or read! I am going to celebrate this Halloween year in my bath robe, sitting  in front of my computer...

[Go to previous section]({{% relref "/post/csp-unit1d.md" %}})
[Go to next section]({{% relref "/post/csp-unit1f.md" %}})
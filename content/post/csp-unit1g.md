+++
title = 'Computer Science Principles Unit 1 Review G'
date = 2026-11-03T11:24:00-05:00
author = "Roy Alvarez"
draft = false
+++

## Overview 
IN this section, we will explore the lossy compression algorithm and its tradeoffs.

## Lossy Compression 
The lossy compression removes details in order to reduce file size. This information is usually very small and the human may never notice a difference.

  Let's take images and audio to explore what I mean by unimportant information.
1. Images

  A computer can use chroma subsampling to reduce color information and keep the brightness. The reason for the reduction in color is the result of how the human eye preceives an image. brightness to  the eye is more noticible than small color differences.
JPEG is a popular file format which uses this algorithm along with several others to compress the file size.

2. Audio

  A computer can use perceptual audio coding to remove sound which is  beyond the range of the human ear.
Additional algorithms can be used to account for other human hearing limitations and remove or represent the information in smaller bits.

## Reconstructing the file
Reconstructing a lossless file will guarantee the file to return the same information as it did before compression. But with lossless, a percentage of the information will be lost at reconstruction time.
It all depends on the format you decide to choose. Each format uses different compression algorithms. For example, PNG format calls on lossless compression algorithms, while JPEG uses lossy compression algorithms that you can choose the quality of which you want to discard.

## Tradeoffs
When formats use lossy compression algorithms, it always comes at a cost. Do you want downloadable high quality images? Then you might have users with sloer internet which download speeds for higher resolution images will take longer.
Sound files are no different. Higher quality sound, the longer the download and more storage is needed in memory.

## Summary
Lossy compression algorithms can never reconstruct a file as it were before compression, but it can be as close and not noticable to the human eye.
Because of its variable nature, there is always a tradeoff in choosing the perfect lossy compression algorithm to match the occasion.

[Go to previous section]({{% relref "/post/csp-unit1f.md" %}})
[Go to next section]({{% relref "/post/csp-unit1h.md" %}})
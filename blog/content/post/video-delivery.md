---
title: "Video Delivery"
date: 2019-10-03T15:41:43+10:00

hiddenFromHomePage: false
postMetaInFooter: false

flowchartDiagrams:
  enable: false
  options: ""

sequenceDiagrams:
  enable: false
  options: ""
---

# Video

**Issue**: Heterogeneity - different capabilities of devices (bandwidth, performance)  
**Solution**: Distributed, application level infrastructure

Videos are quickly progressing sequences of images (each image is called a frame).  
Each frame is made out of pixels, which are ultimately stored (and transmitted) as bits.

> Consider a 1080p video - that is, each frame countains 1920 x 1080 pixels.  
> In total, there are 2073600 pixels.  
> As each pixel can be represented in 8 bits, a 1080p video will require 16588800 bits, or 2073600 bytes.  
> 2073600 bytes is 2025 KB, 1.98 MB.  
> A video at 30 frames per second would require 59.33 MB/s of network bandwidth.  
> &nbsp;  
> But we live in Australia, and that's <s>not possible</s> very hard to achieve without paying $$$.

There is a need for image compression - and they exist yay!

## Coding / Codecs

Smart people developed "coding methods" to reduce the redundancy within and between images.  
In turn this will decrease the number of needed bits

* Spatial Coding - Within the frame
* Temporal Coding - Between frames

## Bit Rate

The bit-rate refers to the number of bits that are required each second.  
Those smart people developed a way to alter the bit-rate of the video at different sections in time.  
(Some parts of the video might have more activity and require more information, whilst other parts may be slow and require less).

* Constant Bit Rate
* Variable Bit Rate

## Dynamic Adaptive Streaming over HTTP (DASH)

DASH is a technology to dynamically change the quality of the video.  
This is done by splitting the the video into small segments known as chunks.  
These chunks are then transcoded (either beforehand, or on the fly) to higher/lower quality/bit-rates.

When a client watches a DASH video, they first download a manifest file that contains the addresses for the different chunks and chunk qualities.

Whilst watching the video, the client will measure the client-server bandwidth, and then require the most optimal quality for the next chunk of the video

---
title: "Internet Connection Mediums"
date: 2019-09-17T10:48:44+10:00

hiddenFromHomePage: false
postMetaInFooter: false

flowchartDiagrams:
  enable: false
  options: ""

sequenceDiagrams:
  enable: false
  options: ""
---

# Internet Connection Mediums

## (Asymmetric / Symmetric) Digital Subscriber Line

DSL and ADSL internet connections operate over the copper telephone line that you might find in your house.

This works by something called **multiplexing**, where through the magic of technology, several streams of data (ie voice, and internet) can be combined and transceived (_To transmit and receive_) over one connection!

In the case of DSL connections, the voice data is multiplexed with the network data by having the **lower frequency spectrum allocated for voice data**, and the **upper frequency spectrum allocated for network data**.

Therefore, to extract the voice data a _low-pass filter_ can be applied to strip the network data.  
Likewise, to extract the network data, a _high-pass filter_ can be applied

This is done in a device called a **DSLAM**, or **D**igital **S**ubscriber **L**ine **A**ccess **M**ultiplexer, often located in telephone exchange buildings. These devices split the voice and network data, and route them into the telephone network or data network.

## The &apos;A&apos; in ADSL

As the bandwidth available over a telephone line is quite limited, the _telephone gods_ decided to allocate more of the bandwidth spectrum for downstream reception rather than upstream transmission - As most people are consumers of data, rather than producers.

As consequence, the Asymmetric Digital Subscriber Line technology was born

## Cable

Cable internet (_currently being phased out because of the nbn_) is a technology which uses coaxial cable (those things you _used_ to connect to TVs) as the transfer medium.

For coaxial cable users, **bandwidth is shared** - the more users on the network, the less bandwidth you are given (RIP peak hour).

**Frequency division multiplexing** is used (you are allocated a frequency range, and another household is allocated a different frequency range).

## Fiber

Who knows.  
It's fast (or meant to be).  
The nbn does this (or at least they're meant to be).  
Eh.

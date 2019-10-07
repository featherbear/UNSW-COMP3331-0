---
title: "Introduction to Networks"
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

# Yada-yada

- The **internet** is interconnection of a group of separate networks.

- Each device connected to a network can be called a **host**, or end system (even if it isn't "host"-ing anything)

- **Network bandwidth** refers to the maximum rate at which data can be transmitted and received over a connection.

## Devices

- **Gateway** - A device that connected two networks together
- **Modem** (_Modulator-Demodulator_) - Converts digital signals to and from analog signals
- **Router** - A device that establishes and maintains connections from and to devices on the network
- **Switch** - A device that forwards packets to its intended destination. Often used to connect more wired devices to a network
- **Hub** - A dumb switch that forwards all the packets it receives to all its connected devices
- **Access Point** - A 'wireless' switch
- **Wireless Router**
  - ... I have an access point-  
    ... I have a router-  
    ... ngh-  
    ... Wireless Router!
  - A commercialised name for a device that functions as both a router and as an access point
- **Wireless Modem**
  - A wireless router, that also has modem functionality
  - Router + Access Point + Modem

## Misc

**Packets** are blocks of data that are transmitted and received over networks.  
They contain control data such as its destination, size, type, age, checksum, etc; and the data (payload) itself.

The _size of a packet_ is limited by several factors, one being the protocol used. Consequently, a packet therefore might not contain the entirety of the data to be sent, rather just a piece of it.

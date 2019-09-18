---
title: "Lecture One"
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

## Protocols

### What&apos;s a protocol?

A protocol is a set procedure to carry out / partake in some communication / an activity. In an abstract sense, it's like saying "Hi" back to someone who greets you.

Likewise, for computers (and especially those connected to other devices) - a protocol is a set of rules dictating how devices communicate with each other.

### Internet Standards

The protocols for transmitting data over a network are collectively known as "Internet Standards"

- **RFC**: Request For Comments
- **IETF**: Internet Engineering Task Force

These protocols dictate how devices communicate with each other, and the structure of the packets that they utilise

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

---

# Finding the destination - switching

In the old times, some people worked as telephone operators - where they physically "switched" network connections on a giant switchboard to connect a caller to the receiver's network. This is known as _circuit switching_

## Circuit Switching

### Pros

- Once a circuit is established, it does not need to be re-established
- Guaranteed bandwidth
- No packet loss

### Cons

- High overhead (need a dedicated line per person)
- Single point of failure
- Inefficient
- Fixed data rate
- Connection state maintenance

---

To address the cons of circuit switching, packet switching was later invented.

## Packet Switching

In packet switching, all devices are connected together (ish). As a client no longer has direct connection to another party, some connection overhead becomes apparent, such as the destination address and other metadata. This allows multiple users to share the same line, and be connected at the same time.

**Packet switching** is most commonly used (if not having replaced circuit switching) in most network environments.

### Pros

- Scalability
- Efficient
- Resilience against failure

### Cons

- No zero time delay
- Shared connection
- Uncertainty of devices hopped onto (security!)
- Some other stuff... eh

---

# Aside: Speed over a switched network

> How fast can switched packets reach their destination?

The speed of which a packet can reach its destination can be dependent on the following:

- Link medium (Connection between devices)
- Hops (The number of devices switched through)
- Switching method

## Link Medium

The physical transmission of the packets can depend upon environmental conditions, electrical interference, and physical distance.

## Hops

Due to the nature of switching networks, packets have to 'hop' through several switching devices to reach their destination.

Ideally we want the packet to reach the destination in the least number of hops (and in the shortest time).

**Packets shouldn't stay alive forever**, and they therefore have an age, known as their TTL value (time to live). Each time the packet hops, its age is decreased by one. When its TTL is zero, the packet is dropped.

## Switching method

One method of switching is **cut-through switching**, where the packet begins to be retransmit as soon as the header of the packet is parsed. However, there may be errors in the packet header that could cause fatal errors.

For example, if the packet header signified that the payload was 677 bytes when it was only 520, the switching device would wait for an extra 157 bytes. _(\*bad stuff ensues\*)_

---

Another method is **Store-and-Forward** switching, where the entire packet is received and parsed before retransmitting to its destination.

While it is 'slower' than cut-through switching, it's arguably more efficient.

As the packet is received and parsed in full at all points of the packet's journey - the packet integrity can also be checked. There's no point transmitting packets if you already know if it's corrupted

# Multiplexing

- **FDM** - Frequency Division Modulation
- **TDM** - Time Division Modulation

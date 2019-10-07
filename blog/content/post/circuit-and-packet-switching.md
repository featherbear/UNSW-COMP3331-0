---
title: "Circuit and Packet Switching"
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

# Finding the destination - Switching

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

---

# Terms

- **Bandwidth** - the maximum capacity / possible rate
- **Throughput** - the rate at which bits are transferred
- **Loss** - When a packet cannot reach its destination (in time).
  - i.e. TTL reached zero

# Delays

- **Propagation delay** is how long it takes one bit to travel from one end of the "wire" to the other (it's proportional to the length of the wire, crudely).
- **Transmission delay** is how long it takes to get all the bits into the wire in the first place (it's packet_length/data_rate).

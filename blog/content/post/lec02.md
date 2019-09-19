---
title: "Lecture Two"
date: 2019-09-19T15:12:37+10:00

hiddenFromHomePage: false
postMetaInFooter: false

flowchartDiagrams:
  enable: false
  options: ""

sequenceDiagrams:
  enable: false
  options: ""
---

# Loss

When a packet cannot reach its destination (in time).  
i.e. TTL reached zero

# Delays

- **Propagation delay** is how long it takes one bit to travel from one end of the "wire" to the other (it's proportional to the length of the wire, crudely).
- **Transmission delay** is how long it takes to get all the bits into the wire in the first place (it's packet_length/data_rate).

# The Toolkit

- `netstat` - Print network connections, routing tables, interface statistics, masquerade connections, and multi‐cast memberships
- `netperf` - a network performance benchmark
- `dig` - DNS lookup utility
- `host` - another DNS lookup utility
- `nslookup` - yet another DNS lookup utility
- `ping` - send `ICMP ECHO_REQUEST` to network hosts
- `traceroute` - print the route packets trace to network host
- `tracepath` - trace route tool
- `mtr` - trace route tool
- `wireshark` - Interactively dump and analyze network traffic

# Terms

- **Bandwidth** - the maximum capacity / possible rate
- **Throughput** - the rate at which bits are transferred

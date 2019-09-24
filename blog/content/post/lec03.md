---
title: "Lecture Three"
date: 2019-09-24T09:16:58+10:00

hiddenFromHomePage: false
postMetaInFooter: false

flowchartDiagrams:
  enable: false
  options: ""

sequenceDiagrams:
  enable: false
  options: ""
---

## Internet Protocol Stack

- Application - _(FTP, HTTP, Skype...)_
- Transport - _(TCP, UDP)_
- Network - _(IP, routing protocols)_
- Link - _(Ethernet, 802.11, PPP)_
- Physical _(bits)_

In the stack, each layer depends on the layer below while supporting the ones above.  
However, they are all independent of each other.

Because of their independence, it is easy to add and adjust layers without worrying about the entire system. It is important to note that **there is only one unifying IP protocol**.

## Drawbacks of Independent Layers

- Layers may reimplement functionality that already exists in lower levels
- Headers start to get really big
- Information hiding (due to abstraction) may interfere with performance (e.g packet loss due to corruption vs congestion
- Layer violations
  => ends are not trusted/gains are too big

### Summary

**Source** (Host/destination) requires:

- Application
- Transport
- Network
- Link
- Physical layer

**Switch** requires:

- Link
- Physical

**Router** requires:

- Network
- Link
- Physical

---

# Application Layer

## Creating a network app

As discussed earlier, as layers are independent, we need to write programs which:

### 1. Connect to other local programs

Using **Interprocess Communication** (IPC), applications are able to communicate with other applications on the same system. These use sockets (and pipes)

### 2. Communicate over the network

Applications also need to communicate over the network (ie servers and clients).  
Over the IP network, connections have identifiers which include their _IP Address_, and a _port number_.

For example, a web server would operate on port `80` (`443` for HTTPS).

## Network Architectures

- Client-Server Architecture
- P2P Architecture

## Transport Services

Requirements:

### 1. Data Integrity

Does the app require 100% reliable data?

### 2. Throughput

Does the app require a minimum amount of throughput to be "effective"?

### 3. Timing

Does the app require low delay, while some require extremely fast connections to be "effective"

### 4. Security

Does the app require encryption and data integrity?

## Transport Layer

### TCP Protocol

- reliable transport
- flow control
- congestion control (slows down the sender then network is busy)
- Does not provide timing, minimum throughput guarantee or security
- connection oriented (setup is required between client and server)

### UDP Protocol

- unreliable data transfer
- does not provide flow control, congestion control, timing, throughput guarantee security or connection setup

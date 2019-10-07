---
title: "The TCP/IP Stack"
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

- [Application](../ip-stack-application-layer) - _(FTP, HTTP, Skype...)_
- [Transport](../ip-stack-transport-layer) - _(TCP, UDP)_
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

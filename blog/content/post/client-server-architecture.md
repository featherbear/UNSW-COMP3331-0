---
title: "Client-Server Architecture"
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

In the client-server network architecture, the network communication is modelled as clients accessing the same server to handle all of their requests.

![](https://simplecore.intel.com/itpeernetwork/wp-content/uploads/sites/38/2011/05/client_net.jpg)

As the server administrator, maintenance of the server can be considered to be easy, as all of the components and parts to the server are centralised.

# Issues

## Uptime

Should the server go offline (restart, crash, down for maintenance, loss of network connectivity), all clients will be unable to utilise services.

Thankfully, many companies have several servers for redundancy, that will take over the main server should it go offline.

## Network Load

As all clients connect to the same server, there will be a high network load from the server's ISP to the server.  
Congestion may occur during heavy usage, slowing down the speeds of all the clients.

Load balancing hardware devices exist to distribute the network load over multiple connections.

## Hardware Load

The server machine must be strong enough to handle the necessary requests.

- Fast-enough network card ( ie gigabit network, 10-gig network, infiniband, etc )
- Fast-enough CPU ( To handle processing )
- Fast-enough read/write access to data ( SSD for caching, RAM Disk )

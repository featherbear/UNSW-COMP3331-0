---
title: "Peer-to-Peer Architecture"
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

In contrast to the [client-server architecture](../client-server-architecture), everyone's machine operates as **both** a client and a server. Every machine therefore houses some service or machine that is accessed by other machines.

![](https://d3i71xaburhd42.cloudfront.net/b396bca4e06bd98a5a717dd67476a0893fb782a4/11-Figure2.1-1.png)

The P2P Architecture offers the advantage of **decentralising data and services** - in effect, providing redundancy and possible performance increases.

- Reduced Network Load - As there is no longer one single machine in which all other machines are accessing, the network load of any connection at any given time is (on average) much less
- Resource Availability - If a machine goes down, another machine will (probably) be offering the same data and services, so that the resource is still available

# Issues

## Connections

Compared to a single connection from a client to a server, the P2P architecture requires every machine to connect to every other (needed) machine.

## Routing

Because of firewalls and different network conditions, it may be hard to establish a direct connection from a 'client' to another 'client'

> See NAT Holepunching

## Resource Availability

Consider a resource that is distributed amongst 5 machines.  
The resource is split exactly into 5 chunks, and no other machine is offering those chunks.  
If one of those machines goes offline indefinitely, that resource will never be able to be retrieved

# DHT (Distributed Hash Tables)

An implication of the peer-to-peer architecture is the eminence of file sharing.  
One way files are efficiently distributed and managed are with Distributed Hash Tables.

A hash table is a data structure where values can be stored and retrieved with a given key.

In a Distributed Hash Table, this hash table is split between subsets of computers (nodes) on the network.

When a file is requested, the machine will first check its portion of its hash table for the key/value pair.  
If the key is not found, the machine will contact a different node and request the key.

This distributed form of data storage is more efficient than storing the entire hash table as:

- (Probable) Minimum performance sacrifice - the internet is fast enough these days
- Minimal space usage - each machine does not need to store the entire hash table, but just a portion of it. So it saves spave
- Limited change propagation - one change to the hash table does not require every machine to update its records

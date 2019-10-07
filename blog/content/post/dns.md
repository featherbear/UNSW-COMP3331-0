---
title: "DNS"
date: 2019-10-01T09:00:00+10:00

description: "Domain Name System"
hiddenFromHomePage: false
postMetaInFooter: false

flowchartDiagrams:
  enable: false
  options: ""

sequenceDiagrams:
  enable: false
  options: ""
---

# DNS

- Computers are identified by IP addresses, but they are not human-friendly, and are hard to remember.
- DNS servers allow host names to be mapped to IP addresses
- Multiple DNS servers are distributed
  - Local DNS
  - Remote DNS
  - Global DNS
- Scalable, autonomous, high availability
- Using a DNS also means that a hostname may be dynamic, and point to a different IP addresses (Dynamic DNS)
  - Content Delivery Networks use the DNS to find the most suitable server for the client to contact
- The local DNS map can be found at `/etc/hosts` for Unix, or `C:\Windows\system32\drivers\etc\hosts` on Windows NT computers
- DNS entries have different types, that can return a different value depending on what was requested
  - Requesting for `MX` records will return `mail.website.com`
  - Requesting for `A` records will return `111.222.333.444`

## DNS Hierarchy

- Hierarchical namespace over a flat namespace
  - `(root)`
    - `com`
      - `facebook`
      - `google`
      - ...
- Hierarchical Administration
  - Authoritative Name Servers control their nested sub-domains
  - Consider if you manage `d.c.b.a`, you may make an entry for `e.d.c.b.a => 1.2.3.4`, but if the owner of `c.b.a` sets `e.d.c.b.a => 9.8.7.6`, then `e.d.b.c.d.a` will resolve to `9.8.7.6`
- Hierarchical Servers
  - Root servers
    - Top Level TLD
    - Authoritative servers

## The DNS request flow

- Consider connecting to `a.b.c.d.e`
  - Contact root server
    - The root server will return the IP of the name server for `e`
      - Contact name server `e`
        - The name server `e` will return the IP of the name server for `d`
          - ...

## DNS Resolution

- Iterated query - if the contacted name server doesn't know the address, it can ask the client to contact another server
- Recursive query - if the contact name server doesn't know the address, it will (itself) try to resolve the address
- Caching

## DNS Resource Records (RR)

- Type - `A`, `NS`, `CNAME`, `MX`, `AAA`, `TXT`, ...
- TTL - Time To Live

# DNS Security

## DNS Cache Poisoning

When a DNS query is made, a malicious DNS servers could reply with extra information regarding domains that it does not own.

**For example**

- Client requests the IP for `google.com`
- Server replies `google.com -> 172.217.25.142; bing.com -> 172.217.25.142`
- Client sees both responses, for `google.com` **but also for `bing.com`**

The next time the client goes to `bing.com`, their DNS cache will tell them to go to `172.217.25.142`,  
rather than than the real IP address of `bing.com`

A solution to DNS Cache poisoning is for the client to only acknowledge and store DNS responses whose hostnames belong to the authoritative server. (ie only storing responses whose hostnames match `*.google.com` )

## DNSSec

DNSsec is an extension of the DNS protocol with further security features

## DoH - DNS over HTTPS

> [Read here](https://featherbear.github.io/UNSW-COMP6441/blog/post/security-everywhere-dns-over-https/)

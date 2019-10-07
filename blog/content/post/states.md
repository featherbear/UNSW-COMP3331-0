---
title: "States"
date: 2019-09-26T14:13:56+10:00

description: "Stateful and stateless communication | HTTP and Cookies"
hiddenFromHomePage: false
postMetaInFooter: false

flowchartDiagrams:
  enable: false
  options: ""

sequenceDiagrams:
  enable: false
  options: ""
---

# Stateful and Stateless Protocols

- TCP is **stateful**, meaning that each request has some sort of knowledge of prior interaction
- HTTP is **stateless**, meaning that each request is unaware of each other

```
## HTTP Request Message

- Request
- Response

Request: METHOD PATH PROTOCOL\r\n

We supply the Host header, as "Virtual Hosts" can be set up -->
```

- HTTP is all plain-text

# Session State

As HTTP(s) requests are stateless, they cannot inherently pass data between different requests. To solve this problem, we can use **cookies**.

Browser cookies are locally stored pieces of data that are appended on to every request made to the server.

This allows us to maintain a form of persistence.

We might use cookies to identify ourselves to the server (ie a user)

## Set-Cookie header

- Domain - The sites that the cookie applies to
- Name - The key (name) of the cookie
- Value - The value of the cookie
- Expires - The time that the cookie will be valid for

## Issues with Cookies

- Privacy concerns - tracking

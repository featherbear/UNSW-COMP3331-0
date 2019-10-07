---
title: "Page Speeds"
date: 2019-09-26T14:13:56+10:00

hiddenFromHomePage: false
postMetaInFooter: false

flowchartDiagrams:
  enable: false
  options: ""

sequenceDiagrams:
  enable: false
  options: ""
---

# Page Speeds

The **Page Load Time** (PLT) is the time it takes for the page to load.

Some factors include:

- Page content / structure (what's on the page)
- Protocols involved
- Network bandwidth
- Round trip time (RTT)
  - _Time for a packet to travel from client to server and pack_

## Improving the user experience

### Requesting resources

- Requesting a file takes about `2 RTT + ~response~` (seconds)
  - 1 RTT for TCP connection
  - 1 RTT for HTTP request
  - lil bit of extra time for headers
  - time to receive the contents
- Solutions are
  - Parallel (Make multiple TCP connections)
  - Reuse the TCP connection (Keep-Alive)
  - Request them all at the same time (Pipe-lining)
    - If the first file requested is very large, the other files will not be received - Head-of line blocking (HOL)
    - _Solved with HTTP2 (data sent in chunks)_

### Compression

- e.g Use thumbnails of images (smaller size)
  - Only request the full / larger image when needed

### Replication

- Content Delivery Network (mirrors of servers that are digitally closer to you)
- These are usually official servers, provided by the content creators themselves

### Caching

- low-key a poor man's CDN
- A middleman server can be placed in between the client and server, which will locally store the remote content, and redistribute it to clients. This saves time as the resource is not fetched from the server over the internet, but rather from a closer device - making requesting cached file much much much faster!
- **Hit-rate**: The percentage of requests that will be served by a caching server
  - Ideally you want a 100% hit-rate
- total delay = internet delay + access delay + lan delay
- Dealing with modified data
  - Browsers can perform a Conditional GET request, with the `If-Modified-Since` header
    - HTTP `304` Not Modified returned if not changed
  - There is also an `ETag` header

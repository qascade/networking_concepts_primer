# What is a protocol ? 
- A system/set of rules that allows two or more parties to communicate.
- A protocol is designed with a set of properties
- There's a why behind a protocol and every single protocol was designed to solve a problem. 

But the question is why do we need new protocols ? Basically any model or protocol was designed to a solve only specific set of problems and frankly you never know how that design will prevail in the ever evolving stack on which the whole internet is built. The TCP protocol that was designed back in the 60s is already pushing datacenters to its limits. Nobody considered the level of scale that datacenters touched. a

# Properties of a protocol ? (Ideas from Hussein Nasser)
## Data format
    - text based (plain text, json, xml)
    - binary (protobuf, RESP (redis serialization protocol), http2, http3). I mean they literally changed to wire for http in http2 and http3 because http literally meant to move around `hypertext` but the compatibility remains for http.

## Transfer Mode
Transfer Mode denotes here the way the data is transferred. I could be: 
    - Message Based (UDP, HTTP) 
    - Stream of bytes (TCP, WebRTC)

## Source/Destination Machine Addressing system: 
Like protocol must define where the machines are located that are trying to communicate with each other. 
    - DNS (Domain Name System), IP, MAC

## State
A protocol can be stateful or stateless. 
- Stateless = “I don’t know who you are and I don’t remember what we talked about last time. Send everything again with full context.” Examples can be (UDP, HTTP1.1, HTTP2, HTTP3)

- Stateful = “I remember you from 5 minutes ago. We can continue exactly where we left off.” Examples can be gRPC, TCP, apache thrift, websockets, ssh, ftp

there are hybrid as well like QUIC which are stateful at transport layer but stateless at application layer because it uses (HTTP/3 semantics)

In 2025, stateless is the default for almost all web APIs and frontends because it scales infinitely and works perfectly with CDNs and serverless. Stateful is reserved for real-time use cases (chat, gaming, WebSockets) or legacy protocols.

## Routing
    - Proxies
    - Gateway

## Flows and Congestion Control
    - TCP (Flow and Congestion)
    - UDP (No control)

## Error Management
    - Error Codes 
    - Retries and Timeouts.







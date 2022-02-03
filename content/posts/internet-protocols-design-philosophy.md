---
title: "The Design Philosophy of the DARPA Internet Protocols"
date: 2022-02-03T15:41:45+05:30
draft: true
---
---
Summary of David D. Clark's 1988 [paper](http://ccr.sigcomm.org/archive/1995/jan95/ccr-9501-clark.pdf) titled "The Design Philoshophy of the DARPA Internet Protocols".

#### Main idea:
\
`Why is the TCP/IP Internet protocol suite designed the way it is? ` \
This paper is an attempt to highlight some of the early reasoning behind the architectural decisions taken while designing the Internet protocols. 

Two key ideas:
1. the datagram (or connectionless service)
2. layering of separate IP and TCP layers


These ideas were not part of the original proposal. The protocol design evolved through the repeated pattern of implementation and testing before being set as standards.

#### Fundamental Goal for the DARPA Internet Architecture:
`To develop an effective technique for multiplexed utilization of existing interconnected networks.` - Essentially to interconnect existing networks.

- Original goal: to connect together the ARPANET with the ARPA packet radio network, to give users on the packet radio network access to machines on the ARPANET
- Integrating a number of separately administrated entities into a common, practical utility, rather than designing a unified system from scratch
- Multiplexing technique chosen: [packet switching](https://en.wikipedia.org/wiki/Packet_switching) (which naturally served expected applications like remote login)
- Interconnecting technique chosen: [store and forward packet switching](https://en.wikipedia.org/wiki/Store_and_forward). Existing expertise from ARPANET. 
```
Fundamental structure of the Internet: Networks would be interconnected by a layer of Internet packet switches, called gateways, and implementing a store-and-forward packet forwarding algorithm.
```

#### Second Level Goals
A more detailed set of goals for the Internet architecture:

1. uninterrupted communication, despite loss of networks / gateways
2. support for multiple types of communications service
3. accommodate a variety of networks
4. permit distributed management of its resources
5. cost-effectiveness
6. low-level effort for host attachment
7. accountability for resources used

These are listed in order of importance, and a different order would have probably resulted in an entirely different architecture. Since this was designed in a military context, survivability and flexibility with service types were given more importance than accounting.

#### Survivability in the Face of Failure


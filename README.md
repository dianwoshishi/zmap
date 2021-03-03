ZMap: The Internet Scanner
==========================

[![Build Status](https://travis-ci.org/zmap/zmap.svg?branch=travis-configuration)](https://travis-ci.org/zmap/zmap)

ZMap is a fast single packet network scanner designed for Internet-wide network
surveys. On a typical desktop computer with a gigabit Ethernet connection, ZMap
is capable scanning the entire public IPv4 address space in under 45 minutes. With
a 10gigE connection and [PF_RING](http://www.ntop.org/products/packet-capture/pf_ring/),
ZMap can scan the IPv4 address space in under 5 minutes.

ZMap operates on GNU/Linux, Mac OS, and BSD. ZMap currently has fully implemented
probe modules for TCP SYN scans, ICMP, DNS queries, UPnP, BACNET, and can send a
large number of [UDP probes](https://github.com/zmap/zmap/blob/master/examples/udp-probes/README).
If you are looking to do more involved scans, e.g.,
banner grab or TLS handshake, take a look at [ZGrab](https://github.com/zmap/zgrab),
ZMap's sister project that performs stateful application-layer handshakes.

Installation
------------

The latest stable release of ZMap is version 2.1.1 and supports Linux, macOS, and
BSD. We recommend installing ZMap from HEAD rather than using a distro package manager.

**Instructions on building ZMap from source** can be found in [INSTALL](INSTALL.md).

Usage
-----

A guide to using ZMap is found in our [GitHub Wiki](https://github.com/zmap/zmap/wiki).

IPv6 support
------------

We added IPv6 support to ZMap and include the following new probe modules:

* ICMPv6 Echo Request: `icmp6_echoscan`
* IPv6 TCP SYN (any port): `ipv6_tcp_synscan` or `ipv6_tcp_synopt`
* IPV6 UDP (any port and payload): `ipv6_udp`

You can specify the respective IPv6 probe module using the `-M` or `--probe-module` command line flag.

In addition, you need to specify the source IPv6 address with the `--ipv6-source-ip` flag and a file containing IPv6 targets using the `--ipv6-target-file` flag.
More information can be found using the `--help` flag.

As targets for your IPv6 measurements you can e.g. use addresses from our [IPv6 Hitlist Service](https://ipv6hitlist.github.io/).


License and Copyright
---------------------

ZMap Copyright 2017 Regents of the University of Michigan

Licensed under the Apache License, Version 2.0 (the "License"); you may not use
this file except in compliance with the License. You may obtain a copy of the
License at http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software distributed
under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR
CONDITIONS OF ANY KIND, either express or implied. See LICENSE for the specific
language governing permissions and limitations under the License.

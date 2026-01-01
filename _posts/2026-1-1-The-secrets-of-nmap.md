---
layout: post
title: The secrets of nmap
description: '"An introduction to the capabilities of the nmap network mapper tool."'
categories: Networking, Exploitation, Firewall bypass, nmap
---
I always heard some people say that `nmap` is not that powerful and that modern firewalls made it useless, i was thinking like this too but i discovered that `nmap` is more complex than just scanning networks unprotected by a firewall.

In fact `nmap` is the most `powerfull` and `versatile` network mapper that ever existed, in the right hands this tool can do everything from simple scans to making complex exploit. 

Some of capabilities of `nmap` are :
- ready to use exploits
- firewalls bypass capabilities
- custom packet size and content creation
- a multitude of scan type
and many more
### Some example of `nmap` capabilities
### `NULL, FIN, Xmas` scan
NULL, FIN and Xmas `TCP` port scans are less commonly used than any of the others, All three are interlinked and are used primarily as they tend to be even stealthier, relatively speaking, than a SYN "stealth" scan. Beginning with NULL scans:

As the name suggests, NULL scans (`-sN`) are when the `TCP` request is sent with no flags set at all. As per the RFC, the target host should respond with a `RST` if the port is closed.  

FIN scans (`-sF`) work in an almost identical fashion; however, instead of sending a completely empty packet, a request is sent with the FIN flag (usually used to gracefully close an active connection). Once again, `Nmap` expects a `RST` if the port is closed.

As with the other two scans in this class, Xmas scans (`-sX`) send a malformed `TCP` packet and expects a `RST` response for closed ports. It's referred to as an `xmas` scan as the flags that it sets (`PSH`, `URG` and FIN) give it the appearance of a blinking `christmas` tree when viewed as a packet capture in `Wireshark`.
### `NSE` scripts
The `Nmap Scripting Engine `(`NSE`) is an incredibly powerful addition to `Nmap`, extending its functionality quite considerably. `NSE` Scripts are written in the `Lua` programming language, and can be used to do a variety of things: from scanning for vulnerabilities, to automating exploits for them. The `NSE` is particularly useful for `reconnaisance`, however, it is well worth bearing in mind how extensive the script library is.

There are many categories available. Some useful categories include:

- `safe`:- Won't affect the target
- `intrusive`:- Not safe: likely to affect the target  
- `vuln`:- Scan for vulnerabilities
- `exploit`:- Attempt to exploit a vulnerability
- `auth`:- Attempt to bypass authentication for running services (e.g. Log into an FTP server anonymously)
- `brute`:- Attempt to `bruteforce` credentials for running services
- `discovery`:- Attempt to query running services for further information about the network (e.g. query an `SNMP` server).

A more exhaustive list can be found [here](https://nmap.org/book/nse-usage.html).
### Firewall evasion
Some of the technique we have seen are `stealth scans, along with NULL, FIN and Xmas scans`.

There are a variety of other switches which Nmap considers useful for firewall evasion. We will not go through these in detail, however, they can be found [here](https://nmap.org/book/man-bypass-firewalls-ids.html).
### Conclusion
If you want to be able to use `nmap` like a pro visit their documentations everything listed and written in an understandable language.
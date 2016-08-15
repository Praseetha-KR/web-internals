#DNS

DNS (Domain Name System) is a hierarchical decentralized naming system for computers, services, or any resource connected to the Internet or a private network. DNS servers store DNS records.

Spec: [RFC 1035](https://www.ietf.org/rfc/rfc1035.txt)

##Types of DNS Records

DNS tables consists of various types of records:

| Type      | Use                                     |
|-----------|-----------------------------------------|
| **A**     | Address Mapping: address to IP          |
| **AAAA**  | IP Version 6 Address                    |
| **CNAME** | Canonical Name: alias to domain names   |
| **MX**    | Mail exchanger                          |
| **NS**    | Name Server: domain name to name server |
| **PTR**   | Reverse-lookup Pointer                  |
| **SOA**   | Start of Authority                      |
| **SPF**   | Sender Policy Framework                 |
| **TXT**   | Text                                    |


##DNS Lookup 

When we enter a URL in address bar, browser takes the domain name and do a DNS lookup to get the corresponding IP address. DNS Lookup flow is like this:
  1. **Browser cache**: Check out `chrome://net-internals/#dns` for Google Chrome.
  2. **OS Cache**: Check out [How to view DNS cache in OSX](http://stackoverflow.com/questions/38867905/how-to-view-dns-cache-in-osx/38882447#38882447)
  3. **Router Cache** --> **ISP DNS server** or **Custom DNS Server List**
  4. Recursive check in **DNS servers** up till **Root DNS Server**

![alt text](/img/dns_lookup.jpg "DNS Lookup flow")


##DNS Message Format

![alt text](http://www.inacon.de/ph/data/images/F_126_OSOS_DNS-Message-Format_002.jpg "DNS Message Fromat")

*source: [www.inacon.de](http://www.inacon.de/ph/data/DNS/DNS-Message-Format_OS_RFC-1035.htm)*

##DNS Utilities

Usually, while creating TCP sockets, HTTP applications do system call with `getaddrinfo(host)` (which in turn call lower level functions such as `gethostbyname`). This will do DNS resolution and return IP addresses.

You can manually do DNS resolution with commands/utilities such as **host**, **nslookup**, **dig**, etc.

```
$ host google.com
google.com has address 216.58.220.46
google.com has IPv6 address 2404:6800:4007:805::200e
google.com mail is handled by 40 alt3.aspmx.l.google.com.
google.com mail is handled by 20 alt1.aspmx.l.google.com.
google.com mail is handled by 10 aspmx.l.google.com.
google.com mail is handled by 50 alt4.aspmx.l.google.com.
google.com mail is handled by 30 alt2.aspmx.l.google.com.
```

```
$ nslookup google.com
Server:		8.8.8.8
Address:	8.8.8.8#53

Non-authoritative answer:
Name:	google.com
Address: 216.58.220.46
```

```
$ dig google.com +short
216.58.220.46
```

(Check out `man` pages of those commands for more details)

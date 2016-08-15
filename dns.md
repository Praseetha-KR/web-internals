#DNS

DNS (Domain Name System) is a hierarchical decentralized naming system for computers, services, or any resource connected to the Internet or a private network.

When we enter a URL in address bar, browser takes the domain name and do a DNS lookup to get the corresponding IP address. DNS Lookup flow is like this:
  1. **Browser cache**: Check out `chrome://net-internals/#dns` for Google Chrome.
  2. **OS Cache**: Check out [How to view DNS cache in OSX](http://stackoverflow.com/questions/38867905/how-to-view-dns-cache-in-osx/38882447#38882447)
  3. **Router Cache** --> **ISP DNS server** or **Custom DNS Server List**
  4. Recursive check in **DNS servers** up till **Root DNS Server**

![alt text](/img/dns_lookup.jpg "DNS Lookup flow")

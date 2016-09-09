# web-internals
Learning how the web works.

The web we use today is built with TCP/IP protocol suite. There are 4 layers according to specs:
1. Application layer 
2. Transport layer
3. Internet layer
4. Network Interface layer

<img src="./img/tcp_ip_protocol_suite.jpg" />

Web browsers are applications which use HTTP protocol. When we type URLs in browser address bar, the following steps are executed.

1. [HTTP](/http.md)
2. [DNS](/dns.md)
3. [TCP/IP](tcp_ip.md)

<img src="./img/tcp_ip_stack_request.png" /> 

more precisely,

<img src="./img/packet_transmission.png" />

Packet transmission occurs through cables/wireless media via routers, bridges, repeaters, gateways & other networking devices, and finally reach the destination server.

Server responds to client requests with HTML/other media files.

If it is an NGINX server, routing is done based on specified routes in the config file.
NGINX can act as gateway interface to incompatible server applications. For example, routes to Flask/Django server have to be send via WSGI. After processing the request, response is send back to NGINX, which responds back to the client on the same way.

When client receive response packet, same processes are reversed.
<img src="./img/packet_reception.png" />

Now browser will start parsing & rendering the response file.
[Here is how browser renders a document](http://www.html5rocks.com/en/tutorials/internals/howbrowserswork/)
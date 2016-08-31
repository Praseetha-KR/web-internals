#TCP

## Sockets
IP address identifies which host & Port number identifies which appication for a connection. 
The IP-Port combination is strictly known as an **endpoint** and is sometimes called a **socket**.

The client-server socket pair `<client IP address, client port number, server IP address, server port number>` tuple specifies the two endpoints that uniquely identifies each TCP connection in an internet. 

Sockets can be thought of as an application's interface to the network. Typical library implementations present a Socket class, an instance of which is used to create and manage a connection. 
  - [Linux socket implementation](https://github.com/torvalds/linux/blob/master/net/socket.c)
  - [Chromium socket implementation files](https://github.com/nwjs/chromium.src/tree/a464d98d0f0ccef34bc0ce30be38a3c497c86c1a/net/socket)


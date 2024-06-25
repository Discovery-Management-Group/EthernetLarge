
# Arduino Ethernet Fork
This is a fork of the Arduino's [Ethernet](https://github.com/maxgerhardt/Ethernet) library with to create larger buffers in the W5500 chip for storing SSL certificates. 

This should probably be synced from time to time, without overwriting our change.

### Ethernet.h
Our only changes are limiting `MAX_SOCK_NUM` to 2, and uncommenting `#define ETHERNET_LARGE_BUFFERS`
```
// Configure the maximum number of sockets to support.  W5100 chips can have
// up to 4 sockets.  W5200 & W5500 can have up to 8 sockets.  Several bytes
// of RAM are used for each socket.  Reducing the maximum can save RAM, but
// you are limited to fewer simultaneous connections.
#define MAX_SOCK_NUM 2

// By default, each socket uses 2K buffers inside the Wiznet chip.  If
// MAX_SOCK_NUM is set to fewer than the chip's maximum, uncommenting
// this will use larger buffers within the Wiznet chip.  Large buffers
// can really help with UDP protocols like Artnet.  In theory larger
// buffers should allow faster TCP over high-latency links, but this
// does not always seem to work in practice (maybe Wiznet bugs?)
#define ETHERNET_LARGE_BUFFERS
```


## How to use HTTPS with Wiznet W5500
[W5500 Plain HTTP and SSL HTTPS](https://mischianti.org/esp32-ethernet-w5500-with-plain-http-and-ssl-https/)
[x509 SSL Verification Engine - used to generate 'trust-anchor.h'](https://mischianti.org/online-bearssl-certificate-trust-anchor-retriever-for-minimal-x509-verification-engine/)




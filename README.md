# notes_for_passionate_tcp-ip_socket_programming

## Part 1: beginning of network programming

### Chapter 1: understanding network programming and socket

for server:
**[socket](https://man7.org/linux/man-pages/man3/socket.3p.html) -> [bind](https://man7.org/linux/man-pages/man3/bind.3p.html) -> [listen](https://man7.org/linux/man-pages/man3/listen.3p.html) -> [accpet](https://man7.org/linux/man-pages/man3/accept.3p.html)**

for client:
**[socket](https://man7.org/linux/man-pages/man3/socket.3p.html) -> [connect](https://man7.org/linux/man-pages/man3/connect.3p.html)**

### Chapter 2: socket types and protocol configuration

```
int socket(int domain, int type, int protocol);
type: 
  SOCK_STREAM: with connection, sequence, without boundary
  SOCK_DGRAM: with boundary, without connection, sequence
```

### Chapter 3: address family and data sequence

IPv4 consists of two parts, include **internet id** and **host id**

- class A: 1 byte for internet id, 3 bytes for host id, and the range of first byte is 0~127
- class B: 2 bytes for internet id, 2 bytes for host id, and the range of first byte is 128~191
- class C: 3 bytes for internet id, 1 bytes for host id, and the range of first byte is 192~223

Endianness
- Big-Endian: store the most significant byte of a word at the smallest memory address and the least significant byte at the largest
- Little-Endian: stores the least significant byte at the smallest address


for network byte order, it's Big-Endian  

INADDR_ANY: will receive network data from same ports of different ip address

### Chapter 4: server/client based on tcp(1)

backlog: max size of waitting connection queue

### Chapter 5: server/client based on tcp(2)

tcp connect in Three-Way handshake and close in Four-Way handshake  

to ensure the overall procedure, should establish a cutomized protocol in application layer

### Chapter 6: server/client based on UDP



# Routing-and-Switching
## Layers
Short: 

All
People
Seems
To 
Need
Data 
Processing

![TCP-IP](https://user-images.githubusercontent.com/124214430/216842129-fce4deb9-656b-440d-8a34-c1343a3b3fb4.png)

![Network Devices](https://user-images.githubusercontent.com/124214430/216842113-21538572-6563-4b7c-8075-eee21c3b4782.png)

## Transformations

| 2 value | 10 value |
| --- |---|
| 10000000 | 128 |
| 11000000 | 192 |
| 11100000 | 224 |
| 11110000 | 240 |
| 11111000 | 248 |
| 11111100 | 254 |
| 11111111 | 255 |

> Double in 10 

| 6 value | 2 value | 10 value |
| --- | --- | --- |
| 0 | 0000 | 0 |
| 1 | 0001 | 1 |
| 2 | 0010 | 2 |
| 3 | 0011 | 3 |
| 4 | 0100 | 4 |
| 5 | 0101 | 5 |
| 6 | 0110 | 6 |
| 7 | 0111 | 7 | 
| 8 | 1000 | 8 |
| 9 | 1001 | 9 |
| A | 1010 | 10 |
| B | 1011 | 11 |
| C | 1100 | 12 |
| D | 1101 | 13 |
| E | 1110 | 14 |
| F | 1111 | 15 |

> Hex-2-10

### Hierarchy scheme for IP address

* 10 : 172.16.30.56
* 2  : 10101100.00010000.00011110.00111000
* 6  : AC.10.1E.38

## Protocols


* Telnet
* SSH
* FTP
* SNMP
* HTTP
* NTP
* DNS
* DHCP / BootP
* APIPA

### Typical Port Use

| TCP | UDP |
| --- | --- |
| Telnet 23 | SNMP 161 |
| SMTP 25 | TFTP 69 |
| HTTP 80 | DNS 53 |
| FTP 20, 21 | DNS 53 |
| DNS 53 | - |
| HTTPS 443 | NTP 123 |
| SSH 22 | - |
| POP3 110 | - |
| IMAP4 143 | - |

> DNS can use TCP and UDP


### TCP Segment

![TCP Segment Format](https://user-images.githubusercontent.com/124214430/216842144-1811903c-70dd-4333-aa19-2d2029e28985.png)

**Putty view**

```
TCP - Transport Control Protocol
Source Port: 5973
Destination Port: 23
Sequence Number: 145389907
Ack Number: 12420545
Offset: 5
Reserved: %000000
Code: %011000

Ack is valid
Push Request

Window: 1320
Checksum: 0x61a6
Urgent Pointer: 0
No TCP Options
TCP Data Area:
vL.5.+.5.+.5.+.5   76 4c 19 35 11 2b 19 35 11 2b 19 35 11
2b 19 35 +. 11 2b 19
Frame Check Sequence: 0x0d00000f
```

### UDP Segment

![UDP Segment](https://user-images.githubusercontent.com/124214430/216842155-ba849d62-dfb1-47b1-a8a7-707426e9c23f.png)

**Puty view**

```
UDP - User Datagram Protocol
Source Port: 1085
Destination Port: 5136
Length: 41
Checksum: 0x7a3c
UDP Data Area:
..Z......00 01 5a 96 00 01 00 00 00 00 00 11 0000 00
...C..2._C._C 2e 03 00 43 02 1e 32 0a 00 0a 00 80 43 00 80
Frame Check Sequence: 0x00000000
```

### IP Segment

![IP Header Block](https://user-images.githubusercontent.com/124214430/216842174-40ff6dae-cebc-4ffc-b0e2-bdac358be09c.png)

**Putty view**

```
IP Header - Internet Protocol Datagram
Version: 4
Header Length: 5
Precedence: 0
Type of Service: %000
Unused: %00
Total Length: 187
Identifier: 22486
Fragmentation Flags: %010 Do Not Fragment
Fragment Offset: 0
Time To Live: 60
IP Type: 0x06 TCP
Header Checksum: 0xd031
Source IP Address: 10.7.1.30
Dest. IP Address: 10.7.1.10
No Internet Datagram Options
```

> IP Type = Protocol block

#### Protocol block - Typical Port Use

| Protocol | Protocol Number |
| --- | --- |
| ICMP | 1 |
| IP in IP | 4 |
| TCP | 6 |
| UDP | 17 | 
| EIGRP | 88 |
| OSPF | 89 |
| IPv6 | 41 |
| GRE | 47 |
| Layer 2 tunnel (L2TP) | 115 |

## Sub-networks

| Class | Format | Default Sub-Mask |
| --- | --- | --- |
| A | network.node.node.node | 255.0.0.0 |
| B | network.network.node.node | 255.255.0.0 |
| C | network.network.network.node | 255.255.255.0 |

> 2^8 = 256

## Classeless Inter-Domain Routing (CIDR)

| Submask | CIDR value |
| --- | --- |
| 255.0.0.0 | /8 |
| 255.128.0.0 | /9 |
| 255.192.0.0 | /10 |
| 255.224.0.0 | /11 |
| 255.240.0.0 | /12 |
| 255.248.0.0 | /13 |
| 255.252.0.0 | /14 |
| 255.254.0.0 | /15 |
| 255.255.0.0 | /16 |
| 255.255.128.0 | /17 |
| 255.255.192.0 | /18 |
| 255.255.224.0 | /19 |
| 255.255.240.0 | /20 |
| 255.255.248.0 | /21 |
| 255.255.252.0 | /22 |
| 255.255.254.0 | /23 |
| 255.255.255.0 | /24 |
| 255.255.255.128 | /25 |
| 255.255.255.192 | /26 |
| 255.255.255.224 | /27 |
| 255.255.255.240 | /28 |
| 255.255.255.248 | /29 |
| 255.255.255.252 | /30 |

> 8 to 15 - A / 16 to 23 A/B / /24 to /30 A/B/C 

| CIDR | Mask | Bit | Block | Subnetwork | Host |
| --- | --- | --- | --- | --- | --- |
|  /25 | 128 | 1 bit inc - 7 bit not inc. | 128 | 0 and 128 | 2 subnetworks, each 126 hosts |
| /26 | 192 | 2 bit inc - 6 bit not inc. | 64 | 0, 64, 128, 192 | 4 subnetworks, each 62 hosts |
| /27 | 224 | 3 bit inc - 5 bit not inc. | 32 | 0, 32, 64, 96, 128, 160, 192, 224 | 8 subnetworks, each 30 hosts |
| /28 | 240 | 4 bit inc - 4 bit not inc. | 16 | 0, 16, 32, 48, 64, 80, 96, 112, 128, 144, 160, 176, 192, 208, 224, 240 | 16 subnetworks, each 14 hosts |
| /29 | 248 | 5 bit inc - 3 bit not inc. | 8 | 0, 8, 16, 24, 32, 40, 48, etc. | 32 subnetworks, each 6 hosts |
| /30 | 252 | 6 bit inc - 2 bit not inc. | 4 | 0, 4, 8, 12, 16, 20, 24, etc. | 64 subnetworks, each 2 hosts |

## VLSM

![VLSM Network example 2](https://user-images.githubusercontent.com/124214430/216857334-66556f0f-a0eb-4c09-8143-62fc28820090.png)

| Application | Mask | Hosts | Block |
| --- | --- | --- | --- |
| /25 | 128 | 126 | 128 |
| /26 | 192 | 62 | 64 |
| /27 | 224 | 30 | 32 |
| /28 | 240 | 14 | 16 |
| /29 | 248 | 6 | 8 |
| /30 | 252 | 2 | 4 |

| Network | Hosts | Block | Sub-network | Mask |
| --- | --- | --- | --- | --- |
| A | 14 | 16 | /28 | 240 | 
| B | 30 | 32 | /27 | 224 |
| C | 20 | 32 | /27 | 224 |
| D | 6  | 8  | /29 | 248 |
| E | 2  | 4  | /30 | 252 |
| F | 2  | 4  | /30 | 252 |
| G | 2  | 4  | /30 | 252 |
| H | 2  | 4  | /30 | 252 |

## General IP Troubleshooting 

![General IP Troubleshooting drawio - 1](https://user-images.githubusercontent.com/124214430/217102801-8eb630ca-87c9-46c8-a472-5b95d357817b.png)


1. **CMD > Ping > 127.0.0.1** (if successful - initiate, if not > install TC/IP in host).

```
C:\> ping 127.0.0.1
Pinging 127.0.0.1 with 32 bytes of data:
Reply from 127.0.0.1: bytes=32 time<1ms TTL=128
Reply from 127.0.0.1: bytes=32 time<1ms TTL=128
Reply from 127.0.0.1: bytes=32 time<1ms TTL=128
Reply from 127.0.0.1: bytes=32 time<1ms TTL=128
Ping statistics for 127.0.0.1:
Packets: Sent &x0003D; 4, Received = 4, Lost = 0 (0% loss),
Approximate round trip times in milli-seconds:
Minimum = 0 ms, Maximum = 0ms, Average = 0ms
```

2. **CMD > Ping > local host** (if successful NIC is OK, if not> > NIC cable connection check).

```
C:\> ping 172.16.10.2
Pinging 172.16.10.2 with 32 bytes of data:
Reply from 172.16.10.2: bytes=32 time<1ms TTL=128
Reply from 172.16.10.2: bytes=32 time<1ms TTL=128
Reply from 172.16.10.2: bytes=32 time<1ms TTL=128
Reply from 172.16.10.2: bytes=32 time<1ms TTL=128
Ping statistics for 172.16.10.2:
Packets: Sent &x0003D; 4, Received = 4, Lost = 0 (0% loss),
Approximate round trip times in milli-seconds:
Minimum = 0 ms, Maximum = 0ms, Average = 0ms
```

3. **CMD > Ping > Default Gateway** (if successful NIC is OK and coms with local, if not > local physical network problem detected in NIC).

```
C:\> ping 172.16.10.1
Pinging 172.16.10.1 with 32 bytes of data:
Reply from 172.16.10.1: bytes=32 time<1ms TTL=128
Reply from 172.16.10.1: bytes=32 time<1ms TTL=128
Reply from 172.16.10.1: bytes=32 time<1ms TTL=128
Reply from 172.16.10.1: bytes=32 time<1ms TTL=128
Ping statistics for 172.16.10.1:
Packets: Sent &x0003D; 4, Received = 4, Lost = 0 (0% loss),
Approximate round trip times in milli-seconds:
Minimum = 0 ms, Maximum = 0ms, Average = 0ms
```

4. **CMD > Ping > Server** (if successful communication with server established, if not potential problem with DNS settings).

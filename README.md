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

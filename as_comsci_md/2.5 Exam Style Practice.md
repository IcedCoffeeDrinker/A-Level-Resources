# 2.5 Exam-Style Questions
\# 2, 4, 5, 6

## 2.
### a)
i. A software is used that compares domain names retrieved from the client with a local database of domain name and IP pairs. The software runs on a variety of servers connected in a hierarchical fashion.
ii. A browser uses DNS. As the user enters a domain name, the browser has to communicate with domain name servers in order to resolve the domain name (find the matching IP address).
Also Email uses DNS. When sending an e-mail the domain name has to be resolved into its current IP address. A domain Name Server is contacted before sending the mail.

### b)
i. 205
   ```
   128 64 32 16 8 4 2 1
   1   1  0  0  1 1 0 1
   ```
   > X the notation is dotted decimal
   
   This would be class ~~B~~ C as the top bits are '110'.
   The 32 bits for the IPv4 address are split into four 1-byte groups, which each code for an individual number. The left-most number codes partially for the IP class, at least in the classful scheme. The notation is in denary form.

ii. Class C, as the top bits of the most significant byte are '110'.

iii. The netID addresses the LAN in which the client can then be identified through the hostID. A netID is partially determined by the location, which significantly increases the efficiency of the routing process.
   > + Addressing is hierarchical (-1 point)

### c)
203.124.16.152 / 24
$$8+8+8=24$$
Conversion of 152 to binary:
```
128 64 32 16 8 4 2 1
```
$$152 = 128+0+0+16+8+0+0+0$$
`10011000`

The 24 defines how many bits are used to determine the netID. Subtracting 24 from 32 leaves 8. As the IP address is segmented into 8 bit chunks and the NetID is to the left, this leaves the 8 bit number to the right of the netID as the hostID. The chunk in denary is separated by a dot, and the number 152 in binary is `10011000`.

## 4.
### a)
Private IP addresses can be used in private networks, also called intranets. End systems in a LAN have different private IP addresses and share the same public IP through a NAT box that connects the router to the Internet.
> + that uses TCP/IP (-1 point)

### b)
Due to the nature of the intranet all local traffic stays inside the intranet if no external IP is addressed. All traffic to the Internet has to pass through the NAT box first, which replaces the private IP with a public one. When receiving data from the Internet the NAT-box then forwards what was received on a specific port on the public IP address to the appropriate private IP inside the intranet.
> missing three points bro. They want you to go deep but also broad

## 5.
### a)
i. 11.64.255.90
   
   Hexadecimal Values:
   - 10 A
   - 11 B
   - 12 C
   - 13 D
   - 14 E
   - 15 F
   
   Conversion to Hex:
   - 11: `0000 | 1011` -> 0B
   - 64: `0100 | 0000` -> 40
   - 255: `1111 | 1111` -> FF
   - 90: `0101 | 1010` -> 5A

   Result: `B.40.FF.5A`
   > (X) not explicitly wrong, book says to keep leading zeros in hex

ii. 32 bits are segmented into four 8-bit (1-byte) groups. Each 8-bit segment codes for a denary number ranging from 0 to 255. Segments are separated with a dot and leading zeros are neglected.
   > + could add separation of hostID and netID

### b)
First the web browser checks its own DNS cache and then the cache of the OS. If the matching IP address can not be found, the browser contacts a DNS recursive resolver server that will follow through a recursive program until it has resolved the DNS. It also has a DNS cache which it first checks, though if that cache doesn't contain any matching address a root name server is contacted. This server then responds with an appropriate top-level server that matches the Top-Level Domain of the address. This server should be able to provide the IP address for the requested domain which is then forwarded over the DNS recursive resolver back to the client's browser.
> good, less detail was requested, rather definition and explanation of URL and DNS would be necessary

## 6.
### a)
IP stands for 'Internet Protocol'.

### b)
- `3.2A.6AA.BBBB` invalid: 'GAA' and 'BBBB' exceed the maximum value of 'FF' (255 in denary) per segment.
- `2.0.255.1` Valid.
  > All denary numbers range from 0-255 there are four segments, all separated with a dot. not required, bad question
- `6.0.257.6` Invalid: The value 257 exceeds 255 and cannot be represented with 8 bits.
- `A.78.F4.38` Invalid: J is not part of the hexadecimal system.

### c)
Public IP addresses are globally unique while private IP addresses are not.
Public IP addresses are exposed to the public, while private IP addresses exist in 'secure' private networks. This means that exclusively public IP addresses are used to directly communicate over the Internet.
# 2.5 Addressing
## What happens when you click on a URL?
`http://example.com/some/path`  
protocol/schema, domain name, path

### On click:
1. Transform domain name into IP-address (destination address)
	- Either it's statically configured:
		`HOSTS.txt` is a file on your local system that maps common domain names to IP-addresses. This file doesn't really get modified, but visited domain IPs are often saved in a DNS-Cache.
	- More commonly, a Domain Name System (DNS) protocol is run. Explained later
2. Connect to server through Transmission controll protocol (TCP)
	**TCP: three-way-handshake**
	
	1. client -> server: `syn` (synchronize)
	2. server -> client: `syn-ack` (synchronize-acknowledge)
	3. client -> server: `ack` (acknowledge)
	
	Connection established
	`GET...` ->
	<- `Data`
3. Send request for data with a TCP packet
	usually with a `GET /some/path/ HTTP/Server IP`
4. Recieve data from server with TCP

## DNS Domain Name Service/System
`www.fireship.io` gets mapped to -> `172.16.259.1`
(sub-domain, domain, Top-Level Domain (TLD)) -> IP-Address

- DNS is executed when a client wants to connect to a server but only has a domain name.

**Search `www.fireship.io`**
1. **Client** searches browser & system DNS-Cache (if already visited). Also has a DNS Cache.
2. If not in cache, **Client** asks **DNS Recursive Resolver** (special server) => Phonebook for Domains.
3. **DNS Recursive Resolver** asks **Root Name Server**: "seen fireship.io?"
4. **Root Name Server** replies: "don't know -> .io name server"
5. **DNS Recursive Resolver** asks **Top-Level-Domain DNS-Server** (e.g. .io name server).
6. **Top-Level-Domain DNS-Server** replies: "fireship.io is 172.16.259.1"

- Domain Name Servers are set up in a hierarchical manner, and the DNS name space is divided amongst the top-level domain name servers so that there is no overlap
- There are more than 250 top-level servers
- The DNS search process is called "name resolution"
- if the domain is under control of the connected server (e.g. a local request) then the server directly provides the matching IP address

## IP addressing
### IPv4 addressing
- developed in the 1970s,
- not enough unique addresses for all global clients
- 32 bits long (4 bytes) ~ 4 billion addresses

**original addressing scheme:**
- five rigid categories that allowed for allocating more or less bits to the hostID and the netID.
- Distinguished by a classifier, some schemes allowed for a select few IPs to have many hosts in the network.

| Class   | Class identifier | bits allocated to netID | bits for hostID |
| ------- | ---------------- | ----------------------- | --------------- |
| Class A | 0                | 7                       | 24              |
| Class B | 10               | 14                      | 16              |
| Class C | 110              | 21                      | 8               |
| ...     | ...              | ...                     | ...             |

- There can be only 128 Class A IP addresses that allow for over 16 million devices. On the other hand two million Class C IP addresses allowed for 256 hosts each.
- There weren't enough Class B addresses available, though companies required more than the 256 hostIDs class C provided.

An IP address is written as the denary equivalent of each byte:
`10000000 00001100 00000010 00011110`
↓
`128.12.2.30`
This is called **dotted decimal**

## Classless inter-domain routing (CIDR)
a fix for IPv4 addresses: flexible IPs

`11000011000011000000011000001110` / `21`
= `195.12.6.14/21`
The first 21 bits are the `netID` (len 21), the rest is the `hostID`. The `/21` is the **suffix**.
*the suffix determines the number of bits used for the netID

This scheme allows for Classes A, B, C+ to be integrated into the new system by adjusting the suffix
- Class A: suffix = 1 class identifier bit + 7 netID bits = 8
- Class B: suffix = 2 + 14 = 16
- Class C: suffix = 3 + 21 = 24

## Sub-netting
a different approach to fixing the IPv4 crises
- first three bytes used for netID, leaves 256 hostIDs for each network
- bits from the hostID can be used to create sub networks, usually the first three bits are used
- 3 bits are standard and allow for 8 subnetworks with 32 devices each

`00000000 00000000 00000000` | `000` `00000`
netID | sub-netID (can vary) | HostID

> [!WARNING]
> `xxx.xxx.xxx.255` can't be used for hosts!
> it's for broadcasting only

### Sub-net mask?
Allows to identify bits used for the netID, including the subnet IDs

- a subnet mask of `255.255.255.0` is multiplied with the IP-address and results in the netID
$$subnet \ mask \times IP \ address = netID \ (subnet \ ID)$$

- A subnetmask of `255.255.255.224` allocates three bits of the HostID to be used as the subnetID, allowing for 8 sub-networks.
	- `224` = `1110000`
	- This is a binary multiplication where the mask 'cuts out' portions.
		- $$1 \times 1 = 1$$
		- $$1 \times 0 = 0$$
		- $$0 \times 1 = 0$$

## Network address translation (NAT)
Another fix for IPv4: IPs inside LAN are only locally unique
- All clients in the LAN connect to a private network, also called intranet.
- An intranet works just like the internet and therefore has its own IP system.
- The private network connects to a "NAT box" which has a single IP with which it connects to the Internet.
- Traffic from the private network is forwarded through that single IP address of the NAT box, while traffic to the NAT box is delivered to specified individual ports of the NAT box and forwarded to the appropriate local client.

Internet <- -> [NAT box (global IP: 123.456.789.123)] <- -> [Internal Router]
Internal Router -> local client (local IP: 10.0.0.1)
Internal Router -> local client (local IP: 192.168.0.1)

There are three types of local IP addresses:
- `10.0.0.0` to `10.255.255.255`
- `172.16.0.0` to `172.31.255.255`
- `192.168.0.0` to `192.168.255.255`

You don't have to remember those numbers, but you will anyway.

## Static and dynamic IP address
- Internet Service Providers usually have more users than IPv4 addresses available to them. So private networks get assigned a global IP address when they reconnect to the ISP/Internet. This would be a dynamic IP address.
- Some users pay more so that their private network is always reachable through the same (static) IP address.

## IPv6 addressing
The internet will soon migrate to IPv6 as it offers significantly more addresses
- 128 bits per address (16 Byte)
- broken into 8 2-byte parts that code for 4 hex digits
- segments are divided by `:`
- Multiple continuous segments of zero can be shortened by `::`
- this can only happen once in any address, as the position has to be clear
- leading zeros are omitted
- IPv4 addresses can be represented in IPv6

`00F6:7C48:FFFF:0000:0000:3D20:0000:00F1`
=> `F6:7C48:FFFF::3D20:0000:F1`
- `00F6` -> `F6` (leading zeros disappear)
- `:0000:0000:` -> `::`
- `:0000:` is not shortened because `::` can only happen once.

IPv4 address:
`::192.31.20.46`
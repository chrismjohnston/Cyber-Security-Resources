# Cybersecurity Notes

## Networking

### IPV4 addresses</h3>
 * dotted decimal format
 * 4 octets (8 bits) separated by a decimal
 * The subnet mask def/ines the network part of the address and the hosts part of the address
 * The subnet mask divides the IP address into two parts. One part identifies the host, and the other the network to which it belongs.
 * The inverted binary subnet mask **added** to the binary network address creates a **sum** that is the binary equivalent of the broadcast address.
 * You can write addresses in CIDR notation:
    * the IP address of the host machine **192.168.0.73**
    * followed by the number of binary ones in the subnet mask 192.168.0.73 /24 for instance if it were **255.255.255.0**

### IPV6
* hexadecimal format
* 128 bits long
* no broadcast address
* prefix length ```prefixlen``` denotes the number of bits for the host portion of the address and the number of bits for the network portion of the address.


### Network Address Classes
|  Address Class	|   Private IP Address Range	|  Subnet Mask 	|  Networks 	|   Hosts	|
|---	|---	|---	|---	|---	|
|  Class A  	|  10.0.0.0 - 10.255.255.255 	|   255.0.0.0 /8	|  128 	|  16,777,214 	|
|  Class B	|   172.16.0.0 - 172.31.255.255	|  255.25.0.0 /16 	|   16,383	|  65,024 	|
|  Class C 	|   192.168.0.0 - 192.168.255.255	|  255.255.255.0 /24 	| 2,097,151 	|  254 	|


### MAC Addressing
* a 48 bit address that every network device is given by the manufacturer and it is burned into the hardware. This is broken into two 24-bit parts:
  * Organizationally Unique Identifier or OUI - given to the manufacturer by the IEEE
  * Assigned by vendor - 

There are [MAC address search engines](https://www.macvendorlookup.com/) that can help you identify a device manufacturer by the MAC Address.
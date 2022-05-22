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
  * Assigned by vendor

There are [MAC address search engines](https://www.wireshark.org/tools/oui-lookup.html) that can help you identify a device manufacturer by the MAC Address.

Switches will build a MAC address table locally as it learns about the devices on its network so that it can more efficiently forward traffic.

### Binary Numbering
This is a topic that seemed daunting at the outset but it's really very simple. Also, like anything in math, it gets easier the more often you do it. 

It's best to start with a table

|  2<sup>7</sup> 	|  2<sup>6</sup> 	|   2<sup>5</sup>	|   2<sup>4</sup>	|  2<sup>3</sup> 	|   2<sup>2</sup>	|  2<sup>1</sup> 	|   2<sup>0<sup>	|  
|---	|---	|---	|---	|---	|---	|---	|---	|
|  128 	|  64 	|  32 	|  16 	|  8 	|  4 	|  2 	|   1	|
|   	|   	|   	|   	|   	|   	|   	|   	|

Then another table

|  Octet 1 	|  Octet 2 	|  Octet 3 	|  Octet 4 	|
|---	|---	|---	|---	|
|   	|   	|   	|   	|

If you have a decimal number like 192.168.0.1 and we want the binary or base-2 equivalent.

First, we ask is 192 greater than or equal to 128?

If the answer is yes, we write a 1 in the first column under 128.
Then we subtract 128 from 192.

192 - 128 = 64
64 - 64 = 0
the rest is 0

|  2<sup>7</sup> 	|  2<sup>6</sup> 	|   2<sup>5</sup>	|   2<sup>4</sup>	|  2<sup>3</sup> 	|   2<sup>2</sup>	|  2<sup>1</sup> 	|   2<sup>0<sup>	|  
|---	|---	|---	|---	|---	|---	|---	|---	|
|  128 	|  64 	|  32 	|  16 	|  8 	|  4 	|  2 	|   1	|
|   1	|   1	|   0	|  0 	|   0	|  0 	|  0 	|  0 	|

Next, we repeat this process in each column entering a 1 for yes or a 0 for no. You keep moving right for until you have a number that is greater than or equal to the column header and enter 1 or reach the end.

For this IP 192.168.0.1 the binary for the first octet is 11000000

|  Octet 1 	|  Octet 2 	|  Octet 3 	|  Octet 4 	|
|---	|---	|---	|---	|
|  11000000 	|   	|   	|   	|


You the repeat this process for the remaining three octets. You end up with

|  Octet 1 	|  Octet 2 	|  Octet 3 	|  Octet 4 	|
|---	|---	|---	|---	|
|  11000000 	|  10101000 	|  00000000 	|  00000001 	|

To reverse the process you just add up the columns with 1's to get the decimal or base-10 equivalent.

Let's try this one.

10010110

|  2<sup>7</sup> 	|  2<sup>6</sup> 	|   2<sup>5</sup>	|   2<sup>4</sup>	|  2<sup>3</sup> 	|   2<sup>2</sup>	|  2<sup>1</sup> 	|   2<sup>0<sup>	|  
|---	|---	|---	|---	|---	|---	|---	|---	|
|  128 	|  64 	|  32 	|  16 	|  8 	|  4 	|  2 	|   1	|
|   1	|   0	|   0	|  1 	|   0	|  1 	|  1 	|  0 	|

128 + 16 + 4 + 2 = 150
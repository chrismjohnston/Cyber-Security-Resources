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

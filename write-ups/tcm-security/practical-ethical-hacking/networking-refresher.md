# Networking Refresher

## Introduction



* IP Addresses
* MAC Addresses
* TCP, UDP, and the Three-Way Handshake
* Common Ports and Protocols
* The OSI Model
* Subnetting



## IP Addresses

IPv4 and IPv6 - core internet addressing protocols, operating on layer 3 of OSI model.

* IPv4: `192.168.0.1` - decimal notation
  * 4 octets of 8 bits = 32 bits
  * Total IPv4 addresses:

$$
2^{32} = 4,294,967,296
$$

* IPv6: `2001:0db8:85a3:0000:0000:8a2e:0370:7334` - hexadecimal notation
  * 8 groups of 16 bits = 128 bits
  * Total IPv6 addresses:

$$
2^{128} ≈ 3.4 × 10^{38}
$$

**Key IPv6 improvements:**

* Enhanced security
* Simplified network configuration
* More efficient routing

**Transition challenges:**

* IPv4 and IPv6 not directly compatible
* Ongoing global shift from IPv4 to IPv6
* Critical for sustaining internet growth and accommodating future devices



<figure><img src="../../../.gitbook/assets/image (30).png" alt=""><figcaption></figcaption></figure>



Displays the network interface configuration and status:

```sh
ifconfig
```




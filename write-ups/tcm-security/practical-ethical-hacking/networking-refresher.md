# Networking Refresher

## Introduction

* IP Addresses
* MAC Addresses
* TCP, UDP, and the Three-Way Handshake
* Common Ports and Protocols
* The OSI Model
* Subnetting



## IP Addresses

**Layer 3 - Network**

IP (Internet Protocol) addresses, IPv4 and IPv6 - core internet addressing protocols, operating on layer 3 of OSI model.

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



<figure><img src="../../../.gitbook/assets/image (30).png" alt="Private IP Address"><figcaption></figcaption></figure>



Displays the network interface configuration and status:

{% tabs %}
{% tab title="Unix" %}
```sh
ifconfig
```
{% endtab %}

{% tab title="Windows" %}
```batch
ipconfig
```
{% endtab %}
{% endtabs %}



## MAC Addresses

**Layer 2 - Data Link**

MAC (Media Access Control) address - unique identifier assigned to network interface controllers (NICs) of network devices.

* MAC Address: `00:1A:2B:3C:4D:5E` - hexadecimal notation
  * 6 pairs of hexadecimal digits = 48 bits:
    * First 3 pairs: Manufacturer identifier
    * Last 3 pairs: Unique device identifier



Lookup devices using the first 3 pairs: [https://www.macvendorlookup.com](https://www.macvendorlookup.com/)

<figure><img src="../../../.gitbook/assets/image.png" alt="Check the Vendor details using the first 3 pairs: https://www.macvendorlookup.com"><figcaption></figcaption></figure>



## TCP, UDP, and the Three-Way Handshake

**Layer 4 - Transport**

TCP (Transmission Control Protocol) and UPD (User Datagram Protocol) - transport layer protocols in computer networks.

* TCP:
  * Connection-oriented
  * Reliable, ordered, error-checked delivery
  * Uses acknowledgment, retransmission, and flow control
  * Breaks data into packets with sequence numbers
  * Suitable for: web browsing, email, file transfer, remote login
* UDP:
  * Connectionless
  * Simpler and lightweight
  * No guaranteed delivery or packet order
  * Suitable for: streaming media, online gaming, DNS, VoIP

Three-Way Handshake - establishes TCP connections:

1. `SYN`: Client sends SYN packet with initial sequence number
2. `SYN-ACK`: Server responds with SYN-ACK packet, own sequence number
3. `ACK`: Client acknowledges with ACK packet, incremented sequence number



Capture Packet Data using Wireshark:

```sh
wireshark&
```

<figure><img src="../../../.gitbook/assets/image (1).png" alt="wireshark&#x26;"><figcaption></figcaption></figure>



## Common Ports and Protocols

TCP Protocols:

| Protocol                                   | Port |
| ------------------------------------------ | ---- |
| FTP (File Transfer Protocol)               | 21   |
| SSH (Secure Shell)                         | 22   |
| Telnet                                     | 23   |
| SMTP (Simple Mail Transfer Protocol)       | 25   |
| HTTP (Hypertext Transfer Protocol)         | 80   |
| HTTPS (Hypertext Transfer Protocol Secure) | 443  |
| POP3 (Post Office Protocol version 3)      | 110  |
| IMAP (Internet Message Access Protocol)    | 143  |
| RDP (Remote Desktop Protocol)              | 3389 |
| SMB (Server Message Block)                 | 445  |
| FTPS (FTP over SSL/TLS)                    | 990  |
| MySQL                                      | 3306 |



UDP Protocols:

<table><thead><tr><th width="411">Protocol</th><th>Port</th></tr></thead><tbody><tr><td>DHCP (Dynamic Host Configuration Protocol)</td><td>67, 68</td></tr><tr><td>SNMP (Simple Network Management Protocol)</td><td>161</td></tr><tr><td>NTP (Network Time Protocol)</td><td>123</td></tr><tr><td>TFTP (Trivial File Transfer Protocol)</td><td>69</td></tr></tbody></table>



Protocols using both TCP and UDP:

<table><thead><tr><th width="402">Protocol</th><th>Port</th></tr></thead><tbody><tr><td>DNS (Domain Name System)</td><td>53</td></tr><tr><td>LDAP (Lightweight Directory Access Protocol)</td><td>389</td></tr></tbody></table>



## The OSI Model

OSI (Open Systems Interconnection) model - conceptual framework standardizing communication system functions into seven distinct layers.

<figure><img src="../../../.gitbook/assets/image (2).png" alt="The OSI model"><figcaption></figcaption></figure>

key aspects:

* Separates complex network communication into manageable layers
* Facilitates interoperability and troubleshooting
* Conceptual model, not always reflecting exact implementations
* Useful reference for understanding network communication



## Subnetting

Subnetting - Process of dividing a network into smaller subnetworks

CIDR - Method to represent IP addresses and subnet masks



Concepts:

* Borrows bits from host portion to create subnet identifier
* Allows efficient use of IP addresses
* Facilitates network management and routing



CIDR Notation:

* Format: IP address/prefix length
* Example: 192.168.0.0/24
  * First 24 bits: Network portion
  * Remaining 8 bits: Host portion



Subnetting example:

| Original Network | 192.168.0.0/24 |
| ---------------- | -------------- |
| Subnet Mask      | 255.255.255.0  |

Subnetting (borrowing 2 bits):

| Subnet | Network Range                 | CIDR Notation    |
| ------ | ----------------------------- | ---------------- |
| 1      | 192.168.0.0 - 192.168.0.63    | 192.168.0.0/26   |
| 2      | 192.168.0.64 - 192.168.0.127  | 192.168.0.64/26  |
| 3      | 192.168.0.128 - 192.168.0.191 | 192.168.0.128/26 |
| 4      | 192.168.0.192 - 192.168.0.255 | 192.168.0.192/26 |

New Subnet Mask: `255.255.255.192`



Benefits:

* Flexible network boundaries
* Efficient address allocation
* Enhanced network organization







\-- Othmane




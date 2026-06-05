# Networking Notes

This folder contains:
- OSI model notes
- TCP/IP notes
- Wireshark labs
- Networking basics

After IP, HTTP, and DNS, follow this order for networking + cyber security. This is the best progression for internships and TryHackMe:

# Networking Roadmap

## 1. TCP & UDP

MOST important next topic.

Learn:

* 3-way handshake
* TCP flags
* SYN, ACK, FIN, RST
* UDP vs TCP
* reliability
* ports

Important ports:

* 80 HTTP
* 443 HTTPS
* 22 SSH
* 21 FTP
* 25 SMTP
* 53 DNS

Wireshark filters:

```plaintext id="k0w8r0"
tcp
udp
tcp.flags.syn == 1
```

---

# 2. OSI Model

Very important for exams/interviews.

Learn:

* all 7 layers
* protocols at each layer
* devices at each layer

Mnemonic:

```plaintext id="c4y0zh"
Please Do Not Throw Sausage Pizza Away
```

---

# 3. TCP Handshake

Deeply understand:

SYN \rightarrow SYNACK \rightarrow ACK

Learn:

* sequence number
* acknowledgment number
* connection establishment

---

# 4. ARP

Super important for Wireshark.

Learn:

* MAC resolution
* ARP request/reply
* ARP spoofing

Commands:

```bash id="jlwm49"
arp -a
```

Wireshark:

```plaintext id="jlwm3q"
arp
```

---

# 5. ICMP

Ping protocol.

Learn:

* echo request/reply
* traceroute
* TTL

Commands:

```bash id="jlwmk7"
ping google.com
traceroute google.com
```

Wireshark:

```plaintext id="jlwm2s"
icmp
```

---

# 6. DHCP

Automatic IP assignment.

Learn:

* DORA process:

Discover \rightarrow Offer \rightarrow Request \rightarrow Acknowledge

Wireshark:

```plaintext id="jlwm7n"
dhcp
```

---

# 7. HTTPS & TLS

Very important for web security.

Learn:

* SSL/TLS handshake
* certificates
* encryption
* port 443

Wireshark:

```plaintext id="jlwm5y"
tls
```

---

# 8. Subnetting

Very important for exams/interviews.

Learn:

* CIDR
* subnet mask
* private/public IP
* network & broadcast address

Examples:

```plaintext id="jlwm1n"
192.168.1.0/24
10.0.0.0/8
```

---

# 9. NAT & PAT

Learn:

* how routers translate IPs
* public vs private IPs

---

# 10. Routing Basics

Learn:

* router
* gateway
* static vs dynamic routing

Commands:

```bash id="jlwm0m"
ip route
route -n
```

---

# 11. FTP, SSH, Telnet

Important protocols.

Learn:

* FTP → file transfer
* SSH → secure remote access
* Telnet → insecure remote shell

Ports:

```plaintext id="jlwm8u"
21 FTP
22 SSH
23 Telnet
```

---

# 12. Packet Analysis (VERY IMPORTANT)

Now start real Wireshark analysis.

Practice:

* DNS traffic
* TCP handshake
* HTTP requests
* suspicious packets
* malware traffic

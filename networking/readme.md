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

Learn:

* all 7 layers
* protocols at each layer
* devices at each layer

# 3. TCP Handshake
it is a connection based protocol
before sending any data via tcp, we need to do the computer connection through three way handshake. 
SYN \rightarrow SYNACK \rightarrow ACK

Learn:

* sequence number
* acknowledgment number
* connection establishment

---
<img width="259" height="279" alt="image" src="https://github.com/user-attachments/assets/21778da8-f3df-46bc-ab0f-dfc7668f09be" />


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
* | Port    | Protocol | Service         | Why It's Important                                 |
| ------- | -------- | --------------- | -------------------------------------------------- |
| 20/21   | TCP      | FTP             | File transfer; credentials often sent in plaintext |
| 22      | TCP      | SSH             | Secure remote login; common brute-force target     |
| 23      | TCP      | Telnet          | Insecure remote access; sends data in plaintext    |
| 25      | TCP      | SMTP            | Email sending; used in phishing investigations     |
| 53      | TCP/UDP  | DNS             | Domain name resolution; DNS tunneling/exfiltration |
| 67/68   | UDP      | DHCP            | Automatic IP assignment                            |
| 69      | UDP      | TFTP            | Simple file transfer; no authentication            |
| 80      | TCP      | HTTP            | Unencrypted web traffic                            |
| 88      | TCP/UDP  | Kerberos        | Windows authentication                             |
| 110     | TCP      | POP3            | Email retrieval; insecure unless encrypted         |
| 123     | UDP      | NTP             | Time synchronization                               |
| 135     | TCP      | MS RPC          | Windows remote procedure calls                     |
| 137-139 | TCP/UDP  | NetBIOS         | Windows file and printer sharing                   |
| 143     | TCP      | IMAP            | Email retrieval                                    |
| 161/162 | UDP      | SNMP            | Network device monitoring                          |
| 389     | TCP/UDP  | LDAP            | Directory services, Active Directory               |
| 443     | TCP      | HTTPS           | Secure web traffic                                 |
| 445     | TCP      | SMB             | Windows file sharing; ransomware favorite          |
| 514     | UDP      | Syslog          | Log collection for SIEM                            |
| 636     | TCP      | LDAPS           | Secure LDAP                                        |
| 993     | TCP      | IMAPS           | Secure IMAP                                        |
| 995     | TCP      | POP3S           | Secure POP3                                        |
| 1433    | TCP      | MSSQL           | Microsoft SQL Server                               |
| 1521    | TCP      | Oracle DB       | Oracle database service                            |
| 2049    | TCP/UDP  | NFS             | Linux file sharing                                 |
| 3306    | TCP      | MySQL           | Popular database                                   |
| 3389    | TCP      | RDP             | Remote Desktop; common attack vector               |
| 5432    | TCP      | PostgreSQL      | Database service                                   |
| 5900    | TCP      | VNC             | Remote desktop access                              |
| 5985    | TCP      | WinRM           | Windows remote management                          |
| 6379    | TCP      | Redis           | In-memory database                                 |
| 8080    | TCP      | HTTP Alternate  | Often used by web applications                     |
| 8443    | TCP      | HTTPS Alternate | Secure web applications                            |
| 9200    | TCP      | Elasticsearch   | SIEM and log storage systems                       |


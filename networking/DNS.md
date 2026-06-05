# DNS Notes

## What is DNS?

DNS (Domain Name System) converts domain names into IP addresses.

Example:

google.com → 142.250.193.14

DNS is called the “phonebook of the internet”.

---

# DNS Working

1. User enters domain name.
2. Browser checks local cache.
3. Query sent to DNS Resolver.
4. Resolver contacts:

   * Root Server
   * TLD Server
   * Authoritative Server
5. IP address returned.
6. Browser connects to website.

---

# DNS Record Types

## A Record

Maps domain → IPv4 address.

Command:

```bash
nslookup -type=A google.com
```

---

## AAAA Record

Maps domain → IPv6 address.

Command:

```bash
nslookup -type=AAAA google.com
```

---

## MX Record

Mail server record.

Command:

```bash
nslookup -type=MX google.com
```

---

## TXT Record

Stores text information.

Used for:

* SPF
* DKIM
* Verification

Command:

```bash
nslookup -type=TXT google.com
```

---

## NS Record

Shows authoritative DNS servers.

Command:

```bash
nslookup -type=NS google.com
```

---

## PTR Record

Used for reverse DNS lookup.

IP → 

Command:

<img width="821" height="123" alt="image" src="https://github.com/user-attachments/assets/17ebaa5b-6c3c-4bf4-9573-53c9779c5c9a" />


# DNS Ports

| Protocol          | Port   |
| ----------------- | ------ |
| DNS               | 53 UDP |
| DNS Zone Transfer | 53 TCP |

---

# Linux DNS Commands

## nslookup

```bash
nslookup google.com
```

## dig

```bash
dig google.com
```

## host

```bash
host google.com
```

---

# Reverse DNS Lookup

```bash
dig -x 8.8.8.8
```

---

# DNS Zone Transfer

```bash
dig axfr @nameserver domain.com
```

---

# Wireshark DNS Filters

## Show DNS Traffic

```plaintext
dns
```

## A Records

```plaintext
dns.a
```

## AAAA Records

```plaintext
dns.aaaa
```

## TXT Records

```plaintext
dns.txt
```

---

# DNS Attacks

## DNS Spoofing

Fake DNS responses redirect users to malicious websites.

## DNS Cache Poisoning

Attacker inserts fake records into DNS cache.

## DNS Tunneling

Data transferred through DNS traffic.

## DNS Exfiltration

Sensitive data stolen through DNS queries.

Example:

secretdata.attacker.com

---

# Important Exam Points

* DNS uses Port 53.
* DNS mainly uses UDP.
* A → IPv4
* AAAA → IPv6
* MX → Mail Server
* TXT → Text Data
* PTR → Reverse Lookup

---

# Quick Revision Table

| Record | Purpose          |
| ------ | ---------------- |
| A      | IPv4 Address     |
| AAAA   | IPv6 Address     |
| MX     | Mail Server      |
| TXT    | Text Information |
| NS     | Name Server      |
| PTR    | Reverse Lookup   |
| CNAME  | Alias Record     |

Save this as:

```plaintext id="e6l6yt"
DNS/dns-notes.md
```

Then push:

```bash id="q4zk2v"
git add .
git commit -m "Added DNS notes"
git push
```


Nmap (Network Mapper) is an open-source network scanning tool used to discover hosts, services, open ports, operating systems, and vulnerabilities on a network.
It is one of the most widely used tools in cybersecurity for reconnaissance and enumeration.
## Why Use Nmap?

- Discover live hosts
- Identify open ports
- Detect running services
- Determine service versions
- Identify operating systems
- Perform network inventory
- Security auditing

## Basic Syntax

nmap <target>
nmap 192.168.1.1
nmap scanme.nmap.org

## Port States

| State           | Meaning                                             |
| --------------- | --------------------------------------------------- |
| Open            | Service is actively accepting connections           |
| Closed          | Port is reachable but no service is listening       |
| Filtered        | Firewall prevents Nmap from determining state       |
| Unfiltered      | Port is accessible but state cannot be determined   |
| Open|Filtered   | Nmap cannot distinguish between open and filtered   |
| Closed|Filtered | Nmap cannot distinguish between closed and filtered |

## Common Scans

### TCP Connect Scan
nmap -sT <target>
* Completes full TCP handshake
* Does not require root privileges

### SYN Scan (Stealth Scan)
sudo nmap -sS <target>

* Sends SYN packet
* Faster than TCP Connect
* Requires root privileges
* Most commonly used scan

### UDP Scan
sudo nmap -sU <target>
* Scans UDP ports
* Slower than TCP scans

### Ping Scan
nmap -sn <target>

* Checks if hosts are online
* Does not perform port scanning

## Port Specification

### Scan Specific Port
nmap -p 80 <target>

### Scan Multiple Ports
nmap -p 22,80,443 <target>

### Scan Port Range
nmap -p 1-1000 <target>

### Scan All Ports
nmap -p- <target>

## Service Version Detection
nmap -sV <target>

Example Output:

22/tcp open ssh OpenSSH 9.0
80/tcp open http Apache 2.4.52

* Identifies software versions
* Helps determine potential vulnerabilities

---

## Operating System Detection

sudo nmap -O <target>

* Attempts to identify target operating system

Examples:

* Linux
* Windows
* FreeBSD
* Cisco IOS


## Aggressive Scan

```bash
sudo nmap -A <target>
```

Includes:

* OS detection
* Version detection
* Script scanning
* Traceroute

Useful for quick reconnaissance.

---

## Timing Templates

### Slow Scan

```bash
nmap -T1 <target>
```

### Normal Scan

```bash
nmap -T3 <target>
```

### Fast Scan

```bash
nmap -T4 <target>
```

### Very Fast Scan

```bash
nmap -T5 <target>
```

---

## Output Options

### Save Normal Output

```bash
nmap -oN scan.txt <target>
```

### Save XML Output

```bash
nmap -oX scan.xml <target>
```

### Save All Formats

```bash
nmap -oA scan <target>
```

Generates:

* scan.nmap
* scan.xml
* scan.gnmap

---

## NSE (Nmap Scripting Engine)

NSE allows automation of security checks.

### Default Scripts

```bash
nmap -sC <target>
```

### Run Specific Script

```bash
nmap --script http-title <target>
```

### Vulnerability Scan

```bash
nmap --script vuln <target>
```

---

## Useful Scan Combinations

### Fast Enumeration

```bash
nmap -T4 -F <target>
```

### Service Detection

```bash
nmap -sV <target>
```

### Full Port Scan

```bash
nmap -p- <target>
```

### Full Recon Scan

```bash
sudo nmap -sS -sV -O -A <target>
```

---

## Common Ports

| Port  | Service |
| ----- | ------- |
| 20/21 | FTP     |
| 22    | SSH     |
| 23    | Telnet  |
| 25    | SMTP    |
| 53    | DNS     |
| 80    | HTTP    |
| 110   | POP3    |
| 143   | IMAP    |
| 443   | HTTPS   |
| 445   | SMB     |
| 3306  | MySQL   |
| 3389  | RDP     |

---

## Nmap Workflow

1. Discover live hosts

```bash
nmap -sn <network>
```

2. Scan open ports

```bash
nmap -p- <target>
```

3. Detect services

```bash
nmap -sV <target>
```

4. Run default scripts

```bash
nmap -sC <target>
```

5. Gather detailed information

```bash
nmap -A <target>
```


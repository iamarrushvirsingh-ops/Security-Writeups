# Pre Security: Quick Revision Notes

> **Note:** This revision sheet was made with the help of AI, based on my own room notes. It's meant for fast revision; the full explanations are in the individual room files.

Use this to revise the whole Pre Security path in about 15 minutes. Then test yourself with the [self-test questions](pre-security-self-test.md).

---

## 1. Hacker Mindset

- **Pentest** = authorized attempt to find and exploit weaknesses within a **scope** (the allowed boundaries).
- **Red teaming** = authorized simulation of a real attacker to test the defences.
- **Vulnerability** = the weakness. **Exploit** = the method used to abuse it.
- Mindset: ask "what if it doesn't work as intended?", try unexpected inputs, chain small flaws together.
- Tools seen: **Gobuster** (finds hidden directories), **Hydra** (automated password guessing).

## 2. Computer Fundamentals

| Part | Job | Analogy |
| --- | --- | --- |
| CPU | Does calculations and logic | Brain |
| RAM | Fast short-term memory, wiped on power-off | Short-term memory |
| SSD / HDD | Long-term storage (SSD fast, HDD cheap and large) | Long-term memory |
| GPU | Turns data into visuals | Visual cortex |
| PSU | Supplies power | Heart and lungs |
| Motherboard | Connects everything | Skeleton and nerves |

**Boot order:** Power button → UEFI/BIOS starts → POST (self-test) → choose boot device → bootloader loads the OS into RAM → OS takes control.

## 3. Operating Systems

- **CIA triad**: **C**onfidentiality (only the right people see it), **I**ntegrity (not tampered with), **A**vailability (usable when needed).
- **3 ways to authenticate**: something you **know** (password), **are** (fingerprint), **have** (phone).
- **Least privilege**: give users only the access they need.
- Common weaknesses: weak passwords, weak file permissions, malware (Trojans, ransomware).
- **Windows accounts**: Guest (very limited), Standard (everyday use), Administrator (full control).
- **Windows Defender Firewall profiles**: Domain, Private, Public.

## 4. Command Line Cheat Sheet

| Task | Linux | Windows |
| --- | --- | --- |
| Where am I? | `pwd` | `cd` |
| List files | `ls` (`ls -al` for hidden) | `dir` (`dir /a` for hidden) |
| Find a file | `find / -name file.txt` | `dir /s file.txt` |
| Read a file | `cat file.txt` | `type file.txt` |
| Who am I? | `whoami` | `whoami` |
| System info | `uname -a`, `/etc/os-release` | `systeminfo` |
| Disk space | `df -h` | — |
| Network info | `ip a` | `ipconfig` |
| Remote login | `ssh user@ip` | — |
| Switch user | `su - username` | — |

## 5. Networking Basics

- **MAC address**: 12 hex characters, burned into the network card. The first half identifies the maker. It can be spoofed, so it's not safe for authentication.
- **Ping** uses **ICMP** echo request and echo reply to test a connection.
- **Topologies**: Star (central switch, scalable, costly), Bus (one backbone cable, single point of failure), Ring (circle, one direction).
- **Subnetting**: splitting a network into smaller networks using a **subnet mask**.
- **ARP**: finds the MAC address that belongs to an IP address (ARP request → ARP reply → saved in the ARP cache).
- **DHCP**: hands out IP addresses automatically: **D**iscover → **O**ffer → **R**equest → **A**CK (remember "DORA").

## 6. OSI Model (7 layers, bottom to top)

| # | Layer | What happens | Example |
| --- | --- | --- | --- |
| 7 | Application | What the user interacts with | HTTP, DNS |
| 6 | Presentation | Standard format, encryption | HTTPS encryption |
| 5 | Session | Opens, keeps and closes connections | Sessions |
| 4 | Transport | TCP or UDP, ports | TCP, UDP |
| 3 | Network | Routing with IP addresses | Routers, OSPF, RIP |
| 2 | Data Link | MAC addresses, frames | Switches, NIC |
| 1 | Physical | Electrical signals (1s and 0s) | Cables |

Memory trick (top to bottom): **A**ll **P**eople **S**eem **T**o **N**eed **D**ata **P**rocessing.

**TCP/IP model (4 layers):** Application, Transport, Internet, Network Interface.

## 7. Packets, TCP and UDP

- **Packet** = layer 3 (IP addresses). **Frame** = layer 2 (MAC addresses).
- **Encapsulation** = each layer adds its own header as data goes down; decapsulation removes them.
- Key IP header fields: **TTL** (expiry), **checksum** (integrity), **source** and **destination** address.

| | TCP | UDP |
| --- | --- | --- |
| Connection | Yes (three-way handshake) | No |
| Delivery guaranteed | Yes (ACKs + resending) | No |
| Speed | Slower | Faster |
| Used for | Web pages, email, file transfer | Streaming, gaming, voice calls |

- **Three-way handshake**: SYN → SYN/ACK → ACK.
- **Closing**: FIN → FIN/ACK → ACK. **RST** = abrupt reset.

**Common ports:**

| Port | Service |
| --- | --- |
| 21 | FTP |
| 22 | SSH |
| 80 | HTTP |
| 443 | HTTPS |
| 445 | SMB |
| 3389 | RDP |

Well-known ports: 0-1023. Total: 0-65535.

## 8. Extending Networks

- **Port forwarding**: the router sends traffic arriving on a port to a specific internal device.
- **Firewall** decides traffic by: source, destination, port, protocol.
    - **Stateful**: watches whole connections, smarter, uses more resources.
    - **Stateless**: checks each packet against fixed rules, lighter, good against floods.
- **VPN**: encrypted tunnel between networks; works for the whole system (a proxy only works per app).
    - **PPTP**: easy but weak encryption. **IPSec**: harder to set up but strong.

## 9. DNS

- Turns domain names into IP addresses.
- `admin.tryhackme.com` → `admin` = subdomain, `tryhackme` = second-level domain, `.com` = TLD.
- **gTLD** = type (`.com`, `.gov`). **ccTLD** = country (`.in`, `.ca`).

| Record | Points to |
| --- | --- |
| A | IPv4 address |
| AAAA | IPv6 address |
| CNAME | Another domain name (alias) |
| MX | Mail server (with priority) |
| TXT | Free text (email security, domain verification) |

**Lookup order:** local cache → recursive DNS server → root server → TLD server → authoritative nameserver. **TTL** = how long an answer can be cached.

## 10. HTTP and the Web

- **URL parts**: scheme `://` user `@` host `:` port / path `?` query string `#` fragment.
- **Request line**: `GET / HTTP/1.1` = method + page + version.
- **Methods**: GET (read), POST (send/create), PUT (update), DELETE (remove).

| Range | Meaning | Must-know codes |
| --- | --- | --- |
| 1xx | Information | — |
| 2xx | Success | 200 OK, 201 Created |
| 3xx | Redirect | 301 Moved Permanently, 302 Found |
| 4xx | Client error | 400, 401 (log in), 403 (forbidden), 404, 405 |
| 5xx | Server error | 500, 503 |

- **Request headers**: Host, User-Agent, Content-Length, Accept-Encoding, Cookie.
- **Response headers**: Set-Cookie, Cache-Control, Content-Type, Content-Encoding.
- **HTTP is stateless**, so **cookies** (usually random tokens) keep you logged in.
- **Client-server**: client sends a request, server sends a response (header + body).

## 11. How Websites Work

- **HTML** = structure, **CSS** = style, **JavaScript** = interactivity.
- `id` is unique per element; `class` can be shared.
- **Sensitive data exposure**: secrets (like test passwords) left in the page source.
- **HTML injection**: unsanitised input gets shown as real HTML on the page.
- **Behind a website**: DNS → (CDN) → WAF → load balancer → web server → database.
    - **Load balancer** methods: round-robin, least connections, weighted. Also does health checks.
    - **CDN**: serves files from the server closest to the user.
    - **WAF**: filters malicious and bot requests (e.g. rate limiting).
- **Web server** (Apache, Nginx, IIS, NodeJS) serves files from its **root directory**.
- **Static** content doesn't change; **dynamic** content does.
- **Crawling** = moving through and indexing pages. **Scraping** = pulling specific data. **robots.txt** tells crawlers what not to index.

## 12. Cryptography

- **Plaintext** → (algorithm + key) → **ciphertext**.
- **Symmetric**: one key, fast, hard to share safely.
- **Asymmetric**: public key encrypts, private key decrypts; slower. Private-key signing = **digital signatures**.
- **HTTPS** = hybrid: asymmetric to share a key safely, then symmetric for speed.
- **Certificates** prove a public key belongs to a website, signed by a trusted **Certificate Authority (CA)**.

## 13. Data and Encoding

- Each colour channel (R, G, B) gets 8 bits → 24 bits → ~16.7 million colours. 3 bits total → 8 colours.
- 1 hex digit = 4 bits.
- **ASCII** (0-127, English only) → **ISO-8859** (European languages) → **Unicode** (everything).
- **UTF-8**: 1-4 bytes (web standard). **UTF-16**: 2 or 4 bytes. **UTF-32**: always 4 bytes.

## 14. SQL Basics

```sql
SELECT drink, price FROM Orders WHERE drink = 'Coffee' ORDER BY price DESC;
```

`SELECT` (which columns) → `FROM` (which table) → `WHERE` (filter) → `ORDER BY` (sort).

## 15. Virtualization and Cloud

- **Hypervisor** runs virtual machines. **Type 1** = on bare hardware (servers). **Type 2** = on top of an OS (VirtualBox).
- **Container** = one app + its dependencies, shares the host OS, starts instantly (**Docker**).
- **Cloud deployment**: Public, Private, Hybrid.
- **Service models**: **IaaS** (you manage OS + app), **PaaS** (you manage just the app), **SaaS** (you just use it, e.g. Gmail).
- **EC2** = AWS virtual server. **Instance type** = how powerful (and expensive) it is.

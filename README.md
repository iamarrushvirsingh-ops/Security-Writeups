# Security Writeups

Hi, I'm **Arrush Vir Singh**, a B.Tech IT student at AKGEC Ghaziabad working towards SOC and VAPT roles.

This repo is where I document what I learn in cybersecurity: every TryHackMe room I complete, plus CTFs, Advent of Cyber and (soon) bug bounty and pentest notes.

**Why I document everything:** writing a topic out myself is how I check that I've actually understood it, and it gives me notes I can come back to later.

---

## What's inside

| Section | Status |
| --- | --- |
| [TryHackMe – Pre Security](TryHackMe/Pre-Security/) | Completed |
| [TryHackMe – Cyber Security 101](TryHackMe/Cyber-Security-101/) | In progress |
| [Advent of Cyber 2026](Advent-of-Cyber-2026/) | Starting 1 Dec 2026 |
| [CTF writeups](CTFs/) | Coming soon |

---

## TryHackMe – Pre Security (completed)

### Revise and test yourself
| File | What it is |
| --- | --- |
| [Quick Revision Notes](TryHackMe/Pre-Security/pre-security-revision-notes.md) | The whole path condensed into one page of tables and key points |
| [Self-Test Questions](TryHackMe/Pre-Security/pre-security-self-test.md) | 55 questions with hidden answers to check what you remember |

### Getting started
| Room | What it covers |
| --- | --- |
| [Becoming a Hacker](TryHackMe/Pre-Security/becoming-a-hacker.md) | Offensive security terms, the hacker mindset, first hands-on use of Gobuster and Hydra |

### Computer and OS fundamentals
| Room | What it covers |
| --- | --- |
| [Computer Systems](TryHackMe/Pre-Security/computer-systems.md) | Hardware components and how a computer boots (UEFI/BIOS, POST, bootloader) |
| [Operating System Security](TryHackMe/Pre-Security/operating-system-security.md) | CIA triad, weak passwords, file permissions, malware |
| [Windows Basics](TryHackMe/Pre-Security/windows-basics.md) | Account types, Task Manager, Windows Security and Firewall |
| [Windows CLI Basics](TryHackMe/Pre-Security/windows-cli-basics.md) | Finding your way around with `dir`, `type`, `whoami`, `systeminfo`, `ipconfig` |
| [Linux CLI Basics](TryHackMe/Pre-Security/linux-cli-basics.md) | Core commands, finding files, system info, SSH and switching users |

### Networking
| Room | What it covers |
| --- | --- |
| [Computer Networks](TryHackMe/Pre-Security/computer-networks.md) | MAC addresses, MAC spoofing, ping and ICMP |
| [Intro to LAN](TryHackMe/Pre-Security/intro-to-lan.md) | Topologies, subnetting, ARP, DHCP |
| [OSI Model](TryHackMe/Pre-Security/osi-model.md) | The 7 layers and what happens at each one |
| [Packets and Frames](TryHackMe/Pre-Security/packets-and-frames.md) | Encapsulation, TCP vs UDP, the three-way handshake, common ports |
| [Extending Your Network](TryHackMe/Pre-Security/extending-your-network.md) | Port forwarding, stateful vs stateless firewalls, VPNs |
| [DNS](TryHackMe/Pre-Security/dns.md) | Domain structure, record types, how a DNS lookup works |

### How the web works
| Room | What it covers |
| --- | --- |
| [Client-Server Model](TryHackMe/Pre-Security/client-server-model.md) | Requests, responses, protocols, ports, HTTP methods |
| [HTTP in Detail](TryHackMe/Pre-Security/http-in-detail.md) | URLs, requests and responses, status codes, headers, cookies |
| [How Websites Work](TryHackMe/Pre-Security/how-websites-work.md) | HTML, CSS, JavaScript, sensitive data exposure, HTML injection |
| [Putting It All Together](TryHackMe/Pre-Security/putting-it-all-together.md) | Load balancers, CDNs, WAFs, web servers, static vs dynamic content |
| [Web Scraping](TryHackMe/Pre-Security/web-scraping.md) | Web crawling vs web scraping, robots.txt |

### Security, data and programming basics
| Room | What it covers |
| --- | --- |
| [Cryptography](TryHackMe/Pre-Security/cryptography.md) | Symmetric vs asymmetric encryption, HTTPS, certificates |
| [Data Representation and Encoding](TryHackMe/Pre-Security/data-representation-and-encoding.md) | Binary, hex, ASCII, Unicode, UTF-8/16/32 |
| [Database SQL](TryHackMe/Pre-Security/database-sql.md) | Basic SQL queries: `SELECT`, `FROM`, `WHERE`, `ORDER BY` |
| [Python Simple Demo](TryHackMe/Pre-Security/python-simple-demo.md) | Variables, input, if/elif/else and loops through a number-guessing game |

### Cloud and virtualization
| Room | What it covers |
| --- | --- |
| [Virtualization](TryHackMe/Pre-Security/virtualization.md) | Hypervisors (Type 1 vs Type 2), containers, Docker |
| [Cloud Computing Fundamentals](TryHackMe/Pre-Security/cloud-computing-fundamentals.md) | Public/private/hybrid cloud, IaaS/PaaS/SaaS, EC2 basics |

---

## How the notes are written

Each room file covers the key concepts from that room, explained in simple language, along with any commands or tools I used.

---

## Repo structure

```
Security-Writeups/
├── README.md
├── TryHackMe/
│   ├── Pre-Security/
│   │   ├── images/
│   │   ├── pre-security-revision-notes.md
│   │   ├── pre-security-self-test.md
│   │   └── <room-name>.md
│   └── Cyber-Security-101/
├── Advent-of-Cyber-2026/
└── CTFs/
```

---

## Note

These are my personal learning notes. **No flags or room answers are published here.** All TryHackMe rooms and images belong to [TryHackMe](https://tryhackme.com).

## Connect with me

- TryHackMe: [iamarrushvirsingh](https://tryhackme.com/p/iamarrushvirsingh)
- LinkedIn: [Arrush Vir Singh](https://www.linkedin.com/in/arrush-vir-singh-6b3328378/)
- GitHub: [iamarrushvirsingh-ops](https://github.com/iamarrushvirsingh-ops)

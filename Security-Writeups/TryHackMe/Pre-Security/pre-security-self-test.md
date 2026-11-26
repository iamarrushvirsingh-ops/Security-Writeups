# Pre Security: Self-Test Questions

> **Note:** These questions were made with the help of AI, based on my own room notes. They're for testing myself after finishing the path.

**How to use this:** answer each question in your head (or on paper) first, then click **Show answer** to check.
Revise anything you get wrong using the [revision notes](pre-security-revision-notes.md) or the room files.

---

## Hacker Mindset

**1. What is the difference between a vulnerability and an exploit?**
<details><summary>Show answer</summary>

A vulnerability is the weakness. An exploit is the technique used to take advantage of that weakness.
</details>

**2. What does "scope" mean in a penetration test, and why does it matter?**
<details><summary>Show answer</summary>

Scope is the boundary of what you're allowed to test: which systems and actions are permitted and what is off-limits. Testing outside scope is unauthorized, and can be illegal.
</details>

**3. Which tool would you use to find hidden directories on a website, and which to guess a login password?**
<details><summary>Show answer</summary>

Gobuster for hidden directories. Hydra for automated password guessing (a dictionary attack).
</details>

## Computer Fundamentals

**4. Why is RAM called "volatile"?**
<details><summary>Show answer</summary>

Because everything stored in it is lost when the power is turned off.
</details>

**5. Put these boot steps in order: bootloader, POST, power button, select boot device, UEFI starts.**
<details><summary>Show answer</summary>

Power button → UEFI starts → POST → select boot device → bootloader.
</details>

**6. What does POST check?**
<details><summary>Show answer</summary>

That every required component is present, set up correctly and working.
</details>

## Operating Systems

**7. What are the three parts of the CIA triad?**
<details><summary>Show answer</summary>

Confidentiality, Integrity, Availability.
</details>

**8. Ransomware mainly attacks which part of the CIA triad?**
<details><summary>Show answer</summary>

Availability, because it locks you out of your own files.
</details>

**9. A fingerprint scanner is which type of authentication factor?**
<details><summary>Show answer</summary>

Something you **are**.
</details>

**10. What is the principle of least privilege?**
<details><summary>Show answer</summary>

Every user gets only the access they actually need, and nothing more.
</details>

**11. What are the three Windows Defender Firewall network profiles?**
<details><summary>Show answer</summary>

Domain, Private and Public.
</details>

## Command Line

**12. Which Linux command shows hidden files in a directory?**
<details><summary>Show answer</summary>

`ls -al` (or `ls -a`). Hidden files start with a dot.
</details>

**13. What is the Windows equivalent of Linux's `pwd`?**
<details><summary>Show answer</summary>

Running `cd` on its own.
</details>

**14. How do you search for `notes.txt` in all subfolders on Windows?**
<details><summary>Show answer</summary>

`dir /s notes.txt`
</details>

**15. Which file gives clear details about a Linux distribution?**
<details><summary>Show answer</summary>

`/etc/os-release`
</details>

## Networking Basics

**16. Why is using MAC addresses for authentication insecure?**
<details><summary>Show answer</summary>

Because MAC addresses can be spoofed (faked), so anyone copying a trusted device's MAC can pretend to be it.
</details>

**17. What protocol does ping use?**
<details><summary>Show answer</summary>

ICMP (echo request and echo reply).
</details>

**18. What does ARP do?**
<details><summary>Show answer</summary>

It finds the MAC address that belongs to a given IP address on the local network.
</details>

**19. What are the four steps of DHCP, in order?**
<details><summary>Show answer</summary>

Discover → Offer → Request → ACK ("DORA").
</details>

**20. Which topology fails completely if its single backbone cable is damaged?**
<details><summary>Show answer</summary>

Bus topology.
</details>

## OSI Model and TCP/IP

**21. List the 7 OSI layers from layer 1 to layer 7.**
<details><summary>Show answer</summary>

Physical, Data Link, Network, Transport, Session, Presentation, Application.
</details>

**22. At which OSI layer do MAC addresses work, and at which do IP addresses work?**
<details><summary>Show answer</summary>

MAC addresses at layer 2 (Data Link). IP addresses at layer 3 (Network).
</details>

**23. What is the difference between a packet and a frame?**
<details><summary>Show answer</summary>

A packet is layer 3 data with IP addresses. A frame is that packet wrapped with MAC address information at layer 2.
</details>

**24. What is encapsulation?**
<details><summary>Show answer</summary>

The process of each layer adding its own header (extra information) to the data as it's prepared for sending.
</details>

**25. What are the three steps of the TCP three-way handshake?**
<details><summary>Show answer</summary>

SYN → SYN/ACK → ACK.
</details>

**26. What does an RST packet do?**
<details><summary>Show answer</summary>

It abruptly ends a connection, usually because something went wrong.
</details>

**27. You're building a video call app. TCP or UDP, and why?**
<details><summary>Show answer</summary>

UDP, because low delay matters more than perfect delivery. Losing a few packets just causes a small glitch.
</details>

**28. What is the purpose of TTL in a packet?**
<details><summary>Show answer</summary>

It makes a lost packet expire after a while, so it doesn't keep clogging the network.
</details>

**29. Match the ports: 22, 80, 443, 3389.**
<details><summary>Show answer</summary>

22 = SSH, 80 = HTTP, 443 = HTTPS, 3389 = RDP.
</details>

## Firewalls and VPNs

**30. Stateful vs stateless firewall: which inspects whole connections?**
<details><summary>Show answer</summary>

Stateful. Stateless checks each packet on its own against fixed rules.
</details>

**31. What is the main difference between a VPN and a proxy?**
<details><summary>Show answer</summary>

A VPN works at the operating system level and tunnels all traffic. A proxy works at the application level and only covers one app.
</details>

**32. PPTP or IPSec: which has stronger encryption?**
<details><summary>Show answer</summary>

IPSec. PPTP is easier to set up but has weak encryption.
</details>

## DNS

**33. In `blog.tryhackme.com`, identify the subdomain, second-level domain and TLD.**
<details><summary>Show answer</summary>

Subdomain = `blog`, second-level domain = `tryhackme`, TLD = `.com`.
</details>

**34. Which DNS record type points to an IPv6 address?**
<details><summary>Show answer</summary>

AAAA.
</details>

**35. Which DNS record tells you where a domain's email should be delivered?**
<details><summary>Show answer</summary>

MX record.
</details>

**36. In what order does a DNS lookup travel if nothing is cached?**
<details><summary>Show answer</summary>

Recursive DNS server → root server → TLD server → authoritative nameserver.
</details>

## HTTP and Websites

**37. Break down this URL: `https://user:pass@site.com:8080/shop?id=5#reviews`**
<details><summary>Show answer</summary>

Scheme = `https`, user = `user:pass`, host = `site.com`, port = `8080`, path = `/shop`, query string = `id=5`, fragment = `reviews`.
</details>

**38. What's the difference between status codes 401 and 403?**
<details><summary>Show answer</summary>

401 = you need to log in first. 403 = you're not allowed, whether you're logged in or not.
</details>

**39. Which HTTP method is used to submit a login form?**
<details><summary>Show answer</summary>

POST.
</details>

**40. Why do websites need cookies?**
<details><summary>Show answer</summary>

Because HTTP is stateless (it doesn't remember previous requests). Cookies let the server recognise you, for example to keep you logged in.
</details>

**41. What is the purpose of the `Host` header?**
<details><summary>Show answer</summary>

It tells the server which website you want, since one server can host many websites.
</details>

**42. What is HTML injection?**
<details><summary>Show answer</summary>

When a website doesn't sanitise user input, so the input is shown on the page as real HTML that the attacker controls.
</details>

**43. A developer left a test password in a page's source code. What is this vulnerability called?**
<details><summary>Show answer</summary>

Sensitive data exposure.
</details>

**44. What does a WAF do?**
<details><summary>Show answer</summary>

It sits in front of the web server and filters out malicious and bot requests, for example using rate limiting.
</details>

**45. What does a load balancer's "health check" do?**
<details><summary>Show answer</summary>

It regularly checks that each server is responding correctly, so traffic isn't sent to a broken server.
</details>

**46. What is the difference between web crawling and web scraping?**
<details><summary>Show answer</summary>

Crawling moves through and indexes many pages. Scraping pulls specific information out of pages.
</details>

## Cryptography

**47. Symmetric vs asymmetric encryption: which uses one shared key?**
<details><summary>Show answer</summary>

Symmetric.
</details>

**48. Why does HTTPS use both symmetric and asymmetric encryption?**
<details><summary>Show answer</summary>

Asymmetric encryption safely shares a secret key; then symmetric encryption is used for the rest of the session because it's much faster.
</details>

**49. What does a Certificate Authority do?**
<details><summary>Show answer</summary>

It digitally signs certificates to confirm that a public key really belongs to the website it claims to.
</details>

## Data, SQL, Virtualization and Cloud

**50. How many bits does one hexadecimal digit represent?**
<details><summary>Show answer</summary>

4 bits.
</details>

**51. How many bytes does UTF-32 use per character?**
<details><summary>Show answer</summary>

Always 4 bytes.
</details>

**52. Write a SQL query to get all columns from the `Users` table where `role` is `admin`.**
<details><summary>Show answer</summary>

```sql
SELECT * FROM Users WHERE role = 'admin';
```
</details>

**53. What is the difference between a Type 1 and a Type 2 hypervisor?**
<details><summary>Show answer</summary>

Type 1 runs directly on the hardware (used for servers). Type 2 runs on top of an existing operating system (like VirtualBox).
</details>

**54. How is a container different from a virtual machine?**
<details><summary>Show answer</summary>

A container shares the host's operating system and runs one app, so it's lightweight and starts almost instantly. A VM is a full virtual computer with its own operating system.
</details>

**55. Gmail is an example of which cloud service model?**
<details><summary>Show answer</summary>

SaaS (Software as a Service).
</details>

---

**Score yourself:** 50+ correct = ready for Cyber Security 101. Below 40 = revise the weak sections first.

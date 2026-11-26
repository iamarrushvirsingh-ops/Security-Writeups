# DNS (Domain Name System)

- DNS turns domain names (like `tryhackme.com`) into IP addresses that computers use to find each other.

## TLD (Top-Level Domain)

- There are 2 types of TLD:
    1. **gTLD** (Generic Top-Level Domain)
    2. **ccTLD** (Country Code Top-Level Domain)
- A gTLD shows what type of domain it is, like `.com` for commercial and `.gov` for government.
- A ccTLD is used for geographical purposes. For example, `.ca` for Canada, `.co.uk` for the United Kingdom, and so on.

## Second-Level Domain

- For example, consider `tryhackme.com`:
    - `.com` is the TLD.
    - `tryhackme` is the second-level domain.
- Rules for domain names:
    - The second-level domain is limited to 63 characters (plus the TLD) and can only use a-z, 0-9 and hyphens. It can't start or end with a hyphen or have consecutive hyphens.
- The rules for creating a subdomain are the same as for a main domain. Subdomains are separated with a `.` (for example `admin.tryhackme.com`).
- The full domain name, including all subdomains, must be 253 characters or less.

## Record Types

### A Record
- Resolves to an IPv4 address.

### AAAA Record
- Resolves to an IPv6 address.

### CNAME Record
- Points one domain name to another domain name, like an alias.
- For example, `www.tryhackme.com` can have a CNAME record pointing to `tryhackme.com`.
- When someone visits `www.tryhackme.com`, the CNAME tells their computer the real name is `tryhackme.com`, and another DNS request is made for that name to get the IP address.
- This way, the IP address only has to be managed in one place, and all the alias names automatically follow it.

### MX Record
- Holds the address of the server that handles email for the domain you're querying.
- These records also have a priority value, which tells which mail server to try first, and which ones to try next if the main server goes down.

### TXT Record
- Free text fields where any text-based data can be stored.
- They have multiple uses.
- The most common one is listing which servers are allowed to send email on behalf of the domain.
- This helps prevent email spoofing and scams.
- They can also be used to prove you own the domain when signing up for third-party services.

## Workflow: What Happens When a Request Is Made?

1. When you first make a request, your computer checks its own DNS cache to see if you looked up this domain recently.
2. If not, a request is made to your **recursive DNS server**. This is usually provided by your ISP, but you can choose your own as well.
3. This server has its own cache, which it checks first. If there's no match, it sends a request to the internet's **root DNS servers**.
4. The root DNS server redirects you to the correct **TLD server** for your request.
5. The TLD server holds records of where to find the **authoritative server** that can answer your request.
6. The authoritative server is also known as the **nameserver** of that domain. You'll often find multiple nameservers for a domain, in case one goes down.
7. The authoritative server stores the DNS records for that particular domain, and it's where you update any changes to those records.

- Every DNS record comes with a **TTL (time to live)**, measured in seconds. It says how long the answer can be saved in cache before it has to be looked up again.

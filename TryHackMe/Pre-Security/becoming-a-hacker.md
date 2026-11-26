# Becoming a Hacker

## Core Offensive Security Terms

- **Red Teaming**: An authorized, structured attack that copies how a real adversary would behave, to test how well the defences hold up and to find weaknesses within an agreed scope.
- **Penetration Test**: An authorized security assessment where the tester tries to find and exploit vulnerabilities within a defined scope, to show what the real-world risk is.
- **Vulnerability**: A weakness or flaw in a system, application or configuration that an attacker could abuse.
- **Exploit**: The technique used to take advantage of a vulnerability to reach a goal, like getting into restricted functions or data.
- **Scope**: The boundaries of a test: which systems, applications and actions are allowed, and what is off-limits.

## Think Like a Hacker

To become a hacker, you have to think like one. A hacker doesn't just check whether something works as intended. They ask how it could be misused, combined with other behaviour, or used to get unauthorized access. This means thinking creatively and testing new ideas. Ethical hackers use the same mindset, but safely and with permission, so they can find and prove the risks before real attackers do.

Key points to keep in mind on the ethical hacking journey:

- **Ask questions**: Don't assume a feature works as intended. Ask "What if it doesn't?"
- **Test the unexpected**: Try inputs and actions the developers didn't think of.
- **Chain small weaknesses**: A small flaw may be harmless alone, but linked with others it can have a bigger impact.
- **Think like an adversary**: Ask "How would a malicious actor approach this target?"

## Hands-on

In this room we used 2 tools:

1. **Gobuster**: to automate finding hidden directories and endpoints on a website.
2. **Hydra**: to automate a dictionary attack to find the right password.

The commands for both:

```bash
gobuster dir --url http://www.onlineshop.thm/ -w /usr/share/wordlists/dirbuster/directory-list.txt
```

```bash
hydra -l admin -P passlist.txt www.onlineshop.thm http-post-form "/login:username=^USER^&password=^PASS^:F=incorrect" -V
```

What the options mean:

- `dir`: Gobuster's directory-finding mode
- `-w`: the wordlist of directory names to try
- `-l admin`: the username to attack
- `-P passlist.txt`: the list of passwords to try
- `F=incorrect`: the text on the page that means the login failed
- `-V`: show every attempt

# Linux CLI Basics

## Commands

1. `pwd`: prints the path of the current (working) directory.

2. `ls`: lists the contents of the current directory.
    - `ls -al`: lists everything, including hidden files.
    - Hidden files start with a dot (`.`).

3. `find`: helps locate files in the file system from the command line.
    - Syntax: `find <starting_point> -name <filename>`
    - If the file exists, Linux prints the full path to it.

4. `uname`: shows system information.
    - Use the `-a` flag to print **all** system info in a structured layout.

5. `df`: "disk free". Shows how much disk storage is used and free on the computer.
    - `df -h`: shows the sizes in a human-readable format (like GB) instead of long byte numbers.
    - `tmpfs` entries are temporary file systems stored in **RAM**, not on the physical disk.
    - `/run/user/114` is similar temporary storage belonging to another system user (user ID 114).

## Extra Info

- Linux stores configuration and informational files in the `/etc` directory.
- The `/etc/os-release` file gives details about the Linux distribution that are often clearer than what the `uname` command shows.

## SSH and Switching Users

- To connect to a machine over SSH, use:

```bash
ssh username@target_machine_ip
```

- Use the `su` command to switch users:

```bash
su - username
```

- `su` also works outside SSH, in a normal terminal on your own system.

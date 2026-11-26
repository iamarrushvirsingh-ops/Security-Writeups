# Windows CLI Basics

## Where Am I?

- Run `cd` on its own (with nothing after it) to see which folder you are in, in the Command Prompt.

## What Is Around Me?

- Use the `dir` command to list the files and folders in the current directory.

### Hidden Files
- To see hidden files, use: `dir /a`

### Locating a File
- To locate a file, use: `dir /s filename.txt`
- The `/s` flag tells Windows to search **all subfolders**, starting from your current directory, and show the full path if the file exists.

## Print File Contents

- To read the contents of a file, use: `type task_brief.txt`. This prints the file's contents directly in the Command Prompt.

## Who Am I?

- Use the `whoami` command to check which user you are logged in as.
- Every Windows machine has a name. To see the computer's name, run: `hostname`

## OS Details

- Use `systeminfo` to get information about the OS.

## How Is the Machine Connected to the Network?

- Use `ipconfig` to see details about the system's network connection.

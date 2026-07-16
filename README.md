# Linux_adminstration_1_Notes

## Roadmap
- Chapter1: Introduction to linux
- Chapter2: Bash Shell and Basic Commands
- Chapter3: Files and Directories Managing
- Chapter4: Getting Help (the man command)
- Chapter5: Create,View, and Editing Text Files
- Chapter6: Managing Local Users and Groups 
- Chapter7: Controlling Access to Files
---
# Chapter1: Introduction to linux
## 1. What is the Linux Kernel?
- The Linux kernel is the core part of the operating system.
```
Applications
    ↓
Linux Kernel
    ↓
Hardware
```
- The kernel is responsible for controlling the computer hardware and giving programs a **safe way** to use it.
- **For example**, when you open a terminal, copy a file, connect to Wi-Fi, or run a program, the application does not talk directly to the CPU, RAM, disk, or network card. It asks the kernel to do that.

### What does the kernel do?
The Linux kernel manages things like:
- CPU management
- Memory management
- Process management
- File system management
- Device management
- 

## 2. What are Linux Distributions?
A Linux distribution, or Linux distro, is a complete operating system built around the Linux kernel.

The kernel alone is not enough for normal users. You also need tools, software, package managers, desktop environments, settings, and system utilities.

A Linux distribution combines all of these together.
```
Linux Distribution
=
Linux Kernel
+
System tools
+
Package manager
+
Desktop environment
+
Default apps
+
Configuration
```

### Popular Linux distros include:
- Ubuntu
- Fedora
- Debian
- Arch Linux
- Linux Mint
- Kali Linux
- openSUSE
- Manjaro
- Red Hat Enterprise Linux

`All of them use the Linux kernel, but they are different in tools, package managers, release style, default software, and target users.`

## 3. Why are there many Linux distributions?
- Because Linux is open-source, different communities and companies can build their own version of a Linux-based operating system.Each distro has a different goal.

### For example:

**Ubuntu** -> Beginner-friendly and popular for desktop/server use.

**Fedora** -> Modern, updated, and close to new Linux technologies.

**Debian** -> Very stable and widely used for servers.

**Arch Linux** -> Minimal, customizable, and aimed at advanced users.

**Kali Linux** -> Focused on cybersecurity and penetration testing tools.

# Chapter2: Bash Shell and Basic Commands

## 1. What is Bash Shell?

A **shell** is a program that allows the user to interact with the operating system by writing commands.

In Linux, instead of using only graphical buttons and menus, we can control the system using commands in the terminal.

The **Bash shell** is one of the most common shells used in Linux.

---

## 2. Shell vs Terminal

Many beginners confuse between **shell** and **terminal**.

### Terminal

The **terminal** is the window or application where you type commands.

Examples:

- GNOME Terminal
- Konsole
- Kitty
- Alacritty
- xterm

### Shell

The **shell** is the program running inside the terminal that understands and executes your commands.

Example shells:

- Bash
- Zsh
- Fish
- Sh

So the terminal is like the screen, and Bash is the program that interprets the commands.

```text
User → Terminal → Bash Shell → Linux Kernel → Hardware
```

## 3. Command Prompt
When you open the terminal, you usually see something like this:
```user@hostname:~$``` <br>
For Example:
```ahmad@fedora:~$```

| Part     | Meaning                                       |
| -------- | --------------------------------------------- |
| `ahmad`  | Current username                              |
| `fedora` | Hostname / computer name                      |
| `~`      | Current directory, usually the home directory |
| `$`      | Normal user prompt                            |
| `#`      | Root/admin user prompt                        |

## 4. Linux Command Syntax
- Most Linux commands follow this structure:
```command [options] [arguments]```.

- For example: ```ls -l /home``` where ```ls``` is command,```-l``` is option and ```/home``` is an argument.

| Command     | Option                                       |
| -------- | --------------------------------------------- |
| `ls -l ` | option shows files in long format.                              |
| `ls -a` | option shows hidden files.                      |
| `ls -la` = `ls -l -a`     | You can combine options |

## 5. Basic Commands
- The `date` command displays the current system date and time.

- The `passwd` command is used to change a user's password.

- The `file` command tells you the type of a file.

## 6. Viewing File Contents
- The `cat` command displays the full content of a file.

- The `less` command allows you to read a file page by page.

- The `head` command shows the first lines of a file.

- The `tail` command shows the last lines of a file.

- The `history` command shows previously executed commands.
    - You can also search command history using: `Ctrl + r`

## 7. Shell Shortcuts

| Moving Cursor Shortcut   | Function                          |
| ---------- | --------------------------------- |
| `Ctrl + A` | Move to the beginning of the line |
| `Ctrl + E` | Move to the end of the line       |
| `Alt + B`  | Move backward one word            |
| `Alt + F`  | Move forward one word             |


| Editing commands Shortcut   | Function                                |
| ---------- | --------------------------------------- |
| `Ctrl + U` | Delete from cursor to beginning of line |
| `Ctrl + K` | Delete from cursor to end of line       |
| `Ctrl + W` | Delete one word before cursor           |
| `Ctrl + Y` | Paste deleted text                      |
| `Ctrl + L` | Clear the screen                        |

| Process control Shortcut   | Function                      |
| ---------- | ----------------------------- |
| `Ctrl + C` | Stop the running command      |
| `Ctrl + Z` | Pause the running command     |
| `Ctrl + D` | Exit the shell or close input |
| `Ctrl + R` | Search command history        |

# Chapter3: Files and Directories Managing

## 1. Main Idea

This chapter explains how Linux organizes files and directories, how to navigate paths, how to list and manage files, and how to search and process text using commands like `ls`, `grep`, `cut`, and `tr`.

In Linux, everything is treated like a file, including:

- Regular files
- Directories
- Devices
- Links
- Sockets
- Pipes

---

## 2. Linux File System Structure

Linux uses a tree-like file system.

The top directory is called the **root directory**.

```bash
/
```

Everything in Linux starts from `/`.

Example:

```txt
/
├── home
├── etc
├── var
├── usr
├── bin
├── sbin
├── tmp
└── root
```

---

## 3. Major Linux Directories

## `/`

The root directory.

It is the beginning of the whole Linux file system.

All files and directories are inside `/`.

---

## `/home`

Contains normal users’ home directories.

Example:

```bash
/home/ahmad
```

This is where user files, downloads, documents, and personal configs are usually stored.

---

## `/root`

The home directory for the root user.

Do not confuse it with `/`.

```bash
/root
```

`/` is the root of the file system.  
`/root` is the home directory of the root admin user.

---

## `/etc`

Contains system configuration files.

Examples:

```bash
/etc/passwd
/etc/hostname
/etc/fstab
```

Linux admins often edit files inside `/etc`.

---

## `/var`

Contains variable data that changes over time.

Examples:

- Logs
- Cache
- Mail
- Spool files

Important directory:

```bash
/var/log
```

This contains system log files.

---

## `/tmp`

Temporary files.

Programs and users can store temporary data here.

Files in `/tmp` may be deleted automatically.

---

## `/usr`

Contains user programs and system resources.

Examples:

```bash
/usr/bin
/usr/lib
/usr/share
```

Most installed software files are stored here.

---

## `/bin`

Contains essential user commands.

Examples:

```bash
ls
cat
cp
mv
rm
```

---

## `/sbin`

Contains essential system administration commands.

Examples:

```bash
reboot
shutdown
fdisk
```

Usually used by root or administrators.

---

## `/boot`

Contains files needed to boot the system.

Examples:

- Linux kernel
- Bootloader files
- initramfs

---

## `/dev`

Contains device files.

Examples:

```bash
/dev/sda
/dev/null
/dev/tty
```

In Linux, hardware devices are represented as files.

---

## `/proc`

A virtual file system that contains information about running processes and the kernel.

Example:

```bash
/proc/cpuinfo
/proc/meminfo
```

---

## `/mnt` and `/media`

Used for mounting external storage devices.

Examples:

```bash
/mnt
/media
```

USB drives, external disks, or network storage may appear here.

---

## 4. Linux File Types

Linux has different file types.

You can see file types using:

```bash
ls -l
```

Example output:

```bash
-rw-r--r-- 1 user user 1200 Jun 18 notes.txt
drwxr-xr-x 2 user user 4096 Jun 18 Documents
lrwxrwxrwx 1 user user   10 Jun 18 link.txt -> notes.txt
```

The first character shows the file type.

| Symbol | File Type |
|---|---|
| `-` | Regular file |
| `d` | Directory |
| `l` | Symbolic link |
| `c` | Character device |
| `b` | Block device |
| `p` | Pipe |
| `s` | Socket |

---

## Regular File

A normal file, like:

```bash
notes.txt
image.png
script.sh
```

Symbol:

```txt
-
```

---

## Directory

A folder that contains files or other directories.

Symbol:

```txt
d
```

---

## Symbolic Link

A shortcut or reference to another file.

Symbol:

```txt
l
```

---

## Device Files

Used to represent hardware devices.

Examples:

```bash
/dev/sda
/dev/tty
```

---

## 5. Rules for Naming Linux Files

Linux file names are case-sensitive.

Example:

```bash
file.txt
File.txt
FILE.txt
```

These are three different files.

---

## Allowed Names

You can use:

```txt
letters
numbers
dots
underscores
hyphens
```

Examples:

```bash
notes.txt
linux_admin_1.md
chapter-03.txt
```

---

## Avoid Spaces

Spaces can cause problems in commands.

Not recommended:

```bash
my file.txt
```

Better:

```bash
my_file.txt
my-file.txt
```

If a file has spaces, use quotes:

```bash
cat "my file.txt"
```

or escape the space:

```bash
cat my\ file.txt
```

---

## Hidden Files

Files that start with a dot `.` are hidden.

Example:

```bash
.bashrc
.config
.ssh
```

To show hidden files:

```bash
ls -a
```

---

## 6. Absolute Path vs Relative Path

## Absolute Path

An absolute path starts from the root directory `/`.

Example:

```bash
/home/ahmad/Documents/notes.txt
```

It gives the full location of the file.

Absolute paths always start with:

```bash
/
```

---

## Relative Path

A relative path starts from your current directory.

Example:

```bash
Documents/notes.txt
```

It depends on where you currently are.

Check your current directory:

```bash
pwd
```

---

## Special Path Symbols

| Symbol | Meaning |
|---|---|
| `.` | Current directory |
| `..` | Parent directory |
| `~` | Current user home directory |
| `/` | Root directory |

Examples:

```bash
cd .
cd ..
cd ~
cd /
```

---

## 7. `ls` Command

The `ls` command lists files and directories.

Basic usage:

```bash
ls
```

---

## Common `ls` Options

### Long format

```bash
ls -l
```

Shows permissions, owner, size, date, and name.

---

### Show hidden files

```bash
ls -a
```

Shows files that start with `.`.

---

### Long format with hidden files

```bash
ls -la
```

---

### Human-readable file sizes

```bash
ls -lh
```

Shows sizes like KB, MB, GB.

---

### List by time

```bash
ls -lt
```

Shows newest files first.

---

### Reverse order

```bash
ls -r
```

---

### List directories recursively

```bash
ls -R
```

Shows files inside subdirectories too.

---

## 8. Managing Files and Directories

## `pwd`

Shows the current working directory.

```bash
pwd
```

Example output:

```bash
/home/ahmad
```

---

## `cd`

Changes the current directory.

```bash
cd Documents
```

Go to home:

```bash
cd ~
```

Go one directory back:

```bash
cd ..
```

Go to root:

```bash
cd /
```

Go to previous directory:

```bash
cd -
```

---

## 9. Create Files and Directories

## `touch`

Creates an empty file.

```bash
touch notes.txt
```

It can also update the timestamp of an existing file.

---

## `mkdir`

Creates a directory.

```bash
mkdir projects
```

Create nested directories:

```bash
mkdir -p linux/admin/notes
```

The `-p` option creates parent directories if they do not exist.

---

## 10. Copy Files and Directories

## `cp`

Copies files.

```bash
cp file1.txt file2.txt
```

This copies `file1.txt` into a new file called `file2.txt`.

Copy file into directory:

```bash
cp notes.txt Documents/
```

Copy directory:

```bash
cp -r dir1 dir2
```

The `-r` option means recursive, used for directories.

---

## 11. Move and Rename Files

## `mv`

The `mv` command is used to move or rename files.

Rename a file:

```bash
mv old.txt new.txt
```

Move a file into a directory:

```bash
mv notes.txt Documents/
```

Move and rename at the same time:

```bash
mv notes.txt Documents/linux_notes.txt
```

---

## 12. Remove Files and Directories

## `rm`

Removes files.

```bash
rm file.txt
```

Remove directory and its contents:

```bash
rm -r mydir
```

Force remove:

```bash
rm -f file.txt
```

Remove directory forcefully:

```bash
rm -rf mydir
```

Important warning:

```bash
rm -rf
```

is dangerous because it deletes files permanently.

Linux does not always move deleted files to Trash when using the terminal.

---

## `rmdir`

Removes an empty directory only.

```bash
rmdir emptydir
```

---

## 13. Hard Links vs Soft Links

Linux supports two important types of links:

- Hard link
- Soft link / symbolic link

---

## Hard Link

A hard link is another name for the same file data.

Both files point to the same inode.

Example:

```bash
ln original.txt hardlink.txt
```

If you edit one, the other changes too.

If you delete the original file, the hard link still works.

Why?

Because the actual data still exists as long as at least one hard link points to it.

---

## Soft Link

A soft link is like a shortcut to another file.

Example:

```bash
ln -s original.txt softlink.txt
```

If you delete the original file, the soft link becomes broken.

Soft links can point to:

- Files
- Directories
- Files on another file system

---

## Hard Link vs Soft Link

| Point | Hard Link | Soft Link |
|---|---|---|
| Also called | Hard link | Symbolic link |
| Points to | Inode/data | File path |
| Works if original is deleted? | Yes | No |
| Can link directories? | Usually no | Yes |
| Can cross file systems? | No | Yes |
| Command | `ln file link` | `ln -s file link` |

---

## 14. Linux Inodes

An inode is a data structure that stores information about a file.

The inode contains metadata such as:

- File size
- Owner
- Group
- Permissions
- Timestamps
- Location of data blocks
- Number of hard links

Important:

The inode does not store the file name.

The file name is stored in the directory.

---

## Show inode number

```bash
ls -i
```

Example:

```bash
123456 notes.txt
```

Here, `123456` is the inode number.

---

## Check detailed inode information

```bash
stat notes.txt
```

---

## 15. Creating Hard Links and Soft Links

## Create a hard link

```bash
ln file.txt hardlink.txt
```

Check inode numbers:

```bash
ls -li
```

Both files should have the same inode number.

---

## Create a soft link

```bash
ln -s file.txt softlink.txt
```

Check it:

```bash
ls -l
```

Example output:

```bash
softlink.txt -> file.txt
```

---

## 16. Pattern Matching

Pattern matching allows you to select files using special characters.

These special characters are called wildcards.

---

## `*`

Matches zero or more characters.

Example:

```bash
ls *.txt
```

Shows all files ending with `.txt`.

Example:

```bash
rm *.log
```

Removes all `.log` files.

---

## `?`

Matches exactly one character.

Example:

```bash
ls file?.txt
```

Matches:

```txt
file1.txt
file2.txt
fileA.txt
```

But not:

```txt
file10.txt
```

---

## `[]`

Matches one character from a group.

Example:

```bash
ls file[123].txt
```

Matches:

```txt
file1.txt
file2.txt
file3.txt
```

---

## Ranges

Example:

```bash
ls file[1-5].txt
```

Matches:

```txt
file1.txt
file2.txt
file3.txt
file4.txt
file5.txt
```

---

## 17. `grep` Command

The `grep` command searches for text inside files.

Basic syntax:

```bash
grep "pattern" file
```

Example:

```bash
grep "root" /etc/passwd
```

This searches for the word `root` inside `/etc/passwd`.

---

## Common `grep` Options

### Ignore case

```bash
grep -i "error" file.txt
```

Matches:

```txt
error
Error
ERROR
```

---

### Show line numbers

```bash
grep -n "root" /etc/passwd
```

---

### Recursive search

```bash
grep -r "password" /etc
```

Searches inside files in a directory and subdirectories.

---

### Show lines that do not match

```bash
grep -v "root" /etc/passwd
```

---

### Count matches

```bash
grep -c "root" /etc/passwd
```

---

## 18. Regular Expressions

Regular expressions are patterns used to search for text more powerfully.

They are commonly used with `grep`.

---

## Basic Regex Symbols

| Symbol | Meaning |
|---|---|
| `^` | Start of line |
| `$` | End of line |
| `.` | Any single character |
| `*` | Zero or more of previous character |
| `[abc]` | Match a, b, or c |
| `[0-9]` | Match any digit |
| `[^abc]` | Match anything except a, b, or c |

---

## Examples

Lines that start with `root`:

```bash
grep "^root" /etc/passwd
```

Lines that end with `bash`:

```bash
grep "bash$" /etc/passwd
```

Lines that contain a number:

```bash
grep "[0-9]" file.txt
```

Lines that start with a capital letter:

```bash
grep "^[A-Z]" file.txt
```

---

## 19. `cut` Command

The `cut` command extracts columns or fields from text.

It is useful when working with structured files.

---

## Cut by character position

```bash
cut -c 1-5 file.txt
```

This shows characters from position 1 to 5.

---

## Cut by delimiter

Example using `/etc/passwd`:

```bash
cut -d ":" -f 1 /etc/passwd
```

Explanation:

| Part | Meaning |
|---|---|
| `-d ":"` | Delimiter is `:` |
| `-f 1` | Show field number 1 |

This shows usernames from `/etc/passwd`.

Show usernames and shells:

```bash
cut -d ":" -f 1,7 /etc/passwd
```

---

## 20. `tr` Command

The `tr` command translates or deletes characters.

It reads from standard input.

---

## Convert lowercase to uppercase

```bash
echo "linux" | tr 'a-z' 'A-Z'
```

Output:

```txt
LINUX
```

---

## Convert uppercase to lowercase

```bash
echo "LINUX" | tr 'A-Z' 'a-z'
```

Output:

```txt
linux
```

---

## Delete characters

```bash
echo "linux123" | tr -d '0-9'
```

Output:

```txt
linux
```

---

## Replace spaces with new lines

```bash
echo "linux admin course" | tr ' ' '\n'
```

Output:

```txt
linux
admin
course
```

---

# 21. Important Command Summary

| Command | Use |
|---|---|
| `pwd` | Show current directory |
| `cd` | Change directory |
| `ls` | List files |
| `touch` | Create empty file |
| `mkdir` | Create directory |
| `cp` | Copy files/directories |
| `mv` | Move or rename files |
| `rm` | Remove files/directories |
| `rmdir` | Remove empty directory |
| `ln` | Create hard link |
| `ln -s` | Create soft link |
| `ls -i` | Show inode number |
| `stat` | Show file metadata |
| `grep` | Search inside text |
| `cut` | Extract fields/columns |
| `tr` | Translate/delete characters |

---

# Chapter4: Getting Help (Manual Pages)


## 1. Main Idea

In Linux administration, it is impossible to memorize every command, option, and configuration file.

A good Linux admin does not memorize everything.  
A good Linux admin knows **how to find help quickly**.

Linux provides built-in documentation tools such as:

- `man`
- `--help`
- `info`
- `apropos`
- `whatis`
- `/usr/share/doc`
- Bash built-in help

These tools help you understand commands, options, files, and system behavior directly from the terminal.

---

# 2. Why Getting Help is Important

Linux has thousands of commands and many options.

For example:

```bash
ls
cp
tar
find
grep
useradd
systemctl
```

Each command may have many options.

Instead of searching randomly online, Linux provides local documentation installed on the system.

This is useful because:

- It works offline
- It matches your installed system version
- It is reliable
- It helps in exams like RHCSA
- It helps admins solve problems faster

---

# 3. Manual Pages Overview

Manual pages, or **man pages**, are built-in Linux documentation pages.

They explain:

- What a command does
- How to use it
- Available options
- Examples sometimes
- Related commands
- Configuration file formats

The command used to open manual pages is:

```bash
man
```

Example:

```bash
man ls
```

This opens the manual page for the `ls` command.

---

# 4. Basic `man` Command

## Syntax

```bash
man command_name
```

Example:

```bash
man date
```

This opens the manual page for the `date` command.

Another example:

```bash
man passwd
```

This opens the manual page for the `passwd` command.

---

# 5. Structure of a Man Page

A man page usually contains sections like:

## NAME

Shows the command name and short description.

Example:

```txt
ls - list directory contents
```

## SYNOPSIS

Shows the command syntax.

Example:

```txt
ls [OPTION]... [FILE]...
```

This means:

- `ls` is the command
- `[OPTION]` means options are optional
- `[FILE]` means file or directory arguments are optional
- `...` means you can use more than one option or argument

---

# 6. Navigating Inside a Man Page

When you open a man page, you can move inside it using keyboard keys.

| Key | Meaning |
|---|---|
| `Space` | Move down one page |
| `b` | Move up one page |
| `Enter` | Move down one line |
| `k` | Move up one line |
| `g` | Go to beginning |
| `G` | Go to end |
| `/word` | Search for a word |
| `n` | Next search result |
| `N` | Previous search result |
| `q` | Quit |

Example:

```bash
man ls
```

Then search inside it:

```txt
/recursive
```

Press:

```txt
n
```

to go to the next match.

Press:

```txt
q
```

to quit.

---

# 7. Man Page Sections

Man pages are divided into numbered sections.

This is important because the same word can have more than one manual page.

| Section | Meaning |
|---|---|
| `1` | User commands |
| `2` | System calls |
| `3` | Library functions |
| `4` | Device files |
| `5` | File formats and configuration files |
| `6` | Games |
| `7` | Miscellaneous |
| `8` | System administration commands |
| `9` | Kernel documentation |

---

## Important Sections for Linux Admins

The most important sections are usually:

| Section | Use |
|---|---|
| `1` | Normal commands |
| `5` | Configuration files |
| `8` | Admin commands |

---

## Example: `passwd`

There is more than one man page related to `passwd`.

To open the command manual:

```bash
man 1 passwd
```

To open the `/etc/passwd` file format manual:

```bash
man 5 passwd
```

This is very important.

`passwd` as a command is different from `/etc/passwd` as a file.

---

# 8. Search for Man Pages

## `man -k`

The `man -k` command searches manual page names and descriptions.

It is similar to `apropos`.

Syntax:

```bash
man -k keyword
```

Example:

```bash
man -k password
```

This searches for man pages related to passwords.

Another example:

```bash
man -k network
```

This searches for manual pages related to networking.

---

## `apropos`

`apropos` also searches for commands related to a keyword.

Example:

```bash
apropos password
```

Example output:

```txt
passwd (1) - update user's authentication tokens
passwd (5) - password file
```

This helps when you do not know the exact command name.

---

## `whatis`

The `whatis` command gives a short description of a command.

Example:

```bash
whatis ls
```

Output example:

```txt
ls (1) - list directory contents
```

Another example:

```bash
whatis passwd
```

Output may show:

```txt
passwd (1) - update user's authentication tokens
passwd (5) - password file
```

---

# 9. Searching Inside Man Pages

After opening a man page, you can search inside it using `/`.

Example:

```bash
man ls
```

Then type:

```txt
/hidden
```

This searches for the word `hidden`.

To go to the next result:

```txt
n
```

To go to the previous result:

```txt
N
```

To quit:

```txt
q
```

---

# 10. Using `--help`

Many commands support the `--help` option.

It gives a quick summary of command usage.

Example:

```bash
ls --help
```

Another example:

```bash
cp --help
```

This usually shows:

- Command syntax
- Common options
- Short explanation

Use `--help` when you want quick information.

Use `man` when you want detailed information.

---

## Difference Between `man` and `--help`

| Tool | Use |
|---|---|
| `man` | Detailed documentation |
| `--help` | Quick command help |
| `apropos` | Search for related commands |
| `whatis` | Short command description |

---

# 11. Bash Built-in Help

Some commands are built into the Bash shell.

Examples:

```bash
cd
alias
history
type
echo
```

For Bash built-in commands, you can use:

```bash
help command
```

Example:

```bash
help cd
```

Another example:

```bash
help history
```

This is useful because some shell commands may not have normal man pages in the same way external programs do.

---

# 12. Documentation in `/usr/share/doc`

Many packages install extra documentation in:

```bash
/usr/share/doc
```

Example:

```bash
ls /usr/share/doc
```

This directory may contain:

- README files
- Examples
- License files
- Configuration examples
- Package documentation

Example:

```bash
ls /usr/share/doc/bash
```

This shows documentation related to Bash if installed.

---
1
# 13. Useful Help Commands Summary

| Command | Use |
|---|---|
| `man command` | Open manual page |
| `man 5 file` | Open section 5 manual page |
| `man -k keyword` | Search man pages by keyword |
| `apropos keyword` | Search related commands |
| `whatis command` | Show short description |
| `command --help` | Show quick command help |
| `help command` | Help for Bash built-ins |
| `type command` | Show command type |
| `info command` | Open info documentation |
| `rpm -qd package` | Show package documentation files |
| `dnf info package` | Show package information |

---
# Chapter5: Create,View, and Editing Text Files

## 1. Main Idea

This chapter explains how to work with text files from the Linux command line.

It covers:

- Input and output redirection
- Pipes
- Editing files using Vim
- Vim modes and useful commands
- Shell variables
- User-defined variables
- Permanent environment variables

In Linux administration, text files are very important because many system configurations are stored as text files.

Examples:

```bash
/etc/passwd
/etc/hosts
/etc/fstab
/etc/ssh/sshd_config
~/.bashrc
```

A Linux administrator must know how to create, view, edit, redirect, and process text files efficiently.

---

# 2. Input and Output Redirection

## What is Redirection?

Redirection means changing where the command gets input from or sends output to.

Normally:

```text
Keyboard → Command → Screen
```

With redirection, we can send output to a file or read input from a file.

```text
Command → File
File → Command
```

---

# 3. Standard Streams

Linux commands use three standard streams:

| Stream | Number | Meaning |
|---|---|---|
| Standard Input | `0` | Input, usually keyboard |
| Standard Output | `1` | Normal output, usually screen |
| Standard Error | `2` | Error output, usually screen |

---

## Standard Output `>`

The `>` operator redirects command output to a file.

Example:

```bash
echo "Hello Linux" > file.txt
```

This creates `file.txt` and writes the text inside it.

Important:

If the file already exists, `>` overwrites it.

Example:

```bash
date > today.txt
```

This saves the output of `date` into `today.txt`.

---

## Append Output `>>`

The `>>` operator adds output to the end of a file without deleting old content.

Example:

```bash
echo "New line" >> file.txt
```

Difference:

| Operator | Meaning |
|---|---|
| `>` | Overwrite file |
| `>>` | Append to file |

---

## Redirect Error `2>`

Errors can be redirected using `2>`.

Example:

```bash
ls /wrongdirectory 2> error.txt
```

This saves the error message inside `error.txt`.

---

## Redirect Output and Error Together

To redirect both normal output and errors:

```bash
command &> file.txt
```

Example:

```bash
ls /home /wrongdirectory &> result.txt
```

This saves both success output and error output in the same file.

---

## Redirect Input `<`

The `<` operator sends file content as input to a command.

Example:

```bash
wc -l < file.txt
```

This counts the number of lines in `file.txt`.

Another example:

```bash
sort < names.txt
```

This sorts the content of `names.txt`.

---

# 4. Useful Redirection Examples

Create a file:

```bash
echo "Linux Admin Notes" > notes.txt
```

Add another line:

```bash
echo "Chapter 05" >> notes.txt
```

Save current date:

```bash
date > date.txt
```

Save command error:

```bash
ls /notfound 2> errors.txt
```

Save output and errors:

```bash
find /etc -name "*.conf" &> result.txt
```

---

# 5. Piping in Linux

## What is a Pipe?

A pipe sends the output of one command as input to another command.

The pipe symbol is:

```bash
|
```

Normal redirection sends output to a file.

Pipe sends output to another command.

```text
Command 1 → Command 2
```

---

## Basic Pipe Example

```bash
ls -l | less
```

Meaning:

1. `ls -l` lists files in long format
2. `less` displays the output page by page

---

## Pipe with `grep`

```bash
cat /etc/passwd | grep root
```

This searches for `root` inside `/etc/passwd`.

Better way:

```bash
grep root /etc/passwd
```

But the pipe version helps understand how pipes work.

---

## Pipe with `wc`

```bash
ls | wc -l
```

This counts how many files/directories are listed.

Explanation:

| Command | Meaning |
|---|---|
| `ls` | List files |
| `wc -l` | Count lines |

---

## Pipe with `sort` and `uniq`

```bash
cat names.txt | sort | uniq
```

Meaning:

1. Read `names.txt`
2. Sort lines
3. Remove repeated lines

---

## Pipe with `tee`

The `tee` command sends output to the screen and saves it to a file at the same time.

Example:

```bash
ls -l | tee output.txt
```

This displays the output and saves it into `output.txt`.

Append using `tee -a`:

```bash
date | tee -a log.txt
```

---

# 6. Redirection vs Pipe

| Feature | Redirection | Pipe |
|---|---|---|
| Symbol | `>`, `>>`, `<`, `2>` | `|` |
| Sends output to | File | Another command |
| Example | `ls > files.txt` | `ls | less` |
| Main use | Save or read from files | Chain commands together |

---

# 7. Vim Editor

## What is Vim?

Vim is a powerful command-line text editor used in Linux.

It is commonly used by system administrators to edit configuration files.

Example:

```bash
vim file.txt
```

If the file exists, Vim opens it.

If the file does not exist, Vim creates it when you save.

---

## Why Vim is Important

Vim is important because:

- It works inside the terminal
- It is available on most Linux systems
- It can be used over SSH
- It is useful for editing system configuration files
- It is fast once you learn the basics

Example:

```bash
sudo vim /etc/ssh/sshd_config
```

---

# 8. Vim Modes

Vim has different modes.

The most important modes are:

| Mode | Use |
|---|---|
| Normal mode | Move, delete, copy, paste, run commands |
| Insert mode | Type and edit text |
| Command-line mode | Save, quit, search, run Vim commands |
| Visual mode | Select text |

---

# 9. Normal Mode

When you open Vim, you start in **Normal mode**.

In Normal mode, typing letters does not insert text.  
Instead, keys are used as commands.

Example:

| Key | Meaning |
|---|---|
| `h` | Move left |
| `j` | Move down |
| `k` | Move up |
| `l` | Move right |

You can also use arrow keys, but Vim users often use `h`, `j`, `k`, and `l`.

---

# 10. Insert Mode

Insert mode is used to write text.

To enter Insert mode:

| Key | Meaning |
|---|---|
| `i` | Insert before cursor |
| `a` | Insert after cursor |
| `o` | Open new line below |
| `O` | Open new line above |

To return to Normal mode:

```text
Esc
```

Important:

If you are stuck in Vim, press `Esc` first.

---

# 11. Command-Line Mode

Command-line mode starts with `:`.

It is used for saving and quitting.

| Command | Meaning |
|---|---|
| `:w` | Save |
| `:q` | Quit |
| `:wq` | Save and quit |
| `:x` | Save and quit |
| `:q!` | Quit without saving |
| `:w filename` | Save as another file |

Example:

```text
:wq
```

This saves the file and exits Vim.

---

# 12. Basic Vim Editing Commands

## Delete

| Command | Meaning |
|---|---|
| `x` | Delete one character |
| `dd` | Delete current line |
| `3dd` | Delete 3 lines |

---

## Copy and Paste

| Command | Meaning |
|---|---|
| `yy` | Copy current line |
| `3yy` | Copy 3 lines |
| `p` | Paste after cursor |
| `P` | Paste before cursor |

---

## Undo and Redo

| Command | Meaning |
|---|---|
| `u` | Undo |
| `Ctrl + r` | Redo |

---

## Search

Search forward:

```text
/word
```

Go to next result:

```text
n
```

Go to previous result:

```text
N
```

Search backward:

```text
?word
```

---

# 13. Extended and Visual Mode

## Visual Mode

Visual mode is used to select text.

| Key | Meaning |
|---|---|
| `v` | Select characters |
| `V` | Select full lines |
| `Ctrl + v` | Select block/column |

After selecting text, you can use:

| Key | Meaning |
|---|---|
| `d` | Delete selected text |
| `y` | Copy selected text |
| `p` | Paste |
| `>` | Indent |
| `<` | Unindent |

---

## Example: Copy a Block of Text

1. Press `v`
2. Move using arrow keys or `h/j/k/l`
3. Press `y` to copy
4. Move to another place
5. Press `p` to paste

---

# 14. Vim Cheat Sheet

## Open File

```bash
vim file.txt
```

## Enter Insert Mode

```text
i
```

## Leave Insert Mode

```text
Esc
```

## Save

```text
:w
```

## Quit

```text
:q
```

## Save and Quit

```text
:wq
```

## Quit Without Saving

```text
:q!
```

## Delete Line

```text
dd
```

## Copy Line

```text
yy
```

## Paste

```text
p
```

## Search

```text
/word
```

## Undo

```text
u
```

---

# 15. User-Defined Variables

## What is a Variable?

A variable is a name that stores a value.

In Bash, variables can store text, numbers, paths, or command results.

Example:

```bash
name="Linux"
```

Print the variable:

```bash
echo $name
```

Output:

```text
Linux
```

---

## Rules for Variable Names

Variable names should:

- Start with a letter or underscore
- Contain letters, numbers, or underscores
- Not contain spaces
- Usually be written in uppercase for environment variables

Valid examples:

```bash
NAME="Ahmad"
COURSE="Linux Admin"
FILE_PATH="/home/user/file.txt"
```

Invalid examples:

```bash
my name="Ahmad"
1name="Ahmad"
course-name="Linux"
```

---

## Important Syntax Rule

No spaces around `=`.

Correct:

```bash
name="Linux"
```

Wrong:

```bash
name = "Linux"
```

---

# 16. Using Variables

Create variable:

```bash
course="Linux Admin 1"
```

Print variable:

```bash
echo $course
```

Use variable inside text:

```bash
echo "I am learning $course"
```

Output:

```text
I am learning Linux Admin 1
```

---

# 17. Command Substitution

Command substitution stores the output of a command in a variable.

Example:

```bash
today=$(date)
```

Print it:

```bash
echo $today
```

Another example:

```bash
current_dir=$(pwd)
echo $current_dir
```

---

# 18. Shell Variables

Shell variables are variables used by the shell.

Some are created by the system automatically.

Examples:

| Variable | Meaning |
|---|---|
| `$USER` | Current username |
| `$HOME` | Current user's home directory |
| `$SHELL` | Current shell |
| `$PWD` | Current directory |
| `$OLDPWD` | Previous directory |
| `$PATH` | Directories where commands are searched |
| `$HOSTNAME` | System hostname |
| `$HISTSIZE` | Number of commands saved in history |

---

## Examples

```bash
echo $USER
```

Shows the current user.

```bash
echo $HOME
```

Shows the home directory.

```bash
echo $SHELL
```

Shows the current shell.

```bash
echo $PWD
```

Shows the current directory.

---

# 19. The `PATH` Variable

`PATH` is one of the most important shell variables.

It tells the shell where to search for commands.

Check your PATH:

```bash
echo $PATH
```

Example output:

```text
/usr/local/bin:/usr/bin:/bin:/usr/local/sbin:/usr/sbin
```

Directories are separated by `:`.

When you type:

```bash
ls
```

The shell searches for `ls` inside the directories listed in `$PATH`.

You can check where a command is located:

```bash
which ls
```

or:

```bash
command -v ls
```

---

# 20. Environment Variables

A shell variable exists only in the current shell.

An environment variable can be used by child processes and programs started from the shell.

To make a variable available to other programs, use `export`.

Example:

```bash
MYVAR="Hello"
export MYVAR
```

Or in one line:

```bash
export MYVAR="Hello"
```

Check it:

```bash
printenv MYVAR
```

---

## `set`, `env`, and `printenv`

| Command | Use |
|---|---|
| `set` | Shows shell variables and functions |
| `env` | Shows environment variables |
| `printenv` | Shows environment variables |
| `echo $VAR` | Prints a variable value |

Example:

```bash
env
```

Example:

```bash
printenv HOME
```

---

# 21. Unset Variables

To remove a variable:

```bash
unset variable_name
```

Example:

```bash
name="Linux"
echo $name
unset name
echo $name
```

After `unset`, the variable has no value.

---

# 22. Permanent Variables

Variables created in the terminal are temporary.

Example:

```bash
export COURSE="Linux Admin"
```

This variable disappears when the terminal is closed.

To make a variable permanent, add it to a shell startup file.

---

## User Permanent Variables

For the current user, add variables to:

```bash
~/.bashrc
```

Example:

```bash
vim ~/.bashrc
```

Add:

```bash
export COURSE="Linux Admin 1"
```

Save and quit.

Apply changes:

```bash
source ~/.bashrc
```

or:

```bash
. ~/.bashrc
```

Now test:

```bash
echo $COURSE
```

---

## System-Wide Permanent Variables

For all users, variables can be added to:

```bash
/etc/profile
/etc/bashrc
/etc/profile.d/*.sh
```

Best practice:

Create a file inside:

```bash
/etc/profile.d/
```

Example:

```bash
sudo vim /etc/profile.d/course.sh
```

Add:

```bash
export COURSE="Linux Admin 1"
```

Save and apply:

```bash
source /etc/profile.d/course.sh
```

This makes the variable available system-wide.

---

# 23. Editing Shell Startup Files Safely

Before editing important config files, make a backup.

Example:

```bash
cp ~/.bashrc ~/.bashrc.bak
```

Then edit:

```bash
vim ~/.bashrc
```

If something goes wrong, restore:

```bash
cp ~/.bashrc.bak ~/.bashrc
```

---

# 24. Important Command Summary

| Command | Use |
|---|---|
| `>` | Redirect output and overwrite |
| `>>` | Redirect output and append |
| `<` | Redirect input |
| `2>` | Redirect errors |
| `&>` | Redirect output and errors |
| `tee` | Show output and save to file |
| `vim file` | Open file in Vim |
| `i` | Enter insert mode in Vim |
| `Esc` | Return to normal mode |
| `:w` | Save in Vim |
| `:q` | Quit Vim |
| `:wq` | Save and quit |
| `:q!` | Quit without saving |
| `dd` | Delete line in Vim |
| `yy` | Copy line in Vim |
| `p` | Paste in Vim |
| `echo $VAR` | Print variable value |
| `export VAR=value` | Create environment variable |
| `unset VAR` | Remove variable |
| `env` | Show environment variables |
| `printenv` | Show environment variables |
| `source file` | Reload shell config file |

---
# Chapter6: Managing Local Users and Groups

## 1. Main Idea

This chapter explains how Linux manages local users and groups.

In Linux, every user has an account, and every account has an ID number called a **UID**.  
Every group also has an ID number called a **GID**.

Linux uses users and groups to control:

- Who can log in
- Who owns files
- Who can read, write, or execute files
- Who can run administrative commands
- Who can access system resources

Important files:

```bash
/etc/passwd
/etc/shadow
/etc/group
/etc/gshadow
```

---

# 2. User Identifier — UID

## What is UID?

UID stands for:

```text
User Identifier
```

It is a unique number used by Linux to identify each user.

Linux does not depend mainly on usernames internally.  
It depends on UID numbers.

Example:

```bash
id username
```

Example:

```bash
id ahmad
```

Output example:

```text
uid=1000(ahmad) gid=1000(ahmad) groups=1000(ahmad),10(wheel)
```

Meaning:

| Part | Meaning |
|---|---|
| `uid=1000` | User ID |
| `gid=1000` | Primary group ID |
| `groups=` | Other groups the user belongs to |

---

## Important UID Ranges

Common UID ranges in RHEL-based systems:

| UID | Meaning |
|---|---|
| `0` | Root user |
| `1 - 999` | System users |
| `1000+` | Normal users |

The root user always has:

```text
UID = 0
```

This is why root has full control over the system.

---

## Where are users stored?

User account information is stored in:

```bash
/etc/passwd
```

View it:

```bash
cat /etc/passwd
```

Each line represents one user.

Example:

```text
ahmad:x:1000:1000:Ahmad Alaa:/home/ahmad:/bin/bash
```

Fields are separated by `:`.

| Field | Meaning |
|---|---|
| `ahmad` | Username |
| `x` | Password placeholder |
| `1000` | UID |
| `1000` | GID |
| `Ahmad Alaa` | Comment / full name |
| `/home/ahmad` | Home directory |
| `/bin/bash` | Login shell |

Important note:

The real encrypted password is not stored in `/etc/passwd`.  
It is stored in:

```bash
/etc/shadow
```

---

# 3. Group Identifier — GID

## What is GID?

GID stands for:

```text
Group Identifier
```

It is a unique number used by Linux to identify a group.

Groups are used to give permissions to multiple users at the same time.

Example:

```bash
id ahmad
```

Output:

```text
uid=1000(ahmad) gid=1000(ahmad) groups=1000(ahmad),10(wheel)
```

Here:

```text
gid=1000(ahmad)
```

means the primary group is `ahmad`.

---

## Primary Group vs Supplementary Groups

### Primary Group

Every user has one primary group.

When the user creates a file, the file usually belongs to the user's primary group.

Check primary group:

```bash
id username
```

---

### Supplementary Groups

A user can belong to extra groups.

Example:

```text
groups=1000(ahmad),10(wheel)
```

Here, `wheel` is an extra group.

The `wheel` group is important because users in this group can usually run commands with `sudo`.

---

## Where are groups stored?

Group information is stored in:

```bash
/etc/group
```

View it:

```bash
cat /etc/group
```

Example line:

```text
wheel:x:10:ahmad
```

Fields:

| Field | Meaning |
|---|---|
| `wheel` | Group name |
| `x` | Password placeholder |
| `10` | GID |
| `ahmad` | Users inside the group |

---

# 4. Gain Superuser Access

## What is the Superuser?

The superuser is the administrator account in Linux.

The superuser is called:

```text
root
```

Root can do anything on the system, such as:

- Install packages
- Delete system files
- Create users
- Change passwords
- Modify system configuration
- Start and stop services

Because root has full control, it must be used carefully.

---

## Using `su`

The `su` command means:

```text
switch user
```

To switch to root:

```bash
su -
```

Then enter the root password.

The `-` is important because it loads the root environment.

Exit root shell:

```bash
exit
```

---

## Using `sudo`

The `sudo` command allows a normal user to run a command with administrative privileges.

Example:

```bash
sudo dnf update
```

Another example:

```bash
sudo useradd testuser
```

With `sudo`, you do not need to log in as root directly.

This is safer because:

- Only specific users can use it
- Commands can be logged
- Users use their own password
- It avoids staying as root all the time

---

## `su` vs `sudo`

| Command | Meaning |
|---|---|
| `su -` | Switch to root shell |
| `sudo command` | Run one command as root |
| `exit` | Leave root shell |

Simple rule:

```text
Use sudo for one admin command.
Use su - when you need a full root shell.
```

---

# 5. Grant Superuser Access

## The `wheel` Group

In RHEL-based systems, users in the `wheel` group can usually use `sudo`.

Check if a user is in the wheel group:

```bash
id username
```

Example:

```bash
id ahmad
```

---

## Add User to Wheel Group

To give a user sudo access:

```bash
sudo usermod -aG wheel username
```

Example:

```bash
sudo usermod -aG wheel ahmad
```

Explanation:

| Part | Meaning |
|---|---|
| `usermod` | Modify user |
| `-a` | Append to group |
| `-G` | Supplementary group |
| `wheel` | Admin group |
| `username` | User to modify |

Very important:

Use `-aG`, not only `-G`.

If you use only `-G`, you may remove the user from other groups.

---

## Test sudo access

After adding the user to `wheel`, log out and log in again.

Then test:

```bash
sudo whoami
```

Expected output:

```text
root
```

---

## Sudoers File

Sudo permissions are controlled by:

```bash
/etc/sudoers
```

You should edit it using:

```bash
sudo visudo
```

Do not edit `/etc/sudoers` directly with a normal text editor.

Why?

Because `visudo` checks for syntax errors before saving.

A syntax error in the sudoers file can break sudo access.

---

# 6. Create, Modify, and Delete Users

## Create a User

Use:

```bash
sudo useradd username
```

Example:

```bash
sudo useradd ali
```

This creates:

- New user account
- Home directory, usually `/home/ali`
- Primary group
- Default shell

---

## Create User with Specific Home Directory

```bash
sudo useradd -d /custom/home username
```

Example:

```bash
sudo useradd -d /home/devuser devuser
```

---

## Create User with Specific Shell

```bash
sudo useradd -s /bin/bash username
```

Example:

```bash
sudo useradd -s /bin/bash ali
```

---

## Set User Password

After creating a user, set a password:

```bash
sudo passwd username
```

Example:

```bash
sudo passwd ali
```

---

## Modify a User

Use:

```bash
sudo usermod [options] username
```

Change username:

```bash
sudo usermod -l newname oldname
```

Change home directory:

```bash
sudo usermod -d /new/home username
```

Move old home content to new home:

```bash
sudo usermod -d /new/home -m username
```

Change shell:

```bash
sudo usermod -s /bin/bash username
```

Add user to group:

```bash
sudo usermod -aG groupname username
```

Example:

```bash
sudo usermod -aG wheel ali
```

---

## Delete a User

Delete user only:

```bash
sudo userdel username
```

Delete user and home directory:

```bash
sudo userdel -r username
```

Example:

```bash
sudo userdel -r ali
```

Important:

Use `-r` carefully because it removes the user’s home directory and mail spool.

---

# 7. Create, Modify, and Delete Groups

## Create a Group

```bash
sudo groupadd groupname
```

Example:

```bash
sudo groupadd developers
```

---

## Create Group with Specific GID

```bash
sudo groupadd -g 2000 groupname
```

Example:

```bash
sudo groupadd -g 2000 developers
```

---

## Modify Group Name

```bash
sudo groupmod -n newname oldname
```

Example:

```bash
sudo groupmod -n devs developers
```

---

## Delete a Group

```bash
sudo groupdel groupname
```

Example:

```bash
sudo groupdel devs
```

---

## Add User to Group

```bash
sudo usermod -aG groupname username
```

Example:

```bash
sudo usermod -aG developers ali
```

Check:

```bash
id ali
```

---

# 8. Change User Password

## Change Your Own Password

```bash
passwd
```

The system asks for:

1. Current password
2. New password
3. Confirm new password

---

## Change Another User’s Password

Root or sudo user can change another user's password:

```bash
sudo passwd username
```

Example:

```bash
sudo passwd ali
```

---

## Password Information

Password data is stored in:

```bash
/etc/shadow
```

View it as root:

```bash
sudo cat /etc/shadow
```

The `/etc/shadow` file contains encrypted passwords and password aging information.

Normal users cannot read it.

---

# 9. Password Aging with `chage`

The `chage` command controls password expiration settings.

View password aging info:

```bash
sudo chage -l username
```

Example:

```bash
sudo chage -l ali
```

---

## Force User to Change Password at Next Login

```bash
sudo chage -d 0 username
```

Example:

```bash
sudo chage -d 0 ali
```

This makes the user change the password when logging in next time.

---

## Set Maximum Password Age

```bash
sudo chage -M 90 username
```

This means the password expires after 90 days.

---

## Set Minimum Password Age

```bash
sudo chage -m 7 username
```

This means the user must wait 7 days before changing the password again.

---

## Set Warning Days

```bash
sudo chage -W 7 username
```

This warns the user 7 days before password expiration.

---

# 10. Restrict User Access

Sometimes an administrator needs to restrict a user account.

This can be done in different ways.

---

## Lock a User Password

```bash
sudo passwd -l username
```

Example:

```bash
sudo passwd -l ali
```

This locks the user's password.

Unlock it:

```bash
sudo passwd -u username
```

Example:

```bash
sudo passwd -u ali
```

---

## Lock User Account with `usermod`

```bash
sudo usermod -L username
```

Unlock:

```bash
sudo usermod -U username
```

---

## Expire a User Account

```bash
sudo chage -E 0 username
```

This immediately expires the account.

Set account expiration date:

```bash
sudo chage -E YYYY-MM-DD username
```

Example:

```bash
sudo chage -E 2026-12-31 ali
```

---

## Prevent Interactive Login

You can change the user shell to `/sbin/nologin`.

```bash
sudo usermod -s /sbin/nologin username
```

Example:

```bash
sudo usermod -s /sbin/nologin ali
```

This prevents the user from logging into a shell.

Check available shells:

```bash
cat /etc/shells
```

---

# 11. Important Files

| File | Use |
|---|---|
| `/etc/passwd` | User account information |
| `/etc/shadow` | Encrypted passwords and password aging |
| `/etc/group` | Group information |
| `/etc/gshadow` | Secure group information |
| `/etc/sudoers` | Sudo permissions |
| `/etc/sudoers.d/` | Extra sudo configuration files |
| `/etc/login.defs` | Default settings for users and passwords |
| `/etc/default/useradd` | Default settings for `useradd` |

---

# 12. Useful Commands Summary

| Command | Use |
|---|---|
| `id username` | Show UID, GID, and groups |
| `whoami` | Show current username |
| `su -` | Switch to root |
| `sudo command` | Run command as root |
| `useradd username` | Create user |
| `usermod` | Modify user |
| `userdel username` | Delete user |
| `userdel -r username` | Delete user and home directory |
| `passwd username` | Change password |
| `groupadd groupname` | Create group |
| `groupmod` | Modify group |
| `groupdel groupname` | Delete group |
| `chage -l username` | Show password aging info |
| `passwd -l username` | Lock user password |
| `passwd -u username` | Unlock user password |
| `usermod -aG group user` | Add user to group |
| `visudo` | Safely edit sudoers file |

---

# 13. Practical Examples

## Create a new user

```bash
sudo useradd student1
sudo passwd student1
```

---

## Add user to wheel group

```bash
sudo usermod -aG wheel student1
```

Check:

```bash
id student1
```

---

## Create a group and add user to it

```bash
sudo groupadd developers
sudo usermod -aG developers student1
```

---

## Lock user account

```bash
sudo passwd -l student1
```

---

## Unlock user account

```bash
sudo passwd -u student1
```

---

## Delete user with home directory

```bash
sudo userdel -r student1
```

---
# Chapter7: Controlling Access to Files

## 1. Main Idea

This chapter explains how Linux controls access to files and directories.

Linux is a multi-user operating system, so file permissions are very important.  
Permissions decide who can:

- Read a file
- Modify a file
- Execute a file
- Enter a directory
- Create or delete files inside a directory

Linux controls access using:

- File ownership
- Group ownership
- Permission bits
- Special permissions
- Default permissions

Important commands:

```bash
ls -l
chmod
chown
chgrp
umask
```

---

# 2. Linux File System Permissions

## Viewing Permissions

To view permissions, use:

```bash
ls -l
```

Example:

```bash
-rw-r--r-- 1 ahmad developers 1200 Jun 18 notes.txt
```

The first part is:

```text
-rw-r--r--
```

This shows the file type and permissions.

---

## Permission Structure

Example:

```text
-rw-r--r--
```

Breakdown:

```text
-    rw-   r--   r--
|     |     |     |
|     |     |     └── Others permissions
|     |     └──────── Group permissions
|     └────────────── User/owner permissions
└──────────────────── File type
```

---

## File Type Symbol

The first character shows the file type.

| Symbol | Meaning |
|---|---|
| `-` | Regular file |
| `d` | Directory |
| `l` | Symbolic link |
| `c` | Character device |
| `b` | Block device |
| `p` | Pipe |
| `s` | Socket |

Example:

```bash
-rw-r--r-- notes.txt
drwxr-xr-x Documents
lrwxrwxrwx link.txt -> notes.txt
```

---

# 3. Permission Types

Linux has three basic permissions:

| Permission | Symbol | Number | Meaning |
|---|---|---|---|
| Read | `r` | `4` | View file content |
| Write | `w` | `2` | Modify file content |
| Execute | `x` | `1` | Run file as program/script |

---

## Permissions for Files

| Permission | Meaning for File |
|---|---|
| `r` | Read file content |
| `w` | Edit or modify file |
| `x` | Execute file as a program/script |

Example:

```bash
-rwxr-xr--
```

Meaning:

| Part | Meaning |
|---|---|
| `rwx` | Owner can read, write, execute |
| `r-x` | Group can read and execute |
| `r--` | Others can only read |

---

## Permissions for Directories

Directory permissions have different meanings.

| Permission | Meaning for Directory |
|---|---|
| `r` | List directory contents |
| `w` | Create, delete, or rename files inside |
| `x` | Enter/access the directory |

Important:

For directories, `x` means you can enter the directory using `cd`.

Example:

```bash
cd Documents
```

Without execute permission on a directory, you cannot access files inside it even if you know their names.

---

# 4. User, Group, and Others

Linux permissions are divided into three categories.

| Category | Meaning |
|---|---|
| User / Owner | The user who owns the file |
| Group | The group that owns the file |
| Others | Everyone else |

Example:

```bash
-rw-r----- 1 ahmad developers notes.txt
```

Meaning:

| Part | Meaning |
|---|---|
| `ahmad` | File owner |
| `developers` | File group |
| `rw-` | Owner can read and write |
| `r--` | Group can read |
| `---` | Others have no permissions |

---

# 5. Changing Permissions with `chmod`

The `chmod` command changes file or directory permissions.

```bash
chmod permissions file
```

There are two ways to use `chmod`:

1. Symbolic method
2. Numeric method

---

# 6. Symbolic Method

The symbolic method uses letters.

## User categories

| Symbol | Meaning |
|---|---|
| `u` | User / owner |
| `g` | Group |
| `o` | Others |
| `a` | All users |

## Operations

| Symbol | Meaning |
|---|---|
| `+` | Add permission |
| `-` | Remove permission |
| `=` | Set exact permission |

## Permission symbols

| Symbol | Meaning |
|---|---|
| `r` | Read |
| `w` | Write |
| `x` | Execute |

---

## Symbolic Examples

Add execute permission for owner:

```bash
chmod u+x script.sh
```

Remove write permission from group:

```bash
chmod g-w file.txt
```

Give others read permission:

```bash
chmod o+r file.txt
```

Give everyone execute permission:

```bash
chmod a+x script.sh
```

Set exact permissions for owner:

```bash
chmod u=rw file.txt
```

Set exact permissions for user, group, and others:

```bash
chmod u=rwx,g=rx,o=r file.txt
```

---

# 7. Numeric Method

The numeric method uses numbers.

| Permission | Number |
|---|---|
| Read `r` | `4` |
| Write `w` | `2` |
| Execute `x` | `1` |

Add the numbers together.

| Permission | Value |
|---|---|
| `r--` | `4` |
| `rw-` | `6` |
| `r-x` | `5` |
| `rwx` | `7` |
| `---` | `0` |

---

## Common Numeric Permissions

| Permission | Meaning |
|---|---|
| `777` | Everyone can read, write, execute |
| `755` | Owner full access, others read and execute |
| `700` | Only owner has full access |
| `644` | Owner read/write, others read only |
| `600` | Only owner can read/write |
| `640` | Owner read/write, group read, others none |

---

## Numeric Examples

Give owner full access, group and others read/execute:

```bash
chmod 755 script.sh
```

Give owner read/write, others read only:

```bash
chmod 644 file.txt
```

Private file:

```bash
chmod 600 secret.txt
```

Private directory:

```bash
chmod 700 private_dir
```

---

# 8. Change Permissions Recursively

To change permissions for a directory and everything inside it, use `-R`.

```bash
chmod -R 755 mydir
```

Important:

Be careful with recursive permission changes.

This command affects all files and directories inside `mydir`.

---

# 9. Changing File and Directory Ownership

## `chown`

The `chown` command changes the owner of a file or directory.

Syntax:

```bash
sudo chown user file
```

Example:

```bash
sudo chown ahmad notes.txt
```

This makes `ahmad` the owner of `notes.txt`.

---

## Change Owner and Group Together

```bash
sudo chown user:group file
```

Example:

```bash
sudo chown ahmad:developers notes.txt
```

This changes:

- Owner to `ahmad`
- Group to `developers`

---

## Change Only Group Using `chown`

```bash
sudo chown :developers notes.txt
```

This changes only the group.

---

## Recursive Ownership Change

```bash
sudo chown -R ahmad:developers project/
```

This changes ownership of the directory and all files inside it.

---

# 10. Change Group Ownership with `chgrp`

The `chgrp` command changes the group owner.

```bash
sudo chgrp group file
```

Example:

```bash
sudo chgrp developers notes.txt
```

Recursive example:

```bash
sudo chgrp -R developers project/
```

---

# 11. Special Permissions

Linux has three special permissions:

| Special Permission | Symbol | Numeric Value |
|---|---|---|
| SetUID | `s` | `4` |
| SetGID | `s` | `2` |
| Sticky Bit | `t` | `1` |

Special permissions are added before normal permissions.

Example:

```bash
chmod 4755 file
chmod 2755 directory
chmod 1777 directory
```

---

# 12. SetUID

## What is SetUID?

SetUID allows a file to run with the permissions of the file owner, not the user who executed it.

It is usually used on executable files.

Example:

```bash
ls -l /usr/bin/passwd
```

Output example:

```bash
-rwsr-xr-x 1 root root /usr/bin/passwd
```

Notice:

```text
rws
```

The `s` means SetUID is enabled.

The `passwd` command needs SetUID because normal users must be able to change their passwords, but the password file is protected.

---

## Set SetUID

Symbolic:

```bash
chmod u+s file
```

Numeric:

```bash
chmod 4755 file
```

Remove SetUID:

```bash
chmod u-s file
```

Important:

SetUID can be dangerous if used incorrectly because it may give users elevated privileges.

---

# 13. SetGID

## SetGID on Files

SetGID allows an executable file to run with the permissions of the file group.

Set it:

```bash
chmod g+s file
```

Numeric:

```bash
chmod 2755 file
```

---

## SetGID on Directories

SetGID is very useful on directories.

When SetGID is applied to a directory, new files created inside inherit the directory group.

Example:

```bash
sudo mkdir /projects
sudo chgrp developers /projects
sudo chmod 2775 /projects
```

Now files created inside `/projects` will belong to the `developers` group.

This is useful for shared team directories.

---

# 14. Sticky Bit

## What is Sticky Bit?

Sticky bit is usually used on shared directories.

It allows users to create files inside a directory, but users can delete only their own files.

The most common example is:

```bash
/tmp
```

Check it:

```bash
ls -ld /tmp
```

Output example:

```bash
drwxrwxrwt root root /tmp
```

Notice the `t` at the end.

---

## Set Sticky Bit

Symbolic:

```bash
chmod +t directory
```

Numeric:

```bash
chmod 1777 directory
```

Example:

```bash
sudo chmod 1777 shared/
```

Remove sticky bit:

```bash
chmod -t directory
```

---

# 15. Special Permissions Summary

| Permission | Used On | Meaning |
|---|---|---|
| SetUID | Files | Run as file owner |
| SetGID | Files | Run as file group |
| SetGID | Directories | New files inherit directory group |
| Sticky Bit | Directories | Users delete only their own files |

---

# 16. Managing Default File Permissions

## What is `umask`?

`umask` controls the default permissions for newly created files and directories.

It removes permissions from the system default.

View current umask:

```bash
umask
```

Example output:

```bash
0022
```

---

## Default Base Permissions

Linux starts with these default maximum permissions:

| Type | Base Permission |
|---|---|
| File | `666` |
| Directory | `777` |

Why files use `666` not `777`?

Because new files should not be executable by default for security.

---

## How `umask` Works

Formula:

```text
Default permission = Base permission - umask
```

Example umask:

```text
022
```

For files:

```text
666 - 022 = 644
```

So new files become:

```text
rw-r--r--
```

For directories:

```text
777 - 022 = 755
```

So new directories become:

```text
rwxr-xr-x
```

---

## Common `umask` Values

| umask | New File Permission | New Directory Permission | Meaning |
|---|---|---|---|
| `022` | `644` | `755` | Default common setting |
| `002` | `664` | `775` | Good for group collaboration |
| `077` | `600` | `700` | Private files/directories |

---

## Change umask Temporarily

```bash
umask 077
```

Now newly created files will be private.

Test:

```bash
touch test.txt
mkdir testdir
ls -l
```

---

## Change umask Permanently

For current user, add it to:

```bash
~/.bashrc
```

Example:

```bash
vim ~/.bashrc
```

Add:

```bash
umask 077
```

Reload:

```bash
source ~/.bashrc
```

For all users, system-wide settings may be configured in files like:

```bash
/etc/profile
/etc/bashrc
/etc/login.defs
```

---

# 17. Practical Examples

## Example 1: Make a Script Executable

```bash
chmod u+x backup.sh
```

or:

```bash
chmod 755 backup.sh
```

Run it:

```bash
./backup.sh
```

---

## Example 2: Make a File Private

```bash
chmod 600 secret.txt
```

Only the owner can read and write it.

---

## Example 3: Create a Shared Group Directory

```bash
sudo groupadd developers
sudo mkdir /projects
sudo chown root:developers /projects
sudo chmod 2775 /projects
```

Meaning:

- Owner is `root`
- Group is `developers`
- Group members can collaborate
- New files inherit the `developers` group because of SetGID

---

## Example 4: Create a Public Temporary Directory

```bash
sudo mkdir /sharedtmp
sudo chmod 1777 /sharedtmp
```

Meaning:

- Everyone can create files
- Users can delete only their own files because of sticky bit

---

# 18. Important Commands Summary

| Command | Use |
|---|---|
| `ls -l` | Show file permissions |
| `ls -ld directory` | Show directory permissions |
| `chmod` | Change permissions |
| `chmod 755 file` | Set numeric permissions |
| `chmod u+x file` | Add execute for owner |
| `chown user file` | Change file owner |
| `chown user:group file` | Change owner and group |
| `chgrp group file` | Change group owner |
| `chmod u+s file` | Set SetUID |
| `chmod g+s file/dir` | Set SetGID |
| `chmod +t dir` | Set sticky bit |
| `umask` | Show default permission mask |
| `umask 077` | Set private default permissions |

---

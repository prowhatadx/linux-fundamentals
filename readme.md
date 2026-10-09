# Day 1 — Linux Commands + Facts

## General Commands

| Purpose       | Command     |
| ------------- | ----------- |
| Root user     | `sudo su -` |
| User Identity | `whoami`    |

---

## Calendar & Date

| Purpose                                  | Command           |
| ---------------------------------------- | ----------------- |
| Calendar (single month)                  | `cal` OR `cal -1` |
| Calendar (previous, current, next month) | `cal -3`          |
| Calendar (entire year)                   | `cal -y 2026`     |
| Calendar (month of any year)             | `cal feb 2026`    |
| Current Date & Time (UTC)                | `date`            |

---

## Create Empty Files

### Create File

```bash
touch filename
```

### Create Multiple Files

```bash
touch f1 f2
```

### Create Multiple Files (Efficiently)

```bash
touch file{1..5}
```

### Create Multiple Files (Leaving One)

```bash
touch f{1..3} f{5..8}
```

### Create File with Spaced Name

```bash
touch "file name"
```

OR

```bash
touch file\name
```

---

## Non-Empty Files

### Create File Using `cat`

```bash
cat > filename
```

OR

```bash
cat >> filename
```

### Overwrite Content in File

```bash
cat > filename
```

### Append Content in File

```bash
cat >> filename
```

### Create File Using `echo`

```bash
echo " content of file " > filename
```

OR

```bash
echo " content of file " >> filename
```

### Overwrite Content in File

```bash
echo " content of file " > filename
```

### Append Content in File

```bash
echo " content of file " >> filename
```

---

## Delete File

### Delete a File

```bash
rm filename
```

### Delete File Forcefully

```bash
rm -f filename
```

### Delete Multiple Files (Efficiently)

```bash
rm file{1..5}
```

### Delete All Files in Directory

```bash
rm *
```

---

## Directory Commands

### Make Directory (Folder)

```bash
mkdir foldername
```

### Delete Directory

```bash
rm -r foldername
```

### Delete Directory Forcefully

```bash
rm -rf foldername
```

### Delete Multiple Directories

```bash
rm -r foldername{1..6}
```

---

## Extra Commands

### See All the Files

```bash
ls
```

> `ls` — listing

### Read File Content

```bash
cat filename
```

---

## Important Notes

1. `rm` means **remove**
2. `r` means **recursive**
3. `-r` is used to delete the subfiles in directory
4. For `cat` command, enter values and then hit **Ctrl + D**

---

## Facts

* Linux is **GUI + CLI** *(Industry Standard: CLI)*
* Linux is **case sensitive**
* Linux is **space sensitive**
* Folders are called **Directory**
* Generally, **Files** is termed for both Files & Folders


# Day 2 — Vim Fundamentals & Others

## Day 1 Revision

| Command | Empty | Non-Empty | Read | Multi Files at the Same Time |
| ------- | ----- | --------- | ---- | ----------------------------- |
| `touch` | ✓ | ✗ | ✗ | ✓ |
| `cat`   | ✓ | ✓ | ✓ | ✗ |
| `echo`  | ✓ | ✓ | ✗ | ✗ |

---

# Vim Commands

## Basic Commands

### Create File

```bash
vim filename
```

### Save and Quit

```vim
:wq!
```

- `w` means save
- `q!` means quit

### Read File

```bash
vim filename
```

### Quit Editor Without Saving

```vim
:q!
```

### Give Numbering to Lines (Command Mode)

```vim
:set number
```

OR

```vim
:set nu
```

---

## Jumping Lines

### Jump on Last Line (Command Mode)

Press:

```text
Shift + G
```

### Jump on First Line (Command Mode)

Press:

```text
GG
```

### Jump on Custom Line (Command Mode)

```vim
:linenumber
```

Example:

```vim
:6
```

---

## Delete

### Delete Cursor-Pointing Line (Command Mode)

Press:

```text
DD
```

### Delete Cursor-Pointing Custom Lines

```text
numberDD
```

Examples:

```text
1dd
2dd
```

### Delete Line Irrespective of Cursor

```vim
:linenumberD
```

Examples:

```vim
:3d
:2d
```

### Delete Custom Line Range Irrespective of Cursor

```vim
:linenumberstart,linenumberendD
```

Examples:

```vim
:3,6d
:2,9d
```

---

## Search & Replace

### Search in Editor

```vim
:/word
```

Examples:

```vim
:/yoo
:/e
:/50
```

### Search and Replace in Entire Editor

```vim
:%s/searchingword/replacingword
```

Example:

```vim
:%s/ankur/dome
```

- `%` means all lines
- `s` means substitute

### Search and Replace at Particular Line

```vim
:linenumberS/searchingword/replacingword
```

Example:

```vim
:4s/ankur/dome
```

### Search and Replace in Entire Editor (Globally)

```vim
:%s/searchingword/replacingword/g
```

Example:

```vim
:%s/ankur/dome/g
```

### Search and Replace at Particular Line (Globally)

```vim
:linenumberS/searchingword/replacingword/g
```

Example:

```vim
:4s/ankur/dome/g
```

---

## Copy & Paste Lines (Yanking Method)

### Copy One Line Pointing on Cursor

Press:

```text
YY
```

### Copy Multiple Lines Pointing on Cursor

```text
numberYY
```

Example:

```text
2yy
```

### Paste One Line Below Pointing on Cursor

Press:

```text
P
```

### Paste One Line Above Pointing on Cursor

Press:

```text
Shift + P
```

---

# Two Modes

## Command Mode

- Default mode
- Only run commands
- Press `Esc`

## Insert Mode

- Data insertion
- Press `i`

---

## Flow

```text
Command Mode
    ↓
Press i
    ↓
Insert Mode
    ↓
Enter Data
    ↓
Esc Key
    ↓
:wq!
    ↓
Press Enter
```

---

# Extra Notes & Examples

- Number in Vim is temporary and need to run again.
- If you want to delete 2nd line & 5d, use `:2d` and `:4d` due to shift in line numbering.
- If you want to delete 13, 18 and 22 line, use `:13d`, `:17d`, `:20d`.
- If thinking about cursor use `DD` and irrespective of cursor use `:numberD`.
- `s%/ankur/dome` this will substitute only the first occurrence at each line. So, use `/g` after command to make it globally.

---

# Others

## Cat Commands

### Show Lines from Top

```bash
cat filename | head -numberoflines
```

Example:

```bash
cat file1 | head -3
```

### Show Lines from Bottom

```bash
cat filename | tail -numberoflines
```

Example:

```bash
cat file1 | tail -3
```

### Show Lines from Top (Efficient)

```bash
head -numberoflines filename
```

Example:

```bash
head -3 filename
```

### Show Lines from Bottom (Efficient)

```bash
tail -numberoflines filename
```

Example:

```bash
tail -3 filename
```

### Show Custom Lines In-Between

```bash
cat filename | head -numberoflines | tail -numberoflines
```

Example:

```bash
cat file1 | head -3 | tail -2
```

---

## Extra Notes & Examples

- If no parameter is passed, by default 10 lines are showed.
- In the custom lines command, we first kinda filter the top lines and then sub-filter the lines using `tail` command.




# Day 3 — Linux Fundamentals

## Linux

- Linux is operating system.
- It was developed by Linus Torvalds in 1991.
- Top Distros: Red Hat, CentOS, Ubuntu.

---

## Features / Advantages

1. Open Source / Free of cost
2. Supports both GUI and CLI
3. Multi user operating system
4. Multi tasking operating system
5. More secure than Windows (user level permissions)

---

# Windows vs Linux

| Windows | Linux |
| ------- | ----- |
| It is proprietary software of Microsoft | It is free of cost |
| More GUI based comparatively | CLI is the primary method to interact |
| Less secure but has products like Windows Defender | Linux is far superior when it comes to security |
| It’s code comes under Copyright laws | It’s open source OS |

---

# Components of Linux

## 1. Shell

It’s an interface between user and kernel. It receives user commands and rectifies the commands, if correct then sent to kernel.

## 2. Kernel

It’s core of operating system. It’s a bridge between shell and hardware. It is responsible for executing the commands.

---

## Flow

```text
User → Shell → Kernel → Hardware
```

---

# Types of Shell

1. **Bourne Shell (`sh`)**: It was the very first shell.
2. **Bash Shell (`bash`)**: It’s advance version of Bourne Shell. (Bash: Bourne Again Shell)
3. **C shell (`csh`)**
4. **TC Shell (`tcsh`)**: Advance version of C shell

---

# Commands

### Check the Kernel Version

```bash
uname -r
```

### See Current Shell

```bash
echo $0
```

### See Default Linux Shell

```bash
echo $SHELL
```

### Get Info of Any Command

```bash
man command
```

Example:

```bash
man mkdir
```

### See IP Address of Linux Machine

```bash
ifconfig
```

OR

```bash
ip addr
```

OR

```bash
hostname -i
```

### See Hostname

```bash
hostname
```

### Change Hostname

```bash
hostname new name
```

AND

```bash
bash
```

---

# Windows Commands

### See IP Address

```cmd
ipconfig
```

### See Hostname

```cmd
hostname
```

---

# Facts

- Types of Kernel: Monolithic, Micro, Hybrid
- Every Linux machine has IP address & hostname




# Day 4 — Linux File System Hierarchy

## Linux File System

- `/` (forward slash) is the top most directory in Linux, also known as root directory.
- Prominent Sub Directories: `tmp`, `etc`, `bin`, `sbin`, `root`, `boot`, `home`, `proc`
- Above directories are predefined & created.

---

# Commands

## Change Directory

### Absolute Path

```bash
cd absolute_path_to_dir
```

Example:

```bash
cd /home/dir1
```

### Relative Path

```bash
cd relative_path_of_dir
```

Examples:

```bash
cd ../../dir2_1
cd dir2/dir3
```

---

## Check Present Directory

```bash
pwd
```

---

## List All Files/Folders in PWD

```bash
ls
```

---

## List All Files/Folders of Any Directory

```bash
ls /directoryname
```

Example:

```bash
cd /etc
```

---

## Make Nested Directories Before Their Parents Exist

```bash
mkdir -p /dir1/dir2/dir3/dir4
```

---

## Create Multiple Files at Different Locations

```text
directoryname
```

---

## Use Cases of `cd` Command

| Command | Use Case |
| ------- | -------- |
| `cd ..` | 1 step back |
| `cd ../..` | 2 steps back |
| `cd .` | Useless command but IMP, goes in pwd |
| `cd -` | Go in previous directory |

---

# Recursive Directories

## Issue

We need to create a directory inside a directory that doesn’t exist yet. Hence, gives error.

## Solution

Make use of `-p` (aka parent directory) for creating directories. This makes sure that the non-existing parents are created and preserved. Later, the sole required directory is created.

## Command

```bash
mkdir -p /dir1/dir2/dir3/dir4
```

---

# Facts

- When EC2 instance is initialised, we are in `/root` direct.
- Absolute path always starts with **forward slash**.
- Irrespective where are you (pwd), using absolute path you can go anywhere.
- `pwd` matters for the relative path.
- Immediate upper level directory is termed as parent directory.
- Immediate lower level directory is termed as child directory.
- Relative path makes sense when traversal is between one/two levels only.

---

# Examples

- See Figure 1 in screenshots.

## Relative Path

```bash
cd ../../../tmp/dir11/dir12
```




# Day 5 — Yum + RPM Commands, Compression & Archiving

## Yum and RPM

- They are package management tools.
- They’re used to install, update, and remove packages from repositories into your Linux machine.
- `rpm`: Red Hat Package Management
- `yum`: Yellowdog Updater Modified
- **RPM doesn’t** resolve dependencies, but **YUM does** resolve dependencies.
- Hence, YUM is the industry standard.

**Structure**

```text
Linux Machine → Repositories → Package
```

---

# RPM Commands

## Install Package

```bash
rpm -ivh pkgname
```

- `i` means install
- `v` means verbose (to show)
- `h` means hash (provides a visual progress bar)

## Update Package

```bash
rpm -Uvh pkgname
```

- `U` means update
- `v` means verbose (to show)
- `h` means hash (provides a visual progress bar)

## Remove Package

```bash
rpm -ev pkgname
```

- `e` means erase/remove/delete
- `v` means verbose (to show)

---

# YUM Commands

## Install Package

```bash
yum install pkgname
```

## Update Package

```bash
yum update pkgname
```

## Remove Package

```bash
yum remove pkgname
```

## Install Packages Without Confirmation

```bash
yum install pkgname -y
```

## List All Packages in Repository

```bash
yum list
```

## See All Installed Packages in Linux Machine

```bash
yum list installed
```

## Check Whether a Particular Package Is Installed

```bash
yum list pkgname
```

- **Available** response: Present in the repository
- **Installed** response: Installed in the Linux machine

## Count All Packages in Repository

```bash
yum list | wc -l
```

## Count All Installed Packages in Linux Machine

```bash
yum list installed | wc -l
```

---

# Compression of Files

- Compression is done to reduce the size of files.
- **Purpose:** Easy file sharing and disk space.

## 1. `gzip` Command

| Purpose | Command | Extension |
| --- | --- | --- |
| Compress | `gzip filename` | `.gz` |
| Read | `zcat filename` | `.gz` |
| Uncompress | `gunzip filename` | `.gz` |

## 2. `bzip2` Command

| Purpose | Command | Extension |
| --- | --- | --- |
| Compress | `bzip2 filename` | `.bz2` |
| Read | `bzcat filename` | `.bz2` |
| Uncompress | `bunzip2 filename` | `.bz2` |

## 3. `xz` Command

| Purpose | Command | Extension |
| --- | --- | --- |
| Compress | `xz filename` | `.xz` |
| Read | `xzcat filename` | `.xz` |
| Uncompress | `unxz filename` | `.xz` |

## Facts

- The maximum compression is acquired by either `bzip2` or `xz`.

---

# Archiving (Basic)

- Archiving is used to store multiple files in a single file.

## Create Archive File

```bash
tar -cvf newFileName existingF1 existingF2 existingF3
```

- `c` means create archive file
- `v` means verbose (to show)
- `f` means archive file

## See Table Content of Archive File

```bash
tar -tvf archive_file_name
```

- `t` means table content
- `v` means verbose (to show)
- `f` means archive file

## Extract File

```bash
tar -xvf archive_file_name
```

- `x` means extract
- `v` means verbose (to show)
- `f` means archive file

## Facts

- These files are contained in a single file but are not yet compressed.

---

# Others

## See the File List with Size

```bash
ls -l
```

- `-l` means long
- `ls` means listing

## See the File List in Human-Readable Size (Non-Bytes Size)

```bash
ls -lh
```

- `-l` means long
- `ls` means listing

## Save Output of One Command in a File

```bash
man history > file
```

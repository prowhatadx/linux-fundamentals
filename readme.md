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



# Day 6 — Archiving (Advanced) and Cron

# Archiving

## For Sending

- In yesterday's notes, we only did archiving steps but never actually compressed it.
- So we're supposed to do archiving, then compress it.

Example:

1. **Archive**

   ```bash
   tar -cvf file5.tar file1 file2 file3
   ```

2. **Compression**

   ```bash
   bzip2 file5
   ```

3. **Final File**: `file5.tar.bzip2`

---

## After Receiving

Follow these steps to get the data:

1. **Uncompress**

   ```bash
   bunzip2 file5
   ```

2. **Unarchiving**

   ```bash
   tar -xvf file5
   ```

---

## Efficient Way

Use the following parameters in the archiving command:

| Compression | Parameter |
| ----------- | --------- |
| gzip        | `z`       |
| bzip2       | `j`       |
| xz          | `J`       |

Commands:

### gzip

```bash
tar -cvzf file5.tar file1 file2 file3
```

### bzip2

```bash
tar -cvzf file5.tar file1 file2 file3
```

### xz

```bash
tar -cvJf file5.tar file1 file2 file3
```

- **Final File**: `file5.tar`

---

## Conclusion

1. **Archiving Without Compression**

   ```bash
   tar -cvf file5.tar file1 file2 file3
   ```

2. **Archiving With Compression**

   ```bash
   tar -cvzf file5.tar file1 file2 file3
   ```

---

## Facts

- We have used `.tar` while creating the zip file.
- Also, when we run the efficient way, there won't be an exclusive file extension of compression.

---

# CRON / Crontab

- It is done to perform a command/task at a particular time.

## Fields of Crontab

Keep the following order:

| Field | Range / Values |
| ----- | -------------- |
| Minute | 0 to 59 |
| Hour | 0 to 23 |
| Date | 1 to 31 |
| Month | 1 to 12 |
| Day | 0/7 (Sun), 1 (Mon), 2 (Tue), 3 (Wed), 4 (Thu), 5 (Fri), 6 (Sat) |

Example: Friday, October 9, 10:30 — `30 10 09 10 05`

---

## Configurations & Run

**Package:** `cronie`

### Config Commands

- **Install**

  ```bash
  yum install -y cronie
  ```

- **Start Service**

  ```bash
  systemctl start crond
  ```

- **Persistent**

  ```bash
  systemctl enable crond
  ```

### Schedule a Job

- **Command**

  ```bash
  crontab -e
  ```

- **Enter cron values**

  ```cron
  30 10 09 10 05 touch /file5
  ```

### See a Job

```bash
crontab -l
```

### Edit the Cron Job

```bash
crontab -e
```

### Remove a Scheduled Job

```bash
crontab -r
```

### Details About Cron Backend Files

```bash
cat /etc/crontab
```

---

## Examples

1. **One-time Job**

   ```cron
   36 10 20 10 03 touch /file5
   ```

2. **Daily Cron Job**

   ```cron
   36 10 * 10 * touch /file5
   ```

3. **Different Slots Cron Jobs**

   ```cron
   */2 10 * 10 * touch /file5
   ```

   Here, the job will run after every two minutes.

4. **Repetitive Store Date in File**

   ```cron
   * * * * * date >> /root/file09
   ```

5. **Reboot Linux Machine**

   ```cron
   00 00 * * * reboot
   ```

6. **Cron Job at 12 AM & 12 PM Every Day, Month, Date**

   ```cron
   00 00,12 * * * command
   ```

---

## Facts

- Be as root user, the cron jobs won't run elsewise.
- When `crontab -e` is executed, Vim editor is opened by default.
- Once a timestamp is relapsed, you can't use past time in a cron job.
- Resource: `crontab.guru`
- All configuration files of Cron & Linux OS are stored in the `/etc` directory.
- In Linux, restart is termed as reboot.



# Day 7 — Hard Links, Soft Links, Grep & WC Commands

## Hard Link File

- **Hard Link File**: It is done to create a backup of a file. The backup file is interconnected, i.e., when changes are made in the original file or backup file, the changes are reflected in both files.
- Both will have the **SAME** size, timestamps (creation, modified, etc.) and inode number (in the hard link case, it is the same).
- Even if we delete the original file, the backup stays.
- We can create hard links for files and not directories (to avoid main sub-directories duplication).

---

## Hard Link Commands

| Purpose | Command |
| --- | --- |
| Create a hard link file | `ln filename hardlinkfilename` |
| Check inode number | `ls -i` |
| Check inode and file size | `ls -li` |

Example:

```bash
ln /ankur /root/ankur.backup
```

---

## Soft Link File

- **Soft Link File**: It is also called a symbolic link / symlink. It is primarily used for making shortcuts of files that are deep inside nested directories, i.e., like a pointer. When changes are made in the original file or shortcut file, the changes are reflected in both files.
- Both will have **DIFFERENT** sizes, timestamps (creation, modified, etc.) and inode numbers (in the hard link case, it is the same).
- Even if we delete the original file, the shortcut stays but becomes useless.
- We can create soft links for both files and directories.

---

## Soft Link Commands

| Purpose | Command |
| --- | --- |
| Create a soft link file | `ln -s filename softlinkfilename` |
| Check inode number | `ls -i` |
| Check inode and file size | `ls -li` |

Example:

```bash
ln -s /d1/d2/d3/ankur ankur.soft
```

---

# WC Command

- `wc` stands for word count. It is used to count words in a file. It counts lines, words and characters in a file. This includes spaces and symbols too.

## WC Commands

| Purpose | Command |
| --- | --- |
| Count lines, words and characters | `wc filename` |
| See number of lines | `wc -l filename` |
| See number of words | `wc -w filename` |
| See number of characters | `we -c filename` |
| Any combination | `we -lc filename` |
| See characters in the longest line | `wc -L filename` |

- The combination can be done in any format. The sequence decides what you’ll see first in the output.
- The longest line is decided by the number of characters.

---

# Grep Command

- It stands for globally search regular expression and print it.
- It is used to search patterns/words in a file without actually opening it. This makes it different from the Vim command.
- If the pattern exists, the line prints; no printing occurs if no result is found.

## Grep Commands

| Purpose | Command |
| --- | --- |
| Search a pattern in a file | `grep pattern filename` |
| Search multiple files | `grep pattern filename1 filename2` |
| Search multiple patterns | `grep -e pattern1 -e pattern2 filename` |
| Print line number for grep output | `grep -n pattern filename` |
| Print lines apart from the line containing the pattern | `grep -v pattern filename` |
| Ignore case sensitivity and print matching lines | `grep -i pattern filename` |
| Match the strict pattern, not as a sub-part of a word | `grep -w pattern filename` |
| Print the pattern and not the entire line | `grep -o pattern filename` |
| Print the matching line and the line after it | `grep -A 1 pattern filename` |
| Print the matching line and the line before it | `grep -B 1 pattern filename` |
| Print the matching line, the line before and the line after | `grep -C 1 1 pattern filename` |
| Combination of before and after lines | `grep -B 1 -A 2 pattern filename` |

### Examples

```bash
grep word ankur
grep the ankur.txt dome.txt
grep -e you -e the ankur.txt
```

---

# Other Commands

## Rename a File

```bash
mv currfilename new filename
```

---

# Facts

- There’s no recycle bin when using CLI in Linux.
- Inode number is a unique number given to every file/folder in Linux. Hard link files make an exception here.



# Day 8 — User Management - 1

## User Management

- It means managing of users.
- It involves:
  - Creation of user.
  - Setting up passcode for user.
  - Deletion of user.
- Every new user gets a user ID (UID) and group ID (GID).

---

## Types of Users

### 1. Root User (Admin/Super User)

- The creator of the Linux machine.
- UID: `0` and GID: `0`

### 2. System Users (System Account)

- This user is created when a package is installed. Like in the command (`yum install -y pkgname`), so `pkgname` user is created.
- UID and GID range: `1` to `999`

### 3. Normal Users

- This includes the user you want to add in the system.
- UID and GID range: `1000` to `60,000`

---

## Commands

### Create Normal User

```bash
useradd username
```

### Check if User Exists

```bash
id username
```

### Set Password

```bash
passwd username
```

### Make Password Visible While Entering

```bash
echo "password" | passwd --stdin username
```

- `stdin` means standard output.

### Delete a User

- Only user deletion:

```bash
userdel username
```

- Both user deletion and user directory:

```bash
userdel -r username
```

### Switch User

```bash
su - username
```

- `su` means switch user.

---

## Fields of `/etc/passwd` File ⭐️

### Root

```text
root:x:0:0:root:/root:/bin/bash
```

### Normal User (User-Defined)

```text
ankur:x:1001:1001::/home/ankur:/bin/bash
```

### EC2 User (Default)

```text
ec2-user:x:1000:1000:EC2 Default User:/home/ec2-user:/bin/bash
```

### Fields

1. Username (`ankur`)
2. Password of user denoted by X (`x`)
3. UID (`1001`)
4. GID (`1001`)
5. Common name (not present, that’s why there are back-to-back colons `::`)
6. Home directory of normal user (`/home/ankur`)
7. Default shell of user

---

## Facts

- When a user is created, a special directory is made for them. It will be present in the `/home` directory.
- Irrespective of where you are, the user is properly created in Linux.
- In an Amazon Linux machine, `ec2-user` is the first normal user and has UID and GID `1000`.
- Multiple users can’t be created simultaneously like `useradd ankur dome`.
- Entries of a new user are saved in `/etc/passwd` and `/etc/shadow`.
- Creation of a user is required before setting up a password.
- By default, while setting up a password, your password isn’t visible.
- Home directory of the root user is `/root`. See Figure 2.

### User Transition Password Requirement

| User Transition | Password Required? |
| --------------- | ------------------ |
| Root → Normal User | No |
| Normal User → Root | Yes |
| Normal User → Normal User | Yes |

- If a normal user wants to change their own password, they have to enter their own password, but not for root.
- The users who has entry in /etc/sudoers file, he can perform all the operations in Linux.
    - You can change it using vim /etc/sudoers
    - Now, this sudoer user can perform all commands but has to use sudo before all commands.



# Day 9 — User Management - 2

## Sudo

- `sudo` means super user do.
- `sudo` has to be used before every command that a normal user with permissions in `/etc/sudoers`.
- If you want to customise permission in `/etc/sudoers` for a user, use which yum command and paste in `/etc/sudoers`.
  - We get a binary path: `/usr/bin/yum`. See Figure 3 to see the same.

---

# Fields of `/etc/shadow` File ⭐️

## Normal User

```text
adx:!!:20741:0:99999:7:::
```

## Fields

1. **Username:** `adx`
2. **Password:** `!!` if not set, else encrypted format if set.
3. **Last Password Change:** Date since 1 January 1970.
4. **Password Change Restriction:** `m = 0` (0 means user can change password anytime; the number tells the days they have to wait before changing passcode).
5. **Password Validity:** `M = 99999` (default 99999 means it expires after 99999 days, basically UNLIMITED).
6. **Warning/Alert before Password Expires:** `W = 7` (default 7 alerts for 7 days before expiry).

---

# Commands

| Purpose | Command | Example |
| --- | --- | --- |
| See password policy of user | `chage -l username` | — |
| Update entire password policy | `chage username` | — |
| Change minimum number of days between password changes | `chage -m daysNumber username` | `chage -m 5 adx` |
| Change password validity | `chage -M daysNumber username` | `chage -M 30 adx` |
| Change password warning | `chage -W daysNumber username` | `chage -W 3 adx` |

---

# Defaults (`/etc/default/useradd` File)

- The defaults in this file are given to every new user.
- The fields are:

```text
GROUP=100
HOME=/home
INACTIVE=-1
EXPIRE=
SHELL=/bin/bash
SKEL=/etc/skel
CREATE_MAIL_SPOOL=yes
```

- These fields can be changed using Vim commands.
- The changes will apply to new users without updating existing users.
- The default shell and home directory are `/bin/bash` and `/home`.

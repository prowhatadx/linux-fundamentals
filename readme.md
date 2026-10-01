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

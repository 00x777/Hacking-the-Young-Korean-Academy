# General Skills in CTFs — Write-ups

**Platform:** CyLab Security Academy

**Original source:** picoCTF 2021

**Category:** General Skills

> Hosts, ports, and download URLs can vary by challenge instance, so `<host>`,
> `<port>`, and `<file-url>` are placeholders. Replace any `academy{...}` flag
> with the flag from your own instance.

## Contents

1. [Let's Warm Up](#1-lets-warm-up)
2. [2Warm](#2-2warm)
3. [Warmed Up](#3-warmed-up)
4. [Obedient Cat](#4-obedient-cat)
5. [Wave a Flag](#5-wave-a-flag)
6. [Magikarp Ground Mission](#6-magikarp-ground-mission)
7. [convertme.py](#7-convertmepy)
8. [What's a net cat?](#8-whats-a-net-cat)
9. [Nice netcat...](#9-nice-netcat)
10. [Tab, Tab, Attack](#10-tab-tab-attack)
11. [Python Wrangling](#11-python-wrangling)
12. [First Grep](#12-first-grep)
13. [First Find](#13-first-find)
14. [Big Zip](#14-big-zip)
15. [Static ain't always noise](#15-static-aint-always-noise)
16. [strings it](#16-strings-it)
17. [plumbing](#17-plumbing)

---

## 1. Let's Warm Up

**Question:** If I told you a word started with `0x70` in hexadecimal, what
would it start with in ASCII?

### Solution

1. Convert hexadecimal to decimal: `(7 × 16) + (0 × 1) = 112`.
2. ASCII value 112 represents the character `p`.

### Flag

```text
academy{p}
```

---

## 2. 2Warm

**Question:** Can you convert the number 42 (base 10) to binary (base 2)?

### Solution

Divide 42 by 2 repeatedly and record the remainder:

| Division | Quotient | Remainder |
| --- | ---: | ---: |
| 42 ÷ 2 | 21 | 0 |
| 21 ÷ 2 | 10 | 1 |
| 10 ÷ 2 | 5 | 0 |
| 5 ÷ 2 | 2 | 1 |
| 2 ÷ 2 | 1 | 0 |
| 1 ÷ 2 | 0 | 1 |

Read the remainders from bottom to top: **101010**.

**Verification:** 32 + 8 + 2 = 42.

### Flag

```text
academy{101010}
```

---

## 3. Warmed Up

**Question:** What is `0x3D` (base 16) in decimal (base 10)?

### Solution

`3` = 3 and `D` = 13, so:

`(3 × 16¹) + (13 × 16⁰) = 48 + 13 = 61`.

### Flag

```text
academy{61}
```

---

## 4. Obedient Cat

**Goal:** Download a file and read the flag from it.

### Solution

1. Download the challenge file with `wget`.
2. Confirm it downloaded with `ls`.
3. Print its contents with `cat flag`.

### Commands

```sh
wget <file-url>
ls
cat flag
```

### Flag

```text
academy{s4n1ty_v3r1f13d_61ddac22}
```

**Takeaway:** Download and inspect files from the Linux terminal.

---

## 5. Wave a Flag

**Goal:** Run a program and get it to reveal the flag.

### Solution

1. Download the `warm` executable with `wget`.
2. Make it executable with `chmod +x warm`.
3. Run it with the `-h` (help) argument and read the flag from its output.

### Commands

```sh
wget <file-url>
chmod +x warm
./warm -h
```

### Flag

The source notes do not include the flag. Run `./warm -h` with the challenge
file and copy the flag from its output.

**Takeaway:** Programs often print useful information when run with `-h` or
`--help`.

---

## 6. Magikarp Ground Mission

**Question:** Do you know how to move between directories and read files in the
shell? Start the container, SSH into it, and run `ls` once connected.

**Hint:** A Bash cheat sheet can be helpful.

### Summary

The flag is split into three files in different directories. Each directory
also has an instructions file pointing to the next piece.

### Connect over SSH

```sh
ssh ctf-player@<host> -p <port>
```

Enter the password from the challenge page. Nothing appears on screen while
you type it; that is normal.

### Part 1: Home directory

```console
$ ls
1of3.flag.txt  instructions-to-2of3.txt
$ cat *
academy{xxsh_
Next, go to the root of all things, more succinctly `/`
```

Here, the shell expands `*` to the two visible filenames. `cat` prints their
contents, showing the first flag piece and the next instruction.

### Part 2: Root directory `/`

```console
$ cd /
$ cat 2of3.flag.txt
0ut_0f_//4t3r_
$ cat instructions-to-3of3.txt
Lastly, ctf-player, go home... more succinctly `~`
```

The `/root` and `/challenge` directories are dead ends: access to `/root` is
denied, and `/challenge` contains only `metadata.json`.

### Part 3: Home `~`

```console
$ cd ~
$ cat 3of3.flag.txt
47c47679}
```

### Flag

```text
academy{xxsh_0ut_0f_//4t3r_47c47679}
```

**Takeaway:** `/` is the top of the filesystem, and `~` is a shortcut for your
home directory. Read the instruction files provided by a challenge.

---

## 7. convertme.py

**Goal:** Run a Python script and answer its question to get the flag.

### Solution

1. Download and run the script.

   ```sh
   wget <file-url>
   python3 convertme.py
   ```

2. The script displays a decimal number and asks for its binary equivalent.
3. Convert the number using the repeated-division method from [2Warm](#2-2warm)
   or Python's `bin()` function. For example:

   ```py
   >>> bin(42)[2:]
   '101010'
   ```

4. Enter the answer. If it is correct, the script prints the flag.

### Flag

```text
academy{...}
```

**Takeaway:** Python's `bin()`, `hex()`, and `int(value, base)` functions can
help with base conversions.

---

## 8. What's a net cat?

**Goal:** Connect to a challenge server with netcat and receive the flag.

### Solution

```sh
nc <host> <port>
```

The server sends the flag after you connect.

### Flag

```text
academy{...}
```

**Takeaway:** `nc` (netcat) connects to a specified host and port over TCP.
Use it only with challenge servers you are authorized to access.

---

## 9. Nice netcat...

**Goal:** Convert numbers sent by the server into readable text.

### Solution

1. Connect to the challenge server. It sends one number per line.

   ```sh
   nc <host> <port>
   ```

2. Treat each number as an ASCII code; for example, 112 represents `p`.
3. Convert the output to characters with Python:

   ```sh
   nc <host> <port> | python3 -c "import sys; print(''.join(chr(int(x)) for x in sys.stdin.read().split()))"
   ```

### Flag

```text
academy{...}
```

**Takeaway:** A list of numbers in the printable ASCII range may represent
ASCII character codes.

---

## 10. Tab, Tab, Attack

**Goal:** Find and run an executable buried in a deeply nested folder tree.

### Solution

1. Download and extract the archive.

   ```sh
   wget <file-url>
   unzip Addadshashanammu.zip
   ```

2. You can use **Tab** to autocomplete directory names as you navigate. You
   can also search for the specific executable:

   ```sh
   find . -type f -name 'fang-of-haynekhtnamet' -print
   ```

3. Run the executable at the path printed by `find`, replacing the placeholder
   with that path:

   ```sh
   ./<path-to-fang-of-haynekhtnamet>
   ```

### Flag

```text
academy{...}
```

**Takeaway:** Tab completion reduces typing, and `find` can locate a file
without manually traversing every directory.

---

## 11. Python Wrangling

**Goal:** Decrypt an encrypted flag using the provided Python script.

### Solution

1. Download `ende.py`, `pw.txt`, and `flag.txt.en`.
2. Read the password:

   ```sh
   cat pw.txt
   ```

3. Run the script in decrypt mode and provide the password when prompted:

   ```sh
   python3 ende.py -d flag.txt.en
   ```

   To provide the password from the file instead:

   ```sh
   python3 ende.py -d flag.txt.en < pw.txt
   ```

### Flag

```text
academy{...}
```

**Takeaway:** Check a script's help output with `python3 ende.py -h` to learn
how to use it.

---

## 12. First Grep

**Goal:** Find the flag in a long text file.

### Solution

```sh
wget <file-url>
grep 'academy{' file
```

### Flag

```text
academy{...}
```

**Takeaway:** `grep` prints lines that match a pattern.

---

## 13. First Find

**Goal:** Find `uber-secret.txt` among many files.

### Solution

```sh
wget <file-url>
unzip files.zip
find . -name 'uber-secret.txt'
```

Use the path printed by `find` to read the file. In the original challenge,
the path was:

```sh
cat ./adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt
```

The path may differ in your instance.

### Flag

```text
academy{...}
```

**Takeaway:** `find <directory> -name <name>` searches for a matching file in
the directory and its subdirectories.

---

## 14. Big Zip

**Goal:** Find the flag among a large number of files.

### Solution

```sh
wget <file-url>
unzip big-zip-files.zip
grep -r 'academy{' big-zip-files/
```

### Flag

```text
academy{...}
```

**Takeaway:** `grep -r` searches files in a directory and its subdirectories.

---

## 15. Static ain't always noise

**Goal:** Find the flag in the `static` binary.

### Solution

1. Download `static` and the provided `ltdis.sh` script.
2. Search the readable strings in the binary for the flag:

   ```sh
   strings static | grep 'academy{'
   ```

   Alternatively, use the challenge script:

   ```sh
   chmod +x ltdis.sh
   ./ltdis.sh static
   grep 'academy{' static.ltdis.strings.txt
   ```

### Flag

```text
academy{...}
```

**Takeaway:** Some readable text, including flags and messages, is stored
directly in binary files.

---

## 16. strings it

**Goal:** Find the flag in a binary without running it.

### Solution

```sh
wget <file-url>
strings strings | grep 'academy{'
```

### Flag

```text
academy{...}
```

**Takeaway:** `strings` prints readable text from a file. Combined with
`grep`, it can quickly locate a flag.

---

## 17. plumbing

**Goal:** Filter a stream of server output to find the flag.

### Solution

```sh
nc <host> <port> | grep 'academy{'
```

### Flag

```text
academy{...}
```

**Takeaway:** A pipe (`|`) sends one command's output to another command.
Pipes let you combine small Linux tools to process output.

---

## Command cheat sheet

| Command | Purpose |
| --- | --- |
| `wget <url>` | Download a file |
| `ls` | List entries in the current directory |
| `cat <file>` | Print a file's contents |
| `cat *` | Print contents of matched files; `*` omits hidden names, and `cat` errors on directories |
| `chmod +x <file>` | Make a file executable |
| `./<program> -h` | Run a program and show its help |
| `python3 <script>` | Run a Python script |
| `unzip <file>.zip` | Extract a ZIP archive |
| `find . -name <name>` | Search for a file by name |
| `grep <pattern> <file>` | Find matching lines in a file |
| `grep -r <pattern> <dir>` | Search files in a directory and its subdirectories |
| `strings <file>` | Print readable text from a file |
| `nc <host> <port>` | Connect to an authorized challenge server over TCP |
| `ssh user@host -p port` | Connect to a remote machine |
| `cd /` | Go to the root of the filesystem |
| `cd ~` | Go to your home directory |

## Conversion cheat sheet

| Conversion | Method | Python |
| --- | --- | --- |
| Hexadecimal to decimal | Multiply each digit by a power of 16 and add the results | `int('3D', 16)` |
| Decimal to binary | Divide by 2 repeatedly, then read the remainders from bottom to top | `bin(42)` |
| Decimal to ASCII | Look up the value in an ASCII table | `chr(112)` |
| ASCII to decimal | Look up the character's numeric value | `ord('p')` |

---
title: "OverTheWire - Bandit Level 2 --> 3 Writeup"
date: 2023-02-06T07:48:13+01:00
draft: true
tags:
- OverTheWire
- Bandit
- Linux
- Writeups
---

## Level Goal
The password for the next level is stored in a file called spaces in this filename located in the home directory.

[Level link](https://overthewire.org/wargames/bandit/bandit3.html)


## Information
In Linux we can use **spaces** and **dashes (-)** or **underscores (_)** ... in naming files, but if we use spaces it can cause some **_issues_** when working with the command line. Such as in this level there is a file with spaces in it's name and if we try to cat this file in a **simple way**, it won't work:

```bash
bandit2@bandit:~$ ls
spaces in this filename
bandit2@bandit:~$ cat spaces in this filename
cat: spaces: No such file or directory
cat: in: No such file or directory
cat: this: No such file or directory
cat: filename: No such file or directory
```
And the reason of this issue is that **the bash** treated each **_"spaces" "in" "this" "filename"_** as separate **arguments** (in this case separate files or directories)
## Solution
To handle filenames with spaces, they need to be **enclosed** in _quotation marks (single or double) (" ") (' ')_ or **escaped** with a _backslash (\\)_

```bash
bandit2@bandit:~$ cat "spaces in this filename" 
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
bandit2@bandit:~$ cat 'spaces in this filename' 
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
bandit2@bandit:~$ cat spaces\ in\ this\ filename 
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
```
You can use tab completion, just type part of the filename then press TAB key and the terminal will automatically complete the rest of the filename.

> This **random strings** is the password of the next level, as we saw in level 0 **"ssh bandit?@bandit.labs.overthewire.org -p 2220"** just replace **"?"** with the level's number.
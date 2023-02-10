---
title: "OverTheWire - Bandit Level 1 --> 2 Writeup"
date: 2023-02-10T09:04:56+01:00
draft: true
tags:
- OverTheWire
- Bandit
- Linux
- Writeups
---

## Level Goal
The password for the next level is stored in a file called - located in the home directory

[Level link](https://overthewire.org/wargames/bandit/bandit2.html)


## Information
In Bash (Bourne-Again Shell), a dash (-) is used to represent options that are passed to commands. So files that start with a dash (-) they can't be treated as a simple files because when these files are passed as arguments to a specific command, the command treats the dash (-) as a command-line option rather than a file name. As a result, this can cause unexpected behavior and errors. So let's see how to handle this type of files.   
In the previous level we have seen the **_"pwd"_**, **_"ls"_** and the **_"cat"_** commands:   
* If we use **_"ls"_** we see a file named **"-"**, let's see if we can **_"cat"_** it:

```bash
bandit1@bandit:~$ cat -

```
but nothing happend! Because the **_"cat"_** treated the **"-"** as an option, so how we can **_"cat"_** this type of files.

## Solution
> I will give you three different ways to **_"cat"_** this type of files:   

1. Using the absolute or relative path of the file, like this:

```bash
bandit1@bandit:~$ ls
-
bandit1@bandit:~$ pwd
/home/bandit1
bandit1@bandit:~$ cat /home/bandit1/-
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
```
2. Using the "./" syntax:

```bash
bandit1@bandit:~$ cat ./-
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
```
3. Using the "<" syntax:

```bash
bandit1@bandit:~$ cat < -
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
```

> This **random strings** is the password of the next level, as we saw in level 0 **"ssh bandit?@bandit.labs.overthewire.org -p 2220"** just replace **"?"** with the level's number.
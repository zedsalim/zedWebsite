---
title: "OverTheWire - Bandit Level 0 --> 1 Writeup"
date: 2023-02-03T05:34:44+01:00
draft: false
tags:
- OverTheWire
- Bandit
- Linux
- Writeups
---

## Level Goal
The **_password_** for the next level is stored in a file called **readme** located in the home directory. Use this password to log into **bandit1** using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.

[Level link](https://overthewire.org/wargames/bandit/bandit1.html)

## Information
The goal of this level is to see the content of a file called **_"readme"_**, and when you log into a machine using SSH, all actions must be performed via the command line and cannot be performed through a graphical interface. So we need learn some basic command line:
* **pwd :** this command stands for **_"print working directory"_**, it displays the file path of your current directory.
* **ls :** this command stands for **_"list"_**, it lists the files and directories within a directory, basically it is used to view the contents of a folder. it has some options like:
  - **ls -a :** the **_"-a"_** option stands for **_"all"_**, it displays all files and directories in the current directory including **hidden** files
  - **ls -l :** the **_"-l"_** option stands for **_"long"_**, it displays the files and directories in a long detailed format _(permissions, owner, group, size, date and time of modification)_.
* **cat :** this command stands for **_"concatenate"_**, it displays the content of one or more files.

## Solution
1. Use **pwd** to see your current directory because in the level goal they told us that the **"readme"** file located in the home directory:

```bash
bandit0@bandit:~$ pwd
/home/bandit0
```
2. Use **ls** to list all the files:

```bash
bandit0@bandit:~$ ls
readme
```
3. Use **cat** to see the content of the **"readme"** file:

```bash
bandit0@bandit:~$ cat readme 
NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
```
> This **random strings** is the password of the next level, as we saw in level 0 **"ssh bandit?@bandit.labs.overthewire.org -p 2220"** just replace **"?"** with the level's number.

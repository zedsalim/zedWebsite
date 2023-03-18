---
title: "OverTheWire - Bandit Level 3 --> 4 Writeup"
date: 2023-03-18T19:01:04+01:00
draft: false
tags:
- OverTheWire
- Bandit
- Linux
- Writeups
---

## Level Goal
The password for the next level is stored in a hidden file in the inhere directory.

[Level link](https://overthewire.org/wargames/bandit/bandit4.html)


## Information
In this level there is a hidden file inside a directory named **"inhere"**, so we need to enter this directory first using the **_cd_** command:
* **cd :** this command stands for **_"change directory"_**, it is used to change the current working directory to a specified directory path.  
  * **_"cd enter/your/path"_** (changing the directory to **/path**)
  * **_"cd .."_** (it will go back one step (one directory back) in this case to **/your**)
  * **_"cd ../.."_** (it will go back two steps (two directories back) in this case to **enter/**)   

To see your current directory use:
*  **pwd :** this command stands for **_"print working directory"_**, it displays the file path of your current directory. (as we saw in level 1)   

To see the hidden files use:
*  **ls -a :** the **_"-a"_** option stands for **_"all"_**, it displays all files and directories in the current directory including. (as we saw in level 1)

## Solution

```bash
bandit3@bandit:~$ pwd
/home/bandit3
bandit3@bandit:~$ ls
inhere
bandit3@bandit:~$ cd inhere/
bandit3@bandit:~/inhere$ ls -a
.  ..  .hidden
bandit3@bandit:~/inhere$ cat .hidden 
2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe
```


> This **random strings** is the password of the next level, as we saw in level 0 **"ssh bandit?@bandit.labs.overthewire.org -p 2220"** just replace **"?"** with the level's number.

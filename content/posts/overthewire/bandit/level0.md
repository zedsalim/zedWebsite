---
title: "OverTheWire - Bandit Level 0 Writeup"
date: 2023-01-01T04:47:11+01:00
draft: false
tags:
- OverTheWire
- Bandit
- Linux
- Writeups
---

## Level Goal
The goal of this level is for you to log into the game using **SSH**. The host to which you need to connect is **bandit.labs.overthewire.org**, on port **2220**. The username is **bandit0** and the password is bandit0. Once logged in, go to the Level 1 page to find out how to beat Level 1.

[Level link](https://overthewire.org/wargames/bandit/bandit0.html)

## Information
#### What is SSH ?
Secure Shell (SSH)  is a protocol that allows
one *computer* to take **control** on another *computer* remotely using command line to navigate, edit and manipulate files **securely** over a network.   
To log in over SSH use this command:
``` 
ssh user@host
```
- **user**: is the username of the server you want to connect to   
- **host**: it can be an IP ADDRESS or an URL of the server you want to connect to

SSH communicates by default through **port 22**, in case the server you want to connect to runs on a different port you need to specify the port number with the **-p** option:

``` 
ssh user@host -p portnumber
```
## Solution
In this level we have:   
- **user**: bandit0
- **host**: bandit.labs.overthewire.org
- **port**: 2220
- **password**: bandit0   

So we need to type this command:
``` 
ssh bandit0@bandit.labs.overthewire.org -p 2220
```
Once you hit *Enter*, you will be prompted to confirm the system's identity, type yes and hit *Enter*. Then you will be promted for the server's password like this:

```sh
zed@linux:~$ ssh bandit0@bandit.labs.overthewire.org -p 2220
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server.    
            More information on http://www.overthewire.org/wargames

bandit0@bandit.labs.overthewire.org's password: 
```
Type the password **"bandit0"** (it won't show up in your terminal just type it and hit *Enter*) and if the password is correct then you will log in and you will notice this in your terminal:

```sh
bandit0@bandit:~$ 
```
> That's it, see you in the next level.
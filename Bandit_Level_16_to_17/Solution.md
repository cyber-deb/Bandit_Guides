# 🚩 Bandit Level 16 → Level 17

## 🎯 Objective
The credentials for the next level can be retrieved by submitting the password of the current level to a port on localhost in the range 31000 to 32000. First find 
out which of these ports have a server listening on them. Then find out which of those speak SSL/TLS and which don’t. There is only 1 server that will give the next
credentials, the others will simply send back to you whatever you send to it.

Helpful note: Getting “DONE”, “RENEGOTIATING” or “KEYUPDATE”? Read the “CONNECTED COMMANDS” section in the manpage.
---

## 📚 Concepts & Prerequisites
Before attempting this level, you should understand how to use the following commands and concepts. 

**Recommended Research (man pages are your friend! and also the helpful resources in Bandit Level):**
* `ssh` - ssh stands for secure shell. It helps us to connect a remote server over private key or password and access the contents of that server. Syntax: ssh 
[option value] username@hostname. Various options included -p to specify port number, -i to specify private key etc.
* `openssl` - openssl is a open-source version of ssl or secure shell protocol. It helps to innitiate a secure remote connection, encrypt 
or decrypt files, create or verify certificates, generate rsa keys etc. General syntax: ssl [option] command. Ex. to connect over a remote 
server, openssl s_client -connect HOST:PORT where s_clint acts as a SSL/TSL (Transport Layer Security) clint. Similarly other commands 
include rsa to generate rsa keys or to do vice versa, dgst to generate various hashes etc. For more detailed info how every command works, 
go through OPENSSL documentation provided by Bandit. -quiet flag helps to reduce the no. of certificates shown during any communication.
* `nmap` - nmap is the GOAT in network scanning and server detection as it can search for open ports in a range of ip address and ports and can also guess the OS 
with versions efficiently as well as server they are running on. Basic syntax: nmap [option] HOST.  There are various option to include such as -sn to scan to see 
if host is up and running, -sT for TCP port scanning (with -sS it does it in sleath mode means it never send ACK packet back to server) -sU for UDP scan -p to 
include the range of port or specific port to use -F to scan withing 100 common port (without -F or -p it will do within 1000 common ports), -T to ensure how fast
to do the scan -o for OS detection, -sV for server detection, -Pn for force scan, -v for verbose, -d for debugging etc. Read more about nmap in details. 
---

## 💡 Progressive Hints
Try to solve the level after reading each hint before moving on to the next one!

* **Hint 1:** First understand how the question really want to find the password of the next level.
* **Hint 2:** Look for which command you can use to scan first which ports are really open. Then use other options to scan the version (Or you can do the both process
* together).
* **Hint 3:** Then use proper command to communicate with the server to get your password for next level. (pipe echo command before echo "bandit16 pass" | command).
* Then copy the private key and save it locally with .private and tune down the permission to 600 using chmod. Then get the pass from /etc/bandit_pass/bandit17.

## 🚶‍♂️ Step-by-Step Methodology
1. **[Step 1 Action]:** Log into bandit16
2. **[Step 2 Action]:** Then use nmap with port range from 31000 to 32000 to look for open ports then use -sV on those specific ports to get if they're running on Openssl.
3. **[Step 3 Action]:** Then pipe echo along with the password on correct port  and it return the bandit17 private key. Save it locally to login into next level.
4. OR you can log into bandit17 now and can retrieve the pass for bandit17 from /etc/bandit_pass/bandit17

## 🧠 Key Takeaway
Throughout this level you can learn how to use nmap to scan for open ports and also how to use various option to operate nmap more efficiently.
---

## ⚠️ Solution (Spoiler Warning!)

<details>
<summary><b>🚨 Click here only if you are completely stuck and need the exact commands! 🚨</b></summary>

<br>

**Exact Commands:**
```bash

# Execute the solution
1. ssh bandit16@bandit.labs.overthewire.org
2. nmap -p 31000-32000 localhost 
3. nmap -sV -p 31046,31518,31691,31790,31960 localhost
4. echo "kS0Hf0u5HiXFwKMKFqXvPdOTNGGa0X8V" | openssl s_client -connect localhost:31790 -quiet
5. [copy-paste it in a file using nano or manually with .private as extension]
6. ssh bandit17@bandit.labs.overthewire.org -i bandit17.private
7. cat /etc/bandit_pass/bandit17

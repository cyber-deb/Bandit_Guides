# 🚩 Bandit Level 15 → Level 16

## 🎯 Objective
The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL/TLS encryption.

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
---

## 💡 Progressive Hints
Try to solve the level after reading each hint before moving on to the next one!

* **Hint 1:** First understand how the question really want to find the password of the next level.
* **Hint 2:** Look for which command you can use to communicate with localhost on port 30001 using a SSL/TLS connection, not any normal connection.

## 🚶‍♂️ Step-by-Step Methodology
1. **[Step 1 Action]:** Log into bandit15
2. **[Step 2 Action]:** Then use openssl with porper command, flags, host and port
3. **[Step 3 Action]:** Then paste the password of bandit14 and wallah!


## 🧠 Key Takeaway
Throughout this level you can learn how to communicate with any remote server using openssl over ssl/tls which provides more security as it hashes the info while sending any communication (not sent in aa a plaintext). So security is more rather than communication between other methonds which don't have any ssl/tls security. 
---

## ⚠️ Solution (Spoiler Warning!)

<details>
<summary><b>🚨 Click here only if you are completely stuck and need the exact commands! 🚨</b></summary>

<br>

**Exact Commands:**
```bash

# Execute the solution
1. ssh bandit15@bandit.labs.overthewire.org
2. openssl s_client -connect localhost:30001 -quiet 
3. [Paste the password of bandit15 now and hit Enter]

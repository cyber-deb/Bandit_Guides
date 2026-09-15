# 🚩 Bandit Level 14 → Level 15

## 🎯 Objective
The password for the next level can be retrieved by submitting the password of the current level to port 30000 on localhost.
---

## 📚 Concepts & Prerequisites
Before attempting this level, you should understand how to use the following commands and concepts. 

**Recommended Research (man pages are your friend! and also the helpful resources in Bandit Level):**
* `ls` - ls command list down every files and directories available in a specific path. In general it lists down everything inside current directory (excluding
hidden ones). But one can specify a selected path by ls [path] to configure selected path. There are many options to attach with ls such as ls -a (List down hidden
files and folders), ls -l (List down files with file permission).
* `ssh` - ssh stands for secure shell. It helps us to connect a remote server over private key or password and access the contents of that server. Syntax: ssh 
[option value] username@hostname. Various options included -p to specify port number, -i to specify private key etc.
* `nc` - Full from of netcat. It helps to connect to a remote server and can interchange info accordingly. Basic syntax: nc [option] HOST PORT. There are few options including -l for listen mode, -u for UDP mode (generally nc works on TCP mode), -z to scan the network, -w to wait before terminating connection etc. Other similar tools are ncat (upgraded version of nc with more option such as --read-only,  --send-only), telnet (very popular to connect over tcp), socat (to connect with any protocol to any protocol) etc.

## 💡 Progressive Hints
Try to solve the level after reading each hint before moving on to the next one!

* **Hint 1:** First understand how the question really want to find the password of the next level.
* **Hint 2:** Look for which command you can use to communicate with localhost on port 30000.

## 🚶‍♂️ Step-by-Step Methodology
1. **[Step 1 Action]:** Log into bandit14
2. **[Step 2 Action]:** Then use nc with porper host and port
3. **[Step 3 Action]:** Then paste the password of bandit14 and wallah!


## 🧠 Key Takeaway
Throughout this level you can learn how to communicate with any remote server using netcat. Other tools such as telnet, socat or ncat also works in the same way, just maybe the dress can be a bit different to manage or wear.
---

## ⚠️ Solution (Spoiler Warning!)

<details>
<summary><b>🚨 Click here only if you are completely stuck and need the exact commands! 🚨</b></summary>

<br>

**Exact Commands:**
```bash

# Execute the solution
1. ssh bandit14@bandit.labs.overthewire.org
2. nc localhost 30000
3. [Paste the password of bandit14 now and hit enter]

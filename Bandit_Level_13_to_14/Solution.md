# 🚩 Bandit Level 13 → Level 14

## 🎯 Objective
The password for the next level is stored in /etc/bandit_pass/bandit14 and can only be read by user bandit14. For this level, you don’t get the next password, 
but you get a private SSH key that can be used to log into the next level. Look at the commands that logged you into previous bandit levels, and find out how to 
use the key for this level.
If you need help with this level: a hint file can be found in the home directory.
Make sure to read the error messages as they are informative.
---

## 📚 Concepts & Prerequisites
Before attempting this level, you should understand how to use the following commands and concepts. 

**Recommended Research (man pages are your friend! and also the helpful resources in Bandit Level):**
* `ls` - ls command list down every files and directories available in a specific path. In general it lists down everything inside current directory (excluding
hidden ones). But one can specify a selected path by ls [path] to configure selected path. There are many options to attach with ls such as ls -a (List down hidden
files and folders), ls -l (List down files with file permission).
* `ssh` - ssh stands for secure shell. It helps us to connect a remote server over private key or password and access the contents of that server. Syntax: ssh 
[option value] username@hostname. Various options included -p to specify port number, -i to specify private key etc.
* `scp` - Full from of scp is Secure Copy. It helps to copy any file from remote host to local server and vice versa. Basic syntax: scp [option] source destination.
Ex. to copy a file from remote host to local system, scp user@host:[path] [path in your local system] and vice versa.

## 💡 Progressive Hints
Try to solve the level after reading each hint before moving on to the next one!

* **Hint 1:** First understand what the question really want to extract data or what information is given so on that basis you can use your command.
* **Hint 2:** Look for what you got in bandit13 that can be used in bandit14 to log in as we can only access the password of bandit14 as bandit14 user not bandit13
* **Hint 3:** Then use it to log in bandit14. Once you are in bandit14, go to /etc/bandit_pass/bandit14 to get the bandit14 password.
---

## 🚶‍♂️ Step-by-Step Methodology
1. **[Step 1 Action]:** Use scp to copy the private key into your local system
2. **[Step 2 Action]:** Then use ssh with the private key during log into bandit14 (before that change the file permission to 600 or 400 using chmod as private key should not be too open to use as)
3. **[Step 3 Action]:** Then use cat to see the pass of bandit14 form /etc/bandit_pass/bandit14


## 🧠 Key Takeaway
Throughout this level you can learn how to use scp to transfer file from remote to local system as well as how to use a private key while logging in through ssh. You should go through the Reading material here for a clarity in private key and stuffs.
---

## ⚠️ Solution (Spoiler Warning!)

<details>
<summary><b>🚨 Click here only if you are completely stuck and need the exact commands! 🚨</b></summary>

<br>

**Exact Commands:**
```bash

# Execute the solution
1. scp bandit13@bandit.labs.overthewire.org:sshkey.private .
2. chmod 600 sshkey.private
3. ssh -p 2220 bandit14@bandit.labs.overthewire.org -i sshkey.private
4. cat /etc/bandit_pass/bandit14

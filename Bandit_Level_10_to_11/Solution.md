# 🚩 Bandit Level 10 → Level 11

## 🎯 Objective
The password for the next level is stored in the file data.txt, which contains base64 encoded data
---

## 📚 Concepts & Prerequisites
Before attempting this level, you should understand how to use the following commands and concepts. 

**Recommended Research (man pages are your friend! and also the helpful resources in Bandit Level):**
* `ls` - ls command list down every files and directories available in a specific path. In general it lists down everything inside current directory (excluding hidden ones). But one can specify a selected path by ls [path] to configure selected path. There are many options to attach with ls such as ls -a (List down hidden files and folders), ls -l (List down files with file permission).
* `ssh` - ssh stands for secure shell. It helps us to connect a remote server over private key or password and access the contents of that server.
* `base64` - Base64 is a encoding and decoding process (Not encryption decryption, meaning anyone can decode the encoded text). It uses 64 items to encode starting
from A-Z, a-z, 0-9, + and /. And it usually ends with = or == so you can identify easily its Base64 encoded. To encode a file, syntax: base64 filename. To decode, 
syntax: base64 -d filename

## 💡 Progressive Hints
Try to solve the level after reading each hint before moving on to the next one!

* **Hint 1:** First understand what the question really want to extract data or what information is given so on that basis you can use your command.
* **Hint 2:** Then understand which encoding is this and how to decode this to get the password

---

## 🚶‍♂️ Step-by-Step Methodology
1. **[Step 1 Action]:** Using ssh command first log in into bandit11. 
2. **[Step 2 Action]:** Use base64 to decode the content of data.txt


## 🧠 Key Takeaway
Throughout this level you can learn how to use base64 to encode and decode data in Linux.
---

## ⚠️ Solution (Spoiler Warning!)

<details>
<summary><b>🚨 Click here only if you are completely stuck and need the exact commands! 🚨</b></summary>

<br>

**Exact Commands:**
```bash
# Connect to the server
ssh bandit10@bandit.labs.overthewire.org -p 2220

# Execute the solution
1. base64 -d data.txt

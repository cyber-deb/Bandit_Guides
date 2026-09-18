# 🚩 Bandit Level 18 → Level 19

## 🎯 Objective
The password for the next level is stored in a file readme in the homedirectory. Unfortunately, someone has modified .bashrc to log you out when you log in with SSH.

---

## 📚 Concepts & Prerequisites
Before attempting this level, you should understand how to use the following commands and concepts. 

**Recommended Research (man pages are your friend! and also the helpful resources in Bandit Level):**
* `ssh` - ssh stands for secure shell. It helps us to connect a remote server over private key or password and access the contents of that server. Syntax: ssh [option value] username@hostname. Various options included -p to specify port number, -i to specify private key etc. Additionally one can pass only a single command to execute right after login that doesn't get interrupted by any .bashrc file.

---

## 💡 Progressive Hints
Try to solve the level after reading each hint before moving on to the next one!

* **Hint 1:** First understand how the question really want to find the password of the next level.
* **Hint 2:** Think how u can pass command without even logging in.

## 🚶‍♂️ Step-by-Step Methodology
1. **[Step 1 Action]:** Log into bandit18 with a cat command to read the content of the readme file

## 🧠 Key Takeaway
Throughout this level you can learn that we can pass a single command to be get executed in a ssh connection right after logging in automatically that changes of .bashrc don't interrupt.

---

## ⚠️ Solution (Spoiler Warning!)

<details>
<summary><b>🚨 Click here only if you are completely stuck and need the exact commands! 🚨</b></summary>

<br>

**Exact Commands:**
```bash

# Execute the solution
1. ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme

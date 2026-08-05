# 🚩 Bandit Level 1 → Level 2

## 🎯 Objective
The password for the next level is stored in a file called - located in the home directory

---

## 📚 Concepts & Prerequisites
Before attempting this level, you should understand how to use the following commands and concepts. 

**Recommended Research (man pages are your friend! and also the helpful resources in Bandit Level):**
* `ls` - ls command list down every files and directories available in a specific path. In general it lists down everything inside current directory (excluding hidden ones). But one can specifiy a selected path by ls [path] to configure selected path. There are many options to attach with ls such as ls -a (List down hidden files and folders), ls -l (List down files with file permission).
* `pwd` - pwd helps to find out the path of the present working directory.
* `ssh` - ssh stands for secure shell. It helps us to connect a remote server over private key or password and access the contents of that server.
* `cat` - cat helps to print the content of any file on the terminal. Syntax: cat [filename].extension
---

## 💡 Progressive Hints
Try to solve the level after reading each hint before moving on to the next one!

* **Hint 1:** First understand how to search the available files in the home directory.
* **Hint 2:** Learn how to open a - file.
* **Hint 3:** Then print the content of the - file to get the password for the next level.

---

## 🚶‍♂️ Step-by-Step Methodology
1. **[Step 1 Action]:** Using ssh command first log in into bandit1 where the - file exists. 
2. **[Step 2 Action]:** Using ls find out the contents of the directory 
3. **[Step 3 Action]:** Use cat and appropriate way to open up - file.

---

## 🧠 Key Takeaway
Throughout this level you can learn how to open - file or any other file which is starting without any alpha numeric number.

---

## ⚠️ Solution (Spoiler Warning!)

<details>
<summary><b>🚨 Click here only if you are completely stuck and need the exact commands! 🚨</b></summary>

<br>

**Exact Commands:**
```bash
# Connect to the server
ssh bandit1@bandit.labs.overthewire.org -p 2220

# Execute the solution
1. ls
2. cat ./-

# 🚩 Bandit Level 0 → Level 1

## 🎯 Objective
The password for the next level is stored in a file called readme located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.

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

* **Hint 1:** First uderstand where can you find the password file. 
* **Hint 2:** If you are already inside the server, then find out in which directory are you currently inside
* **Hint 3:** Then if you are inside of the current directory, then think how can you find out that the specific 'readme' file really exist in your directory.
* **Hint 4:** Then if you have got the file, then think which command can you use to open or print the content of the file.

---

## 🚶‍♂️ Step-by-Step Methodology
1. **[Step 1 Action]:** Using ssh command first log in into bandit0 where the readme file exists. 
2. **[Step 2 Action]:** Using pwd check which directory you are really in.
3. **[Step 3 Action]:** Use ls to find out the contents of that specific directory or just use cat command to print the content of the readme file 

---

## 🧠 Key Takeaway
Throughout this level you can have a grasp the use of some small but very needful commands such as ls, cat, pwd, ssh which is going to help you out throughout completing other Bandit levels.

---

## ⚠️ Solution (Spoiler Warning!)

<details>
<summary><b>🚨 Click here only if you are completely stuck and need the exact commands! 🚨</b></summary>

<br>

**Exact Commands:**
```bash
# Connect to the server
ssh bandit0@bandit.labs.overthewire.org -p 2220

# Execute the solution
1. pwd
2. ls
3. cat readme

# 🚩 Bandit Level 7 → Level 8

## 🎯 Objective
The password for the next level is stored in the file data.txt next to the word millionth
---

## 📚 Concepts & Prerequisites
Before attempting this level, you should understand how to use the following commands and concepts. 

**Recommended Research (man pages are your friend! and also the helpful resources in Bandit Level):**
* `ls` - ls command list down every files and directories available in a specific path. In general it lists down everything inside current directory (excluding hidden ones). But one can specify a selected path by ls [path] to configure selected path. There are many options to attach with ls such as ls -a (List down hidden files and folders), ls -l (List down files with file permission).
* `ssh` - ssh stands for secure shell. It helps us to connect a remote server over private key or password and access the contents of that server.
* `grep` - grep is a powerful command in Linux that helps to extract a specific pattern containing lines from specific file(s) (with a recursive tag -r it can extract the name of the files containing the pattern). Syntax: grep [option] "pattern" file_names.There are various tags in grep that u can get from the man page of grep. 
---

## 💡 Progressive Hints
Try to solve the level after reading each hint before moving on to the next one!

* **Hint 1:** First understand what the question really want to extract data or what information is given so on that basis you can use your command
* **Hint 2:** Then use grep command with the pattern and the filename. That's it.

---

## 🚶‍♂️ Step-by-Step Methodology
1. **[Step 1 Action]:** Using ssh command first log in into bandit1 where the - file exists. 
2. **[Step 2 Action]:** Use grep command to find out the password containing line from the file data.txt.


## 🧠 Key Takeaway
Throughout this level you can learn how to use grep command to find a pattern containing line without wasting time to manually go through every line.
---

## ⚠️ Solution (Spoiler Warning!)

<details>
<summary><b>🚨 Click here only if you are completely stuck and need the exact commands! 🚨</b></summary>

<br>

**Exact Commands:**
```bash
# Connect to the server
ssh bandit7@bandit.labs.overthewire.org -p 2220

# Execute the solution
1. grep "millionth" data.txt

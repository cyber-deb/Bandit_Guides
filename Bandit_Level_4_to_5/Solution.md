# 🚩 Bandit Level 4 → Level 5

## 🎯 Objective
The password for the next level is stored in the only human-readable file in the inhere directory. Tip: if your terminal is messed up, try the “reset” command.

---

## 📚 Concepts & Prerequisites
Before attempting this level, you should understand how to use the following commands and concepts. 

**Recommended Research (man pages are your friend! and also the helpful resources in Bandit Level):**
* `ls` - ls command list down every files and directories available in a specific path. In general it lists down everything inside current directory (excluding hidden ones). But one can specify a selected path by ls [path] to configure selected path. There are many options to attach with ls such as ls -a (List down hidden files and folders), ls -l (List down files with file permission).
* `ssh` - ssh stands for secure shell. It helps us to connect a remote server over private key or password and access the contents of that server.
* `cat` - cat helps to print the content of any file on the terminal. Syntax: cat [filename].extension.
* `cd` - cd stands for change directory. Use cd [path or foldername] to use your terminal in that specific directory. To go back to previous directory, you can use cd .. to return back or can use cd ~ to go to home directory directly.
* `file` - file determines what type of data a file actually contains. It doesn't rely only on the filename or extension. Basic syntax: file [option] filename. To print every file's datatype, simply use file ./* to print all. Also there's -d option to show datatype of specific file or -i to show MIME type.
---

## 💡 Progressive Hints
Try to solve the level after reading each hint before moving on to the next one!

* **Hint 1:** First understand how to go to the specific inhere directory.
* **Hint 2:** Then understand how to search for files in a directory.
* **Hint 3:** Then think how to understand which file is the one readable among these. (N.B. : ASCII files are readable and all files are starting with a -)

---

## 🚶‍♂️ Step-by-Step Methodology
1. **[Step 1 Action]:** Using ssh command first log in into bandit1 where the - file exists. 
2. **[Step 2 Action]:** Using cd, change your directory to inhere directory. Use ls to find the filename if needed.
3. **[Step 3 Action]:** Use ls to find the list of all files and directories list.
4. **[Step 4 Action]:** use find to find out which file is human readable. Then remember how to open a file starting with - and if you know that then enjoy :).
---

## 🧠 Key Takeaway
Throughout this level you can learn how to identify filetypes without opening them in Linux.

---

## ⚠️ Solution (Spoiler Warning!)

<details>
<summary><b>🚨 Click here only if you are completely stuck and need the exact commands! 🚨</b></summary>

<br>

**Exact Commands:**
```bash
# Connect to the server
ssh bandit4@bandit.labs.overthewire.org -p 2220

# Execute the solution
1. cd inhere
2. ls 
3. find ./*
4. cat ./-file07

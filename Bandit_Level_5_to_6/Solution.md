# 🚩 Bandit Level 5 → Level 6

## 🎯 Objective
The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:
1. human-readable
2. 1033 bytes in size
3. not executable
---

## 📚 Concepts & Prerequisites
Before attempting this level, you should understand how to use the following commands and concepts. 

**Recommended Research (man pages are your friend! and also the helpful resources in Bandit Level):**
* `ls` - ls command list down every files and directories available in a specific path. In general it lists down everything inside current directory (excluding hidden ones). But one can specify a selected path by ls [path] to configure selected path. There are many options to attach with ls such as ls -a (List down hidden files and folders), ls -l (List down files with file permission).
* `ssh` - ssh stands for secure shell. It helps us to connect a remote server over private key or password and access the contents of that server.
* `cat` - cat helps to print the content of any file on the terminal. Syntax: cat [filename].extension.
* `cd` - cd stands for change directory. Use cd [path or foldername] to use your terminal in that specific directory. To go back to previous directory, you can use cd .. to return back or can use cd ~ to go to home directory directly.
* `find` - As the name suggest, find command helps to find out specific files (including hidden ones) inside of a directory. It scans through every directories in the specified path and will tell what's matching our request. Basic Syntax: file [path] [options] [values]. There are many options such as -type to specify file type, -size to specify file size, -name to specify filename, -perm to find file matching exact permission and many more. Use man command to find more about 'find' and these options. 
---

## 💡 Progressive Hints
Try to solve the level after reading each hint before moving on to the next one!

* **Hint 1:** First understand how to go to the specific inhere directory.
* **Hint 2:** Then understand what's the demand of the goal like what's the specifications of that exact file.
* **Hint 3:** Then use find command with exact flags to search throughout all directories inside inhere. (To mention size you need to write c at the end of the byte numerical value as c indicates byte)

---

## 🚶‍♂️ Step-by-Step Methodology
1. **[Step 1 Action]:** Using ssh command first log in into bandit1 where the - file exists. 
2. **[Step 2 Action]:** Using cd, change your directory to inhere directory. Use ls to see what's really inside.
3. **[Step 3 Action]:** Use find command with specific flags like -size, -type etc to find out the file.
4. **[Step 4 Action]:** To check the specific file is not executable, use ls -l [filename or path to the file] to find it out. (If there's no 'x' in the list that means it's not executable). Then open your file.
---

## 🧠 Key Takeaway
Throughout this level you can learn how to use find command to find out specific file without sweating a bit.

---

## ⚠️ Solution (Spoiler Warning!)

<details>
<summary><b>🚨 Click here only if you are completely stuck and need the exact commands! 🚨</b></summary>

<br>

**Exact Commands:**
```bash
# Connect to the server
ssh bandit5@bandit.labs.overthewire.org -p 2220

# Execute the solution
1. cd inhere
2. find -type f -size 1033c 
3. cat maybehere07/.file2 
N.B.: You can also do ls -l maybehere07/.file2 to check if its truly non executable or not.

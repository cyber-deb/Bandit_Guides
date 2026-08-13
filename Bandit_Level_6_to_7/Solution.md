# 🚩 Bandit Level 6 → Level 7

## 🎯 Objective
The password for the next level is stored somewhere on the server and has all of the following properties:
1. owned by user bandit7
2. owned by group bandit6
3. 33 bytes in size
---

## 📚 Concepts & Prerequisites
Before attempting this level, you should understand how to use the following commands and concepts. 

**Recommended Research (man pages are your friend! and also the helpful resources in Bandit Level):**
* `ls` - ls command list down every files and directories available in a specific path. In general it lists down everything inside current directory (excluding hidden ones). But one can specify a selected path by ls [path] to configure selected path. There are many options to attach with ls such as ls -a (List down hidden files and folders), ls -l (List down files with file permission).
* `ssh` - ssh stands for secure shell. It helps us to connect a remote server over private key or password and access the contents of that server.
* `cat` - cat helps to print the content of any file on the terminal. Syntax: cat [filename].extension.
* `find` - As the name suggest, find command helps to find out specific files (including hidden ones) inside of a directory. It scans through every directories in the specified path and will tell what's matching our request. Basic Syntax: file [path] [options] [values]. There are many options such as -type to specify file type, -size to specify file size, -name to specify filename, -perm to find file matching exact permission and many more. Use man command to find more about 'find' and these options. 
---

## 💡 Progressive Hints
Try to solve the level after reading each hint before moving on to the next one!

* **Hint 1:** First understand what's the demand of the goal like what's the specifications of that exact file.
* **Hint 2:** Then use find command with exact flags to search throughout all directories inside inhere. (To mention size you need to write c at the end of the byte numerical value as c indicates byte)

---

## 🚶‍♂️ Step-by-Step Methodology
1. **[Step 1 Action]:** Using ssh command first log in into bandit1 where the - file exists. 
3. **[Step 2 Action]:** Use find command with specific flags like -size, -type -user -group etc. to find out the file.
4. **[Step 3 Action]:** Then learn a bit about piping and redirection beforehand from here as it may require to send the error messages outside from the output result. (Helpful resource: https://ryanstutorials.net/linuxtutorial/piping.php ) [N.B.: you don't generally need to learn this a lot else you output can be a little messy to find the exact file]
---

## 🧠 Key Takeaway
Throughout this level you can learn how to use find command to find out specific file without sweating a bit. Also you are going to learn about Handling input error and output processes a  bit if u read that resource. 

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
1. find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null
2. cat /var/lib/dpkg/info/bandit7.password
N.B.: 2> means you are handling the errors in the specific path which is /dev/null which basically dumps error messages into null.

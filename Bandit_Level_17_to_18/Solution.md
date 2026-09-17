# 🚩 Bandit Level 17 → Level 18

## 🎯 Objective
There are 2 files in the homedirectory: passwords.old and passwords.new. The password for the next level is in passwords.new and is the only line that has been 
changed between passwords.old and passwords.new
---

## 📚 Concepts & Prerequisites
Before attempting this level, you should understand how to use the following commands and concepts. 

**Recommended Research (man pages are your friend! and also the helpful resources in Bandit Level):**
* `ssh` - ssh stands for secure shell. It helps us to connect a remote server over private key or password and access the contents of that server. Syntax: ssh 
[option value] username@hostname. Various options included -p to specify port number, -i to specify private key etc.
* `diff` - diff is a useful command to find out whether two files are different in any parts or not. It also returns exit code 0 for if any difference exists or 0 if not. Syntax: diff [option] file1 file2. It generally returns the thing which is found different in both file with a code (e.g. 42c42) and the line in first file which is different with '<' and the line in second file that has been found in correspond different with '>'. The code can have 'c' to identify change, 'd' to identify different and 'a' for extra line. The options include -y for side by side comparison, -u for unified format (generally to see git patches), -q to tell only if different, -i to be case insensitive -w to ignore whitespace -r to search recursively in folder etc.
---

## 💡 Progressive Hints
Try to solve the level after reading each hint before moving on to the next one!

* **Hint 1:** First understand how the question really want to find the password of the next level.
* **Hint 2:** Look for which command you can use to find the line different in both files

## 🚶‍♂️ Step-by-Step Methodology
1. **[Step 1 Action]:** Log into bandit17
2. **[Step 2 Action]:** Then use diff on password.old and password.new respectively and pick the pass starting with > OR, u can pipe the output in grep and only extract the line with '>' in it. [Remember, first line will show the difference in first line and the second one wlll second file.]

## 🧠 Key Takeaway
Throughout this level you can learn how to use diff command to find difference between two files more efficiently.
---

## ⚠️ Solution (Spoiler Warning!)

<details>
<summary><b>🚨 Click here only if you are completely stuck and need the exact commands! 🚨</b></summary>

<br>

**Exact Commands:**
```bash

# Execute the solution
1. ssh bandit17@bandit.labs.overthewire.org
2. diff password.old password.new | grep '>'

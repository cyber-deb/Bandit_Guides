# 🚩 Bandit Level 26 → Level 27

## 🎯 Objective
Good job getting a shell! Now hurry and grab the password for bandit27!

---

## 📚 Concepts & Prerequisites
Before attempting this level, you should understand how to use the following commands and concepts. 

**Recommended Research (man pages are your friend! and also the helpful resources in Bandit Level):**
* `ssh` - ssh stands for secure shell. It helps us to connect a remote server over private key or password and access the contents of that server. Syntax: ssh 
[option value] username@hostname. Various options included -p to specify port number, -i to specify private key etc. Type quit to exit a ssh session. 
* `setuid` - SetUID (Set User ID) is a Linux file permission that makes a program run with the permissions of the file's owner, rather than the user who executes it. Suppose, a file, which can be run by only root has a setuid (-rwsrw-r--). But for the setuid, the specific command can be run as a user and it will act as if that permitted user is running the command. For more info, check out the content provided by Bandit.

  
## 💡 Progressive Hints
Try to solve the level after reading each hint before moving on to the next one!

* **Hint 1:** First understand how the question really want to find the password of the next level. Here if you show what's inside home directory, you can find bandit27-do and inspect its permissions to see that it has the SUID bit set. 
* **Hint 2:** Then if you run it within attaching any command you will understand that this setuid runs any command as another user, here in our case bandit27
* **Hint 3:** Then just add a command that will read the password of bandit27 from /etc/bandit_pass.
 
## 🚶‍♂️ Step-by-Step Methodology
1. **[Step 1 Action]:** Log into bandit26
2. **[Step 2 Action]:** Then run bandit27-do with cat command that will read the bandit27 pass from /etc/bandit_pass.


## 🧠 Key Takeaway
Throughout this level you will revise the concept of setuid that it doesnt run based on the user you are currently running with, but the user it has been set to and how critical a SETuid file can be as it executes commands based on another user's identity.

---

## ⚠️ Solution (Spoiler Warning!)

<details>
<summary><b>🚨 Click here only if you are completely stuck and need the exact commands! 🚨</b></summary>

<br>

**Exact Commands:**
```bash

# Execute the solution
1. ssh bandit26@bandit.labs.overthewire.org -p 2220
2. ls -l bandit27-do
3. ./bandit27-do cat /etc/bandit_pass/bandit27

# 🚩 Bandit Level 19 → Level 20

## 🎯 Objective
To gain access to the next level, you should use the setuid binary in the homedirectory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (/etc/bandit_pass), after you have used the setuid binary.

---

## 📚 Concepts & Prerequisites
Before attempting this level, you should understand how to use the following commands and concepts. 

**Recommended Research (man pages are your friend! and also the helpful resources in Bandit Level):**
* `ssh` - ssh stands for secure shell. It helps us to connect a remote server over private key or password and access the contents of that server. Syntax: ssh 
[option value] username@hostname. Various options included -p to specify port number, -i to specify private key etc.
* `setuid` - SetUID (Set User ID) is a Linux file permission that makes a program run with the permissions of the file's owner, rather than the user who executes it. Suppose, a file, which can be run by only root has a setuid (-rwsrw-r--). But for the setuid, the specific command can be run as a user and it will act as if that permitted user is running the command. For more info, check out the content provided by Bandit.

## 💡 Progressive Hints
Try to solve the level after reading each hint before moving on to the next one!

* **Hint 1:** First understand how the question really want to find the password of the next level.
* **Hint 2:** Look if the the file inside home directory is a file with setuid. If it is then check what it can perform by just running it. Watch the error.
* **Hint 3:** Then according to the error add suitable command to dump the password of bandit20.
 
## 🚶‍♂️ Step-by-Step Methodology
1. **[Step 1 Action]:** Log into bandit19
2. **[Step 2 Action]:** Then use ls -l to check if it has setuid.
3. **[Step 3 Action]:** Then execute the file using ./ to see what it actually do.
4. **[Step 4 Action]:** Then run the command with necessary command such as cat to get the file content from /etc/bandit_pass/bandit20 

## 🧠 Key Takeaway
Throughout this level you can learn what setuid really is and how it acts. SUID programs can be useful when a normal user needs privileged functionality, but a misconfigured or vulnerable SUID binary can allow privilege escalation.

---

## ⚠️ Solution (Spoiler Warning!)

<details>
<summary><b>🚨 Click here only if you are completely stuck and need the exact commands! 🚨</b></summary>

<br>

**Exact Commands:**
```bash

# Execute the solution
1. ssh bandit17@bandit.labs.overthewire.org -p 2220
2. ls -l ./bandit20-do  #jsut to check whether its setuid or not
3. ./bandit20-do cat /etc/bandit_pass/bandit20

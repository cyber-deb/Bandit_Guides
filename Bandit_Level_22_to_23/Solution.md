# 🚩 Bandit Level 22 → Level 23

## 🎯 Objective
A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.

NOTE: Looking at shell scripts written by other people is a very useful skill. The script for this level is intentionally made easy to read. If you are having problems understanding what it does, try executing it to see the debug information it prints.

---

## 📚 Concepts & Prerequisites
Before attempting this level, you should understand how to use the following commands and concepts. 

**Recommended Research (man pages are your friend! and also the helpful resources in Bandit Level):**
* `ssh` - ssh stands for secure shell. It helps us to connect a remote server over private key or password and access the contents of that server. Syntax: ssh 
[option value] username@hostname. Various options included -p to specify port number, -i to specify private key etc. Type quit to exit a ssh session. 
* `crontab` - Before knowing what crontab command is, first you need to know what Cron is. Cron is a job scheduler which runs command or script automatically at a specific time. crond is the background daemon that runs cron jobs and crontab is a command that helps to show table of cron jobs. To list all jobs, we can use crontab -l and to edit -e and to remove all jobs -r. There's a structure to know how the command is running and what is running. Cron files can be found in /etc/crontab/

## 💡 Progressive Hints
Try to solve the level after reading each hint before moving on to the next one!

* **Hint 1:** First understand how the question really want to find the password of the next level. First see what the specific cron job actually doing.
* **Hint 2:** Then you can find a location of a file which is executing as bandit23. Go and check what that file is executing.
* **Hint 3:** Then you can see what the password is actually doing while being run by bandit23 username. Now here you need to get the specific md5 hash of that line that has been piped into it to go to the file location in tmp directory.
* **Hint 4:** So, you can do one thing that is to copy the specific mytarget variable innitiation line and by changing the $myname to bandit23, you can either run it in terminal as assiging variable called mytarget and then echoing the variable $mytarget or can simply echo the whole thing to get the md5 hash of that line when being ran by bandit23.
* **Hint 5:** Now see the content of the file in the tmp directory to get the password of next level.
 
## 🚶‍♂️ Step-by-Step Methodology
1. **[Step 1 Action]:** Log into bandit22
2. **[Step 2 Action]:** Then go to /etc/cron.d where you can find cronjob_bandit23. Open it.
3. **[Step 3 Action]:** Then go to the location of the script file and see what it is performing.
4. **[Step 4 Action]:** Then copy the full line 3 i.e. the line containing the assignment of mytarget variable. Paste it in terminal and change the $myname to bandit23.
5. **[Step 5 Action]:** Then echo the variable $mytarget and get the md5 hash. Now go to the specific file in the tmp directory to get the password. Or just open the file /tmp/$mytarget.

## 🧠 Key Takeaway
Throughout this level you can learn what cron is and how to use or investigate into cronjobs. There are many parts about cron and crontab. Study in details. I haven't tell much in this solution as that is irrelevant from solving this level. In addition, you can learn how to solve problem by going through any script and seeing what it actually does rather than relying on known commands.

---

## ⚠️ Solution (Spoiler Warning!)

<details>
<summary><b>🚨 Click here only if you are completely stuck and need the exact commands! 🚨</b></summary>

<br>

**Exact Commands:**
```bash

# Execute the solution
1. ssh bandit22@bandit.labs.overthewire.org -p 2220
2. cat /etc/cron.d/cronjob_bandit23
3. cat /usr/bin/cronjob_bandit23.sh
4. #[copy paste the line containing the variable assignment of 'mytarget' and change the variable '$myname' with 'bandit23' and run it]
5. cat /tmp/$mytarget

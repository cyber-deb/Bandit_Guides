# 🚩 Bandit Level 21 → Level 22

## 🎯 Objective
A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.

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
* **Hint 2:** Then you can find a location of a file which is executing as bandit22. Go and check what that file is executing.
* **Hint 3:** Then you can see where the password is stored. Simply go there and open the file to get the password of bandit22.
 
## 🚶‍♂️ Step-by-Step Methodology
1. **[Step 1 Action]:** Log into bandit21
2. **[Step 2 Action]:** Then go to /etc/cron.d where you can find cronjob_bandit22. Open it.
3. **[Step 3 Action]:** Then go to the location of the script file and see what it is performing.
4. **[Step 4 Action]:** Then finally go to the file where the cronjob is storing the password of bandit22.

## 🧠 Key Takeaway
Throughout this level you can learn what cron is and how to use or investigate into cronjobs. There are many parts about cron and crontab. Study in details. I haven't tell much in this solution as that is irrelevant from solving this level.

---

## ⚠️ Solution (Spoiler Warning!)

<details>
<summary><b>🚨 Click here only if you are completely stuck and need the exact commands! 🚨</b></summary>

<br>

**Exact Commands:**
```bash

# Execute the solution
1. ssh bandit21@bandit.labs.overthewire.org -p 2220
2. cat /etc/cron.d/cronjob_bandit22
3. cat /usr/bin/cronjob_bandit22.sh
4. cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv

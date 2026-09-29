# 🚩 Bandit Level 23 → Level 24

## 🎯 Objective
A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.

NOTE: This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level!

NOTE 2: Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…

---

## 📚 Concepts & Prerequisites
Before attempting this level, you should understand how to use the following commands and concepts. 

**Recommended Research (man pages are your friend! and also the helpful resources in Bandit Level):**
* `ssh` - ssh stands for secure shell. It helps us to connect a remote server over private key or password and access the contents of that server. Syntax: ssh 
[option value] username@hostname. Various options included -p to specify port number, -i to specify private key etc. Type quit to exit a ssh session. 
* `crontab` - Before knowing what crontab command is, first you need to know what Cron is. Cron is a job scheduler which runs command or script automatically at a specific time. crond is the background daemon that runs cron jobs and crontab is a command that helps to show table of cron jobs. To list all jobs, we can use crontab -l and to edit -e and to remove all jobs -r. There's a structure to know how the command is running and what is running. Cron files can be found in /etc/crontab/
*  `bash` - Bash is a command-line shell used to interact with Linux/Unix systems. It also allows you to write scripts to automate tasks and run commands. To learn more about bash go through You Suck At Proramming's video (https://www.youtube.com/watch?v=Sx9zG7wa4FA). For this level, remember this, Every scripting language starts with a shebang and for bash, it is #! and next the /bin/bash which specifies which scripting language should be used to execute this file as there are multiple shells like bash such as FISH or zsh etc. [in altogether, the first line is #!/bin/bash]
  
## 💡 Progressive Hints
Try to solve the level after reading each hint before moving on to the next one!

* **Hint 1:** First understand how the question really want to find the password of the next level. First see what the specific cron job actually doing.
* **Hint 2:** Then you can find a location of a file which is executing as bandit24. Go and check what that file is executing.
* **Hint 3:** Then you can see what the file is actually doing while being run by bandit24 username. It's basically executing all files in that specific location but if you try to open the location you don't have the permission. Now what you can do is create your own script in tmp directory as if u directly create it in executing directory it will delete it periodically whether its successful or not.
* **Hint 4:** Then create a file or nano to type in, first shebang with the location. Then write something that can get the password from /etc/bandit_pass/bandit24 inside of your tmp directory from where you can open.
* **Hint 5:** Then if the process is successful then you can find your file in tmp directory. See the next level's password.
 
## 🚶‍♂️ Step-by-Step Methodology
1. **[Step 1 Action]:** Log into bandit23
2. **[Step 2 Action]:** Then go to /etc/cron.d where you can find cronjob_bandit24. Open it.
3. **[Step 3 Action]:** Then go to the location of the script file and see what it is performing.
4. **[Step 4 Action]:** Then create a script in /tmp directory using nano, and the main  content of the script is to cat the bandit24 from /etc/bandit_pass and dump it into a new file in /tmp.
5. **[Step 5 Action]:** Then see the password using cat /tmp/[filename]

## 🧠 Key Takeaway
Throughout this level you can learn what cron is and how to use or investigate into cronjobs. There are many parts about cron and crontab. Study in details. I haven't tell much in this solution as that is irrelevant from solving this level. In addition, you can learn how to write your own script in bash and again it isn't discussed deeply about scripting using  bash but as always you can go through my video reference and Bandit's resources to learn more about it

---

## ⚠️ Solution (Spoiler Warning!)

<details>
<summary><b>🚨 Click here only if you are completely stuck and need the exact commands! 🚨</b></summary>

<br>

**Exact Commands:**
```bash

# Execute the solution
1. ssh bandit23@bandit.labs.overthewire.org -p 2220
2. cat /etc/cron.d/cronjob_bandit24
3. cat /usr/bin/cronjob_bandit24.sh
4. nano /tmp/cracker.sh
[#Insode Nano
#!/bin/bash
cat etc/bandit_pass/bandit24 > /tmp/password]
5. chmod +x cracker.sh
6. cat /tmp/password

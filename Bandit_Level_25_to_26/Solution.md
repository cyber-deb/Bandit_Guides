# 🚩 Bandit Level 25 → Level 26

## 🎯 Objective
Logging in to bandit26 from bandit25 should be fairly easy… The shell for user bandit26 is not /bin/bash, but something else. Find out what it is, how it works and how to break out of it.

NOTE: if you’re a Windows user and typically use Powershell to ssh into bandit: Powershell is known to cause issues with the intended solution to this level. You should use command prompt instead.

---

## 📚 Concepts & Prerequisites
Before attempting this level, you should understand how to use the following commands and concepts. 

**Recommended Research (man pages are your friend! and also the helpful resources in Bandit Level):**
* `ssh` - ssh stands for secure shell. It helps us to connect a remote server over private key or password and access the contents of that server. Syntax: ssh 
[option value] username@hostname. Various options included -p to specify port number, -i to specify private key etc. Type quit to exit a ssh session. 
* `more` - more is a Linux command-line pager used to display the contents of a text file one screen/page at a time, especially when the file is too large to fit on the terminal. Basic syntax: more filename. 

Useful keys:
- Space → next page
- Enter → next line
- /pattern → search
- v → open the current file in vi
- q → quit
  
## 💡 Progressive Hints
Try to solve the level after reading each hint before moving on to the next one!

* **Hint 1:** First understand how the question really want to find the password of the next level. It says that the bandit26 uses different shell other than bash. When you log into bandit25, you can find the private key for bandit26. You can use scp or simply copy paste it into a file and set the permission to to at least 600 or below and try to go into bandit26.
* **Hint 2:** Then you can see you are automatically logged out of the bandit26. Now go back to bandit25 in the /etc/passwd file to get the shell name from passwd file. You can use grep to avoid manual search as passwd file contains shell address of an user. 
* **Hint 3:** Then you will finf out the shell address of bandit26. See what the shell is acutally performing.
* **Hint 4:** You will find out it is executing more command in a file called text.text. Now you have to stop more command to fully print or dump the content of the text file while you try to log into bandit26 so that you can access the vi editor.
* **Hint 5:** Now the trick is as more use the full page to print the content, resize the page as small as possible so that more cannot able to print 100% of the content. In the meantime, you can press v to enter into the vi editor for the text file.
* **Hint 6:** There, you can use a shell in vi editor by pressing escape button and typing :set shell=/bin/bash and hit enter. Then again press esc and type :shell and enter to get into the bash shell. From there just simply retrieve the password from /etc/bandit_pass/bandit26.
 
## 🚶‍♂️ Step-by-Step Methodology
1. **[Step 1 Action]:** Log into bandit25
2. **[Step 2 Action]:** Then copy the private key for bandit26 and set the permission to 600.
3. **[Step 3 Action]:** Then see the address of the shell bandit26 is using by going into /etc/passwd.
4. **[Step 4 Action]:** Then go to the shell address to see what the shell is actually performing each time one is trying to log in using private key. As you can see there is a file called text.text which is been called by more command.
5. **[Step 5 Action]:** Now as more required effective terminal size to paste the content of any file, resize the terminal as small as possible so that more cannot able to print the content of text file. Then during the process press v to enter into vi editor of text file.
6. **[Step 6 Action]:** As vi editor has it's own shell, press Esc and type :set shell=/bin/bash and then hit Enter. Next again press Esc and type :shell to enter into a bash shell in bandit26. From there just retrieve the pass from /etc/bandit_pass/bandit26.

## 🧠 Key Takeaway
Throughout this level you can learn where to find the shell information. How to use vulnerability to access a certain objective and how to set preferable shell in vi editor to use it. This level is nothing but the gathering of all ideas and skills to achieve something from known concepts. 

---

## ⚠️ Solution (Spoiler Warning!)

<details>
<summary><b>🚨 Click here only if you are completely stuck and need the exact commands! 🚨</b></summary>

<br>

**Exact Commands:**
```bash

# Execute the solution
1. ssh bandit25@bandit.labs.overthewire.org -p 2220
2. cat bandit26.sshkey #[copy it in your local system and save it with name bandit26.private and use chmod 600 bandit26.private]
3. cat /etc/passwd | grep bandit26
4. cat /usr/bin/showtext
5. exit
#[Resize the terminal window as small as possible]
6. ssh bandit26@bandit.labs.overthewire.org -p 2220 -i bandit26.private
#[If you see something like more(52%), press V to enter vi editor, then press Esc and type]
7. :set shell=/bin/bash  --> Enter
8. Esc --> :shell
9. cat /etc/bandit_pass/bandit26

# 🚩 Bandit Level 31 → Level 32

## 🎯 Objective
here is a git repository at ssh://bandit31-git@bandit.labs.overthewire.org/home/bandit31-git/repo via the port 2220. The password for the user bandit31-git is the same as for the user bandit31.

From your local machine (not the OverTheWire machine!), clone the repository and find the password for the next level. This needs git installed locally on your machine.

---

## 📚 Concepts & Prerequisites
Before attempting this level, you should understand how to use the following commands and concepts. 

**Recommended Research (man pages are your friend! and also the helpful resources in Bandit Level):**
* `git` - Git is a distributed version control system used to track changes in files and manage the history of a project. It allows developers to save changes as commits, work with branches, and collaborate through remote repositories.
Some common commands are git init (create a repository), git clone (copy a remote repository), git status (check changes),git branch (to see availabe branches), git switch branch_name (to swith to that specific branch instead of HEAD branch), git add (stage changes), git commit (save changes), git log (view commit history), git show (inspect a commit using the hash that has been generated over a specific log data), git branch (manage branches), git tag (to show available tag objects), git pull (download changes), and git push (upload changes).
The Git from the Bottom Up is the excellent resource to learn Git which is already provided in Bandit Level Resources.
  
## 💡 Progressive Hints
Try to solve the level after reading each hint before moving on to the next one!

* **Hint 1:** First understand how the question really want to find the password of the next level. Here you dont need to ssh into any remote server. Rather than you need to clone remote directory and the link is given in the question
* **Hint 2:** Then after cloning it in your local system, read the README.md file as it says that you need to push a file which contains the specific content and the filename should be key.txt. Now first create the key.txt.
* **Hint 3:** Then when you try to commit it, you will see that no file is updated as .gitignore is removing all txt files. So add something forcefully so that commit can ignore the restriction of .gitignore and can add your file.
* **Hint 4:** You can get a message to add your username and email. Just follow exact command and add whatever username and random email to just continue the process. Then after committing the change and confirming from the commit output, Push the file. Then you will get the password of bandit32.
 
## 🚶‍♂️ Step-by-Step Methodology
1. **[Step 1 Action]:** Clone the folder using git.
2. **[Step 2 Action]:** Go to the repo directory and create the key.txt.
3. **[Step 3 Action]:** Then add the file to commit using git add. Add the flag -f to forcefully add it as else, it will be ignored by .gitignore.
4. **[Step 4 Action]:** Then commit it using git commit with a message with -m flag. [Add those username and email if it asks before committing.]
5. **[Step 5 Action]:** Then push the repo using git push and with the password of bandit31 and the system will verify the file and will give the pass.

N.B.: If you do this using Powershell, as powershell creates file using UTF-16 it will be rejected by the system which will check the file that you are pushing. So either change the file's content into UTF-8 or di this form any Linux distribution to avoid this problem.

## 🧠 Key Takeaway
Throughout this level you are introduced how to add commit and push a file using git. The important thing to understand here is .gitignore only prevents normal git add from tracking a file; git add -f overrides that rule.

---

## ⚠️ Solution (Spoiler Warning!)

<details>
<summary><b>🚨 Click here only if you are completely stuck and need the exact commands! 🚨</b></summary>

<br>

**Exact Commands:**
```bash

# Execute the solution
1. git clone ssh://bandit31-git@bandit.labs.overthewire.org:2220/home/bandit31-git/repo
2. cd repo
3. echo "May I come in?" > key.txt
4. git add -f key.txt
5. git commit -m "Key added"
6. git push

# 🚩 Bandit Level 29 → Level 30

## 🎯 Objective
There is a git repository at ssh://bandit29-git@bandit.labs.overthewire.org/home/bandit29-git/repo via the port 2220. The password for the user bandit29-git is the same as for the user bandit29.

From your local machine (not the OverTheWire machine!), clone the repository and find the password for the next level. This needs git installed locally on your machine.

---

## 📚 Concepts & Prerequisites
Before attempting this level, you should understand how to use the following commands and concepts. 

**Recommended Research (man pages are your friend! and also the helpful resources in Bandit Level):**
* `git` - Git is a distributed version control system used to track changes in files and manage the history of a project. It allows developers to save changes as commits, work with branches, and collaborate through remote repositories.
Some common commands are git init (create a repository), git clone (copy a remote repository), git status (check changes),git branch (to see availabe branches), git switch branch_name (to swith to that specific branch instead of HEAD branch), git add (stage changes), git commit (save changes), git log (view commit history), git show (inspect a commit using the hash that has been generated over a specific log data), git branch (manage branches), git pull (download changes), and git push (upload changes).
The Git from the Bottom Up is the excellent resource to learn Git which is already provided in Bandit Level Resources.
  
## 💡 Progressive Hints
Try to solve the level after reading each hint before moving on to the next one!

* **Hint 1:** First understand how the question really want to find the password of the next level. Here you dont need to ssh into any remote server. Rather than you need to clone remote directory and the link is given in the question
* **Hint 2:** Then after cloning it in your local system, you will find that it is saying "No password in production" and in this case if you go through the log of that directory there's nothing to find. But you should know that there may be more than one repository to search for the password as maybe the password can be in other than current directory.
* **Hint 3:** Then use commands of git to find out what branches are there. Then switch go through each branch until you find the password of bandit30.
 
## 🚶‍♂️ Step-by-Step Methodology
1. **[Step 1 Action]:** Clone the folder using git.
2. **[Step 2 Action]:** Go to the repo directory and get the list of branches using git branch
3. **[Step 3 Action]:** Switch to dev branch and see the README file for password


## 🧠 Key Takeaway
Throughout this level you are introduced with one of the most popular and very useful command git and how it's functionality helps to retrieve data from remote repositories. Specifically this level is teaching you that secrets may be hidden in Git branches, not necessarily in the current branch.

---

## ⚠️ Solution (Spoiler Warning!)

<details>
<summary><b>🚨 Click here only if you are completely stuck and need the exact commands! 🚨</b></summary>

<br>

**Exact Commands:**
```bash

# Execute the solution
1. git clone ssh://bandit29-git@bandit.labs.overthewire.org:2220/home/bandit29-git/repo
2. cd repo
3. git branch -a
4. git switch dev
5. cat README

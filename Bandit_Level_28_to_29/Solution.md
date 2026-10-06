# 🚩 Bandit Level 28 → Level 29

## 🎯 Objective
There is a git repository at ssh://bandit28-git@bandit.labs.overthewire.org/home/bandit28-git/repo via the port 2220. The password for the user bandit28-git is the same as for the user bandit28.

From your local machine (not the OverTheWire machine!), clone the repository and find the password for the next level. This needs git installed locally on your machine.

---

## 📚 Concepts & Prerequisites
Before attempting this level, you should understand how to use the following commands and concepts. 

**Recommended Research (man pages are your friend! and also the helpful resources in Bandit Level):**
* `git` - Git is a distributed version control system used to track changes in files and manage the history of a project. It allows developers to save changes as commits, work with branches, and collaborate through remote repositories.
Some common commands are git init (create a repository), git clone (copy a remote repository), git status (check changes), git add (stage changes), git commit (save changes), git log (view commit history), git show (inspect a commit using the hash that has been generated over a specific log data), git branch (manage branches), git pull (download changes), and git push (upload changes).
The Git from the Bottom Up is the excellent resource to learn Git which is already provided in Bandit Level Resources.
  
## 💡 Progressive Hints
Try to solve the level after reading each hint before moving on to the next one!

* **Hint 1:** First understand how the question really want to find the password of the next level. Here you dont need to ssh into any remote server. Rather than you need to clone remote directory and the link is given in the question
* **Hint 2:** Then after cloning it in your local system, you will find that password is censored. But you should know that there's a possibility that the password may be pushed in past and git never really omits any changes, it just creates a branch to the next commit.
* **Hint 3:** Then see the log to find the history or the hash that has been changed later to fix some leak.
* **Hint 4:** Use the hash before the leak to see the log of the previous data before final latest commit.
 
## 🚶‍♂️ Step-by-Step Methodology
1. **[Step 1 Action]:** Clone the folder using git.
2. **[Step 2 Action]:** Go to the repo directory and see the log file of the repo directory using git log.
3. **[Step 3 Action]:** Find the log hash which is just before the leak fix and use that hash to see the content using git show.


## 🧠 Key Takeaway
Throughout this level you are introduced with one of the most popular and very useful command git and how it's functionality helps to retrieve data from remote repositories. Specifically in this level you will understand that any commit that has been done over git is always stays as a past data or history and can be retrieved using hash through log history. So one must always be careful before pushing something as that can cause some serious security problems.

---

## ⚠️ Solution (Spoiler Warning!)

<details>
<summary><b>🚨 Click here only if you are completely stuck and need the exact commands! 🚨</b></summary>

<br>

**Exact Commands:**
```bash

# Execute the solution
1. git clone ssh://bandit28-git@bandit.labs.overthewire.org:2220/home/bandit28-git/repo
2. cd repo
3. git log
4. git show ad8a5f812f24e793d2657f926f503a2fd1c5e256
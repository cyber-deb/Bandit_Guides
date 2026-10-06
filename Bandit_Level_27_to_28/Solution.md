# 🚩 Bandit Level 27 → Level 28

## 🎯 Objective
There is a git repository at ssh://bandit27-git@bandit.labs.overthewire.org/home/bandit27-git/repo via the port 2220. The password for the user bandit27-git is the same as for the user bandit27.

From your local machine (not the OverTheWire machine!), clone the repository and find the password for the next level. This needs git installed locally on your machine.

---

## 📚 Concepts & Prerequisites
Before attempting this level, you should understand how to use the following commands and concepts. 

**Recommended Research (man pages are your friend! and also the helpful resources in Bandit Level):**
* `git` - Git is a distributed version control system used to track changes in files and manage the history of a project. It allows developers to save changes as commits, work with branches, and collaborate through remote repositories.
Some common commands are git init (create a repository), git clone (copy a remote repository), git status (check changes), git add (stage changes), git commit (save changes), git log (view commit history), git show (inspect a commit), git branch (manage branches), git pull (download changes), and git push (upload changes).
The Git from the Bottom Up is the excellent resource to learn Git which is already provided in Bandit Level Resources.
  
## 💡 Progressive Hints
Try to solve the level after reading each hint before moving on to the next one!

* **Hint 1:** First understand how the question really want to find the password of the next level. Here you dont need to ssh into any remote server. Rather than you need to clone remote directory and the link is given in the question
* **Hint 2:** Then after cloning it in your local system, find the content inside of the cloned folder to find out the password of the next level.
 
## 🚶‍♂️ Step-by-Step Methodology
1. **[Step 1 Action]:** Clone the folder using git.
2. **[Step 2 Action]:** Read the README file.


## 🧠 Key Takeaway
Throughout this level you are introduced with one of the most popular and very useful command git and how it's functionality helps to retrieve data from remote repositories. In later level you will see there are many things that make git more efficient in one way but vulnerable in another.

---

## ⚠️ Solution (Spoiler Warning!)

<details>
<summary><b>🚨 Click here only if you are completely stuck and need the exact commands! 🚨</b></summary>

<br>

**Exact Commands:**
```bash

# Execute the solution
1. git clone ssh://bandit27-git@bandit.labs.overthewire.org:2220/home/bandit27-git/repo
2. cat repo/README

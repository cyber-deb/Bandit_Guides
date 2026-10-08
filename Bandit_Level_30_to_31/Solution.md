# 🚩 Bandit Level 30 → Level 31

## 🎯 Objective
There is a git repository at ssh://bandit30-git@bandit.labs.overthewire.org/home/bandit30-git/repo via the port 2220. The password for the user bandit30-git is the same as for the user bandit30.

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
* **Hint 2:** Then after cloning it in your local system, you will find that wither you go through log or branch there's nothing to get password from and the main file obviously doesn't contain the pass. So now you need to remember that git has another object other than repository of file, it's tag.
* **Hint 3:** Then use commands of git to find out which tags are there. Then show the available tag to get the password of bandit31.
 
## 🚶‍♂️ Step-by-Step Methodology
1. **[Step 1 Action]:** Clone the folder using git.
2. **[Step 2 Action]:** Go to the repo directory and get the list of tags using git tag 
3. **[Step 3 Action]:** Then show the available tag using git show tagname.


## 🧠 Key Takeaway
Throughout this level you are introduced that Git tag is a named reference to a specific Git object/commit. Even if the password isn't visible in the current working tree, it can still be stored in an object referenced by a tag.

---

## ⚠️ Solution (Spoiler Warning!)

<details>
<summary><b>🚨 Click here only if you are completely stuck and need the exact commands! 🚨</b></summary>

<br>

**Exact Commands:**
```bash

# Execute the solution
1. git clone ssh://bandit30-git@bandit.labs.overthewire.org:2220/home/bandit30-git/repo
2. cd repo
3. git tag
4. git show secret
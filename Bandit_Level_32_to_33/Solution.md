# 🚩 Bandit Level 32 → Level 33

## 🎯 Objective
After all this git stuff, it’s time for another escape. Good luck!

---

## 📚 Concepts & Prerequisites
Before attempting this level, you should understand how to use the following commands and concepts. 

**Recommended Research (man pages are your friend! and also the helpful resources in Bandit Level):**
* `$0` - $0 is a shell parameter that refers to the name of the shell/script being executed.

## 💡 Progressive Hints
Try to solve the level after reading each hint before moving on to the next one!

* **Hint 1:** First understand how the question really want to find the password of the next level. Here the shell is currently an UPPERCASE wrapper in a shell and if you try to use any command, the shell will change it into uppercase character and as Linux terminal commands are case-sensitive, the commands will not work. So you have to do something that, if executed in this shell cannot be transformed into UPPERCASE.  
* **Hint 2:** Not there is a command or I can say a shell parameter $0 that effectively means currently executing shell i.e. the shell through which the UPPERCASE wrapper is executing. Running  $0 will bring your terminal back to that shell outside of any extra wrapper and one can executes command as usual. 
 
## 🚶‍♂️ Step-by-Step Methodology
1. **[Step 1 Action]:** ssh into the level.
2. **[Step 2 Action]:** Run $0
3. **[Step 3 Action]:** Then cat the bandit_pass file of bandit33. Location: /etc/bandit_pass/bandit33.

## 🧠 Key Takeaway
The main lesson is understanding how a shell works and looking for ways to bypass restrictions.
The uppercase shell modifies your commands by converting them to uppercase, but shell variables/parameters aren't affected the same way. $0 refers to the currently executing shell, so executing $0 lets you escape the restricted wrapper and return to a normal shell.

---

## ⚠️ Solution (Spoiler Warning!)

<details>
<summary><b>🚨 Click here only if you are completely stuck and need the exact commands! 🚨</b></summary>

<br>

**Exact Commands:**
```bash

# Execute the solution
1. ssh bandit32@bandit.labs.overthewire.org -p 2220
2. $0
3. cat /etc/bandit_pass/bandit33

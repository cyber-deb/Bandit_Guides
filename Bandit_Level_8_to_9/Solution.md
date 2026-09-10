# 🚩 Bandit Level 8 → Level 9

## 🎯 Objective
The password for the next level is stored in the file data.txt and is the only line of text that occurs only once
---

## 📚 Concepts & Prerequisites
Before attempting this level, you should understand how to use the following commands and concepts. 

**Recommended Research (man pages are your friend! and also the helpful resources in Bandit Level):**
* `ls` - ls command list down every files and directories available in a specific path. In general it lists down everything inside current directory (excluding hidden ones). But one can specify a selected path by ls [path] to configure selected path. There are many options to attach with ls such as ls -a (List down hidden files and folders), ls -l (List down files with file permission).
* `ssh` - ssh stands for secure shell. It helps us to connect a remote server over private key or password and access the contents of that server.
* `sort` - As the name suggest, sort command is used to sort contents of a file in an order. Generally it sorts according to the first letter of a line. But you can use -n flag to sort numerical value in increasing order. You can use -u to remove duplicates, means it includes both unique and duplicate but each one time only. Basic Syntax: sort [option] filename. For more info you can visit man page of sort.
* `uniq` - It's a special command used with sort to filter out various result. As name suggests, uniq is piped with sort to remove duplicates and show unique elem. However with -d flag, you can particularly show duplicate lines of that file or with -u flag you can see the unique lines in a file.
* `|` - This is piping. It means to pipe result or output of one output into another one. Basic Structure: command1 | command2. So it will give the output of command1 to command2 to work on. For more info visit the link provided by Bandit OTW in problem page.

## 💡 Progressive Hints
Try to solve the level after reading each hint before moving on to the next one!

* **Hint 1:** First understand what the question really want to extract data or what information is given so on that basis you can use your command
* **Hint 2:** Then use sort command along with uniq with proper flags to extract what u really need

---

## 🚶‍♂️ Step-by-Step Methodology
1. **[Step 1 Action]:** Using ssh command first log in into bandit1 where the - file exists. 
2. **[Step 2 Action]:** Use sort command and then pipe that into uniq command with -u  flag


## 🧠 Key Takeaway
Throughout this level you can learn how to use sort command and also uniq command. But mostly what you will specifically learn is how piping works which is very important to know for long term investment in Linux.
---

## ⚠️ Solution (Spoiler Warning!)

<details>
<summary><b>🚨 Click here only if you are completely stuck and need the exact commands! 🚨</b></summary>

<br>

**Exact Commands:**
```bash
# Connect to the server
ssh bandit8@bandit.labs.overthewire.org -p 2220

# Execute the solution
1. sort data.txt | uniq -u

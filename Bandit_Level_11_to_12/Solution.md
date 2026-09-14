# 🚩 Bandit Level 11 → Level 12

## 🎯 Objective
The password for the next level is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions
---

## 📚 Concepts & Prerequisites
Before attempting this level, you should understand how to use the following commands and concepts. 

**Recommended Research (man pages are your friend! and also the helpful resources in Bandit Level):**
* `ls` - ls command list down every files and directories available in a specific path. In general it lists down everything inside current directory (excluding hidden ones). But one can specify a selected path by ls [path] to configure selected path. There are many options to attach with ls such as ls -a (List down hidden files and folders), ls -l (List down files with file permission).
* `ssh` - ssh stands for secure shell. It helps us to connect a remote server over private key or password and access the contents of that server.
* `tr` - Full form Translate. It is typically used to translate text from one format into another. It not only translates but also helps to squeeze or delete specific text from the text. Basic syntax: tr [old pattern] [new pattern] or tr [option] [pattern] (for delete or squeeze or to select specific items from text). N.B. if tr finds nothing to translate from the given text, it will just show the [new pattern] exact as it is in output. Eg. echo "hello" | tr "abc" "xyz" -> it will return xyz. Also to write a series of pattern you can use "A-Z" and also can add other patterns together as "A-Za-z" as it maps your list with new pattern. Some common options are -d to delete specific letters, -s to squeeze, -cd to only show selected text from the pattern.
* `Rot13` - It's not a command its just a swapping technique to swap alphabets by their 13th position i.e. it will change the letter A with N (Pos. of A + 13 Pos = Pos. of N). Go through the Rot13 Wikipedia to learn more about it.

## 💡 Progressive Hints
Try to solve the level after reading each hint before moving on to the next one!

* **Hint 1:** First understand what the question really want to extract data or what information is given so on that basis you can use your command.
* **Hint 2:** Then understand how you can use the contents of data.txt to change its all character by its succeeding 13th character. 

---

## 🚶‍♂️ Step-by-Step Methodology
1. **[Step 1 Action]:** Using ssh command first log in into bandit11. 
2. **[Step 2 Action]:** Use cat to show the output and pipe it into tr command with proper pattern to translate the contents accordingly.


## 🧠 Key Takeaway
Throughout this level you can learn how to use tr to translate or change the content of any text file accordingly using a specific pattern.
---

## ⚠️ Solution (Spoiler Warning!)

<details>
<summary><b>🚨 Click here only if you are completely stuck and need the exact commands! 🚨</b></summary>

<br>

**Exact Commands:**
```bash
# Connect to the server
ssh bandit11@bandit.labs.overthewire.org -p 2220

# Execute the solution
1. cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'

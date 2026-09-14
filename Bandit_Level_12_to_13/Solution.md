# 🚩 Bandit Level 12 → Level 13

## 🎯 Objective
The password for the next level is stored in the file data.txt, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work. Use mkdir with a hard to guess directory name. Or better, use the command “mktemp -d”. Then copy the datafile using cp, and rename it using mv (read the manpages!)
---

## 📚 Concepts & Prerequisites
Before attempting this level, you should understand how to use the following commands and concepts. 

**Recommended Research (man pages are your friend! and also the helpful resources in Bandit Level):**
* `ls` - ls command list down every files and directories available in a specific path. In general it lists down everything inside current directory (excluding hidden ones). But one can specify a selected path by ls [path] to configure selected path. There are many options to attach with ls such as ls -a (List down hidden files and folders), ls -l (List down files with file permission).
* `ssh` - ssh stands for secure shell. It helps us to connect a remote server over private key or password and access the contents of that server.
* `mkdir` - Create directory. If used without Path, it will create directory in current working directory. But with path, it will create in destination directory.
* `cp` - copy a file or folder from one location to another location. Basic syntax: cp [old_location/filename] [new location]
* `mv` - permanently move a file from one directory to another. Basic syntax: mv [old_location/filename] [new_location]. If mv is used within same directory, it can be used to rename a file or directory as it overwrites the name if the content already exists.
* `tar` - Tar stands for Tape Archiee. It doesn't compress main files but it just store many file in one single location. Basic Syntax: tar [option] file1 file2. Some options include -f to use same filename as tape archive, -c to create a tar or -x to extract the tar and -t to show the list of files inside of a tar.
* `gzip` - gzip stands for GNU Zip. It's an compression method. Basic syntax: gzip [option] filenames. Extension of gzip is .gz and to extract a gzip, Either one need to use gzip -d file or gunzip file. Other options include -k to keep the original file as it is while compression, -l to list all files inside of a gzip, -r to compress everything inside of a folder.
* `bzip2` - bzip2 or one can say block zip, also an compression method. Basic syntax: bzip2 [options] filenames. Extension: .bz2 . To decompress something, one can either use bzip2 -d file.bz or bunzip2 file.bz. Other options are as same as of gzip.
* `xxd` - xxd helps us to change a ASCII file to hexadecimal format. Basic syntax: xxd [options] filename.txt. To get the ASCII from a hex dump, we can use -r as xxd -r dump.txt > original as it will store the binary file in the original file. Other option include -p to product plain hex dump without offset and ASCII preview. Go through Hax Dump on Wikipedia to learn more. 

## 💡 Progressive Hints
Try to solve the level after reading each hint before moving on to the next one!

* **Hint 1:** First understand what the question really want to extract data or what information is given so on that basis you can use your command.
* **Hint 2:** Then understand where to take the file to perform the operation so create directory accordingly and copy the file there.
* **Hint 3:** Then understand how are you able to learn what type of file is this currently (first one is Hex Dump, use cat to see that) and change the extension accordingly before doing any further action.
* **Hint 4:** Then continue it until you get a ASCII file, that's your password file.

---

## 🚶‍♂️ Step-by-Step Methodology
1. **[Step 1 Action]:** Using ssh command first log in into bandit1 where the - file exists. 
2. **[Step 2 Action]:** Use mkdir create a new drectory in tmp and copy the file there using cp
3. **[Step 3 Action]:** Then use file to know the type of file data.txt is and change the extension using rename feature of mv.
4. **[Step 3 Action]:** Then use gunzip, bunzip, tar -xf or xxd -r accordingly till you get an ASCII file and theat's your password


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
ssh bandit12@bandit.labs.overthewire.org -p 2220

# Execute the solution
1. mkdir /tmp/abc
2. cp data.txt /tmp/abc/
3. cd /tmp/abc/
4. xxd -r data.txt > original
5. file original
6. mv original original.gz
7. gunzip original.gz
8. file original
9. mv original original.bz2
10. bunzip original.bz2
.
.
.
.
.
.
idk: cat original

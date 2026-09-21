# 🚩 Bandit Level 20 → Level 21

## 🎯 Objective
There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

NOTE: Try connecting to your own network daemon to see if it works as you think

---

## 📚 Concepts & Prerequisites
Before attempting this level, you should understand how to use the following commands and concepts. 

**Recommended Research (man pages are your friend! and also the helpful resources in Bandit Level):**
* `ssh` - ssh stands for secure shell. It helps us to connect a remote server over private key or password and access the contents of that server. Syntax: ssh 
[option value] username@hostname. Various options included -p to specify port number, -i to specify private key etc. Type quit to exit a ssh session. 
* `setuid` - SetUID (Set User ID) is a Linux file permission that makes a program run with the permissions of the file's owner, rather than the user who executes it. Suppose, a file, which can be run by only root has a setuid (-rwsrw-r--). But for the setuid, the specific command can be run as a user and it will act as if that permitted user is running the command. For more info, check out the content provided by Bandit.
* `tmux` - tmux (Terminal Multiplexer) is a command that helps to run multiple terminal session inside one single terminal window. It helps to connect something from where it is disconnected and keeps on running. To start tmux just type tmux. To create a named session: tmux new -s [session name]. Now inside tmux, to create new Window, use Ctrl+B then c, to go next window Ctrl+b the n for previous p, to rename r, to list windows , , to split panes vertically %, horizontally " , to move between panes -> keys.
* `nc` - Full from of netcat. It helps to connect to a remote server and can interchange info accordingly. Basic syntax: nc [option] HOST PORT. There are few options including -l for listen mode, -u for UDP mode (generally nc works on TCP mode), -z to scan the network, -w to wait before terminating connection etc. Other similar tools are ncat (upgraded version of nc with more option such as --read-only,  --send-only), telnet (very popular to connect over tcp), socat (to connect with any protocol to any protocol) etc. 

## 💡 Progressive Hints
Try to solve the level after reading each hint before moving on to the next one!

* **Hint 1:** First understand how the question really want to find the password of the next level. The setuid will run a connection with a port which you are currently listening into and according to your reply with correct password, the setuid will send the pass of next level through the listening command running.
* **Hint 2:** In this case, you basically need to run two terminal session from one terminal. Look for the command which helps you to run multiple terminal session into a single terminal. One terminal will learn the listening and other terminal will run the setuid executable on the same port.
* **Hint 3:** Then paste the bandit20 password in the listening terminal and you will get the pass of bandit21 in return.
 
## 🚶‍♂️ Step-by-Step Methodology
1. **[Step 1 Action]:** Log into bandit20
2. **[Step 2 Action]:** Then run tmux and press Ctrl+B with % to open two split window vertically. Traverse between two terminal sessions using Ctrl+B with Arrow keys (-> or <-).
3. **[Step 3 Action]:** Then run nc on listening on a specific port.
4. **[Step 4 Action]:** Then run the suconnect in another session with the port number your nc is listening into.
5. **[Step 5 Action]:** Then paste the password of bandit20 in nc listening session and hit Enter and you will get the password for next level.

## 🧠 Key Takeaway
Throughout this level you can learn how to run multiple sessions within a single terminal session using tmux.

---

## ⚠️ Solution (Spoiler Warning!)

<details>
<summary><b>🚨 Click here only if you are completely stuck and need the exact commands! 🚨</b></summary>

<br>

**Exact Commands:**
```bash

# Execute the solution
1. ssh bandit20@bandit.labs.overthewire.org -p 2220
2. ls -l ./suconnect  #jsut to check whether its setuid or not
3. tmux
4. # Ctrl+B then % to open two vertical window
5. nc -l 1234
6. # Ctrl+B then <- or -> (arrow keys) to go to the next terminal.
7. ./suconnect 1234
8. # Ctrl+B then <- or -> (arrow keys) to go to the next terminal.
9. [paste the password of bandit20]

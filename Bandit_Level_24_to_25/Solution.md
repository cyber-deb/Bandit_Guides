# 🚩 Bandit Level 24 → Level 25

## 🎯 Objective
A daemon is listening on port 30002 and will give you the password for bandit25 if given the password for bandit24 and a secret numeric 4-digit pincode. There is no way to retrieve the pincode except by going through all of the 10000 combinations, called brute-forcing.
You do not need to create new connections each time

---

## 📚 Concepts & Prerequisites
Before attempting this level, you should understand how to use the following commands and concepts. 

**Recommended Research (man pages are your friend! and also the helpful resources in Bandit Level):**
* `ssh` - ssh stands for secure shell. It helps us to connect a remote server over private key or password and access the contents of that server. Syntax: ssh 
[option value] username@hostname. Various options included -p to specify port number, -i to specify private key etc. Type quit to exit a ssh session. 
* `nc` - Full from of netcat. It helps to connect to a remote server and can interchange info accordingly. Basic syntax: nc [option] HOST PORT. There are few options including -l for listen mode, -u for UDP mode (generally nc works on TCP mode), -z to scan the network, -w to wait before terminating connection etc. Other similar tools are ncat (upgraded version of nc with more option such as --read-only, --send-only), telnet (very popular to connect over tcp), socat (to connect with any protocol to any protocol) etc.
* `bash` - Bash is a command-line shell used to interact with Linux/Unix systems. It also allows you to write scripts to automate tasks and run commands. To learn more about bash go through You Suck At Programming's video (https://www.youtube.com/watch?v=Sx9zG7wa4FA). For this level, remember this, Every scripting language starts with a shebang and for bash, it is #! and next the /bin/bash which specifies which scripting language should be used to execute this file as there are multiple shells like bash such as FISH or zsh etc. [in altogether, the first line is #!/bin/bash]. In this specific level, you need to know how to use for loop. [for loops starts with
  for [variable_name] in {start_range..end_range}; do
     <content to repeat>
   done]
 where the start_range is from where you want to start the iteration and stop_range is where to close the iteration. And to implement the variable in anywhere you have to use the variable name with a $ sign at the beginning so that the bash can understand that that is calling the value of the variable.
  
## 💡 Progressive Hints
Try to solve the level after reading each hint before moving on to the next one!

* **Hint 1:** First understand how the question really want to find the password of the next level. First just run netcat on that port with <bandit_24_pass><space><random_4_digits> to see what the listeners returns.
* **Hint 2:** Then you need to understand that you have to use a script to automate the process of choosing the 4 digit numbers in a sequence. 
* **Hint 3:** Then you have to run a loop in your script which will echo the password with the 4 digit value together and at the end of the loop you have to pipe it into the netcat as from hint 1 you will understand that the listener will only close when correct password will be given. 
* **Hint 4:** Then run it after giving execution permission.
 
## 🚶‍♂️ Step-by-Step Methodology
1. **[Step 1 Action]:** Log into bandit24
2. **[Step 2 Action]:** Then create a bash script in /tmp directory e.g. pass.sh
3. **[Step 3 Action]:** Then write a for loop which will dump the passowrd along with the 4 digit value together and then pipe the output into netcat which will listen on port 30002
4. **[Step 4 Action]:** Then give it execution permission and then run it and you will get the password of bandit 25. 

## 🧠 Key Takeaway
Throughout this level you can learn how to write an actual bash script and will understand how a script really helps to solve a complex problem. Specifically one can learn how to use for loop and can use that to solve real world scenario like vulnerability.

---

## ⚠️ Solution (Spoiler Warning!)

<details>
<summary><b>🚨 Click here only if you are completely stuck and need the exact commands! 🚨</b></summary>

<br>

**Exact Commands:**
```bash

# Execute the solution
1. ssh bandit24@bandit.labs.overthewire.org -p 2220
2. nano /tmp/pass.sh
Inside pass.sh
#!/bin/bash
for i in {0000..9999}; do
  echo "hVQMk3lJNsmQ7VF3ubyrNNBom7BOgVXv $i"
done | nc localhost 30002
3.chmod +x /tmp/pass.sh
4../tmp/pass.sh

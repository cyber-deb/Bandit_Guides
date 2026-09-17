# 🐧 Bandit Guide

### A hands-on Linux & Cybersecurity learning journey through OverTheWire Bandit

<p align="center">
  <img src="https://img.shields.io/badge/Linux-Learning-FCC624?style=for-the-badge&logo=linux&logoColor=black" alt="Linux">
  <img src="https://img.shields.io/badge/Cybersecurity-Learning-00A67E?style=for-the-badge&logo=hackthebox&logoColor=white" alt="Cybersecurity">
  <img src="https://img.shields.io/badge/OverTheWire-Bandit-000000?style=for-the-badge" alt="OverTheWire">
  <img src="https://img.shields.io/github/stars/cyber-deb/Bandit_Guide?style=for-the-badge" alt="GitHub Stars">
</p>

<p align="center">
  <b>Learn Linux by solving problems. Learn cybersecurity by understanding why they work.</b>
</p>

---

## 📖 About This Repository

This repository contains my **write-ups and learning notes for the Bandit wargame by OverTheWire**.

Bandit is one of the best starting points for developing practical Linux and cybersecurity skills. Instead of simply documenting the final answers, this repository focuses on **understanding the process behind each solution**.

For every level, the goal is to explain:

* 🎯 What the level is actually asking
* 🧠 What concept you need to understand
* 💡 Useful hints without immediately giving everything away
* 🔍 How to investigate the environment
* 💻 Commands and techniques used
* 🪜 A step-by-step approach to solving the level
* 📚 What you should learn from the challenge
* 🔐 The final password is **not intentionally published**

> **The purpose of this repository is to teach the process, not to provide a password dump.**

---

## 🏴 What is OverTheWire Bandit?

[OverTheWire](https://overthewire.org/) provides several wargames designed to help people learn and practice cybersecurity concepts in an interactive environment.

**Bandit** is specifically aimed at beginners and focuses heavily on:

* Linux fundamentals
* Shell usage
* File manipulation
* Permissions
* SSH
* Networking
* Processes
* Text processing
* Encoding
* Compression
* Git
* Basic scripting
* And much more

You can play Bandit yourself here:

👉 **[OverTheWire Bandit](https://overthewire.org/wargames/bandit/)**

---

# 🎯 Repository Philosophy

This project follows a simple principle:

> **Don't memorize the command. Understand why the command works.**

For example, instead of simply saying:

```bash
cat file.txt
```

the write-up should explain:

> Why are we using `cat` here?
> What does `cat` actually do?
> Why is this file accessible?
> Is there another way to solve the problem?

That approach makes the guide useful beyond Bandit.

The commands learned here can later become useful when working with:

* 🐧 Linux systems
* 🌐 Web servers
* 🔐 Penetration testing
* 🛡️ SOC environments
* 🧪 CTF competitions
* 🐚 Bash scripting
* ☁️ Cloud environments
* 🐳 Containers
* ⚙️ System administration

---

# 🗂️ Repository Structure

Each Bandit level has its own directory containing a dedicated write-up.

```text
Bandit_Guide/
│
├── Bandit_Level_0_to_1/
│   └── Solution.md
│
├── Bandit_Level_1_to_2/
│   └── Solution.md
│
├── Bandit_Level_2_to_3/
│   └── Solution.md
│
├── Bandit_Level_3_to_4/
│   └── Solution.md
│
├── ...
│
└── README.md
```

Each `Solution.md` follows a consistent structure so that readers can easily navigate between levels.

---

# 🧩 What Every Write-up Contains

Every level is documented using a structured approach.

### 1️⃣ Objective

What is the challenge asking you to accomplish?

### 2️⃣ Concept

What Linux, networking, security, or programming concept is involved?

### 3️⃣ Hints

Useful clues to help you solve the challenge yourself.

### 5️⃣ Commands

The relevant Linux commands and their purpose.

### 6️⃣ Step-by-Step Solution

A detailed explanation of the reasoning process.

### 7️⃣ Command Breakdown

Instead of blindly copying commands, each important command is explained.

### 8️⃣ What You Learned

The key takeaway from completing the level.

---

# 🔐 Why Passwords Aren't Published

You may notice that the final passwords are intentionally excluded from the repository.

There is a reason for that.

The objective of Bandit is **learning by doing**.

If the password is directly available, a learner can simply copy it and move to the next level without understanding the underlying concept.

This repository therefore focuses on:

> **Objective → Investigation → Reasoning → Commands → Solution**

rather than:

> **Question → Password**

If you are stuck, the write-ups are designed to give you enough information to understand the problem and continue solving it yourself.

---

# 👀 Hidden Solutions & Commands

Some parts of the write-ups may contain commands or solution details that are hidden initially.

They can be revealed by clicking the expandable section.

For example:

<details>
<summary>💻 Click to reveal the command</summary>

```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
```

</details>

This keeps the write-ups readable while still allowing readers to reveal the exact command when they need it.

The same approach may be used for:

* Commands
* Important output
* Solution hints
* Code snippets
* Advanced explanations

---

# 🛠️ Skills Covered

As the levels progress, the guide covers a wide range of practical concepts.

| Category           | Topics                                     |
| ------------------ | ------------------------------------------ |
| 🐧 Linux           | Files, directories, permissions, processes |
| 🐚 Shell           | Bash commands, pipes, redirection          |
| 🔎 Searching       | `find`, `grep`, `sort`, `uniq`             |
| 📄 Text Processing | `cut`, `strings`, `tr`, `sed`, `awk`       |
| 🔐 Permissions     | Ownership, permissions, SUID               |
| 🌐 Networking      | Ports, connections, services               |
| 🔑 SSH             | Authentication and remote access           |
| 🗜️ Compression    | `gzip`, `bzip2`, `tar`, archives           |
| 🔢 Encoding        | Base64 and other representations           |
| 🧬 Binary Data     | File signatures and binary inspection      |
| 🧠 Processes       | Process identification and management      |
| 🐙 Git             | Repositories, commits, branches, history   |
| 💻 Bash            | Shell concepts and scripting               |
| 🔍 Enumeration     | Investigating unknown environments         |

---

# 📈 Progress

My progress through the Bandit levels:

* [x] Level 0 → 1
* [x] Level 1 → 2
* [x] Level 2 → 3
* [x] Level 3 → 4
* [x] Level 4 → 5
* [x] Level 5 → 6
* [x] Level 6 → 7
* [x] Level 7 → 8
* [x] Level 8 → 9
* [x] Level 9 → 10
* [x] Level 10 → 11
* [x] Level 11 → 12
* [x] Level 12 → 13
* [x] Level 13 → 14
* [x] Level 14 → 15
* [x] Level 15 → 16
* [x] Level 16 → 17
* [ ] Level 17 → 18
* [ ] Level 18 → 19
* [ ] Level 19 → 20
* [ ] Level 20 → 21
* [ ] Level 21 → 22
* [ ] Level 22 → 23
* [ ] Level 23 → 24
* [ ] Level 24 → 25
* [ ] Level 25 → 26
* [ ] Level 26 → 27
* [ ] Level 27 → 28
* [ ] Level 28 → 29
* [ ] Level 29 → 30
* [ ] Level 30 → 31
* [ ] Level 31 → 32
* [ ] Level 32 → 33

> 🚧 **This repository is actively being updated. More write-ups will be added as I upload my writeups.**

---

# 🧪 Recommended Learning Method

If you're using this repository to learn, I recommend the following approach:

### 🥇 Step 1 — Try the level yourself

Read the official challenge description and attempt the level before opening the write-up.

### 🥈 Step 2 — Get a hint

If you're stuck, look at the **Hints** section rather than immediately reading the complete solution.

### 🥉 Step 3 — Understand the concept

Before copying a command, understand what it does.

### 🏆 Step 4 — Solve it yourself

Run the command manually and verify the result.

### 🔁 Step 5 — Reproduce the solution

Try solving the level again without looking at the write-up.

### 🧠 Step 6 — Keep the knowledge

Ask yourself:

> "Where could I use this technique outside Bandit?"

That's where the real learning happens.

---

# 💻 Useful Linux Commands

Some commands that repeatedly become useful throughout Bandit include:

```text
ls
cd
pwd
cat
file
find
grep
sort
uniq
strings
cut
tr
base64
tar
gzip
bzip2
chmod
chown
ps
ssh
scp
git
```

Don't just memorize them.

Learn:

* What they do
* Their common options
* How to combine them
* How input/output works
* How they behave in different situations

---

# 🧠 The Real Goal

Bandit isn't about collecting passwords.

It is about developing the ability to look at an unfamiliar Linux environment and think:

> **"I don't know what's happening yet. How can I investigate it?"**

That mindset is far more valuable than memorizing solutions.

The ultimate goal of this repository is therefore not just:

**Complete Bandit → Done**

but:

**Complete Bandit → Understand Linux → Build security fundamentals → Apply them to real security problems**

---

# 🤝 Contributing

This repository is primarily a personal learning project, but suggestions, corrections, and improvements are welcome.

If you notice:

* ❌ An incorrect command
* 🐛 An error in an explanation
* 💡 A better approach
* 📚 A missing concept
* ✍️ An unclear explanation

feel free to open an **Issue** or submit a **Pull Request**.

Constructive feedback is always appreciated.

---

# ⭐ Support the Project

If this repository helped you learn something useful, you can support it by:

⭐ **Starring the repository**

🍴 **Forking the repository**

💬 **Opening an issue with suggestions**

🔗 **Sharing it with someone learning Linux or cybersecurity**

Even a ⭐ helps the project reach more learners and motivates me to continue documenting the journey.

---

# 📚 Resources

### OverTheWire

👉 [OverTheWire](https://overthewire.org/)

### Bandit

👉 [OverTheWire Bandit](https://overthewire.org/wargames/bandit/)

### Linux Manual Pages

```bash
man <command>
```

Example:

```bash
man find
```

The best way to learn a command is often to read its documentation and then experiment with it yourself.

---

# 🚀 Future Plans

This repository will continue evolving as I progress.

Planned improvements include:

* [ ] Complete all Bandit levels
* [ ] Improve explanations
* [ ] Add command breakdowns
* [ ] Add Linux concept notes
* [ ] Add alternative solutions where useful
* [ ] Add common mistakes
* [ ] Add beginner-friendly explanations
* [ ] Improve navigation between levels
* [ ] Add additional cybersecurity learning resources

---

# 📌 Disclaimer

This repository is intended for **educational purposes**.

The write-ups are created to document my own learning process and help others understand the concepts involved in the Bandit wargame.

Please use the techniques learned here responsibly and only against systems you have permission to test.

---

## 🐧 Keep Learning. Keep Breaking. Keep Understanding.

> **"The goal isn't to know the answer.**
> **The goal is to know how to find the answer."**

⭐ If you find this guide useful, consider starring the repository and following the journey.

**Made while learning Linux & Cybersecurity, one Bandit level at a time.**

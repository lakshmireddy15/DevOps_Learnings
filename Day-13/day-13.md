
# Git and Shell Scripting Basics

---

## 🚫 Disadvantages of Manual Work

1. **Time-consuming**
2. **Tedious / Long Process**
3. **Human Errors**

> 🧠 Analogy:  
> Moving 100 logs manually from farm to home = slow and error-prone  
> Using a lorry = automation (fast, efficient)

---

## 💻 Programming Fundamentals

- **Variables**
- **Data Types**
- **Functions**
- **Conditions**
- **Loops**
- **Error Handling**

> 📌 Programming = 90% Design + 10% Coding

---

## 🐚 Shell vs 🐍 Python

### OS Architecture:
```
[UI] → [Shell] → [Kernel]  
[UI] → [Python] → [Shell] → [Kernel]
```

- **Shell** is native and best for automating Linux internal tasks.
- **Python** is best when working with external systems or APIs.

---

## 🔁 Version Control & Git

> We store source code in VCS / Source Code Management (SCM)  
> **Git** is a distributed version control system that tracks changes in code.

### Git Workflow:
```
Your Code (VS Code) 
    ↓
git add (Staging Area) 
    ↓
git commit (Local Repo) 
    ↓
git push (GitHub - Remote Repo)
```

---

## 🧠 VS Code Git Concepts

| Concept             | Tool / Location     | What It Does                          |
|---------------------|---------------------|----------------------------------------|
| Working Directory   | VS Code / folder    | Where you write code                   |
| Staging Area        | Git index           | Prepares selected changes for commit   |
| Local Repository    | `.git` folder       | Saves commit snapshots locally         |
| Remote Repository   | GitHub, GitLab, etc | Central shared repo for collaboration  |

---

### Git Areas:

```
Working Directory → Staging Area → Local Repository
 (unsaved changes)   (prepared)      (saved snapshots)
     |                  |                 |
  edit files      git add <file>   git commit -m "msg"
```

- **Staging Area** = your personal review zone before committing.
- **Commit** = a snapshot of your staged files stored locally.
- **Push** = send local commits to the remote repo (e.g., GitHub).
- **Pull** = bring remote changes to your local system.

---

## ❌ Problems of Keeping Code Only on Local Machine

- No backup → **security risk**
- Hard to share code with team
- No version history or collaboration

---

## 🧩 Centralized vs Distributed Version Control

### 1. Centralized VCS (e.g., SVN)
- One central repo for all developers
- Code history lives only on the server
- Devs push and pull from the central server
- Example: SVN

### 2. Distributed VCS (e.g., Git)
- Every developer has a full copy of the repo (local + history)
- You can work offline
- You only push to remote when ready

---

## ⚙️ Linux Shell Executables

Common shebangs:
```bash
#!/bin/bash
#!/bin/sh
#!/bin/dash
```

- **Shebang (`#!`)** must be the first line in shell scripts.
- It tells the OS which interpreter to use (bash, sh, etc).

On **Ubuntu**, `/bin/sh` is linked to `/bin/dash`.

---

## 🧪 Git Setup & Shell Script Execution

### ✅ GitHub Steps:
1. Create a new repo on GitHub

### ✅ Clone in Local Machine:
```bash
git clone https://github.com/lakshmireddy15/shell-practice.git
```

### ✅ Inside VS Code:
```bash
touch hello-world.sh         # Create file
git status                   # See untracked files
git add hello-world.sh       # Stage file
git commit -m "Hello World"  # Commit to local repo
git push origin main         # Push to GitHub
```

### 🧨 One-liner for all:
```bash
git add . ; git commit -m "message" ; git push origin main
```

---

## 🖥️ Run Shell Script on Linux (EC2):

1. Launch EC2 and connect using **MobaXterm**
2. Run:
```bash
git clone https://github.com/lakshmireddy15/shell-practice.git
cd shell-practice
git pull
sh hello-world.sh
```

---

## 🔣 Shell Scripting Components

- **Variables**
- **Data Types**
- **Conditions**
- **Loops**
- **Functions**
- **Error Handling**

---
 

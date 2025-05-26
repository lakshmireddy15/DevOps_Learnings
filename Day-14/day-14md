
# 🐚 Special Variables in Shell

Shell provides some **special predefined variables** that give information about the script’s execution, such as arguments passed, exit status, process IDs, etc. These are reserved and provided automatically — no need to define them manually.

## 📌 Common Special Variables

| Variable | Description |
|----------|-------------|
| `$0`     | 📝 Name of the script |
| `$1`, `$2`, ... `$n` | 📥 First to nth positional arguments |
| `$#`     | 🔢 Number of arguments passed to the script |
| `$@`     | 🗣️ All arguments passed (individually quoted) |
| `$*`     | 🧾 All arguments passed as a single word |
| `$$`     | 🔁 PID of the current shell |
| `$?`     | ❓ Exit status of the last executed command |
| `$!`     | 🧠 PID of the last background command |
| `$PWD`   | 📂 Present working directory |
| `$HOME`  | 🏠 Home directory of the user running the script |
| `$USER`  | 👤 Username of the user running the script |

---

# 🔁 IF-ELSE in Shell

```bash
if [ condition ]; then
    # ✅ commands for true condition
else
    # ❌ commands for false condition
fi
```

---

# 🔢 Integer Comparisons in Shell

| Operator | Meaning |
|----------|---------|
| `-eq`    | Equal to |
| `-ne`    | Not equal to |
| `-gt`    | Greater than |
| `-ge`    | Greater than or equal to |
| `-lt`    | Less than |
| `-le`    | Less than or equal to |

---

# 🛠️ MySQL Installation Script

**Objective:**
1. ✅ Check if the user has root access.
2. 📥 If yes, proceed with MySQL installation.
3. ❗ If not, show an error and stop the script.

## `install-command.sh`

```bash
#!/bin/bash

USERID=$(id -u)

if [ $USERID -ne 0 ]; then
    echo "Error:: Run this script with root access"
    exit 1
else
    echo "You are running with root access"
fi

dnf install mysql -y
```

---

## ❓ Why Use `exit`?

Shell scripts **do not stop automatically** on errors unless explicitly told to using `exit`. In the above example, without `exit`, the script continues to the installation step even if not run as root. Adding `exit 1` ensures that the script stops execution when root access is not present.

---

## ✅ Checking Exit Status

The exit status helps us know whether a command succeeded or failed.

```bash
echo hi
echo $?      # Outputs 0 (success)

unknowncommand
echo $?      # Outputs a non-zero number (e.g., 127 = command not found)
```

---

## 🔍 Manually Check MySQL Installation

```bash
dnf list installed mysql
```

Check exit status:

```bash
echo $?
```

- `0` → ✅ MySQL is installed
- Non-zero → ❌ Not installed or error occurred

---

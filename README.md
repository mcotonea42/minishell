# Minishell - As Beautiful as a Shell

![Language](https://img.shields.io/badge/Language-C-blue?style=for-the-badge&logo=c&logoColor=white)
![Bash](https://img.shields.io/badge/System-Bash_Like-4EAA25?style=for-the-badge&logo=gnu-bash&logoColor=white)
![42 School](https://img.shields.io/badge/School-42-000000?style=for-the-badge&logo=42&logoColor=white)
![Status](https://img.shields.io/badge/Grade-101%2F100-success?style=for-the-badge)

## 📝 Description

**Minishell** is a 42 School project aimed at creating a simple shell.
The goal is to understand the inner workings of a shell, specifically **process management** (`fork`, `execve`, `waitpid`), **file descriptors** (redirections, pipes), and **signal handling**.

## ✨ Features

### 🔹 Builtins
We re-implemented the following builtins from scratch:
* `echo` with `-n` option.
* `cd` with relative or absolute paths.
* `pwd` (Print Working Directory).
* `export` to manage environment variables.
* `unset` to remove environment variables.
* `env` to display the environment.
* `exit` to handle shell termination and status codes.

### 🔹 Shell Capabilities
* **Pipes (`|`)**: Connects the output of a command to the input of the next.
* **Redirections**:
    * `<` (Input)
    * `>` (Output - Truncate)
    * `>>` (Output - Append)
    * `<<` (Here-doc)
* **Environment Variables**: Expands variables like `$HOME` or `$?`.
* **Signals**: Handles `Ctrl-C`, `Ctrl-D`, and `Ctrl-\` appropriately (interactive vs non-interactive mode).

## 🛠️ Installation & Usage

### Prerequisites
You need `readline` library installed.

**Linux (Debian/Ubuntu):**
```bash
sudo apt install libreadline-dev
```

**MacOS:**
```bash
brew install readline

# Note: You might need to link readline in the Makefile if not found automatically:
# -I/opt/homebrew/opt/readline/include
# -L/opt/homebrew/opt/readline/lib
```

**Compile & Run:**

```bash
make && ./minishell
```

**Valgrind & Memory Leaks:**

A valgrind.supp file is provided to suppress false positives related to the readline library (which creates reachable leaks on some systems).

```bash
valgrind --suppressions=valgrind.supp ./minishell
```

**Testing:**

We used extensive testing suites to ensure robustness:

- MPANIC tester : (https://github.com/ChewyToast/mpanic)
- Minishell tester : (https://github.com/LucasKuhn/minishell_tester)

## Authors ✍️

This project was built by a duo:

* **COTONEA Melvin** - [Voir le profil GitHub](https://github.com/mcotonea42)
* **MILLIOT Marc** - [Voir le profil GitHub](https://github.com/NaYruk)
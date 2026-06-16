# Shell, Subshells, Command Substitution & Quoting

---

# 1. What is a Shell?

A **shell** is a command-line interpreter that acts as an interface between the user and the Linux kernel.

It allows you to:

* Run commands
* Launch programs
* Manage files and processes
* Automate tasks using scripts

## Linux Architecture

```text
User
 ↓
Shell (bash, zsh, sh, ...)
 ↓
Kernel
 ↓
Hardware
```

The shell interprets your commands and requests services from the kernel.

---

# 2. Types of Shells

| Shell | Full Name          | Features                            |
| ----- | ------------------ | ----------------------------------- |
| sh    | Bourne Shell       | Original UNIX shell                 |
| bash  | Bourne Again Shell | Most common Linux shell             |
| csh   | C Shell            | C-like syntax                       |
| ksh   | Korn Shell         | Advanced scripting                  |
| zsh   | Z Shell            | Powerful customization & completion |

---

# 3. Check Your Current Shell

```bash
echo $SHELL
```

Example:

```bash
/bin/bash
```

Current shell process:

```bash
ps -p $$
```

---

# 4. Useful Shell Variables

Current shell PID:

```bash
echo $$
```

Current Bash PID:

```bash
echo $BASHPID
```

Parent Process ID:

```bash
echo $PPID
```

Example:

```bash
echo "Shell PID : $$"
echo "Bash PID  : $BASHPID"
echo "Parent PID: $PPID"
```

---

# 5. What is a Subshell?

A **subshell** is a child shell process created by the current shell.

Characteristics:

* Runs as a separate process
* Inherits environment from parent
* Variable changes do NOT affect parent shell
* Directory changes do NOT affect parent shell
* Useful for isolation and temporary operations

---

# 6. Creating a Subshell

## Method 1: Parentheses ()

```bash
(
    echo "Inside subshell"
)
```

## Verify Using BASHPID

```bash
echo "Parent: $BASHPID"

(
    echo "Child : $BASHPID"
)
```

Example:

```text
Parent: 2145
Child : 2146
```

Different PID = different process.

---

# 7. Variable Scope in Subshells

```bash
VAR="Hello"

(
    VAR="World"
    echo "Inside: $VAR"
)

echo "Outside: $VAR"
```

Output:

```text
Inside: World
Outside: Hello
```

Changes inside the subshell do not affect the parent shell.

---

# 8. Directory Changes in Subshells

```bash
pwd

(
    cd /tmp
    pwd
)

pwd
```

Output:

```text
/home/user
/tmp
/home/user
```

The parent shell remains unchanged.

---

# 9. Export and Subshells

Parent → Child works.

Child → Parent does NOT work.

```bash
VAR="Linux"
export VAR

(
    echo "$VAR"
)
```

Output:

```text
Linux
```

The child receives exported variables.

However:

```bash
(
    export TEST="Hello"
)

echo "$TEST"
```

Output:

```text
```

A child process cannot modify the parent environment.

---

# 10. Subshell vs Current Shell

## Subshell ()

```bash
pwd

(
    cd /tmp
)

pwd
```

Output:

```text
/home/user
/home/user
```

## Command Group {}

```bash
pwd

{
    cd /tmp
}

pwd
```

Output:

```text
/home/user
/tmp
```

### Difference

| Feature                  | ()        | {}                |
| ------------------------ | --------- | ----------------- |
| Creates new process      | Yes       | No                |
| Changes persist          | No        | Yes               |
| Variable changes persist | No        | Yes               |
| Common use               | Isolation | Grouping commands |

---

# 11. Running Scripts

Execute script:

```bash
./script.sh
```

Runs in a separate process.

Example:

```bash
# script.sh
VAR="Inside Script"
```

Parent shell:

```bash
VAR="Parent"

./script.sh

echo "$VAR"
```

Output:

```text
Parent
```

---

# 12. Source vs Execute

## Execute

```bash
./script.sh
```

Runs in a child shell.

Changes are lost after script exits.

## Source

```bash
source script.sh
```

or

```bash
. script.sh
```

Runs in the current shell.

Changes remain.

Example:

```bash
# script.sh
VAR="Changed"
```

```bash
source script.sh

echo "$VAR"
```

Output:

```text
Changed
```

---

# 13. Command Substitution

Command substitution runs a command and replaces it with its output.

Modern syntax:

```bash
$(command)
```

Older syntax:

```bash
`command`
```

Preferred:

```bash
$()
```

---

# 14. Basic Command Substitution

```bash
DATE=$(date)

echo "$DATE"
```

Example:

```text
Mon Jun 16 12:00:00 UTC 2026
```

---

# 15. Capture Command Output

Current directory:

```bash
CURRENT_DIR=$(pwd)

echo "$CURRENT_DIR"
```

Count files:

```bash
FILES=$(ls | wc -l)

echo "$FILES"
```

Latest log file:

```bash
LATEST=$(ls -t /var/log | head -1)

echo "$LATEST"
```

---

# 16. Nested Command Substitution

```bash
echo "$(date)"
```

Nested:

```bash
echo "$(basename $(pwd))"
```

Example:

```text
projects
```

This is one reason `$()` is preferred over backticks.

---

# 17. Backticks (Legacy Syntax)

```bash
DATE=`date`

echo "$DATE"
```

Works, but nesting becomes difficult.

Prefer:

```bash
$(date)
```

---

# 18. Pipelines and Subshells

```bash
echo -e "a\nb\nc" | while read LINE
do
    VAR="$LINE"
done

echo "$VAR"
```

Output:

```text
```

In Bash, commands in pipelines usually execute in subshells.

Variable changes may not be visible outside the pipeline.

---

# 19. Background Jobs and Subshells

Run in background:

```bash
(
    sleep 5
    echo "Done"
) &
```

Wait for background jobs:

```bash
wait
```

---

# 20. Practical Uses of Subshells

## Temporary Directory Change

```bash
(
    cd /tmp
    ls
)
```

## Temporary Environment

```bash
(
    PATH=/tmp
    echo "$PATH"
)
```

Parent PATH remains unchanged.

## Group Commands

```bash
(
    echo "Start"
    date
    echo "End"
)
```

## Parallel Execution

```bash
(
    sleep 3
    echo "Task 1"
) &

(
    sleep 2
    echo "Task 2"
) &

wait

echo "All completed"
```

---

# 21. Quoting in Linux

Linux has three commonly used quoting mechanisms:

```bash
' '
" "
$()
```

Each behaves differently.

---

# 22. Single Quotes (' ')

Everything is treated literally.

* No variable expansion
* No command substitution
* No escape interpretation

```bash
VAR="Linux"

echo '$VAR'
```

Output:

```text
$VAR
```

```bash
echo 'Today is $(date)'
```

Output:

```text
Today is $(date)
```

---

# 23. Double Quotes (" ")

Allows:

* Variable expansion
* Command substitution
* Preserves spaces

```bash
VAR="Linux"

echo "$VAR"
```

Output:

```text
Linux
```

```bash
echo "Today is $(date)"
```

Output:

```text
Today is Mon Jun 16 ...
```

---

# 24. Escape Character ()

Backslash escapes special characters.

```bash
echo \$HOME
```

Output:

```text
$HOME
```

```bash
echo \"Linux\"
```

Output:

```text
"Linux"
```

```bash
echo \\tmp
```

Output:

```text
\tmp
```

---

# 25. Single vs Double Quotes

```bash
VAR="Linux"

echo '$VAR'
echo "$VAR"
```

Output:

```text
$VAR
Linux
```

---

# 26. Quick Reference

## Shell Information

```bash
echo $SHELL
echo $$
echo $BASHPID
echo $PPID
```

## Subshell

```bash
(
    command
)
```

## Command Group

```bash
{
    command
}
```

## Command Substitution

```bash
$(command)
```

## Source Script

```bash
source script.sh
```

## Execute Script

```bash
./script.sh
```

## Background Job

```bash
(command) &
```

## Wait for Jobs

```bash
wait
```

## Quotes

```bash
'text'      # literal
"text"      # expand variables
$(cmd)      # command substitution
```

---

# Mental Model

```text
Shell
│
├── Executes commands
├── Runs scripts
├── Expands variables
├── Performs command substitution
│
└── Creates Subshells
      │
      ├── Separate process
      ├── Separate variables
      ├── Separate working directory
      └── Cannot modify parent shell
```

## Golden Rule

```text
Shell      = Your current command interpreter
Subshell   = Temporary child shell
$()        = Run command and capture output
' '        = Literal text
" "        = Expand variables and commands
source     = Run in current shell
./script   = Run in child process
```


| Variable | Meaning |
| --- | --- |
| $$ | Current shell PID |
| $PPID | Parent PID |
| $? | Last exit status |
| $0 | Script name |
| $# | Number of arguments |
| $* | All arguments |
| $@ | All arguments (quoted-safe) |

**exec Command** 
Example:

	echo $$
	exec bash
	echo $$
New shell replaces old shell.
**Explain:**

	exec replaces the current process.
	No child process is created.

**Common examples:**

	exec bash
	exec > logfile.txt
	exec 2>/dev/null

Great for understanding parent-child relationships.

	$pstree -p $$
	$ps -f --forest

**Login vs Non-Login Shell **

Many Linux learners get confused by:

	.bashrc
	.bash_profile 
	.profile

Login Shell Reads: 

	~/.bash_profile
	~/.profile

Interactive Non-login Shell Reads: 

	~/.bashrc

---

# What is a Login Shell?

A login shell is the first shell started after authentication.

Examples:

* SSH login
* Console login (TTY)
* `su -`
* `sudo -i`

Example:

```bash
ssh user@server
```

After authentication, Bash starts as a **login shell**.

Verify:

```bash
shopt login_shell
```

Output:

```text
login_shell    on
```

---

# What Files Does a Login Shell Read?

Bash checks these files **in order**:

```text
~/.bash_profile
~/.bash_login
~/.profile
```

It stops at the first one it finds.

Example:

```text
Home Directory
├── .bash_profile
└── .profile
```

Bash reads:

```text
~/.bash_profile
```

and ignores:

```text
~/.profile
```

---

# Typical Login Shell Flow

```text
User Login
    │
    ▼
~/.bash_profile
    │
    ▼
~/.bashrc
```

Most Linux distributions include this inside `.bash_profile`:

```bash
if [ -f ~/.bashrc ]; then
    . ~/.bashrc
fi
```

This means:

```text
Login Shell
    │
    ▼
.bash_profile
    │
    ▼
.bashrc
```

So login shells usually end up reading both files.

---

# What is a Non-Login Shell?

A non-login shell is any Bash started after login.

Example:

Open a terminal window inside GNOME, KDE, XFCE, etc.

```text
Terminal Window
```

This starts:

```text
Interactive Non-Login Shell
```

Verify:

```bash
shopt login_shell
```

Output:

```text
login_shell    off
```

---

# What Files Does a Non-Login Shell Read?

Only:

```text
~/.bashrc
```

Example:

```text
Open Terminal
    │
    ▼
.bashrc
```

`.bash_profile` is not read.

---

# Interactive vs Non-Interactive Shell

## Interactive Shell

Interactive means:

```text
You type commands manually.
```

Example:

```bash
bash
```

You get a prompt:

```bash
$
```

This is an interactive shell.

---

## Non-Interactive Shell

Non-interactive means:

```text
Runs commands automatically without user interaction.
```

Example:

```bash
bash script.sh
```

No prompt appears.

This is a non-interactive shell.

---

# Startup File Matrix

| Shell Type            | Startup Files Read                            |
| --------------------- | --------------------------------------------- |
| Login Interactive     | `.bash_profile`, `.bash_login`, or `.profile` |
| Interactive Non-Login | `.bashrc`                                     |
| Non-Interactive       | None by default                               |
| SSH Login             | `.bash_profile`                               |
| Terminal Emulator     | `.bashrc`                                     |
| `su - user`           | `.bash_profile`                               |
| `bash`                | `.bashrc`                                     |

---

# Purpose of Each File

## ~/.bash_profile

Used for login-specific configuration.

Examples:

```bash
export PATH="$HOME/bin:$PATH"
export EDITOR=vim
```

Things you want initialized once per login session.

---

## ~/.bashrc

Used for interactive shell settings.

Examples:

```bash
alias ll='ls -lh'
alias la='ls -la'

PS1='\u@\h:\w\$ '
```

Things you want every time a terminal opens.

---

## ~/.profile

Generic POSIX shell startup file.

Used when:

```text
.bash_profile does not exist
```

Works with:

```text
sh
dash
bash
```

Example:

```bash
export PATH="$HOME/bin:$PATH"
```

---

# Why Put Aliases in .bashrc?

Suppose:

```bash
alias ll='ls -lh'
```

is stored in:

```text
.bash_profile
```

You log in:

```bash
ssh server
```

Alias exists.

But when you open another terminal:

```bash
gnome-terminal
```

Alias may not exist because `.bash_profile` wasn't read.

Correct location:

```text
.bashrc
```

---

# Why Put PATH in .bash_profile?

Example:

```bash
export PATH="$HOME/bin:$PATH"
```

Usually belongs in:

```text
.bash_profile
```

because it only needs to be initialized once per login session.

---

# Common Real-World Setup

## ~/.bash_profile

```bash
# Load .bashrc

if [ -f ~/.bashrc ]; then
    . ~/.bashrc
fi

export PATH="$HOME/bin:$PATH"
```

---

## ~/.bashrc

```bash
alias ll='ls -lh'
alias la='ls -la'

export HISTCONTROL=ignoreboth

PS1='\u@\h:\w\$ '
```

This is how many Linux distributions configure Bash.

---

# Visual Diagram

```text
SSH Login
    │
    ▼
.bash_profile
    │
    ▼
.bashrc


Open Terminal
    │
    ▼
.bashrc


bash script.sh
    │
    ▼
(no .bashrc)
(no .bash_profile)
```

---

# How to Test What Bash Reads

Add a line to `.bashrc`:

```bash
echo "Loaded .bashrc"
```

Add a line to `.bash_profile`:

```bash
echo "Loaded .bash_profile"
```

Then test:

### SSH Login

```bash
ssh localhost
```

Output:

```text
Loaded .bash_profile
Loaded .bashrc
```

### Open Terminal

Output:

```text
Loaded .bashrc
```

This is the easiest way to observe the difference.

---

# Quick Interview Answer

### What is the difference between `.bashrc` and `.bash_profile`?

```text
.bash_profile
    Executed for login shells.
    Used for environment initialization.

.bashrc
    Executed for interactive non-login shells.
    Used for aliases, prompt customization,
    shell options, and interactive settings.

Most Linux distributions source .bashrc
from .bash_profile so login shells
receive both configurations.
```

---

# Quick Revision

| File            | Purpose                               |
| --------------- | ------------------------------------- |
| `.bash_profile` | Login shell configuration             |
| `.bash_login`   | Alternative login shell configuration |
| `.profile`      | POSIX-compatible login configuration  |
| `.bashrc`       | Interactive shell configuration       |

### Rule of Thumb

```text
Aliases       → .bashrc
Prompt (PS1)  → .bashrc
Functions     → .bashrc

PATH          → .bash_profile
EDITOR        → .bash_profile
Environment Variables → .bash_profile
```

---

# Mental Model

```text
Login Shell
    │
    ▼
.bash_profile
    │
    ▼
.bashrc


Non-Login Shell
    │
    ▼
.bashrc


Script Execution
    │
    ▼
No startup files by default
```

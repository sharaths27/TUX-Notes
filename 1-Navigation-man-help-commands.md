
Linux Command Line Productivity

├── Bash Navigation Shortcuts

├── Command Documentation

│ ├── man

│ ├── info

│ ├── whatis

│ ├── type

│ ├── which

│ └── whereis

├── Bash History

└── Date Command

Bash Navigation
------------
**Cursor Move**

	Ctrl + A = goto start of the line
	Ctrl + E = goto end of the line

	Alt + F = move forward one word
	Alt + B = move back  one word

	Ctrl + P = previous command (up arrow key)
	Ctrl + N = next command( down arrow key)

**Cut/Delete line, word, char**

	Ctrl + K = delete to end of the line
	Ctrl + U = delete to benining of the line

	Ctrl + W = delete one word(left)
	Alt + D  = delete one word(right)

	Ctrl + D = Deletes character under cursor. 
	Ctrl + H = Delete Character Left

	Ctrl + Y = Yank (Paste Last Killed Text)
	Ctrl + L = Clear
	Ctrl + _ = undo
	Ctrl + C = Abort foreground job with SIGINT
	Ctrl + Z = Stop a foreground job with SIGTSTP
	
Manual Pages
----------------
$ man man

man  is  the system's manual pager
Each man page belongs to a section:

 | Section  | Meaning  |
| ------------ | ------------ |
|  1  |  User commands (ls, cp, grep) |
|  2  |  System calls |
|  3 |   Library functions|
|  4  | Device files  |
|  5  |  Config file formats |
|  6  |  Games |
|  7  |   Miscellaneous|
| 8  | System admin commands|


Example:

	 $ man 5 passwd
	 $ man 1 passwd

Show All Matching Pages

	$man -a passwd

Locate Man Page

		man -w ls

Search by Section

	man 2 open
	man 3 printf

**Navigation**

 	arrow keys
 	spacebar = next page
 	b 		 = previous page
 	q 		 = quit
 	g        = Go to Start
 	G  		 = Go to End

**Search**

	Forward Search (/)
	Search from top to bottom:   	/word
	Example: 	/option
	Press Enter to jump to the match.

**Backward Search (?)**

 	Search from bottom to top:   ?permission

**Repeat Search**

	 keys		Action
	 n 		Next match (same direction)
	 N 		Previous match

**By default:**
 • Case-sensitive
 
	 To ignore case:  /word\c
	 Example: /size\c

**Most man pages have standard sections:**
	 NAME
	 SYNOPSIS
	 DESCRIPTION
	 OPTIONS
	 EXAMPLES
	 FILES
	 SEE ALSO

**Jump using search**

	 /OPTIONS
	 or
	 /EXAMPLES

**Disable pager (raw output)**

	$man ls | cat


**Save to file**

	man ls > ls.txt

**Save as PDF**

	man -Tpdf ls > ls.pdf

**Searching inside man pages (apropos)**

	$man -k  copy
	$apropos copy

Useful when you don’t know the command name

**--help — Quick Command Help**
------------
Example:

	ls --help
	cp --help
	grep --help

Faster than man
Less detailed

**info — GNU Documentation System**
------------
More detailed and structured than man

Example:

	info ls
	info bash


**whatis — One-Line Description**
------------

Shows short description of a command

Example:

	whatis ls
	whatis grep

Output:

	ls - list directory contents

**type — Command Type Checker**
------------

Tells what kind of command it is

Example:

	type ls  , type cd , type python

**Output examples:**

ls is aliased to `ls --color=auto`
cd is a shell builtin
python is /usr/bin/python

**which — Command Location**
------------
Shows path of executable
Example:

	which ls
	which gcc

**whereis — Find Binary, Source, Man Page**
------------
Locates command files

Example:

	whereis bash
Output:

	bash: /bin/bash /usr/share/man/man1/bash.1.gz

**Offline Documentation Files**
------------

Many programs store docs in:

	 /usr/share/doc/
Example:

	 ls /usr/share/doc/bash/

**Main modes of operation:**

| Option | Description |
|:---------|:--------------|
| -f, --whatis | equivalent to whatis |
| -k, --apropos | equivalent to apropos |
| -K, --global-apropos | search for text in all pages |
| -w, --where, --path, --location | print physical location of man page(s) |
| -W, --where-cat, --location-cat | print physical location of cat file(s) |
| -i, --ignore-case | look for pages case-insensitively (default) |
| -I, --match-case | look for pages case-sensitively |
| -a, --all | find all matching manual pages |


**History Command**
------------

Linux keeps a record of commands you’ve typed in the shell (Bash, Zsh, etc.) so you can:

	 • Re-run commands
	 • Edit previous commands
	 • Search past commands
	 • Automate workflows faster

In Bash, this is managed mainly by:

	• history command
	 • ~/.bash_history file
	 • Shell shortcuts (↑, Ctrl+R, etc.)

**This file is: (~/.bash_history)**

	 • Written when you log out (or shell exits)
	 • Read when you log in

**Important:**
 • Commands from current session may not appear until you exit or run:
 
 	$ history -w

** Command:	 $ history **

	 show last 10 commands 
	 $history 10
	 Execute command number 52 from history 
	 $!52
	 run last command 
	 $ !!
	 run last command containing a word
	 $ !?rm?

** History Search**

	 Ctrl + r
	 Type part of a command:
	 (reverse-i-search)`apt`: sudo apt install nginx

	Press:
	 • Ctrl + r → next match
	 • Enter → run
	 • Ctrl + C → cancel

Last argument of previous command   :  Esc + .

**Show command without running**

	$ !:p
	 $ !50:p
	Last command  : 	$ !!
	Last argument of previous command : 	$ !$

**Example:**

	tar -xvf archive.tar.gz
	cd !$

**History Behavior**

Check history settings

	$ set | grep HIST

**Important variables:**


| Variable     | Meaning                 |
| ------------ | ----------------------- |
| HISTSIZE     | Commands kept in memory |
| HISTFILESIZE | Commands saved to disk  |
| HISTFILE     | History file location   |
| HISTCONTROL  | Ignore rules            |
| HISTIGNORE   | Ignore patterns         |

Ignore duplicates & commands starting with space

	 $ export HISTCONTROL=ignoreboth

Ignore sensitive commands

	 $ export HISTIGNORE="ls:pwd:exit:clear"

**Clear History**

	Clear current session :	$history -c

Clear file too :

	 $history -c
	 $history -w

Delete a specific command

	 $history -d 998

**Timestamp Your History**

Enable timestamps:

	export HISTTIMEFORMAT="%F %T "

Example:

	998  2020-01-30 18:45:12 sudo apt update

(Quick Reference)
----------------------
| Command | Description |
| --- | --- |
| `history` | show history |
| `!!` | last command |
| `!n` | command number n |
| `!string` | last starting with string |
| `!?string?` | last containing string |
| `Ctrl+R` | reverse search |
| `Alt+.` | last argument |
| `history -c` | clear history |
| `history -w` | write to file |

**Temporarily Disable History for a Single Command**
You can turn off history just for one command:

		set +o history        # disable history
		ls -l /etc
		set -o history        # re-enable history

Result:

	• Command runs normally.
	• Not saved in history at all.
	• Safe for sensitive commands like passwords.

**One-Liner: Run & Delete Immediately**
If you want a single-line trick:

	$ ls -l /etc && history -d $((HISTCMD-1)) && history -w

How it works:
    1. Run the command (ls -l /etc)
    2. Delete the previous command from session history ($((HISTCMD-1)))
    3. Write the changes to ~/.bash_history (history -w)

Result: Command runs and is immediately removed from both session and disk history.

	OR  $ echo "discreet"; history -d $((HISTCMD-1))

**Run in a Subshell With History Disabled (maximum stealth )
(Run in a Subshell Without Recording History)**

This method doesn’t touch your main shell history at all:

	 $( set +o history; ls -l /etc )

	 • Runs inside a temporary subshell
	 • History is disabled inside the subshell
	 • Command output shows normally
	 • Nothing is recorded in your main history


**Edit previous command in editor**

	$ fc

opens previous command in vim/nano.

**date command**
------------

 **options**
 Displays the date and time specified by the given string

	 $date -d  "2 days ago"
	 $ date -d "2024-10-15"
	 Tue 15 Oct 2024 12:00:00 AM UTC

 Displays the date and time in UTC instead of the local timezone

	 $ date -u

 | Format | Description | Example |
|---------|--------------|---------|
| %Y | Full year (4 digits) | date +"%Y" outputs 2024 |
| %m | Month (01-12) | date +"%m" outputs 10 |
| %d | Day of the month (01-31) | date +"%d" outputs 08 |
| %H | Hour (00-23, 24-hour format) | date +"%H" outputs 14 |
| %M | Minute (00-59) | date +"%M" outputs 45 |
| %S | Second (00-59) | date +"%S" outputs 30 |
| %A | Full weekday name | date +"%A" outputs Tuesday |
| %a | Abbreviated weekday name | date +"%a" outputs Tue |
| %B | Full month name | date +"%B" outputs October |
| %b | Abbreviated month name | date +"%b" outputs Oct |
| %p | AM or PM indicator (12-hour format) | date +"%I %p" outputs 02 PM |
| %I | Hour (01-12, 12-hour format) | date +"%I" outputs 02 |
| %T | Time in 24-hour format (HH:MM) | date +"%T" outputs 14:45:30 |
| %D | Date in MM/DD/YY format. | date +"%D" outputs 10/08/24.

**Examples:**

	date +"Year: %Y, Month: %m, Day: %d"
	date "+DATE: %D%nTIME: %T"
	sudo date --set="20100513 05:30"
	date --date="yesterday"
	date --date="2 year ago"
	date --date="10 hour ago"
	date --date="next monday"
	date --date="4 day"
	date --date="tomorrow"
	$date +%x
	02/03/2026
	$mysqldump database_name > database_name-$(date +%Y%m%d).sql
	$touch file_$(date +"%Y%m%d").txt

**IMP **
Display Last Modified Timestamp of a Date File

		$ date -r /etc/hosts

**ISO Format**
	$date - I
	Output:  2026-06-16

**RFC Format**
	$date -R
	Output:  Tue, 16 Jun 2026 10:30:00 +0530

**Use Unix Epoch Time (Epoch Converter)**

	 $date +%s
	 $date -d "1984-04-08" +"%s"

	reverse
	 $date  -d @1770076800


**Quick Revision**

	Ctrl+A -> Start of line
	Ctrl+E -> End of line
	Ctrl+R -> History search
	Ctrl+K -> Delete to end
	Ctrl+U -> Delete to start
	Ctrl+Y -> Paste killed text

	man -> Full documentation
	info -> GNU documentation
	whatis -> One-line description
	which -> Executable path
	whereis -> Binary + docs

	history -> Show history
	!! -> Last command
	!$ -> Last argument
	Ctrl+R -> Search history

	date -> Current date
	date +%s -> Epoch
	date -d -> Parse date
	date -r -> File timestamp
	Ctrl + T = Transpose Characters ( sl -> ls)


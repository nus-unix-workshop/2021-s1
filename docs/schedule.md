# Tentative Schedule for Unix@Home Workshop

(Note: Allocated time is a very rough approxmiate)

## Day 1
### Plenary Session 1: Introduction (20 minutes)

- [What is Unix?  Why are we learning/using Unix?](why-unix.md)
- [What is CLI? Why are we learning/using CLI?](why-cli.md)
- [What is a terminal? What is a shell?](shell.md)

### Breakout Session 2: Basic Unix Files Operations I (30 minutes) 

- Install WSL and Windows Terminal
- Installing tmate for terminal sharing
- File Organization
    - Root directory
    - Home directory
	- Looking inside a directory (`ls`)
    - Directory tree
    - Navigating around the directory tree (`cd`)
    - Shortcut: `.` `~`, `..`
    - Bash shortcut (tab, up arrow)
    - Referring to manuals (`man`)

#### Break (20 minutes)

### Breakout Session 3:  Basic Unix Files Operations II (20 minutes) 

- Making and removing your own directory (`mkdir` and `rm`)
- Creating, moving, and copying files (`touch`, `mv`, `cp`)
- Looking inside a file (`cat`, `more`, `less`)
- File permissions (`chmod`)

#### Break (20 minutes)

### Breakout Session 4: Composition (30 minutes)

- Standard output and standard input
- Redirection (`<`, `>`, `>>`)
- Piping (`|`)
- Pattern matching in bash (`*`, `?`, `{}`)
- Unix power tools:
    - Looking for something in a file (`grep`)
    - Comparing two files (`diff`)
    - Counting lines, words, and characters (`wc`)

## DAY 2
### Plenary Session 5: Gaining Efficiency with Unix (10 minutes)

- Automation, Staying in Your Zone, and Powertools
- The philosophy and power of `vim`

### Breakout Session 5: Simple file editing with vim (30 minutes) 

- Running and quitting `vim`
- Insert mode and command mode (i and esc)
- Moving cursor around with hjkl

#### Break (20 minutes)
### Breakout Session 6: Very Basic Shell Scripts (30 minutes)

- Putting a sequence of commands in a file and executing the file
- Command-line arguments and variables

#### Break (20 minutes)
### Breakout Session 7: Extending your Unix Environment (20 minutes)

- Using `apt` (WSL) and `brew` (macOS), `curl`
- install, list, search, uninstall

### Breakout Session 8: Remote Servers (10 minutes)

- Concepts of hosts, client, server.
- Accessing a remote server via `ssh`
- Ssh into `sdf.org`
    - Preview of SoC Unix environments (`stu0`) 

#### Break (20 minutes)
### Plenary Session 9: Conclusion and The Unix Philosophy (15 minutes)

- The Unix Philosophy
    - Do one thing well
    - Use simple text file
    - Make every program a filter and make them work together
    - Avoid unnecessary output


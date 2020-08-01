# Unit 3: Terminal and Shell

## What is a Terminal?

With the advances in Cathode-ray tube (CRT), the teletype machine 
is replaced with _computer terminals_ in the late 1970s.  Instead of
printing the output on paper, the output from CLI is now printed
on a monitor supporting 24x80 characters on screen in black and 
white (or green).

<br><div align=center>
<a title="Jason Scott / CC BY (https://creativecommons.org/licenses/by/2.0)" href="https://commons.wikimedia.org/wiki/File:DEC_VT100_terminal.jpg"><img width="512" alt="DEC VT100 terminal" src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/99/DEC_VT100_terminal.jpg/512px-DEC_VT100_terminal.jpg"></a>
<br>Figure: The VT100 Computer Terminal.
</div><br>

In modern days, operating systems still use similar underlying 
functionalities to read in keyboard inputs and print out text 
to show to the users, but instead of these clunky special
purpose devices, the functionality of a terminal is replaced
by programs called _terminal emulator_ or _virtual terminal_.
Examples include `Terminal` and `iTerm2` on macOS; `Windows Terminal`
on Microsoft; `xterm` and `konsole` on Ubuntu, etc.
Many legacy control commands on these teletype machines remain
in today's computing environment, such as the terminal control 
sequence.

## What is a Shell?

The term CLI refers to a type of user interface.  To realize this 
interface, Unix computing environments rely on another type of
program called _shell_.  

A shell usually works closely with a terminal to get inputs from the
users, interpret the meaning of the inputs, execute the tasks
(perhaps through the invocation of other programs), and returned the
output back to the user through the terminal.

Note that a shell can run on its own without a 
terminal (it can read input from a file, and write the output to a
file, for instance).

There are many shells available, each with different bells and 
whistles to help improve our productivity.  

The most popular shell that comes as default on many Unix systems
is `bash`, or Bourne Again Shell.  This is the shell that we will
use in this workshop and as default in the SoC Unix computing environment.

I (Wei Tsang) personally use [`fish`](https://fishshell.com/) for 
my day-to-day work.  [Oh-my-zsh](https://ohmyz.sh/) (`zsh`) is 
another shell popular among experienced users.

## Command Prompt

A shell has a _command prompt_. It typically looks something like this, but will be different depending on the default configuration on your machine:
```
ooiwt@pe111:~$
```

The prompt is where you type in a command for the shell to interpret and execute.  

In `bash`, the command prompt can be customized to include information such as the username, hostname, time, current working directory, etc.  It is customary to use the `$` sign as the final character of the prompt.  In our examples, we will just show `$` to incidate the command prompt.

Depending on the habit, sometimes you are asked to type in a command "into the terminal", "into the shell", or "into bash".  They all mean the same thing: type in the command at the command prompt of the shell.

## Terminal Control Sequence

On the old teletype machines (see [history of command-line interfaces](shell.md)), a user can send special commands to 
the teletype machines to control its operation.  Many of these
special commands still exists today, and can be triggered by
with hitting a combination of ++control++ and another key (i.e.,
a control sequence). 

The following lists some of the most useful control sequences
to know:

++control+d++
:   signal the end of input to a program.  This is also used
    to exit from a shell (by telling the shell that you have no more input
    to send and you are done with it).

++control+z++
:   suspend the current running program.  This _pauses_ the execution
    of the program (but not terminating it).  In the `bash` shell, the most recently suspended program can resume executing in the background with the command `bg` or brought back to execution in the foreground again with the command `fg`.   

++control+c++
:   terminate the current running program.

++control+s++
:   freeze the terminal.  This is a legacy control command that pauses the output printing of a teletype machine.  You shouldn't need to use this control sequence.

++control+q++
:   resume the terminal.  This is a legacy control command that resume the printing of a teletype machine.  You shouldn't need to use this control sequence, unless you accidentally hit ++control+s++


!!! note "++control+z++ vs. ++control+c++"
    A common mistake for new students is to hit ++control+z++ frequently if something goes wrong with their program -- this behavior leads to large number of suspended programs (which still occupy resources such as memory on the computer).  The right sequence to use is ++control+c++ -- which terminates the program (and frees up the resources).

!!! note "++control+s++ accidents"
    Since ++control+s++ is used as the "save" shortcut in non-Unix environment, many students accidentally hit this contorl sequence, causing their terminal to freeze.  Don't panic if this happens.  Just hit ++control+q++ and things will be back to normal.


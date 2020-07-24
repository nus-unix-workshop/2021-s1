# Terminal and Shell

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

## What is a Shell?

The term CLI refers to a type of user interface.  To realize this 
interface, Unix computing environments rely on another type of
program called _shell_.  

A shell usually works closely with terminal to get inputs from the
users, interpret the meaning of the inputs, execute the tasks
(perhaps through invocation of other programs), and returned the
output back to the user through the terminal.

Note that it is possible for a shell to run on its own without a 
terminal (it can read input from a file, and write the output to a
file, for instance).

There are many shells available, each with different bells and 
wistles to help improve our productivity.  

The most popular shell that comes as default on many Unix system
is `bash`, or Bourne Again Shell.  This is the shell that we will
use in this workshop and as default in SoC Unix computing environment.

I (Wei Tsang) personally use [`fish`](https://fishshell.com/) for 
my day-to-day work.  [Oh-my-zsh](https://ohmyz.sh/) (`zsh`) is 
another shell popular among experience users.

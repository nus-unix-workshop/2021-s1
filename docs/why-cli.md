# Unit 2: Command-Line Interfaces

## What is Command-Line Interfaces?

The command-line interfaces, or just CLI for short, is an important 
interface that we, as computing professionals, interact with 
the computer for most of our day-to-day tasks.

In contrast to graphical user interfaces where users use a mouse to
click/drag on menus and windows to interact with a computer, the
command-line interface uses keyboard and text.  The users would type
a command to instruct the computer to do something, and the computer
would respond by displaying the reply to the user.

CLI evolves from teletypes machines where users would interact with
the computer through a typewriter-like machine (see Figure 2.2. of
this article for an example).  Users would type a command on the 
keyboard, and the typewriter would print out, line-by-line, the output
on a piece of paper.  This is the era before monitors and mice. 
Again, driven by the constraints and the necessity, CLI interfaces
are designed to be simple and economical.  _The commands are short and
fast to type; the responses are succinct._

<br><div align="center">
<a title="Bubba73 (Jud McCranie) / CC BY-SA (https://creativecommons.org/licenses/by-sa/3.0)" href="https://commons.wikimedia.org/wiki/File:ASR_33.jpg"><img width="256" alt="ASR 33" src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/18/ASR_33.jpg/256px-ASR_33.jpg"></a>
<br>Figure: A teletype device (Model 33 ASR) to interact with a computer.
</div><br>

## Why CLI over GUI?

Since CLI is designed to be economical, CLI is much more efficient
and productive to use, in particular when we are interacting with
a remote computer over the network -- sending text back and forth
is much more efficient than sending graphical elements over the
network.  Each character takes up to two bytes, but each pixel alone
takes up 3 bytes of data.

Another reason why using CLI is faster and more productive is that
user can keep their hands on the keyboard at all time and _not
needing to switch frequently between keyboard and mouse._  While
research has shown that GUI and mouse are great for casual users,
for software developers that need to type on the keyboard most of
the time, having to switch between keyboard and mouse is a
productivity-killer.

Further, CLI commands typically provides a host of options that is
accessible directly (including of clicking through preference dialogues)
from the command line, making these commands flexible and customizable.

Finally, since these commands are just text, we can put together a
sequence of commands easily as a _script_, to automate highly repetitive
tasks.

## References
- [The Art of Unix Usability: Command Line Interfaces](http://www.catb.org/~esr/writings/taouu/taouu.html#id3017631), by Eric Steven Raymond

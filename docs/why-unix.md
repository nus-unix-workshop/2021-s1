# Unix

## History of Unix

To understand what the word _Unix_ means and to appreciate its
importance, we need to know the history of computing.  So, let's
start with a glimpse into the history book.

Early computers, in the 1940s and early 1950s, do not have an
operating system.  Every program will have to be designed specifically
for a given hardware specification and only one program can run on
the computer at one time.  To run a program, a user will have to
carry a stack of punch cards or tapes into the computer room and
load them into the computer at a scheduled time.

As the computers become more sophisticated and the demand to run
programs on the machine increases, humans operators are hired to
manage the requests to run the programs, and these human operators
have to manually schedule and manage the time allocated to each
program on the machine.

These tasks are slowly being replaced by a layer of software that
runs on the computers starting late 1950s.  Termed _operating
systems_, this system software helps to manage "which program runs
when", and it includes more functionalities such as resource
accounting (e.g., which user used how much time on the machine) and
hardware management (e.g., hide the tedious operations of 
interfacing with memory and storage from the programmer).

One of the defining development in the 1960s is the idea of time
sharing - allowing multiple programs to be submitted to run at the
same time on the computer remotely.  Time sharing is revolutionary
since users do not have to queue or schedule a slotted time to run
a program on a computer.  In the late 1960s, with the early Internet,
users can remotely access a computer.  Thus, users do not have to
be physically in the computer room to use the computer.

Unix is an operating system that was developed in the late 1960s and 
early 1970s around these revolutions, by Dennis Ritchie and Ken 
Thompson from Bell Laboratories.  Learning from the mistakes of the
past operating systems, which tend to be difficult to use and bloated
with features, the duo set to develop an operating system with _simplicity_
and _elegance_ at the core of its design.  Part of the push towards
simplicity is also due to the lack of powerful computers in many 
places at that time -- the design constraints has lead to design 
decisions that favour economy.

<br><div align=center>
<a title="Peter Hamer / CC BY-SA (https://creativecommons.org/licenses/by-sa/2.0)" href="https://commons.wikimedia.org/wiki/File:Ken_Thompson_(sitting)_and_Dennis_Ritchie_at_PDP-11_(2876612463).jpg"><img width="512" alt="Ken Thompson (sitting) and Dennis Ritchie at PDP-11 (2876612463)" src="https://upload.wikimedia.org/wikipedia/commons/thumb/8/8f/Ken_Thompson_%28sitting%29_and_Dennis_Ritchie_at_PDP-11_%282876612463%29.jpg/512px-Ken_Thompson_%28sitting%29_and_Dennis_Ritchie_at_PDP-11_%282876612463%29.jpg"></a>
<br>Figure: Ken thompson (sitting) and Dennis Ritchie working in front of their computer.
</div><br>

The simplicity and elegance has propelled the popularity of the Unix
operating system, leading to over 600 installations reported by 1974[^3].

Closely tied to the rise of Unix is the invention of C, a programming
language that Dennis Ritchie and Ken Thompson used to write Unix in.
This is revolutionary by itself, as programmers can then write tools
and programmes in a higher level structured language, rather than in 
low level assembly languages as in the operating systems before.

As a result of these development, Unix is the first operating system
where programmers can write and run program on the fly in front of a
terminal.  This ability leads to a pleatora of contributions to Unix
systems, utilities, and tools in the 1970s, fueling its popularity 
among the developers.

The ease of programming and its superiority in terms of simplicity
has lead to emergence of variants of the original Unix operating
systems, developed by modifying the original Unix source code. 
The Berkeley Software Distribution (BSD) is among most important 
ones (macOS is its decendant).  Another notable decendant from the
original Unix is Solaris, from Sun Microsystem (now Oracle), which
the School of Computing runs on its computing server (called `sunfire`).

Another variant of Unix is Linux -- which interestingly is developed
from scratch as a hobby initially by Linus Torvalds at the age of 21.
Linux follows many of the principles of Unix, but is not based on the 
original Unix source code.

<br><div align="center">
<a title="Eraserhead1, Infinity0, Sav_vas / CC BY-SA (https://creativecommons.org/licenses/by-sa/3.0)" href="https://commons.wikimedia.org/wiki/File:Unix_history-simple.svg"><img width="800" alt="Unix history-simple" src="https://upload.wikimedia.org/wikipedia/commons/thumb/7/77/Unix_history-simple.svg/800px-Unix_history-simple.svg.png"></a>
<br>Figure: Unix and Unix-like Operating Systems.
</div><br>

While a majority of personal desktop is still running Microsoft Windows 
10 (88%), a vast majority of server software is running on some flavour 
of Unix (>70%)[^1].  Almost all mobile phones are running on a variant of Unix 
(iOS, Android).  Among software developers, more than half (53%) uses a 
Unix-based OS on the primary work machines[^2].  Microsoft, after years of
competing with Unix-based OS, has started to embrace Unix-based systems
and released the Windows Subsystems for Linux, allowing Windows user
to run a sandboxed Linux subsystems within Windows.

We collectively call these variants of operating systems and subsystems
the _Unix computing environment_, which today includes all OS from Apple 
(macOS, iOS, etc), Linux-based systems (Ubuntu, Android, etc), commercial
servers (Oracle's Solaris, HP's HP-UX, IBM's AIX), and subsystems within
Microsoft Windows 10.

## Why Learn Unix?

There are several reasons:

- Unix-based OS is the dominant operating system in the world, and
as a computing student, it is likely that you will have to interface
with one sometime in your career.

- Unix design is rooted at its simplicity and economy.  It is
probably the most _productive_ programming environment you can have
to do most of your day-to-day tasks and to develop software as a
computing professional.

- Unix design is also rooted at its programmability.  If there is
something that you wish to automate a task to improve your productivity,
you can easily compose new tools from the existing ones.

- The Unix philosophy serves as a great example of how good 
software should be designed: simple, do one thing well, 
composable.

[^1]: [Stack Overflow Developer Survey 2020](https://insights.stackoverflow.com/survey/2020#development-environments-and-tools)
[^2]: [Usage Share of OS](https://en.wikipedia.org/wiki/Usage_share_of_operating_systems), by Wikipedia
[^3]: [The Unix Time Sharing System](https://people.eecs.berkeley.edu/~brewer/cs262/unix.pdf), by Dennis Ritchie and Ken Thompson.

## Further Readings
- [The Art of Unix Programming: History of Unix](http://www.catb.org/~esr/writings/taoup/html/ch02s01.html), by Eric Steven Raymond

# Setting Up `tmate`

Before you continue, read about [what is a terminal](shell.md).

Make sure you have set up `apt` if you use WSL and `brew` if you use macOS.

## What is `tmate`?

`tmate` is a tool that allows you to share your [terminal](shell.md) with others.  This allows another person to have enter text into _your_ terminal and to see the output returned by _your_ terminal.

We will use `tmate` to allow tutors to view and type into your terminal.  

Giving someone else full control of your computer is dangerous -- so you need to be sure that you are sharing your terminal with someone you trust (e.g., your professor and your tutor).  Do NOT share your `tmate` link publicly.

## Installing `tmate` on WSL or Ubuntu

Run the following in your terminal:
```
sudo apt-get install tmate
```

## Installing `tmate` on macOS

Run the following in your terminal:
```
brew install tmate
```

## Running `tmate`

To share your screen with someone you trust, run:

```
tmate
```

You should then see the following messages:

```
Tip: if you wish to use tmate only for remote access, run: tmate -F        [0/0]
To see the following messages again, run in a tmate session: tmate show-messages
Press <q> or <ctrl-c> to continue
---------------------------------------------------------------------
Connecting to ssh.tmate.io...
Note: clear your terminal before sharing readonly access
web session read only: https://tmate.io/t/ro-Zv6kbZxwLtc84NXnnFJtGvnYE
ssh session read only: ssh ro-Zv6kbZxwLtc84NXnnFJtGvnYE@sgp1.tmate.io
web session: https://tmate.io/t/3svwMBrjhwgp93QmZFHLnwzRP
ssh session: ssh 3svwMBrjhwgp93QmZFHLnwzRP@sgp1.tmate.io
```

Note that your output will not be exactly the same as the above, particular, the seemingly gibberish text is randomly generated when
you run `tmate`, so it will be a different gibberish every time.

There are several important piece of information here:

There are a list of links for you to share with your tutors.  Suppose your tutor wants to see (but not control) your screen through a web browser, you can send the link marked as `web session read only:` to him or her (e.g., via private chat in Zoom).  If your tutor needs to show you something on your shell through a web browser, you can send the link marked as `web session:` to him or her.  (In the example above: send `https://tmate.io/t/3svwMBrjhwgp93QmZFHLnwzRP`)

If you do not copy down the links and need to access them later, just run `tmate show-messages`.

Note that the links are randomly generated and are different every time you run `tmate`.

Once you have copied and send the link to your tutor, press ++q++ or ++ctrl+c++ to continue.  Your terminal is now shared with your tutor.  You can tell this as there is a small bar at the bottom of your terminal's screen.

To stop sharing, hit ++ctrl+d++ at the command prompt[^1]. 

[^1]: For an overview of all special terminal ++ctrl++ commands, see [terminal control sequence](shell.md).

Here is a small screencast to demonstrate this:

[![asciicast](https://asciinema.org/a/sfHoPFqV2kqHk21v23nnHuqX6.svg)](https://asciinema.org/a/sfHoPFqV2kqHk21v23nnHuqX6)

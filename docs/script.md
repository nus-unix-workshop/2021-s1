# Unit 13: `bash` Scripts

Now that we know the basic of text editing, we will start
writing some simple bash scripts.  

## `.bashrc`

First, let's write a bash script that will be executed every time
we run bash.  Just like `.vimrc`, the "run commands" for `bash`
is called `.bashrc`.  Recall that the `rc` files should be hidden
and located in the home directory.

So, start `vim` by

```
$ vim ~/.bashrc
```

and add the following lines at the bottom of `.bashrc`.

```
alias rm="rm -i"
alias mv="mv -i"
alias cp="cp -i"
echo ".bashrc loaded"
```
If your `.bashrc` already contains some text, leave the existing text
there.  Otherwise, you will see a splash screen about `vim`.  Just to
into `INSERT` more to get rid of the splash screen.

Remember that the `-i` flag causes these commands to interact with you
and ask to confirm whether you want to remove/override a file.
The `alias` command is used to create a new command.  Here,
```
alias rm="rm -i"
```
creates a new command called `rm` that does perform `rm -i`.  So now,
every time you type `rm` in `bash`, `bash` will run _your_ `rm`,
which is just `rm -i` (the second `rm` is `bash`'s `rm`).

Go ahead and hit ++shift+z+z++ to save and quit.  Now, exit `bash` and
reload `bash` again.  You should see the message `.bashrc loaded`
printed.

Try to create a dummy file and remove it.  `bash` should now prompt you
for confirmation.
```
$ touch dummy
$ rm dummy
remove dummy?
```
You can hit ++y++ for yes or ++n++ for no.

## Bash Environment Variables

In addition to creating your customized commands, you can also
affect the behavior of `bash` by configuring its environment
variables.  An environment variable is something that can hold a
value (just like $$x$$ in math).  The naming convention for an environment variable is to use all upper cases.

The most common ones used are:

- `PATH`: which is where `bash` would search for a command to execute.
- `PS1`: which allows you to customize your command prompt.
- `EDITOR`: which allows you to configure the default text editor.

For `PS1` configuration, there are many neat examples on the
Internet.  We recommend that you should least have your identity
displayed somewhere on the command prompt so that the tutors
know which terminal they are looking at via `tmate`.

For `EDITOR`, you can set it to `vim`.

Remember that earlier, to run `hello.sh`, we needed to include the
prefix `./hello.sh`?  The `./` is to tell `bash` to look for the
executable in the current directory.  To avoid typing `./` all the
time (remember our goal: minimize finger movement), we can add `.`
to the `PATH`.

Now, `cd` into the directory where you have `hello.sh`, and type
```
$ echo $PATH
$ export PATH=$PATH:.
$ echo $PATH
```

The first command shows you what the current `PATH` variable
contains.  The `$` sign refers to the value of that variable instead of the variable name.  The `PATH` contains a list of paths in the directory structure, separated by `:`.

In the second line, we add `.` (the current directory) to the `PATH`
variable.  The third line checks if `.` is added correctly.

If `.` is indeed added to the path, you can now run `hello.sh`
without the prefix `./`.

Note that there is a security risk in adding `.` to `PATH`.  My recommendation is only to do it on your personal Unix system (not a shared
computing server) and add `.` only at the end of `PATH`.  See this
[FAQ](http://www.faqs.org/faqs/unix-faq/faq/part2/section-13.html)
for more information.

If you wish, you can now edit this line into `.bashrc`, so that it is
executed every time you launch `bash.
```
export PATH=$PATH:.
```

## Simple Bash Scripts

In addition to creating aliases, you can put commonly used commands in
a `bash` script. The advantage is that it allows us to pass in
arguments so that the script is more flexible.

For instance, the following script finds out the size of a directory and
the size of the largest subdirectory (in MBs)

```
#!/bin/bash
du -m $1 | sort -n | tail -2
```

You can read the man pages for what `du`, `sort`, and `tail` and the
various options do.  But the two interesting points we wish to point
out are the first line:
```
#!/bin/bash
```
and the variable `$1`.

The `#!` sequence is called `shebang`.  It is used by Unix to
determine which interpreter to use to run this script.  It could be
replaced with `/usr/bin/python` or other language interpreters, for
instance.  But here, we meant this to be a `bash` script so we tell
Unix to invoke `bash`.

The variable `$1` will be replaced by the argument passed into the
script on the command line.  Suppose that we save the script above as `dirsize.sh`.  Then you run:

```
dirsize.sh /usr/local
```

`$1` will become `/usr/local` and so the size of `/usr/local` and its subdirectories will be determined.

If you do not pass in any argument, `$1` will be empty, and the size
of the current working directory will be determined instead.

## Developing an Automation Mind Set

If you find yourself typing the same command or sequence of commands
over and over again, it is probably good to start creating a script
to automate it.  

You will need to invest some time upfront to get the script written
and tested, but in the long run, it will save you time.

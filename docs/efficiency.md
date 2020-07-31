# Unit 10: Leveling Up Your Productivity with CLI

## Minimizing Hand Movements

In Day 1 of the workshop, you have seen how you can manage files and navigate around the directory structure, all by interacting with the command-line interface.  No windows. No mouse.  Just you, the keyboard,
and the terminal.  You do not even need to use any arrow keys or function keys.  

Why is this a big deal?  Let's look at the image of the keyboard below:

![keyboard](figures/keyboard.png)

We only need to use the keys colored in pink.  And since these keys concentrated in a small region on the keyboard, for most of us, we can reach the keys if we just position our hands over the keyboard[^1], we
only need move _our fingers_ to type.  

[^1]: The recommended placement of hands over the keyboard is so that the thumbs are over the ++space++ bar, the left fingers are over ++a++ ++s++ ++d++ ++f++, and the right fingers are over ++j++ ++k++ ++l++ ++semicolon++.

![typing](figures/fast-typing.gif)

## Minimizing Typing

We can even minimize the movement of our fingers in several ways by typing less.  We have seen several ways where we have achieved these:

- Unix commands are named economically -- they are often only a few characters long.
- We can use ++tab++ to auto-complete a command or a file name.
- We can use ++control-p++ or ++control+n++ to repeat a previous commands.

There are many more `bash` shortcuts for productivity, if you are keen, take a look here: https://github.com/fliptheweb/bash-shortcuts-cheat-sheet

You have also seen in Day 1 of the workshop that Unix has many small, simple, utilities that we can compose to solve a task.  But composing them requires much typing:

```
$ cat ID | sort | uniq | grep CEG | wc -l
```

If we need to run this over and over again or share this command with someone, we can simply put these commands in a file, and then run it by invoking its name.  Such a file containing commands for the shell is called a _shell script_.

For example, let's create a file named `hello.sh` containing the line `echo hello!` by:
```
$ cat > hello.sh
echo hello!^D
```

The extension `.sh` is not necessary but it is just something I use so that I can tell that this file contains a shell script.  In the example above, `cat` will wait for me to enter something on the keyboard.  So I entered `echo hello!` followed by ++control+d++ to indicate the end of the input.

Now, to execute this file, we run:
```
$ bash hello.sh
hello!
```
or
```
$ bash < hello.sh
hello!
```

Recall that we said Unix shells do not necessarily interact with the users?  This is an example.  We pass the file `hello.sh` to _a new instance of `bash`_, asking it to interpret the lines inside this file as commands to execute.  

Remember that we want to minimize typing, so can we run it with less typing?  What if we can just pass the filename directly to `bash` to execute?

```
$ ./hello.sh
bash: ./hello.sh: Permission denied
```

Here, we specify the relative path of the script `hello.sh`, including the prefix `./` (for reasons that we will explain later).  But we should get an
error telling us `Permission defined`.  Recall from the [`File Permissions`](chmod.md) unit that a file needs to have the executable `x` permission to be executed.  So we need to add this permission for ourselves:
```
$ chmod u+x hello.sh
$ ./hello.sh
hello!
```

Now we can run our script without typing `bash`.  We can remove `./` as well, but we will learn about that only when we talk about [`environment variables`](script.md).

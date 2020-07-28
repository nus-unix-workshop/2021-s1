# Unit 7: Standard Input/Output

## History

Two of the design decisions of Unix that lead to its simplicity are the decisions to (i) decouple the physical input/output devices from the programs, allowing programs written for Unix to read from _abstract_ input and output devices; and (ii) make all programs read and write from these abstract input and output devices by default.  Before Unix, the older operating systems often require programmers to painstakingly set up connections to the teletype machines and other devices for reading inputs and printing outputs.   With Unix, programmers can now focus on solving the tasks at hand and let Unix takes care of the input and output.

The two abstract devices that Unix provides are called _standard input_ and _standard output_.  By default, the standard input refers to the _keyboard_ and the standard output is the _terminal_.

## Examples using `cat` and `wc`

Let's look at these concepts closer, by examining some examples.

Remember `cat`?  The `cat` command takes in a filename and it prints the content of the file to the standard output.

```
$ cat test.txt
This is a test file for learning Unix file management commands.
```

If no filename is given, `cat` by default try to read from the standard input.  Try running:

```
$ cat
```

You will see that the command is waiting for you to type in something.  Type in anything, as soon as you press ++enter++, `cat` is going to read in the text from the standard input, as if it is the content of a file, and then prints the content to the standard output.  You can keep typing, supplying text to `cat`, or you can type ++control+d++ to send the end-of-input command to `cat`.

Let's look at another command, `wc`.  `wc` is a utility that counts the number of lines, words, characters.  If we call `wc` and supply it a file name, it will count the number of lines, words, and characters in that given file.

```
$ wc test.txt
       1      11      64 test.txt
```

The output means that there is 1 line, 11 words, and 64 characters in the file `test.txt`.

But if you do not pass in any file name, `wc` is going to read in the text from the standard input, as if it is the content of a file, and prints the three counters to the standard output.  Go ahead and try:

```
$ wc
```

You will see that the `wc` command is waiting for you to type in something.  Type in a few sentences, you can hit ++enter++ for a new line.  When you are done, type ++control+d++.  `wc` will count the number of lines, words, and characters for the text that you just entered.

## Output Redirection

By defining two abstract input and output devices (or channels), Unix frees the programmers from worrying about where to read the input from and write the output to.  Most of the time, we can write the output of the program to the standard output.  In instances where we need to write the output to another location, we can just _redirect_ the output.

The operators `>` and `>>` are used to redirect the standard output to a file.  The difference is that `>` will overwrite the given file, while `>>` will concatenate into the given file.

For example:
```
$ wc test.txt > test.count
$ cat test.count
       1      11      64 test.txt
```

The first command redirects the output from `wc` to a file named `test.count`, so you do not see anything printed to the output anymore.  We can check by running `cat` on the new file `test.count` -- indeed the original output from `wc` is now stored in the file `test.count`.

If we repeat the command `wc test.txt > test.count` again, you can see that the file has been
overwritten with the output from `wc` again.  But if we replace `>` with `>>`, a new line is concatenated into `test.count`.   So the file now has two lines.

```
$ wc test.txt > test.count
$ cat test.count
       1      11      64 test.txt
$ wc test.txt >> test.count
$ cat test.count
       1      11      64 test.txt
       1      11      64 test.txt
```

## Input Redirection

The operator `<` is used to redirect a file into the standard input. So, instead of reading from the keyboard, we can now read from a file.  Commands such as `cat` and `wc` already support from a file directly, so there is no difference in terms of functionality to run the commands by passing in the file name, or by using the `<` operator.

```
$ wc test.txt
       1      11      64 test.txt
$ wc < test.txt
       1      11      64
$ cat test.txt
This is a test file for learning Unix file management commands.
$ cat < test.txt
This is a test file for learning Unix file management commands.
```

Note the slight difference in the output format of the second `wc` above -- it no longer prints the file name since from `wc` points of view, it is read from the standard input and not from a file, so it is not aware of the file named `test.txt`

In most CS programming assignments, however, to keep things simple, you will be asked to read from the standard input only, so the `<` is a great time-saver -- you do not have to repeatedly type in the same input data over and over from the keyboard.  You can just save the input data in a file, then redirect it to standard input with the `<` operator.

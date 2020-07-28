# Unit 8: Composing Programs with `|`

Another key innovation of Unix is that led to its success is the invention of the `|` operator.  

Before Unix, operating systems tend to provide complex, monolithic, programs.  The philosophy of Unix, however, is to provide many small, simple, utility programs, that can be composed to complete a more complex task.  These small programs each do one thing only (and do it well) and so are easier to write and less prone to bugs.

The composition of these utility programs relies on two things.  First, plain text is often used as input and output of the programs.  These allow the programs to understand each other easily.  Second, they use `|` to communicate with each other.  The `|` operator takes the standard output from one program and redirects it as the standard input of another program.

For instance,
```
$ cat test.txt | wc
       1      11      64
```
compose `cat` and `wc` together.  Recall that `cat` reads the content of the file and prints it to standard output.  Here, we pipe the standard output from `cat` to `wc`.  So now, these printed texts are redirected as the standard input to `wc`.

But this is just the same as
```
$ wc < test.txt
```
that we have seen before.  What's the power in `|`?  

Now, recall that we have made copies of `test.txt` earlier, into `foo.txt` and `bar.txt`.  If you have not done so or have removed them, you can quickly reproduce the files with:
```
$ cp test.txt foo.txt
$ cp test.txt bar.txt
```

Let's suppose now I want to count the total number of words for all three files.  Instead of calling `wc` on each file one by one, and sum them up myself.  I can just run:

```
$ cat test.txt foo.txt bar.txt | wc
       3      33     192
```

Here, `cat` read the three files, concatenate their content, and pass the output to `wc` for counting.

## Useful Utilities

Before we see more interesting examples of using `|`, let's move beyond `cat` and `wc`, and see what other simple tools are there in Unix.

### `head` and `tail`

`head` and `tail` prints out the first $k$ lines and last $k$ lines from a file (or standard input if the file name is not given).  By default, $k$ is 10, but you can pass in an argument to specify $k$.

```
$ cat test.txt foo.txt bar.txt
This is a test file for learning Unix file management commands.
This is a test file for learning Unix file management commands.
This is a test file for learning Unix file management commands.
$ cat test.txt foo.txt bar.txt | tail -1
This is a test file for learning Unix file management commands.
```

### `echo`

`echo` simply prints out the command-line argument to the standard output.

```
$ echo "hello world!"
hello world!
```

### `sort`

`sort` rearrange the input lines in alphabetical order.
```
$ sort
john
jane
peter
mary^D
jane
john
mary
peter
```

In the example above, I entered `john`, `jane`, `peter`, `mary` followed by ++control+d++ to signify the end of input.  `sort` prints out `jane`, `john`, `mary`, `peter`, in that order.

### `uniq`

`uniq` remove any two consecutive lines that are the same.

```
$ uniq
1
2
2
2
1
1^D
1
2
1
```

For instance, in the above, there are three consecutive lines of `2`, so only one remained.  There are also two consecutive lines of `1`, so only one remained.`

### `grep`

`grep` returns the lines of text from the given file (or the standard input) that matches the given string.  For instance, run

```
$ grep abc
```

and start typing in some lines of text, some containing `abc`, some do not.  `grep` will spew out into the standard output all the lines that contain the text `abc` somewhere.  As usual,
hit ++control+d++ when you are done.

## Pipe Example

To give you an example of how useful `|` is, here is a real example.  When processing the registration of the workshop, I have quite a few registrations that are duplicates -- students registered more than ones.  I need a quick way to count how many unique registrants are there.
So I keep the student id of all registrants in a file called `ID`.  For instance, the file `ID` contains (not real data, of course)

```
A1234567X,CS
A1234559A,CEG
A1239999J,CEG
A1234580K,CEG
A1233210O,CS
A1234567X,CS
A1234581Q,ISC
A1233216T,ISC
A1239999J,CEG
```

Now, to count how many unique registrants, I just need to run:

```
$ cat ID | sort | uniq | wc -l
    7
```

To count how many uniq registrants are `CEG` students, I just change it to:
```
$ cat ID | sort | uniq | grep CEG | wc -l
    3
```

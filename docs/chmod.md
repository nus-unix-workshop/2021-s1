# Unit 6: File Permission Management

File permissions determine _who_ can do _what_ to a file.  Typically, you do not need to fiddle with the file permission, but when you need to, it is usually for an important reason and it is critical to do it right.

## The _What_ of File Permissions
Let's look at _what_ you can do to a file first.  Unix file permissions allow control of three actions: `r` (read), `w` (write) and `x` (execute).  These permission settings allow the following different actions to be done for regular files and directories.

permission | effect on file | effect on directory
-----------|----------------|--------------------
`r`| reading the content of a file | read the names of the files in the directory
`w`| writing into a file | create/delete/rename files in the directory
`x`| executing a file | access contents and meta-info (size, creation time) of files in the directory

These three actions can be controlled independently.  

The permissions on a file can be expressed in two ways:

- using symbolic notation.  For instance,  `rwx`, `r-x`, `-wx`, where a `-` means that the corresponding permission is not given (in the order of `r`, `w`, `x`).

- using a numerical notation. This notation uses a digit between 0 and 7, which is computed as a sum of the individual digit representing the permissions: `r` is represented with 4, `w` is represented with 2, and `x` is represented with 1.
For instance, `r-x` has a numerical representation of 5, and `-wx` has a numerical representation of 3.

## The _Who_ of File Permissions

Unix divides the users into three classes: `u` is the <b>u</b>ser who owns the file; `g` refers to the users in the same <b>g</b>roup as the user; and `o` are all the <b>o</b>ther users.

The permissions can be controlled separately for these classes of users.  The permission notation simply concatenates the file permissions of each class of users together, in the order of `u`, `g`, and `o`.

For instance, the permission of 644, or `rw-r--r--`, on a file means that:

- the owner can read and write
- the group users can only read
- all the other users can only read

## Checking file permission

You can view the permission of a file by using the `ls -l` command (`l` for long format):

```
$ ls -l test.txt
-rw-r--r--@ 1 ooiwt  staff  64 Jul 28 09:52 test.txt
```

Ignoring the first `-` and the last `@`, you can see that the permission of `test.txt` is 644.

## The `chmod` command

You can use `chmod` command to change the permissions of a file or a directory.

For instance,
```
$ chmod 666 test.txt
$ ls -l test.txt
-rw-rw-rw-@ 1 ooiwt  staff  64 Jul 28 09:52 test.txt
```
would change add the permission `w` to both group and other users[^1].

An alternative way is to just specify the changes.  To remove the write permission from others, you can write:
```
$ chmod o-w test.txt
$ ls -l test.txt
-rw-rw-r--@ 1 ooiwt  staff  64 Jul 28 09:52 test.txt
```

[^1]: Giving write permission to other users is a security risk and you should not do this unless you know what you are doing.

## Common Scenarios for `chmod`

Here are some scenarios where you might need to use the `chmod` command:

- If you use the SoC Unix server to do your homework, you should prevent the directory that stores your homework from being accessible by other users.  Make sure that your homework directory as the permission of `700`.

- If you download a file from the Internet and you do not have the permission to read it, you should do a `u+r` to give yourself the read permission.

- A program should have execution permission to run.  If you have a script or an executable file that you can't run, give yourself the execution permission `u+x`.

# Accessing Remote Shell

So far, we have been accessing the Unix computing environment
locally, on your laptop or desktop computer.

Using the shell, however, opens up a whole new world -- you can
now access a remote computer over the Internet using the same
interface.

Let's try this out, using one of the two remote servers:

### sunfire
A Unix computing server called `sunfire`, hosted by the
School of Computing.  To access this, you need to have a
SoC Unix Account.  If you do not have one yet, you can create
a new account here: https://mysoc.nus.edu.sg/~newacct

After that, activate "General Unix Servers" and "The SoC
Compute Cluster" in MySoC here: https://mysoc.nus.edu.sg/~myacct/services.cgi

`sunfire` is a shared machine running Solaris.  

To log into `sunfire`, type:

```
$ ssh sunfire.comp.nus.edu.sg
```
or
```
$ ssh <username>@sunfire.comp.nus.edu.sg
```

The first option above assumes your SoC Unix account name is the same
as your username on your local machine (Remember we advised you to
choose the same username when you installed WSL?  This is why!). In
the second option, we have to explicitly provide our user name.  For
instance,
```
$ ssh ooiwt@sunfire.comp.nus.edu.sg
```

These commands are too long to type so you could add an alias for this command into your `~/.bashrc`.

### sdf.org

For those students who do not have a NUSNET or SoC account, as a
backup, you can apply for an account at public access Unix system
provided by the Super Dimension Fortress at http://www.sdf.org.

Once you receive your account, you can ssh into sdf.org by

```
$ ssh sdf.org
```

## Secure Shell

`ssh` stands for secure shell.  It is called secure as it encrypts
all communications between you and the remote server.  It is an
efficient way to access a remote computer since only texts are
transmitted, not graphics.

The first time you access a remote computer using `ssh`, it will ask
you a question, which looks sometimes like this:
```
The authenticity of host 'sunfire (137.132.80.55)' can't be established.
RSA key fingerprint is SHA256:UUyiI25neTV5AT/q3CJi0BAA4ztfo+7doi77bkzpLJ4.
Are you sure you want to continue connecting (yes/no/[fingerprint])?
```

Type `yes` then hit ++enter++.  You won't be asked the same question
again.

Once you log in, you will be presented the same interface as you are
used to -- a command prompt.  You can do everything that you have
learned at this command prompt, with the only difference being you are
doing it on a remote computer (aka remote _host_  or remote
_server_).

## Transferring Files Back and Forth

Secure copy, or `scp`, is one way to transfer files between the remote host and your local computer for archiving or storage. Let's say you want to transfer jfk.txt from the current working directory to your remote directory, then, on your local computer, run:

```
$ scp jfk.txt sunfire.comp.nus.edu.sg:~/
```

`scp` behaves just like `cp`, except that we add `sunfire.comp.nus.edu.sg:` in front of a path (add `<username>@` as necessary) to indicate the name of the remote host to copy the files to.  The path `~/` now refers to the home directory on the remote host.

If you have files with the same name in the remote directory, the files will be overwritten without warning. I have lost my code a few times due to `scp`.

`scp` supports `-r` (recursive copy) as well.

# Unit 9: Pattern Matching in `bash`

We now show you another productivity shortcut.  In an [example earlier](pipe.md), you have seen how we passed in more than one file names into `cat`.  Recall that we can use ++tab++ to auto-complete the file names, so we can hit fewer keys on the keyboards.  
Now, we show you there is an even faster way.

Instead of
```
$ cat test.txt foo.txt bar.txt | wc
```

We could just run
```
$ cat *.txt | wc
```

The `*` is a special character in `bash` that represents 0 or more characters.  So, this command essentially says, `cat` any files that contain 0 or more characters, followed by `.txt`.

The table below summarizes the useful patterns:

Pattern | Matches
--------|--------
`*`     | 0 or more characters
`?`     | one character
`[..]`  | one character, coming from the given set between `[` and `]`, `-` to indicate a range.
`{.., ..}` | Either one of the names, separated by `,`.

#### Example 1:
```
$ ls ???.txt
bar.txt foo.txt
```

Since we use three `?`, it matches any file name with three characters followed by `.txt`.

#### Example 2:
```
$ ls [f-t]*t
foo.txt test.txt
```

The expression `[f-t]*t` matches all file names the start with alphabet `f`, `g`, etc, until `t`, followed by zero or more characters, followed by `t`.

#### Example 3:
```
$ ls {fo,ba}??txt
foo.txt test.txt
```

The expression `{fo,ba}??txt` matches any file names the start with either `fo` or `ba`, followed by two characters, followed by `txt`.

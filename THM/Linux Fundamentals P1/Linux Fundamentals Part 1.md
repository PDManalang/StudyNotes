# 1 Linux Fundamentals Part I
## 1.2 Background on Linux
**Linux**
- considerably more lightweight.
- powers things like: websites, car entertainment/control panels, point-of-sale (POS) systems, critical infrastructures
- Linux is an umbrella term for `multiple OS's` that are based on `UNIX (another OS)`.

## 1.4 Running Your First Few Commands
- `echo` output any text that we provide.
- `whoami` find out what user we're logged in as.

## 1.5 Interacting with File System
- `ls` listing
- `cd` change directory
- `cat` concatenate (to output file content)
- `pwd` print working directory

## 1.6 Searching Files
- `find` to automate finding files (instead of consistently using `cd` and `ls`)
  - this command helps you find the location of files (esp if you don't remember much of its information).
- `grep` search contents of files for specific values we are looking for.
- `wc` count the number of entries in a file.

## 1.7 Introduction to Shell Operators
- `&` operator that allows you to run commands in the background of your terminal.
  - basically allows the user to do other things while a previously executed command is running in the background.
- `&&` operator that allows you to `combine multiple commands together` in one line of your terminal.
- `>` operator that is a `redirector` - meaning it can take the output from a command (ex. using `cat` to output a file) and direct it elsewhere.
  - command `echo` is a good example of redirecting an output.
- `>>` does the same function as `>` but `appends the output` rather than replacing (nothing is overwritten).

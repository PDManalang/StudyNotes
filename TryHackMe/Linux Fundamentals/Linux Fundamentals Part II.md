## 2.2 Accessing your Linux Machine Using SSH (Deploy)
**Secure Shell (SSH) Protocol** a protocol between devices in an `encrypted form`.
  - allows to remotely execute commands on another device remotely.
  - command syntax for logging in `ssh username@ip.address` then provide username and password.

## 2.3 Introdcution to Flags and Switches
- `ls` list the content of the working directory (does not include hidden files), but if typed `ls -a (all)` this will include hidden ones.
- `man` manual page (documentation of Linux system commands and applications).

## 2.4 Filesystem Interaction Continued
- `touch` create a file
- `mkdir` create a folder
- `cp` copy a file or folder
- `mv` move a file or folder
- `rm` remove a file
  - `rm -R` to remove a folder
- `file` determine type of file

## 2.5 Permission 101
- `ls -lh` list of permissions of all files in the directory
  - can give overview on what actions are allowed and who has the ability to perform an action -- `Read`,`Write`,`Execute`.
- `su` switch user, new session drops into previous user's home directory.
- `su -l` switch user, new session drops into the current user's home directory.

## 2.6 Common Directories
- `/etc` root directory.
  - a commonplace location to store files that are used by the operating system.
- `/var` variable data directory.
  - stores data that is frequently accessed or written by services or applications running on the system.
- `/root` home for the `root` user system.
- `/tmp` temporary directory
  - stores data that is only needed to be accessed once or twice.
  - similar to computer memory, content is cleared out once computer is restarted.

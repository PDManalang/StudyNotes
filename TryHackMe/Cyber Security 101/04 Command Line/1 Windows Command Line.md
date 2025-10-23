# 1 Windows Command Line

## 1.1 Introduction
- `Command-Line Interface (CLI)` advantages: *Lower resource usage, Automation, Remote Management*

## 1.2 Basic System Information
- `set` check your path from the command line.
- `ver` determine the operating system (OS) version.
- `systeminfo` in-depth information about the system.
- `more` to pipe in the content if it's too long.
- `help` provides information for a specific command.
- `cls` clears command screen.

## 1.3 Network Troubleshooting
- `ipconfig` to check network information.
    - can also be `ipconfig /all` to get more information about the network.
- `ping target_name` to check if the server can access a particular server on the Internet (ICMP packet).
- `tracert target_name` traces the network route traversed to reach the target.
- `nslookup` looks up the host or domain and returns its IP address.
- `netstat`displays current network connections and listening ports. additional options:
    - `-a` displays ALL established connections and listening ports.
    - `-b` shows the program associated with each listening port and established connection.
    - `-o` reveals the process ID (PID) associated with the connection.
    - `-n` uses a numerical form for addresses and port numbers.
    - `-abon` combination of the four.

## 1.4 File and Disk Management
- `cd` display the current drive and directory.
    - `cd target_directory` to change to any specific directory.
    - `cd ..` change directory, one-level up.
- `dir` display the child directories.
    - `dir /a` display hidden and system files as well.
    - `dir /s` display files in the current and all subdirectories.
- `tree` visual representation of child directories and subdirectories.
- `mkdir` create a directory.
- `rmdir` remove a directory.
- `type` dump the contents of the file on the screen.
- `more` for longer text files.
- `copy` copy files from one location to another.
- `move` does the same thing as `copy` (but moves the entire thing, not a duplicate).
- `del or erase` delete a file.
- `*` wildcard, example use `copy *.md C:\Markdown` which will copy all files with extension .md to directory C:\Markdown.

## 1.5 Task and Process Management
- `tasklist` list the processes running.
- `tasklist /?` help page for tasklist.
- `tasklist /FI "imagename eq sshd.exe"` meaning to *Filter image name equal to sshd.exe* (can be other image name).
- `taskkill /PID target_pid`.
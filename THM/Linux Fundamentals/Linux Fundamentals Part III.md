# 3 Linux Fundamentals Part III

## 3.3 Terminal Text Editors
- `nano` features:
    - search for text
    - copy and paste
    - jump to a line number
    - find out what line number you are on
- `vim` a much more advanced editor. benefits:
    - customize keyboard shortcuts to your liking
    - syntax highlighting (useful for writing or maintaining code)
    - works on all terminals (as compared to nano)
    - lot of resources to learn from

## 3.4 General/Useful Utilities
- `wget` command that allows user to download file from the web via HTTP
    - sample command `wget https://assets.tryhackme.com/additional/linux-fundamentals/part3/myfile.txt`
- `scp` transferring files using the SSH protocol to provide both authentication and encryption. allows user to:
    - copy files & directories from your current system to a remote system (`scp important.txt ubuntu@xxx.xxx.x.xx:/home/ubuntu/transferred.txt`)
    - copy file & directories from a remote system to your current system (`scp ubuntu@xxx.xxx.x.xx:/home/ubuntu/transferred.txt backtocurrent.txt`)
- `python3` part of Ubuntu pre-package (web server)

## 3.5 Processes 101
- processes are programs that are running in your machine.
- PID (Process ID) increments for the order in which the process starts. Ex. `the 60th process will have the PID of 60`.
- `ps` command to provide a list of running processes.
- `ps aux` to see processes run by other users.
- `top` command that gives real-time statistics about the processes running in your system.
- `kill` command that terminates processes.
    - `sigterm` kill the process, but do some cleanup tasks beforehand.
    - `sigkill` kill the process, no cleanup done.
    - `sigstop` stop/suspend a process.
- `systemd` a process that sits between the OS and the user.
- `systemct1` command that allows us to interact with the `systemd` process/daemon.
    - options to work with `systemct1`: `start, stop, enable, disable`.

## 3.6 Maintaining Your System: Automation
- `crontab` a special file with formatting that is recognizd by `cron` process to execute each line-by-line steps.
    - requires 6 specific values:
        - `MIN` what minute to execute at
        - `HOUR` what hour to execute at
        - `DOM` what day of month to execute at
        - `MON` what month of the year to execute at
        - `DOW` what day of week to execute at
        - `CMD` actual command that will be executed
    - `(*) asterisk` can be used if you do not wish to provide a value for a specific field.
    - crontabs can be edited by using the command `crontab -e`.

## 3.7 Maintaining Your System: Package Management
- `apt` normally used as command to install software unto an Ubuntu system.
    - it's part of the package management software that also named `apt` - it contains a whole suite of tools to manage packages (install and remove softwares).
    - `add-apt-repository` command use to add a repository.
    - `add-apt-repository --remove ppa:PPA_Name/ppa` remove package.
    - `apt remove [software-name-here]` remove software.

## 3.8 Maintaining Your System: Logs
- read logs lol.
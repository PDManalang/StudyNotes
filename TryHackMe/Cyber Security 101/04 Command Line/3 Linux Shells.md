# 3 Linux Shells

## 3.2 How to Interact with a Shell?
- `pwd` print working directory.
- `cd` change directory.
- `ls` list directory contents.
- `cat` display file contents.
- `grep` search a word inside a file.

## 3.3 Types of Linux Shells
- Bourn Again Shell (Bash), default for most Linux distributions.
    - scripting capabilities.
    - tab completion feature.
    - keeps history file and logs all commands.
- Friendly Interactive Shell (Fish), more user-friendly.
    - simple syntax.
    - auto spell correction for commands you write.
    - customize command prompt with cool themes.
    - color features based on the role of commands.
- Z Shell (zsh)
    - advanced tab completion and is also capable of writing scripts.
    - auto spelling correction
    - extensive customization

## 3.4 Shell Scripting and Components
- to execute scripts in one-go, can create a file with a `.sh` extension.
- every script should start with a shebang `#!`
- `chmod +x script_name.sh` execute permission to script.
- `./script_name.sh` script execution
- Variables:
    - `echo` display string on the screen.
    - `read` used to take input from the user.
- Loops:
    - `for i in {1..10}; do echo $i done`, sample loop command.
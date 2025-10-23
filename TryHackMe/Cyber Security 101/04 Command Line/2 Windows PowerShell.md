# 2 Windows PowerShell

## 2.2 What is PowerShell?
- **PowerShell** is a cross-platform task automation solution made up of command-line shell, a scripting language, and a configuration management framework.
    - object-oriented (retains properties and methods of an object).

## 2.3 PowerShell Basics
- `cmdlets (command-lets)`, is what the PS commands are called.
- follows the `verb-noun` naming convention.
- `get-command` lists all the available cmdlets, functions, aliases, and scripts.
- `get-command -commandtype "commandtype name"` displays the available command of specified commandtype.
- `get-alias` command-line tool shortcuts (alias of a command).
- `get-help` gives detailed information on a command.

## 2.4 Navigating the File System and Working with Files
- `Get-ChildItem` list the files and directories in a location (add `-Path` parameter for specific ones).
    - command is similar to CLIs `dir` and Linux `ls`.
- `Set-Location` to navigate to a different directory.
    - command is similar to CLIs `cd`.
- `New-Item` creates a new item. Need to specify the path of an item (`-Path`) and its type (file or directory) (`-ItemType`).
- `Remove-Item` removes both directories and files.
- `Copy-Item` to copy or `Move-Item` move files and directories `-Path` for the current path `-Destination` for the new location.
- `Get-Content` to display contents of a file.
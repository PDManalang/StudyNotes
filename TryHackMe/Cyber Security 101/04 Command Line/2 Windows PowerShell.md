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

## 2.5 Piping, Filtering, and Sorting Data
- **Piping** a technique used in CLIs that allows the *output of one command to be used as input of another*.
    - creates a sequence of operations where data flows from one command to the next.
    - represented by the symbol `|`.
- `Sort-Object Length` to sort object by their length (size).
- `Where-Object -Property "Extension" -eq ".txt"` to filter object based on property (in this case the file extension) which is equals to text files.
    - other useful **comparison operators**:
        - `-ne` not equal, exclude objects from the results.
        - `-gt` greater than, filter objects that exceed specified value.
        - `-ge` greather than or equal, combination of `-eq` and `-gt`.
        - `-lt` less than, filter object that are below specified value.
        - `-le` less than or equal, conbination of `-eq` and `-lt`.
- `-like` filter properties that match specified pattern.
- `Select-Object` specified properties from objects (return details you only need).
- `Select-String` search text patterns in files.

## 2.6 System and Network Information
- `Get-ComputerInfo` returns comprehensive system information. (similar to `systeminfo`)
- `Get-LocalUser` returns list of all local user account on the system.
- `Get-NetIPConfiguration` returns detailed information about the network interfaces on the system.
- `Get-NetIPAddress` returns all IP addresses configured in the system.

## 2.7 Real-time System Analysis
- `Get-Process` provide detailed view of all currently running processes.
- `Get-Service` allow retrieval of information about the status of services on the machine.
- `Get-NetTCPConnection` monitor active connections (TCP), give insight on both local and remote endpoints.
- `Get-FileHash`generate file hashes.

## 2.8 Scripting
- the process of writing and executing a series of commands contained in a text file, known as script, to automate tasks.
- `Invoke-Command` execute commands on remote systems. automate tasks across multiple machines.
- `Get-Help [Command] -Examples` to find examples and how to use a command.
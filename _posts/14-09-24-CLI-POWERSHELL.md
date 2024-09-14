---

title:  "Powershell"
date: 2024-04-23 00:00:00 +0800 
categories: [CLI, powershell] 
tags: [CLI, powershell] 
---
Hey Friends!😄👋

Welcome to the world of PowerShell – Microsoft's powerful command-line shell and scripting language. Microsoft's PowerShell is a modern shell framework designed for administrative tasks and automation. Built on the .NET framework, PowerShell offers advanced scripting capabilities and seamless integration with Windows systems, making it a favorite among system administrators and power users.


### Getting Started with PowerShell

To launch PowerShell, simply open the Start menu and search for "PowerShell." Once launched, you'll be greeted with a command prompt where you can start typing commands.

### Basic PowerShell Commands

1. **`Get-Help`**: Use this command to get help about PowerShell commands and topics. For example:
   ```
   Get-Help Get-Process
   ```

2. **`Get-Command`**: Use this command to list all available commands in PowerShell. For example:
   ```
   Get-Command
   ```

3. **`Get-Service`**: Use this command to list all the services on your system. For example:
   ```
   Get-Service
   ```

### Working with Files and Directories

1. **`Get-ChildItem`**: Use this command to list the files and directories in a specified location. For example:
   ```
   Get-ChildItem C:\Users
   ```

2. **`New-Item`**: Use this command to create a new file or directory. For example:
   ```
   New-Item -ItemType File -Path C:\temp\newfile.txt
   ```

3. **`Copy-Item`**: Use this command to copy files or directories. For example:
   ```
   Copy-Item C:\source\file.txt C:\destination\
   ```

### Managing Processes and Services

1. **`Start-Process`**: Use this command to start a new process. For example:
   ```
   Start-Process notepad.exe
   ```

2. **`Stop-Process`**: Use this command to stop a running process. For example:
   ```
   Stop-Process -Name chrome
   ```

3. **`Restart-Service`**: Use this command to restart a service. For example:
   ```
   Restart-Service -Name Spooler
   ```

### Advanced PowerShell Commands

1. **`ForEach-Object`**: Use this command to perform an operation on each object in a collection. For example:
   ```
   Get-ChildItem | ForEach-Object { $_.Name }
   ```

2. **`Where-Object`**: Use this command to filter objects in a collection based on specified criteria. For example:
   ```
   Get-Process | Where-Object { $_.CPU -gt 50 }
   ```

3. **`Invoke-Command`**: Use this command to run commands on remote computers. For example:
   ```
   Invoke-Command -ComputerName Server01 -ScriptBlock { Get-Service }
   ```

Woohooo congratulations! You've now learned about the fundamentals of PowerShell and a variety of commands that will enable you to manage and automate tasks on Windows operating systems. With continued practice and exploration, you'll become proficient in using PowerShell to streamline your administrative workflows and increase your productivity. So go ahead, experiment with these commands, and unlock the full potential of PowerShell in your daily operations.

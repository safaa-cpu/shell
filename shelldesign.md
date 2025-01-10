##Design of a shell program

Simple Shell Implementation in C

##Design Overview

This project is a simple shell program written in C. It allows users to execute shell commands interactively or in batch mode using a file. The shell supports multiple commands separated by ;, provides basic error handling, and executes commands in parallel using child processes.


##Features

##1. Interactive Mode:

Provides a terminal-like interface.

Accepts and executes commands entered by the user.

Supports multiple commands separated by ;.

Handles the built-in quit command to exit the shell.

##2. Batch Mode:

Reads commands from a specified file.

Executes each command sequentially and outputs the results.

##3. Error Handling:

- Detects invalid commands.

- Limits the number of arguments to 10 per command.

- Restricts input to a maximum of 512 characters.

- Displays descriptive error messages.

##4. Interrupt Handling:

Ignores Ctrl+C (SIGINT) in the parent process to prevent accidental termination.

##Requirements

A Unix-like operating system (Linux or macOS).

A C compiler (e.g., GCC).

##Usage

##Interactive Mode

- Run the program without any arguments:

./shell

You will see a prompt (shell>). Enter commands to execute them.

- Example:

shell> ls; pwd; echo Hello, World!

Output:

<list of files>
/home/user/project
Hello, World!

- To exit the shell, use the quit command:

shell> quit

##Batch Mode

- Run the program with the name of a batch file as an argument:

./shell commands.txt

The commands.txt file should contain one or more commands, each on a new line.

- Example: commands.txt:

ls
pwd
echo This is a batch file

Output:

<list of files>
/home/user/project
This is a batch file


##Specifications

- Maximum Input Length: 512 characters.

- Maximum Arguments per Command: 10.

- Command Separator: Use ; to separate multiple commands.

##Known Bugs and Limitations

##1. Argument Limit: Commands with more than 10 arguments will result in an error.


##2. Input Length: Commands longer than 512 characters are not supported.


##3. No Advanced Features: Does not support piping (|), redirection (>, <), or background execution (&).


##4. Special Characters: Commands with special characters may not be handled correctly.

##Test Cases

##Interactive Mode

##1. Single Command:

shell> ls

Expected: Lists files in the current directory.

2. Multiple Commands:

shell> ls; pwd; whoami

Expected: Executes ls, pwd, and whoami in sequence.

##3. Quit Command:

shell> quit

Expected: Exits the shell.

##4. Too Many Arguments:

shell> echo a b c d e f g h i j k

Expected: Displays an error for too many arguments.


##5. Invalid Command:

shell> invalid_command

Expected: Error message indicating the command is not found.


##Batch Mode

1. Valid Commands in File: File: commands.txt

ls
pwd
echo Batch mode test

Run:

./shell commands.txt

Expected: Executes all commands in the file.


2. Invalid Command in File: File: commands.txt

invalid_command
ls

Run:

./shell commands.txt

Expected: Displays an error for the invalid command and continues to execute ls.

made by:
Mohammed Yahia Mohammed Ahmed
Riham Morwan Mohammed Abd algadir
Reham Tariq Hussain
Safaa Bashir abdeljabbar

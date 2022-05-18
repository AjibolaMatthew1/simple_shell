# simple_shell

## Table of Contents
- [Description](#Description)
- [File Structure](#File Structure)
- [Requirements](#Requirements)
- [Installation](#Installation)
- [Example of Use](#Example of Use)
- [Authors](#Authors)


# Description
Shell is often confused with as a terminal window and I was a victim of this false thinking too. I got to find out that a shell is just a middleman between the typed commands entered by the users and the computer system that performs an action based on the commands. The picture below best describes the shell.

![Image of Shell](https://miro.medium.com/max/700/0*-OOMpchdZWQZr4zw)

This project deals with creating a shell with minimal functionalities and the standard functions that were employed were: 
-access, execve, exit, fork, free, fstat, getline, malloc, perror, signal, stat, wait, write.


# File Structure
- [AUTHORS](./AUTHORS) - This file lists the people that contributed the project
- [man_1_simple_shell](./man_1_simple_shell) - Custom manual page for the simple shell.
- [shell.h](./shell.h) - This is the header file that contains the library dependencies and structures required for compilation of the program.
- [builtins.c](./builtins.c) - Contains the major builtin functions. Down below lists the functions names and their use:
  - check_for_builtins - This helps to check if the command is a builtin
  - new_exit - This exits the shell with an option for specified status
  - \_env - This prints the environment shell variables to stdout.
  - new_setenv - initializes a new environment variable, or modifies an existing one
  - new_unsetenv - removes an environment variable
 - [builtins2.c](./builtins2.c) - helper functions for the builtins
  - add_key - creates a new environment variable
  - find_key - finds an environment variable in the environment array
  - add_value - creates a new environment variable string
  - \_atoi - converts a string into a non-negative integer
 - [environment.c](./environment.c) - These are functions that deals with the environment.
  - make_env - creates the shell's environment from the parent process
  - free_env - frees the shell's environment
 - [errors.c](./errors.c) - functions related to printing errors
  - print_error - prints an error message to the standard error
  - \_puts2 - prints a string to the standard error
 - [memory_allocation.c](./memory_allocation.c) - Functions related to memory allocation
  - \_realloc - a custom realloc function for arrays of pointers
 - [new_strtok.c](./new_strtok.c) - Custom strtok and helper functions
  - check_match - checks if a character matches any in a string
  - new_strtok - a custom strtok for the shell
 - [path.c](./path.c) - functions related to executing commands
  - path_execute - executes a command in the PATH
  - find_path - finds the PATH environment variable
  - check_for_path - checks if the command is in the PATH
  - execute_cwd - executes a command with an absolute path
  - check_for_dir - checks if the command contains an absolute path
 - [simple_shell.c](./simple_shell.c) - These is the main shell functions for the shell
  - main - the main function of the program
  - sig_handler - handles SIGINT( this is what is sent when ^C is sent as a command by the user)
 - [strfunc.c](./strfunc.c) - Functions concerned with manipulating the string
  - \_puts.c - This writes to the standard output.
  - \_strdup - duplicates a string
  - \_strcmpr - compares two strings
  - \_strcat - concatenates two strings with a / in the middle
  - \_strlen - calculates the length of a string
 - [tokenize.c](./tokenize.c)
  - tokenize - creates an array of tokens from a buffer with a specified delimiter

# Requirements

Simple shell should be ompiled on Ubuntu 20.04 LTS using gcc, using the options -Wall -Werror -Wextra -pedantic -std=gnu89. 

# Installation
- Clone this repository.
- Change directories into the repository:  `cd simple_shell `
- Compile: `gcc -Wall -Werror -Wextra -pedantic *.c -o hsh`
- Run the shell in interactive mode: `./hsh`
- Or run the shell in non-interactive mode: example `echo "pwd" | ./hsh`

# Example of Use

```
$ ./hsh
$ # This is our rendition of the shell
$ ls -al
total 100
drwxrwxr-x  3 vagrant vagrant  4096 Jul 19 22:49 .
drwxr-xr-x 14 vagrant vagrant  4096 Jul 17 22:37 ..
-rw-rw-r--  1 vagrant vagrant   144 Jul 19 17:16 AUTHORS
-rw-rw-r--  1 vagrant vagrant  2367 Jul 19 22:33 builtins2.c
-rw-rw-r--  1 vagrant vagrant  2764 Jul 19 22:14 builtins.c
-rw-rw-r--  1 vagrant vagrant   710 Jul 16 01:03 environment.c
-rw-rw-r--  1 vagrant vagrant  1217 Jul 16 03:24 errors.c
drwxrwxr-x  8 vagrant vagrant  4096 Jul 19 22:34 .git
-rwxrwxr-x  1 vagrant vagrant 32287 Jul 19 22:34 hsh
-rw-rw-r--  1 vagrant vagrant  1792 Jul 19 22:12 man_1_simple_shell
-rw-rw-r--  1 vagrant vagrant   484 Jul 15 20:09 memory_allocation.c
-rw-rw-r--  1 vagrant vagrant  1273 Jul 18 21:00 new_strtok.c
-rw-rw-r--  1 vagrant vagrant  3427 Jul 19 22:06 path.c
-rw-rw-r--  1 vagrant vagrant  2347 Jul 19 22:49 README.md
-rw-rw-r--  1 vagrant vagrant  1769 Jul 19 22:04 shell.h
-rw-rw-r--  1 vagrant vagrant  1480 Jul 18 21:15 simple_shell.c
-rw-rw-r--  1 vagrant vagrant  2111 Jul 16 01:10 strfunc.c
-rw-rw-r--  1 vagrant vagrant   719 Jul 19 21:46 tokenize.c
```

# Authors

Ajibola Matthew [LinkedIn](www.linkedin.com/in/jibbycodes) | [Twitter](www.twitter.com/jibsyyyyy)
Joshua Ajayi [LinkedIn](#) | [Twitter](#)

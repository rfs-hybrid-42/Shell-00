*This project has been created as part of the 42 curriculum by [Your Login].*

# 🐚 Shell 00

[![Version](https://img.shields.io/badge/Version-4.5-blue.svg)](#) [![Module](https://img.shields.io/badge/Module-Shell_00-success.svg)](#)

## 📖 Description

This document is the subject for the Shell 00 module of the C Piscine @ 42. These exercises are carefully laid out by order of difficulty from easiest to hardest. The primary goal of this module is to introduce fundamental concepts of the Unix command line, file system navigation, permissions management, and basic version control.

### 🎯 Featured Exercises

* **ex00 (Z):** Create a file called `z` that returns "Z", followed by a new line, whenever the command `cat` is used on it.
* **ex01 (testShell00):** Figure out a way for the output to match a specific `ls -l` output, then execute `tar -cf testShell00.tar testShell00` to create the archive to be submitted.
* **ex02 (Oh yeah, mooore...):** Create specific files and directories to match a detailed `ls -l` output, and run `tar -cf ex02.tar` to create the archive.
* **ex03 (SSH me!):** Create your own SSH key and add your public key to your repository in a file named `id_rsa_pub`.
* **ex04 (midLS):** Place the command line that will list all files and directories in your current directory, making sure directory names are followed by a slash character, separated by a comma and a space, by order of modification date.
* **ex05 (GiT commit):** Create a shell script that displays the IDs of the last 5 commits of your git repository.
* **ex06 (gitignore):** Write a short shell script that lists all the existing files ignored by your GiT repository.
* **ex07 (diff):** Create a file `b` to successfully execute the command `diff a b > sw.diff`.
* **ex08 (clean):** Place the command line that will search for all files ending by `~`, or a name that starts and ends by `#`. The command line will show and erase all files found, and only one command is allowed.
* **ex09 (Illusions, not tricks, Michael...):** Create a magic file called `ft_magic` formatted appropriately to detect files of 42 file type, built with a "42" string at the 42nd byte.

## 🚀 Instructions

### Execution Requirements
* Exercises in Shell must be executable with `/bin/sh`.
* You cannot leave any additional file in your directory than those specified in the subject.

### How to Test
1.  Clone this repository to your local machine.
2.  Navigate into the directory of the specific exercise you wish to test (e.g., `cd ex05/`).
3.  For shell scripts, run them using the terminal:
    ```bash
    bash [filename.sh]
    ```
4.  For text or configuration files, use standard Unix commands (e.g., `cat z`) to verify the output.

## 📚 Resources

Your reference guide is called Google / man / the Internet / ... Specific manual pages referenced for completing these exercises include:
* `man patch`
* `man find`
* `man file`

### AI Usage Disclaimer
* **Code Generation:** No AI was used to write the shell scripts or solve the exercises in this repository. All solutions are my own.
* **Documentation:** AI was utilized solely to format and structure this `README.md` file to adhere to the strict 42 documentation standards, ensuring clear and professional presentation.

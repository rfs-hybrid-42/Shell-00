*This project has been created as part of the 42 curriculum by maaugust.*

<div align="center">
  <img src="https://raw.githubusercontent.com/rfs-hybrid/42-piscine-artwork/main/assets/covers/cover-shell00.png" alt="Shell 00 Cover" width="100%" />
</div>

<div align="center">
  <h1>🐚 Shell 00: Discovering the Unix Command Line</h1>
  <p><i>Introduction to the Unix command line, file system navigation, permissions, and basic version control.</i></p>

  <img src="https://img.shields.io/badge/Environment-Linux%2FUnix-blue" alt="Environment badge" />
  <img src="https://img.shields.io/badge/Grade-100%2F100-success" alt="Grade badge" />
</div>

---

## 💡 Description
**Shell 00** is the first module of the C Piscine @ 42. For many, it is the very first introduction to a terminal environment. 

The primary goal of this project is to strip away the graphical user interface (GUI) and teach the fundamentals of the Unix command line. It covers navigating the file system, manipulating file permissions (attributes), understanding symbolic links, basic version control with Git, and secure authentication using SSH keys.

---

## 🧠 Exercise Breakdown & Logic

*The following section explains the core concepts and commands required to solve each exercise. It is designed to help future Pisciners understand the **why** behind the commands, rather than just copying and pasting them.*

### 🔹 Basic Navigation & Permissions
| Exercise | Concept & Logic |
| :--- | :--- |
| **[`ex00: Z`](ex00)** | **Standard Output:** The goal is to create a file that outputs "Z" and a newline when `cat` is called on it. <br><br>**Logic:** Use the `echo` command combined with the output redirection operator (`>`) to write text directly into a file without opening a text editor. <br>`echo "Z" > z` |
| **[`ex01: testShell00`](ex01)** | **File Attributes & Size:** Requires modifying a file's permissions to exactly match `-r--r-xr-x` and its size to match exactly 40 bytes. <br><br>**Logic:** Use `chmod 455 testShell00` to set the read/execute permissions for user/group/other. Use `truncate -s 40 testShell00` to artificially set the exact byte size. Finally, package it using `tar -cf testShell00.tar testShell00`. |
| **[`ex02: Oh yeah, mooore...`](ex02)** | **Advanced Attributes, Sizes & Symlinks:** A deeper dive into `ls -l` outputs, requiring specific file sizes, timestamps, and symbolic links. <br><br>**Logic:** <br>1. **Timestamps:** Use `touch -t YYYYMMDDHHMM filename` to forge exact creation dates.<br>2. **Sizes:** Use `truncate -s` to match the exact byte sizes required by the subject.<br>3. **Symlinks:** Use `ln -s target link_name` to create the pointer file.<br>4. **Directories:** Remember that to *enter* or read a directory, it requires the execute (`x`) permission. |

### 🚀 Advanced Tools (Git, Find, Diff, Magic)
| Exercise | Concept & Logic |
| :--- | :--- |
| **[`ex03: SSH me!`](ex03)** | **Secure Shell (SSH):** Requires generating an SSH key pair. <br><br>**Logic:** Passwords are weak. SSH keys use public-key cryptography. You use `ssh-keygen` to create two keys: a private one (never share this) and a public one (`id_rsa_pub`) which you submit to the repository. |
| **[`ex04: midLS`](ex04)** | **Listing Formatting:** Requires listing files separated by a comma and a space, ordered by modification date, with trailing slashes for directories. <br><br>**Logic:** The `ls` command has flags for everything. <br>`-m` separates with commas.<br>`-t` sorts by time modified.<br>`-p` appends a `/` to directories. Combine them: `ls -mtp`. |
| **[`ex05: GiT commit`](ex05)** | **Git History:** Extracting specific data from Git logs. <br><br>**Logic:** `git log` shows history, but we only want the last 5 commit IDs. We use `-n 5` to limit the output, and `--format="%H"` to print *only* the full hash. |
| **[`ex06: gitignore`](ex06)** | **Git Ignored Files:** Listing files that Git is explicitly ignoring. <br><br>**Logic:** `.gitignore` dictates what Git ignores, but to actually list those hidden files in the terminal, you use plumbing commands like `git ls-files --others --ignored --exclude-standard`. |
| **[`ex07: diff`](ex07)** | **Patching Files:** Recreating an original file using a modified file and a `.diff` file. <br><br>**Logic:** The `diff` command creates a roadmap of changes between two files. The `patch` command applies that roadmap. You must use `patch` to reverse-engineer file `b`. |
| **[`ex08: clean`](ex08)** | **Finding & Deleting:** Locating and erasing temporary files (`*~` or `#*#`) in a single command line. <br><br>**Logic:** The `find` command is incredibly powerful. Use `find . -type f` to look for files. Use `\( -name "*~" -o -name "#*#" \)` to set the search parameters (the `-o` means OR). Finally, use `-print -delete` to display and remove them. |
| **[`ex09: Illusions`](ex09)** | **File Signatures (Magic Bytes):** Creating a file that identifies as a custom "42" file type. <br><br>**Logic:** The `file` command doesn't look at file extensions (like `.txt`); it looks at "magic numbers" hidden in the file headers. You must create a custom magic file definition mapping the string "42" to the 42nd byte offset. |

---

## 🛠️ Instructions

### 📦 Usage & Testing
Since these are Shell scripts and basic text/configuration files, there is no compilation required. They must be executed using `/bin/sh`.

1. **Clone the repository:**
   ```bash
   git clone <your_repository_link>
   cd 42-Piscine/Shell00
   ```

2. **Run Scripts:**
   Navigate to the specific exercise folder and run the `.sh` files using bash or sh:
   ```bash
   cd ex05
   bash git_commit.sh
   ```

3. **Verify File Outputs:**
   For exercises like `ex00` or `ex04`, you can verify the contents or the execution using `cat` or by directly pasting the command line into your terminal.

---

## 📚 Resources & References

The terminal can be intimidating, but the answers are always built into the system. The command `man` (manual) is your best friend.

* `man chmod` - Understanding permissions and the octal number system.
* `man ls` - Discovering all the hidden formatting flags.
* `man find` - Mastering the search parameters.
* `man patch` - Understanding how `.diff` files are applied.
* `man file` - Understanding magic numbers and file signatures.
* `man truncate` - Understanding how to shrink or extend the size of a file to the specified size.
* [Ryans Tutorials: Linux Command Line](https://ryanstutorials.net/linuxtutorial/) - A highly recommended resource for beginners.

### 🤖 AI Usage Guidelines
* **Code:** No AI-generated code was used to solve these exercises. All shell commands, scripts, and configurations were manually written and tested to ensure a deep, practical understanding of the Unix system.
* **Documentation:** AI tools were utilized to structure this `README.md` and format the logic breakdowns to create a clean, accessible educational resource for fellow 42 students.

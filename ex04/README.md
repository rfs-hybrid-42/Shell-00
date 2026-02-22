# 🟢 Exercise 04: midLS

## 📝 Objective
Create a file named `midLS` that contains the exact command line needed to list all visible files and directories (no hidden files), separated by a comma and a space, ordered by modification date, with a trailing slash (`/`) for directories.

## 💡 The Logic
The standard `ls` command is incredibly versatile if you know the right flags. 
* `-m`: Fills the width with a comma-separated list of entries.
* `-t`: Sorts by modification time, newest first.
* `-p`: Appends a `/` indicator to directories.

Because the subject specifically asks for "the command line" inside the file, we just need to echo those flags into `midLS`.

## 🛠️ Step-by-Step Solution

1. **Write the command into the file:**
   Combine the flags `-m`, `-t`, and `-p` into `-tmp`.
   ```bash
   echo "ls -tmp" > midLS
   ```

2. **Test it:**
   Run the file using bash to ensure the formatting matches the prompt exactly.
   ```bash
   bash midLS
   ```

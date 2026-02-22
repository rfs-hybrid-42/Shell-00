# 🟢 Exercise 08: clean

## 📝 Objective
Create a file called `clean` that contains a single command line to search for and delete all temporary files (ending in `~` or starting and ending in `#`) in the current directory and subdirectories.

## 💡 The Logic
The `find` command is built for this. 
* `.` : Look in the current directory.
* `-type f` : Look only for files.
* `\( ... \)` : Group logical conditions.
* `-name "*~" -o -name "#*#"` : Find files matching pattern 1 OR (`-o`) pattern 2.
* `-print` : Show the files found.
* `-delete` : Delete them.

## 🛠️ Step-by-Step Solution

1. **Write the command to the file:**
   *Note: We must use single quotes around the echo string so the terminal doesn't try to interpret the `*` or `~` right now.*
   ```bash
   echo 'find . -type f \( -name "*~" -o -name "#*#" \) -print -delete' > clean
   ```

2. **Test it safely:**
   Use `touch "test~" "#test#"` to create fake temporary files, then run `bash clean` to watch them get deleted.

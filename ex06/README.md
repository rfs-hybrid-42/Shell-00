# 🟢 Exercise 06: gitignore

## 📝 Objective
Write a short shell script named `git_ignore.sh` that lists all the existing files ignored by your Git repository.

## 💡 The Logic
Git uses a file called `.gitignore` to know which files to skip tracking. However, printing the `.gitignore` file isn't enough; we need Git to tell us exactly which existing files are currently being ignored. 
The plumbing command `git ls-files` is perfect for this.
* `--others` (or `-o`): Shows untracked files.
* `--ignored` (or `-i`): Shows only ignored files.
* `--exclude-standard`: Uses standard `.gitignore` rules to determine what is ignored.

## 🛠️ Step-by-Step Solution

1. **Create the shell script:**
   ```bash
   echo "git ls-files --others --ignored --exclude-standard" > git_ignore.sh
   ```

2. **Test it:**
   Create a dummy file, add it to `.gitignore`, and run `bash git_ignore.sh` to see if your script successfully detects it.

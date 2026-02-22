# 🟢 Exercise 05: GiT commit

## 📝 Objective
Write a shell script named `git_commit.sh` that displays the exact commit IDs (hashes) of the last 5 commits in your Git repository.

## 💡 The Logic
The `git log` command prints the commit history, but by default, it includes the author, date, and commit message. We need *only* the hash.
* `-n 5` or `-5`: Limits the output to the last 5 commits.
* `--format="%H"`: Formats the output to print *only* the full commit hash (`%H`).

## 🛠️ Step-by-Step Solution

1. **Create the shell script:**
   Use `echo` to redirect the correct Git command into the file.
   ```bash
   echo 'git log -n 5 --format="%H"' > git_commit.sh
   ```

2. **Test it:**
   Ensure you are inside a Git repository, then run:
   ```bash
   bash git_commit.sh
   ```

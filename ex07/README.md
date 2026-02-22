# 🟢 Exercise 07: diff

## 📝 Objective
You are given a `.diff` patch file (`sw.diff`) and an original text file (`a`). Your goal is to recreate the modified file (`b`) so that running `diff a b > sw.diff` perfectly recreates the patch file.

## 💡 The Logic
The `diff` command creates a "patch" (a roadmap of changes) between file A and file B. The `patch` command does the reverse: it takes file A and a patch file, and uses them to construct file B. 

## 🛠️ Step-by-Step Solution

1. **Apply the patch:**
   Use the `patch` command. Tell it to take file `a`, apply the changes found in `sw.diff`, and output (`-o`) the result to a new file named `b`.
   ```bash
   patch a sw.diff -o b
   ```

2. **Verify your work:**
   Run the exact command from the subject to ensure it doesn't fail.
   ```bash
   diff a b > sw.diff
   ```

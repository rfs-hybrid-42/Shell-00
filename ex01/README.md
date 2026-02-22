# 🟢 Exercise 01: testShell00

## 📝 Objective
Create a file named `testShell00` and modify its attributes (permissions) so that running `ls -l` matches a very specific output. Finally, compress it into a `.tar` archive.

## 💡 The Logic
File permissions in Unix are divided into three groups: **User** (owner), **Group**, and **Other**. 
* Read (`r`) = 4
* Write (`w`) = 2
* Execute (`x`) = 1

The target permissions are `-r--r-xr-x`. Breaking this down:
* User: `r--` (4 + 0 + 0 = 4)
* Group: `r-x` (4 + 0 + 1 = 5)
* Other: `r-x` (4 + 0 + 1 = 5)
This gives us the octal permission code `455`.

## 🛠️ Step-by-Step Solution

1. **Create the file:**
   ```bash
   touch testShell00
   ```

2. **Set the correct permissions:**
   Use the `chmod` command with the octal code we calculated.
   ```bash
   chmod 455 testShell00
   ```

3. **Verify the permissions:**
   ```bash
   ls -l testShell00
   ```
   *(Expected: `-r--r-xr-x`)*

4. **Create the tar archive:**
   The subject requires submitting `testShell00.tar`. Use the `tar` command with `-c` (create) and `-f` (file) flags.
   ```bash
   tar -cf testShell00.tar testShell00
   ```

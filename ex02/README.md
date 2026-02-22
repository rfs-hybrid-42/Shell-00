# 🟢 Exercise 02: Oh yeah, mooore...

## 📝 Objective
Create a specific hierarchy of files, directories, and symbolic links with precise permissions, sizes, and timestamps, so that `ls -l` outputs an exact match to the subject. Then, package everything into a `.tar` archive.

## 💡 The Logic
This exercise combines several Unix concepts:
* **`chmod`:** Setting file/directory permissions.
* **`touch -t`:** Forging specific creation timestamps.
* **`ln -s`:** Creating symbolic links (shortcuts that point to another file).
* **Directory Execute Permissions:** To enter a directory (`cd`), it must have the execute (`x`) permission.

## 🛠️ Step-by-Step Solution

1. **Create the files and directories:**
   ```bash
   mkdir test0 test2
   touch test1 test3 test4 test5
   ```

2. **Create the symbolic link:**
   `test6` needs to point to `test0`.
   ```bash
   ln -s test0 test6
   ```

3. **Set the required timestamps:**
   Use `touch -t YYYYMMDDHHMM` to set the exact dates from the subject. *(Note: The year doesn't matter as long as the time matches).*
   ```bash
   touch -t 202306012047 test0
   touch -t 202306012146 test1
   touch -t 202306012245 test2
   touch -t 202306012344 test3
   touch -t 202306012343 test4
   touch -t 202306012344 test5
   touch -h -t 202306012220 test6  # The -h flag applies the time to the symlink itself, not the target
   ```

4. **Set the correct permissions:**
   Calculate the octal codes based on the `ls -l` output requested in the subject.
   ```bash
   chmod 715 test0
   chmod 714 test1
   chmod 500 test2
   chmod 404 test3
   chmod 645 test4
   chmod 040 test5
   ```

5. **Package into a tar archive:**
   ```bash
   tar -cf ex02.tar *
   ```

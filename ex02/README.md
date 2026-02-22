# 🟢 Exercise 02: Oh yeah, mooore...

## 📝 Objective
Create a specific hierarchy of files, directories, and symbolic links with precise permissions, **sizes**, and timestamps, so that `ls -l` outputs an exact match to the subject. Then, package everything into a `.tar` archive.

## 💡 The Logic
This exercise combines several Unix concepts:
* **`chmod`:** Setting file/directory permissions.
* **`touch -t`:** Forging specific creation timestamps.
* **`ln -s`:** Creating symbolic links. The size of a symlink is dictated by the length of the string it points to (e.g., pointing to "test0" makes it 5 bytes automatically).
* **`truncate -s`:** Artificially setting exact file sizes (in bytes) to match the required output.

## 🛠️ Step-by-Step Solution

1. **Create the directories and files:**
   ```bash
   mkdir test0 test2
   touch test1 test3 test4 test5
   ```

2. **Set the exact file sizes:**
   Based on the subject's `ls -l` output, we must adjust the sizes of specific files:
   ```bash
   truncate -s 4 test1
   truncate -s 1 test3
   truncate -s 2 test4
   truncate -s 1 test5
   ```

3. **Create the symbolic link:**
   `test6` needs to point to `test0` (this automatically makes `test6` 5 bytes in size).
   ```bash
   ln -s test0 test6
   ```

4. **Set the required timestamps:**
   Use `touch -t YYYYMMDDHHMM` to set the exact dates.
   ```bash
   touch -t 202306012047 test0
   touch -t 202306012146 test1
   touch -t 202306012245 test2
   touch -t 202306012344 test3
   touch -t 202306012343 test4
   touch -t 202306012344 test5
   touch -h -t 202306012220 test6  # The -h flag applies the time to the symlink itself
   ```

5. **Set the correct permissions:**
   Calculate the octal codes based on the `ls -l` output.
   ```bash
   chmod 715 test0
   chmod 714 test1
   chmod 500 test2
   chmod 404 test3
   chmod 645 test4
   chmod 040 test5
   ```

6. **Verify and package into a tar archive:**
   Run `ls -l` to ensure all sizes, permissions, and timestamps are a perfect match, then archive:
   ```bash
   tar -cf ex02.tar *
   ```

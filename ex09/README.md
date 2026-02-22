# 🟢 Exercise 09: Illusions, not tricks, Michael...

## 📝 Objective
Create a "magic file" named `ft_magic` formatted to detect a custom file type ("42") by identifying the string "42" specifically at the 42nd byte of a file.

## 💡 The Logic
The `file` command in Unix identifies file types by reading the first few bytes (the header) and comparing them against a database of "magic numbers." 
We can write our own custom magic file database. The format generally requires three columns:
1.  **Offset:** Where in the file to look. The 42nd byte is index 41 (since we count from 0).
2.  **Type:** What type of data we are looking for (a `string`).
3.  **Value:** The actual data we want to find (`42`).
4.  **Message:** What to print if a match is found (`42`).

## 🛠️ Step-by-Step Solution

1. **Create the magic file definition:**
   ```bash
   echo '41 string 42 42' > ft_magic
   ```

2. **Test it:**
   Create a dummy file with exactly 41 garbage characters, followed by "42".
   ```bash
   # Create exactly 41 'A's, then '42'
   echo -n "AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA42" > dummy_test_file
   ```
   Now test it using the `file` command, passing your custom magic file with the `-m` flag:
   ```bash
   file -m ft_magic dummy_test_file
   ```
   *(Expected output: `dummy_test_file: 42`)*

# 🟢 Exercise 00: Z

## 📝 Objective
The goal of this exercise is to create a file named `z` that outputs "Z" followed by a newline whenever the `cat` command is used on it.

## 💡 The Logic
In Unix-like systems, you don't always need a text editor (like `vim` or `nano`) to create a file or write text to it. You can use the `echo` command to print text, and the `>` operator to redirect that output directly into a file. 

## 🛠️ Step-by-Step Solution

1. **Create the file and insert the text:**
   Use the `echo` command to output the letter Z, and redirect it into a new file called `z`.
   ```bash
   echo "Z" > z
   ```
   *(Note: `echo` automatically adds a newline at the end of the string by default, which perfectly satisfies the subject's requirement).*

2. **Verify the output:**
   Use the `cat` command to read the file.
   ```bash
   cat z
   ```
   **Expected Output:**
   ```text
   Z
   ```

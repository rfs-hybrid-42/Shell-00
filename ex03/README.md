# 🟢 Exercise 03: SSH me!

## 📝 Objective
Create your own SSH key pair and submit the public key in a file named `id_rsa_pub`. 

## 💡 The Logic
SSH (Secure Shell) keys are a much safer alternative to standard passwords for authenticating with servers like Git or the 42 intra. You generate a "pair" of keys:
* **Private Key:** Stays on your computer. Never share this.
* **Public Key:** The padlock you give to the server. You can share this freely.

The `ssh-keygen` command handles the creation of this pair.

## 🛠️ Step-by-Step Solution

1. **Generate the SSH Key Pair:**
   Run the following command. When prompted for a file to save the key, you can hit Enter to accept the default (`~/.ssh/id_rsa`).
   ```bash
   ssh-keygen -t rsa -b 4096
   ```

2. **Copy the Public Key into your repository:**
   The subject requires the file to be specifically named `id_rsa_pub`. You can use the `cat` command to read your newly generated public key and redirect it into your repository folder.
   ```bash
   cat ~/.ssh/id_rsa.pub > id_rsa_pub
   ```

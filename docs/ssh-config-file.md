# SSH Config File

This document teaches you how to:
- Find or create your SSH config file
- Tell SSH which key to use for GitHub
- Test that GitHub is using your key
- Fix common SSH config problems

The SSH config file lets you save connection settings so you do not have to type them every time.

This guide assumes that you already:
- Generated an SSH key
- Added the public key to your GitHub account
- Tested SSH at least once with GitHub

If you have not done those steps yet, start with `docs/1-start-here-basics.md`.

---

# What's the config file do?

TODO: Explain what the config file is in simple terms.

This file lives inside you .ssh folder along with your keys. It can store settings for different websites and servers including which keys to use. In `docs/1-start-here-basics.md`, keys were added to the ssh agent using ssh-add, but this will be reset on agent restart, including reboot. Updating the config file with your preferred settings will ensure that you don't need to run ssh-add every time you reboot.

---

# Find or Create Your SSH Config File

The config file is named `config`.

It does **not** have a file extension.

## Windows

The file should be located here:

```text
C:\Users\<your-username>\.ssh\config
```

TODO: Add Windows instructions for opening or creating this file.

Example command:

```powershell
notepad $env:USERPROFILE\.ssh\config
```

---

## MacOS/Linux

The file should be located here:

```text
~/.ssh/config
```

TODO: Add MacOS/Linux instructions for opening or creating this file.

Example commands:

```bash
touch ~/.ssh/config
nano ~/.ssh/config
```

---

# Add GitHub to Your SSH Config

Add this block to your SSH config file:

```sshconfig
Host github.com
    HostName github.com
    User git
    IdentityFile ~/.ssh/id_ed25519
    IdentitiesOnly yes
```

Keyword meanings:
- `Host github.com` means these settings are used when connecting to GitHub
- `HostName github.com` is the real server address
- `User git` is the SSH username GitHub expects
- `IdentityFile ~/.ssh/id_ed25519` tells SSH which private key to use
- `IdentitiesOnly yes` tells SSH to use this key instead of guessing

TODO: Add a screenshot or example of the completed file.

---

# If Your Key Has a Different Name

If your private key is not named `id_ed25519`, update the `IdentityFile` line.

Example:

```sshconfig
IdentityFile ~/.ssh/github-school-key
```

TODO: Explain how to check the exact key filename.

---

# Save and Close the File

TODO: Add editor-specific instructions.

Examples:
- Notepad
- VS Code
- nano
- vim/vi

---

# Test the GitHub Connection

Run:

```bash
ssh -T git@github.com
```

If it works, you should see a message that includes your GitHub username.

TODO: Add the expected success message and screenshot.

---

# Make Sure Your Repo Uses the SSH URL

Your GitHub remote should look like this:

```text
git@github.com:username/repo-name.git
```

It should **not** look like this:

```text
https://github.com/username/repo-name.git
```

Check your current remote:

```bash
git remote -v
```

TODO: Add instructions for changing an HTTPS remote to SSH.

---

# Common Problems

## Problem: GitHub Still Asks for a Password

TODO: Explain that the repo might be using an HTTPS remote instead of an SSH remote.

---

## Problem: SSH Uses the Wrong Key

TODO: Explain how to check the `IdentityFile` path and key filename.

---

## Problem: Bad Permissions

TODO: Add MacOS/Linux permissions fix.

Example:

```bash
chmod 600 ~/.ssh/config
```

---

## Problem: The Config File Has the Wrong Name

TODO: Explain that the file should be named `config`, not `config.txt`.

---

# Optional: Multiple GitHub Accounts

TODO: Add a future section for users who need separate school and personal GitHub keys.

Example structure:

```sshconfig
Host github-school
    HostName github.com
    User git
    IdentityFile ~/.ssh/school_key
    IdentitiesOnly yes
```

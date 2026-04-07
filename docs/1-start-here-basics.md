# Git Basics

This guide teaches you how to:
- Install git and initialize your git config name and email
- Generate an SSH key
- Get code from a repository
- Make changes
- Save your work
- Share your work with others

You are **not expected to understand everything yet**. just follow the steps.

---

## Core Concepts

Git is like a **save system for code**.

- **Repository (repo)** = the project folder
- **Commit** = a save point
- **Branch** = your personal workspace
- **Pull Request (PR)** = asking to merge your work into the project

The goal is to make changes without breaking other people’s work

---

# One-Time Setup
### <u>Setting Up Git</u>
#### Step 1:
Install git following the instructions provided by the devlopers. Windows users will want to use the standalone installer for their appropriate cpu architecture: <br>
https://git-scm.com/

#### Step 2:
Set your identity

```
git config --global user.name "Your Name"
git config --global user.email "your@email.com"
```

#### Step 3:
Setup your github account at:
```
https://github.com
```


### <u>Setting Up SSH</u>

#### Step 1:
Open your terminal and test that ssh is installed by typing the following:

Windows:

```
where.exe ssh
```

MacOS/Linux:
```
which ssh
```

Ask for help if an error is returned.

#### Step 2:
Generate your key with the following command. Use the email address associated with your github account:
```
ssh-keygen -t ed25519 -C "your_email@example.com"
```
When prompted for file location/name and password, continuously press enter: <br>
![ssh-keygen step2](https://github.com/soraWontForget/cs-club-git-guide/blob/docs/basics/img/ssh-gen-ex.png "Screenshot")

#### Step 3:
Add your ssh key to ssh-agent:

Windows:
```
Set-Service -Name ssh-agent -StartupType Automatic
Start-Service ssh-agent
ssh-add $env:USERPROFILE\.ssh\id_ed25519
```

MacOS/Linux:
```
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```

#### Step 4:
In your terminal, cat the contents of your public key: <br>
![ssh-keygen step4](https://github.com/soraWontForget/cs-club-git-guide/blob/docs/basics/img/cat-ssh-key.png "Screenshot")


#### Step 5:
Go to your github account and open your settings: <br>
![ssh-keygen step5](https://github.com/soraWontForget/cs-club-git-guide/blob/docs/basics/img/gh-settings-button.png "Screenshot")

#### Step 6:
Click on the ssh and gpg key menu button: <br>
![ssh-keygen step6](https://github.com/soraWontForget/cs-club-git-guide/blob/docs/basics/img/ssh-gpg-key-loc.png "Screenshot")

#### Step 7:
Click the Add New Key button: <br>
![ssh-keygen step7](https://github.com/soraWontForget/cs-club-git-guide/blob/docs/basics/img/new-ssh-key-but.png "Screenshot")

#### Step 8:
Name the key, select "Authentication Key" for the Key typoe and paste the whole key into the textbox: <br>
![ssh-keygen step8](https://github.com/soraWontForget/cs-club-git-guide/blob/docs/basics/img/add-new-ssh-key.png "Screenshot")

#### Step 9:
If successful, you should see the sucess toast message: <br>
![ssh-keygen step9](https://github.com/soraWontForget/cs-club-git-guide/blob/docs/basics/img/ssh-key-add-success.png "Screenshot")

#### Step 10:
In your terminal enter the following to test that your key is working with github: <br>
```
ssh -T git@github.com
```
![ssh-keygen step10](https://github.com/soraWontForget/cs-club-git-guide/blob/docs/basics/img/key-check.png "Screenshot")

---

## Clone the Project (First Time Only)

#### Step 1:
Navigate to the repo and click on the '<> Code' button:<br>
![clone-proj step1](https://github.com/soraWontForget/cs-club-git-guide/blob/docs/basics/img/gh-code-but.png "Screenshot")

#### Step 2:
Click on the "SSH" tab and copy the link: <br>
![clone-proj step2](https://github.com/soraWontForget/cs-club-git-guide/blob/docs/basics/img/gh-ssh-url.png "Screenshot")

#### Step 3:
In your terminal, navigate to the directory you want to download the repo to then type the following:

```
git clone <repo-ssh-url>
cd <repo-folder>
```

---

# Workflow

Follow these steps every time you work.

---

#### Step 1:
Get latest code from the `develop` branch

```
git checkout develop
git pull
```

---

#### Step 2:
Create a branch

```
git checkout -b feature/your-feature-name
```

Branch naming rules:
- lowercase only
- use hyphens (`-`)
- no spaces

Examples:
- `git checkout -b feature/login-page`
- `git checkout -b feature/nfc-attendance`
- `git checkout -b fix/navbar-alignment`
- `git checkout -b docs/instructions`

---

#### Step 3:
Make changes and commit

```
git add <filename>
git commit -m "feat: describe what you did"
```

Examples:
- `feat: add login button`
- `fix: correct typo in header`
- `docs: update workflow guide with examples`

---

#### Step 4:
Push your branch

```
git push origin feature/your-feature-name
```

---

#### Step 5:
Open a Pull Request

On GitHub:
- Click "Compare & Pull Request"
- Base branch: `develop`

Include:
- What you did
- How to test it

---

# Branch Strategy

Use:

- `main` → stable version
- `develop` → current working version
- `feature/*` → your work

Flow:

```
develop → feature → develop → main
```

---

# Rules

- Do NOT push directly to `main`
- Do NOT work directly on `develop`
- ALWAYS create a branch
- ALWAYS pull before starting work
- Use clear commit messages

---

## Commit Message Format

```
<type>: <what you did>
```

Types:
- `feat:` new feature
- `fix:` bug fix
- `docs:` documentation

---

## Definition of Done

Before opening a PR:
- Code runs
- You tested it
- You understand it
- Someone else can understand it

---

## If You Get Stuck

That’s normal!

Ask a club officer or another club member for help


---

# Checklist

You should be able to:

- [ ] Clone a repo
- [ ] Create a branch
- [ ] Commit changes
- [ ] Push to GitHub
- [ ] Open a Pull Request
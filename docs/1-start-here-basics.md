# Git Basics (CS Club)

## Purpose

This guide teaches you how to safely:
- Get code from a repository
- Make changes
- Save your work
- Share your work with others

You are **not expected to understand everything yet.** just follow the steps.

---

## Core Concept

Git is like a **save system for code**.

- **Repository (repo)** = the project folder
- **Commit** = a save point
- **Branch** = your personal workspace
- **Pull Request (PR)** = asking to merge your work into the project

Your goal:
> Make changes without breaking other people’s work

---

## One-Time Setup

### Install Git
https://git-scm.com/

### Set your identity

```
git config --global user.name "Your Name"
git config --global user.email "your@email.com"
```

---

## Clone the Project (First Time Only)

```
git clone <repo-url>
cd <repo-folder>
```

---

## Workflow

Follow these steps every time you work.

---

### Step 1: Get latest code from the `develop` branch

```
git checkout develop
git pull
```

---

### Step 2: Create a branch

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

### Step 3: Make changes and commit

```
git add <filename>
git commit -m "feat: describe what you did"
```

Examples:
- `feat: add login button`
- `fix: correct typo in header`
- `docs: update workflow guide with examples`

---

### Step 4: Push your branch

```
git push origin feature/your-feature-name
```

---

### Step 5: Open a Pull Request

On GitHub:
- Click "Compare & Pull Request"
- Base branch: `develop`

Include:
- What you did
- How to test it

---

## Branch Strategy (Simple)

We use:

- `main` → stable version
- `develop` → current working version
- `feature/*` → your work

Flow:

```
develop → feature → develop → main
```

---

## Rules

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

Ask:
- A club officer
- Another member

---

## Checklist

You should be able to:

- [ ] Clone a repo
- [ ] Create a branch
- [ ] Commit changes
- [ ] Push to GitHub
- [ ] Open a Pull Request
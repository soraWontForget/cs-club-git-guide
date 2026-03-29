

# Branching Strategy (CS Club)

## Purpose

This document explains how we organize our work using branches.

Our goal is to:
- Keep the project stable
- Allow multiple people to work at the same time
- Prevent people from breaking each other’s work

---

## Key Idea

Branches are **not folders** — they are separate timelines of work.

When you create a branch, you are making your own version of the project to safely work on.

---

## Our Branch Structure

We use three main types of branches:

### main
- The most stable version of the project
- Used for demos and milestones
- Should always work

Rules:
- No direct commits
- Only updated by merging from `develop`

---

### develop
- The current working version of the project
- Where completed features come together

Rules:
- Do not do regular work directly here
- Branch FROM `develop`
- Merge INTO `develop`

---

### feature/* and fix/*
- Your personal work branches

Examples:
- `feature/login-page`
- `feature/nfc-attendance`
- `fix/navbar-alignment`

Rules:
- One branch per task
- Keep branches small and focused
- Merge back into `develop` using a Pull Request

---

## Workflow Overview

```
develop → feature/your-work → develop → main
```

Step-by-step:
1. Start from `develop`
2. Create a branch
3. Do your work
4. Open a Pull Request into `develop`
5. After testing, `develop` is merged into `main`

---

## What NOT to Do

- Do NOT create branches like `develop/feature/...`
- Do NOT work directly on `main`
- Do NOT keep branches for too long without updating

---

## Branch Naming Rules

Format:

```
<type>/<short-description>
```

Rules:
- lowercase only
- use hyphens (`-`)
- no spaces
- keep names short and clear

Examples:
- `feature/desktop-app`
- `feature/web-login`
- `fix/button-alignment`

---

## How This Works With a Team

For a team of ~10 people:

- Everyone works on their own branch using the `develop` branch as a starting point
- Work happens in parallel
- Changes are combined in `develop`
- Stable versions are moved to `main`

This prevents conflicts and keeps the project organized.

---

## Simple Explanation

> “You don’t work inside develop — you branch off of it.”

---

## Summary

- `main` = stable
- `develop` = team progress
- `feature/*` = your work

Keep it simple. Keep it consistent.
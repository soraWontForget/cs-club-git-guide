# Workflow

This document shows the full workflow from starting work to merging it into the project.

If you are unsure what to do when working on a task, follow this guide.

---

## Key Idea

```text
develop → feature → commit → push → PR → develop → main
```

 You work on your own branch, then merge your work back into the team.

---

# Example: Adding a Login Button

Let’s walk through a real example whgere you are adding a login button to the project.

#### Step 1:
Get the latest code from the `develop` branch.

```bash
git checkout develop
git pull
```

Always start here so you are working on the latest version.


#### Step 2:
Create your branch

```bash
git checkout -b feature/login-button
```

This is your personal workspace. No one else is working here.

#### Step 3:
Do your work

- Add your code
- Comment your code
- Edit files
- Create new files if needed

Examples of a milestone of work done:
- Complete the implementation of a function
- Update UI with a pane of buttons
- Connect a set of UI elements to functions


#### Step 4:
Save your work

```bash
git add <filename>
git commit -m "feat: add login button"
```

Think of this as saving your progress.
Perform a commit when you've reached a milestone in your program progress.
Commit messages should be short and use imparative present tense:
- feat: add login button to homepage
- fix: correct navbar alignment on mobile
- docs: update workflow guide with examples

Let your comments in the code itself explain in detail.

#### Step 5:
Push your branch

```bash
git push --set-upstream origin feature/login-button
```

This uploads your work to GitHub.

#### Step 6:
Open a Pull Request (PR)

When your task is complete, open a pull request

On GitHub:
- Click "Compare & Pull Request"
- Base branch: `develop`

Include:
- Summary of what you did
- How to test it

#### Step 7:
Review and Merge

- Another member (usually a maintainer) reviews your code
- Changes may be requested
- Once approved, your branch is merged into `develop`

#### Step 8:
Promote to main (maintainers only)

Later, when `develop` is stable:

```bash
git checkout main
git pull
git merge develop
git push
```

This updates the `main` stable version of the project.

---

# Repeat the Process

Every new task = new branch

Example:
- `feature/signup-page`
- `fix/login-error`
- `docs/update-readme`

---

# Keeping Your Branch Updated

If others have made changes:

```bash
git checkout develop
git pull
git checkout feature/login-button
git merge develop
```

This prevents merge conflicts later.

---

# Common Mistakes

#### Mistake 1: Forgetting to pull first
- You may get conflicts later.

#### Mistake 2: Working directly on `develop`
- This can break the shared project.

#### Mistake 3: Huge branches
- Large changes are harder to review and merge.

#### Mistake 4: Mixing multiple features in one branch
- Keep branches focused on one task.
---

# Summary

- Start from `develop`
- Create a branch
- Make changes
- Commit your work
- Push your branch
- Open a PR
- Merge into `develop`
- Later merge into `main`

Keep it simple. Follow the steps.

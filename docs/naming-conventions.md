# Naming Conventions
This document defines our naming conventions for files, folders, branches, and code.

Our goal is to:
- keep projects readable
- reduce confusion
- make collaboration easier
- avoid mixing styles in the same repo

Consistency matters more than perfection.

---

## General Rule

Pick one style for each category and use it consistently.

We do **not** want a mix like:
- `loginPage`
- `login_page`
- `LoginPage`
- `login-page`

in the same project unless there is a clear language-specific reason.

---

# Files and Folders Names

Use **kebab-case** for folders:
- my-project
- docs
- desktop-app
- nfc-attendance

### Rules
- lowercase only
- use hyphens (`-`)
- no spaces

### Good
- `level-1-basics.md`
- `pull-request-template.md`
- `event-calendar.js`

### Avoid
- `Level1Basics.md`
- `level_1_basics.md`
- `eventCalendar.js`

---

## Special Files

Some files follow standard naming conventions and should **NOT** be changed:

```text
README.md
LICENSE
.gitignore
Dockerfile
```

Always follow tool or ecosystem expectations when they exist.

---

# Branch Names

Format:

```text
<type>/<short-description>
```

### Examples
- `feature/login-page`
- `fix/navbar-alignment`
- `docs/git-basics`

### Rules
- lowercase only
- use hyphens (`-`)
- no spaces

---

# Commit Messages

Format:

```text
<type>: <short description>
```

### Examples
- `feat: add login button`
- `fix: correct navbar alignment`
- `docs: add naming conventions guide`

### Types
- `feat:` new feature
- `fix:` bug fix
- `docs:` documentation
- `refactor:` cleanup
- `test:` testing
- `chore:` maintenance

---

# Code Naming

## Important Rule

Follow the language or framework’s standard when it exists.

Examples:
- Python → `snake_case`
- JavaScript → `camelCase`
- C# / Java → `PascalCase` for classes
- React components → `PascalCase`

If a language has a strong convention, **follow it over the club standard**.

---

## Variables and Functions

### camelCase (most common in JS, Java, C#)

```text
userName
totalScore
getUserProfile()
renderLoginPage()
```

### snake_case (Python style)

```text
user_name
total_score
get_user_profile()
```

---

## Classes and Structs

Use **PascalCase**:

```text
UserProfile
LoginPage
AttendanceScanner
```

---

## Constants

Use **UPPER_SNAKE_CASE**:

```text
MAX_USERS
DEFAULT_TIMEOUT
API_BASE_URL
```

---

## Private Fields (optional)

Some languages like python use prefixes:

```text
_userName
_cachedResult
```

Use consistently if your project uses them.

---

# Language-Specific Overrides

If a language or framework defines a style, it takes precedence.

### Examples:

#### Python
- files → `snake_case.py`
- variables → `snake_case`
- classes → `PascalCase`

#### C++
- varies by project
- often:
  - classes → `PascalCase`
  - functions → `camelCase` or `snake_case`

#### Web (HTML/CSS/JS)
- files → `kebab-case`
- JS variables → `camelCase`
- React components → `PascalCase`

---

# Rule of Thumb

If unsure:

- files/folders → `kebab-case`
- branches → `type/kebab-case`
- variables/functions → `camelCase`
- classes → `PascalCase`
- constants → `UPPER_SNAKE_CASE`

---

# Summary

Default styles:

- files/folders → `kebab-case`
- branches → `type/kebab-case`
- variables/functions → `camelCase`
- classes → `PascalCase`
- constants → `UPPER_SNAKE_CASE`

Follow language conventions when they exist.  
Otherwise, follow this guide.
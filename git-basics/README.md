# Git Commands for DevOps (Basics → Advanced)

## 📌 Overview
This document covers commonly used Git commands in DevOps workflows.  
Each command includes a short explanation and example for quick reference.

---

## 🔹 Repository Setup

### git init
**Purpose:** Initialize a new repository

```bash
git init
```

### git clone
**Purpose:** Clone an existing repository

```bash
git clone https://github.com/org/project.git
```

---

## 🔹 Staging & Committing

### git status
**Purpose:** Show current changes

```bash
git status
```

### git add
**Purpose:** Stage a file for commit

```bash
git add app.py
git add .  # Stage all changes
```

### git commit
**Purpose:** Commit staged changes with a message

```bash
git commit -m "Add login feature"
git commit -am "Update configuration"  # Stage and commit tracked files
```

---

## 🔹 Branching & Merging

### git branch
**Purpose:** Create, list, or delete branches

```bash
git branch                    # List local branches
git branch feature/login      # Create a new branch
git branch -d feature/login   # Delete a branch
```

### git checkout
**Purpose:** Switch to a different branch

```bash
git checkout feature/login
git checkout -b feature/login # Create and switch to new branch
```

### git switch
**Purpose:** Switch branches (modern alternative to checkout)

```bash
git switch feature/login
git switch -c feature/login   # Create and switch to new branch
```

### git merge
**Purpose:** Merge a branch into the current branch

```bash
git checkout main
git merge feature/login
```

---

## 🔹 Collaboration

### git push
**Purpose:** Push branch to remote repository

```bash
git push origin feature/login
git push -u origin feature/login  # Set upstream tracking
git push origin --all             # Push all branches
```

### git pull
**Purpose:** Pull latest changes from remote

```bash
git pull origin main
git pull --rebase origin main     # Pull with rebase instead of merge
```

### git fetch
**Purpose:** Download changes without merging

```bash
git fetch origin
git fetch --all                   # Fetch from all remotes
```

---

## 🔹 Viewing History

### git log
**Purpose:** View commit history

```bash
git log --oneline                 # Compact history
git log --oneline -10             # Last 10 commits
git log --graph --all --oneline   # Visual branch history
git log --author="DevOps"         # Filter by author
```

### git diff
**Purpose:** Show changes before commit

```bash
git diff                          # Unstaged changes
git diff --staged                 # Staged changes
git diff main..feature/login      # Compare branches
```

### git show
**Purpose:** Display commit details

```bash
git show abc123
git show HEAD~1                   # Show previous commit
```

---

## 🔹 Advanced Commands

### git rebase
**Purpose:** Reapply commits on top of another branch (clean history)

```bash
git checkout feature/login
git rebase main
```

### git cherry-pick
**Purpose:** Apply a specific commit to current branch

```bash
git cherry-pick abc123
git cherry-pick abc123 def456     # Multiple commits
```

### git stash
**Purpose:** Save unfinished work temporarily

```bash
git stash                         # Save changes
git stash list                    # List all stashes
git stash pop                     # Apply and remove stash
git stash apply                   # Apply without removing
```

### git revert
**Purpose:** Undo a commit safely (creates new commit)

```bash
git revert abc123
git revert HEAD                   # Revert last commit
```

### git reset
**Purpose:** Undo commits (use with caution)

```bash
git reset --soft HEAD~1           # Undo last commit, keep changes staged
git reset --mixed HEAD~1          # Undo last commit, keep changes unstaged
git reset --hard HEAD~1           # Undo last commit, discard changes
```

---

## 🔹 Release Management

### git tag
**Purpose:** Create a tag for release versions

```bash
git tag v1.0.0                    # Lightweight tag
git tag -a v1.0.0 -m "Release 1.0.0"  # Annotated tag
git push origin v1.0.0            # Push tag to remote
git push origin --tags            # Push all tags
```

### git describe
**Purpose:** Get readable version info

```bash
git describe --tags
git describe --tags --abbrev=0    # Latest tag only
```

---

## 🔹 Common DevOps Workflows

### Feature Branch Workflow

```
main (production)
  ↓
  └─→ feature/login (development)
       ↓
       └─→ commit → push → Pull Request → code review → merge back to main
```

**Steps:**
```bash
git checkout -b feature/login
# Make changes
git add .
git commit -m "Add login feature"
git push -u origin feature/login
# Create Pull Request on GitHub
# After merge
git checkout main
git pull origin main
```

---

### Gitflow Workflow

```
main (production releases)
  ↓
  ├─→ release/v1.0 (release candidates)
  │    ↓
  │    └─→ merge to main + develop
  │
develop (staging/integration)
  ↓
  ├─→ feature/* (new features)
  │
  ├─→ bugfix/* (bug fixes)
  │
  └─→ hotfix/* (production fixes)
       ↓
       └─→ merge to main + develop
```

**Example:**
```bash
# Start feature
git checkout -b feature/auth develop

# Finish feature
git checkout develop
git merge --no-ff feature/auth

# Create release
git checkout -b release/v1.0 develop
# Fix bugs only
git checkout main
git merge --no-ff release/v1.0
git tag -a v1.0
```

---

## 🔹 Useful Aliases

Add these to your `.gitconfig` to speed up workflow:

```bash
git config --global alias.st status
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.unstage 'reset HEAD --'
git config --global alias.last 'log -1 HEAD'
git config --global alias.visual 'log --graph --oneline --all'
```

---

## 🔹 Best Practices for DevOps

✅ **DO:**
- Write clear commit messages
- Use feature branches for new work
- Push regularly to avoid losing work
- Use tags for release versions
- Review code before merging
- Keep commits atomic (one logical change per commit)

❌ **DON'T:**
- Force push to shared branches (`git push -f origin main`)
- Commit sensitive data (passwords, tokens, keys)
- Use rebase on shared branches
- Ignore merge conflicts
- Make huge commits with multiple unrelated changes

---

## 📚 Additional Resources

- [Official Git Documentation](https://git-scm.com/doc)
- [GitHub Flow Guide](https://guides.github.com/introduction/flow/)
- [Gitflow Workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow)
- [Conventional Commits](https://www.conventionalcommits.org/)

---

**Last Updated:** 2026-02-19 09:19:01  
**Maintained by:** DevOps Team
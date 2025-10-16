# Git Workflow Guide

Understanding the Git workflow is essential for saving and publishing your work. This guide covers the three main commands you'll use every time you make changes.

## The Three-Step Git Workflow

Every time you make changes to your files, you'll follow these three steps:

### 1. Add (Stage Your Changes)

```bash
git add .
```

This command stages all your changes, preparing them to be saved. Think of it as putting your files in a box, ready to be shipped.

**What it does:**
- Tells Git which files you want to save
- The `.` means "add all changed files"
- You can also add specific files: `git add index.html`

### 2. Commit (Save Your Changes)

```bash
git commit -m "Your descriptive message here"
```

This command saves your changes with a message describing what you did. Think of it as sealing the box and writing a label on it.

**What it does:**
- Creates a snapshot of your changes
- The `-m` flag lets you add a message
- Messages should be clear and descriptive

**Good commit messages:**
- ✅ "Add About Me page with bio and interests"
- ✅ "Fix broken image link"
- ✅ "Update contact form with email field"

**Bad commit messages:**
- ❌ "changes"
- ❌ "stuff"
- ❌ "asdfasdf"

### 3. Push (Publish Your Changes)

```bash
git push origin main
```

This command sends your saved changes to GitHub. Think of it as shipping the box to its destination.

**What it does:**
- Uploads your commits to GitHub
- Makes your changes visible in your GitHub repository
- Triggers a new deployment on Render (if set up)

## Complete Workflow Example

Here's what a typical workflow looks like:

```bash
# 1. Check what files have changed
git status

# 2. Stage all changes
git add .

# 3. Commit with a descriptive message
git commit -m "Add About Me page with personal bio"

# 4. Push to GitHub
git push origin main
```

## Before You Start: Check Your Status

Always check what's changed before you add and commit:

```bash
git status
```

This shows you:
- Which files have been modified
- Which files are staged
- Which files are untracked (new files Git doesn't know about yet)

## Common Scenarios

### Scenario 1: Created a New HTML File

```bash
git status                    # See the new file listed as "untracked"
git add .                     # Stage the new file
git commit -m "Add new portfolio page"
git push origin main          # Publish to GitHub
```

### Scenario 2: Modified Existing Files

```bash
git status                    # See which files were modified
git add .                     # Stage all changes
git commit -m "Update bio section with new information"
git push origin main          # Publish to GitHub
```

### Scenario 3: Multiple Changes

```bash
git status                    # Review all changes
git add .                     # Stage everything
git commit -m "Add contact form, update styles, fix typos"
git push origin main          # Publish to GitHub
```

## Troubleshooting

### Error: "Your branch is behind"

This means the version on GitHub is newer than your local version.

**Solution:**
```bash
git pull origin main          # Get the latest changes from GitHub
# Then continue with your add/commit/push
```

### Error: "Please tell me who you are"

Git needs to know your identity for commits.

**Solution:**
```bash
git config --global user.email "your@email.com"
git config --global user.name "Your Name"
```

### Error: "Nothing to commit"

You haven't made any changes, or your changes are already committed.

**Solution:**
- Make sure you've actually saved your files in VS Code
- Check `git status` to see what's going on

### Error: "Failed to push"

This can happen for various reasons, often if GitHub is ahead of your local copy.

**Solution:**
```bash
git pull origin main          # Get latest changes
git push origin main          # Try pushing again
```

## Best Practices

1. **Commit often** - Don't wait until you've made tons of changes. Commit after each logical piece of work.

2. **Write clear messages** - Future you (and your teammates) will appreciate knowing what each commit does.

3. **Check before you commit** - Use `git status` to review what you're about to commit.

4. **Pull before you push** - If working with others, always pull the latest changes before pushing yours.

5. **Don't commit broken code** - Make sure your HTML is valid before committing.

## Quick Reference

```bash
# See what's changed
git status

# Stage all changes
git add .

# Stage a specific file
git add filename.html

# Commit with message
git commit -m "Description of changes"

# Push to GitHub
git push origin main

# Pull latest changes
git pull origin main

# See commit history
git log

# See commit history (compact)
git log --oneline
```

---

[← Back to Class 5](../classes/05/)

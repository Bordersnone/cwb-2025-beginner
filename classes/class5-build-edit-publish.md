# Class 5 - Build, Edit, and Publish Your First Page

**Lead:** Kiley  
**Assistant:** Timotej  
**Date:** October 7, 2025

## 📝 What We Actually Covered

> **Note:** We adjusted our plans based on student needs! Instead of completing the full deployment + build workflow, we focused deeply on Git fundamentals to ensure everyone has a solid foundation.

### Git from the Ground Up

We discovered that some students weren't clear on Git commands, so we started from the very beginning and built up understanding piece by piece.

#### Understanding Git Commands & Syntax
- **Why spaces matter** - Discussed why `git add.` doesn't work but `git add .` does
- **Command structure** - Broke down how terminal commands are structured (command + subcommand + arguments)
- **Getting help** - Introduced the `-h` and `--help` flags for any command

#### What is a Repository?
- Used the **post office metaphor** to explain Git concepts
- A repository is like a post office where you prepare packages to ship

#### The Git Workflow (Post Office Metaphor)

1. **`git init`** - Announcing you want to ship something
   - Like walking into a post office and saying "I have things to ship"
   - Initializes a new Git repository

2. **`git add`** - Packing boxes
   - Like choosing what items go into which boxes
   - We explored several variations:
     - `git add .` - Add ALL changes in the current directory
     - `git add filename.html` - Add a specific file
     - **What `.` means** - Current directory
     - **What `..` means** - Parent directory
     - **Why `git add.` fails** - No space between command and argument
   - Discussed that both `git add .` and `git add tuesday_git_example.html` can achieve the same result if there's only one change
   - **Selective staging** - Sometimes you DON'T want to add everything (e.g., `test_dont_share.html`, `timotej_bank_account.html`)
   - **Unstaging files** - What to do if you accidentally add a file you didn't mean to

3. **`git commit`** - Taping up the box
   - Like sealing your package before shipping
   - Once taped, you can still modify it, but it's more complicated
   - **Importance of commit messages** - Labeling what's in the box

4. **Git Remotes & `origin`**
   - Explained what a "remote" is - the destination where you're shipping
   - **What is `origin`?** - The default name for your remote repository
   - You can have multiple remotes pointing to different places
   - Used `git remote` command to view configured remotes

5. **Branches**
   - Discussed **branches and trunks** - the tree analogy
   - **History of Git** - Why branching matters for collaboration
   - **`main` vs `master`** - The naming change and why GitHub made it
   - **`origin/main`** - How your local `main` branch relates to GitHub's `main` branch

6. **`git push origin main`** - Shipping the package
   - Pushed code to GitHub successfully!
   - Everything synced and ready for deployment

### Key Moments
- ✅ Created a file called `tuesday_git_example.html` to practice
- ✅ Intentionally staged/unstaged files to see what happens
- ✅ Emphasized taking notes (2 out of 3 students took notes, 1 very detailed!)

### What We Skipped
We started confirming Render configurations but pivoted to focus on Git fundamentals when we discovered the knowledge gap. Most students had Render set up, but one hadn't connected her GitHub repository yet.

## 🎯 Original Planned Goals

Below is what we originally planned to cover (for reference):

1. ~~**Confirm Render deployment**~~ - Partially started, will complete next class
2. ~~**Build your "About Me" HTML page**~~ - Postponed
3. **Practice the Git workflow** - ✅ Covered in depth!
4. ~~**Complete a mini-challenge**~~ - Postponed
5. **Wrap-up and reflection** - ✅ Completed

## 📚 Class Structure (Original Plan)

<details>
<summary>Click to expand original lesson plan</summary>

### 1. Confirm Render Deployment

We'll start by making sure everyone's Render deployment is working correctly.

[→ Render Deployment Check Guide](./steps/render-deployment-check.md)

### 2. Build Your "About Me" Page

Time to create your first complete web page! We'll build an "About Me" page that includes:

- A proper HTML5 structure
- Headings and paragraphs
- Lists of your interests or hobbies
- Links to your social media or projects
- At least one image

[→ HTML About Page Guide](./steps/html-about-page.md)

### 3. Practice the Git Workflow

Learn the essential Git commands to save and publish your work:

- `git add` - Stage your changes
- `git commit` - Save your changes with a message
- `git push` - Publish your changes to GitHub

[→ Git Workflow Guide](./steps/git-workflow.md)

### 4. Mini-Challenge

Once your About Me page is live, enhance it by adding one of the following:

- An embedded video
- A contact form
- A table with information about yourself

[→ Mini-Challenge Guide](./steps/mini-challenge.md)

</details>

## 🏠 Homework & Practice

Practice what we learned in this class (Class #5)! Complete these exercises to reinforce your Git knowledge.

### Required Practice

**1. Practice Git Commands with a New File**

Create a new HTML file and practice the full Git workflow:

```bash
# 1. Create a new file
# Use VS Code or your text editor to create: practice_git.html

# 2. Stage your changes
git add practice_git.html

# 3. Commit your changes
git commit -m "Add practice Git file"

# 4. Push to GitHub
git push origin main
```

**2. Experiment with Selective Staging**

Create multiple files and practice adding them selectively:

1. Create 3 new files: `file1.html`, `file2.html`, `file3.html`
2. Add only `file1.html` and `file2.html` to staging (not `file3.html`)
3. Check what's staged using `git status`
4. Commit the staged files
5. Then stage and commit `file3.html` separately

**3. Use the Help Flag**

Practice using the help documentation:

```bash
# Try these commands
git add --help
git commit -h
git status --help
```

Pick one command and write down 3 things you learned from the help documentation.

### Extra Credit (Optional)

**Challenge: Fix a Mistake**

1. Create a file called `secret.html`
2. Accidentally stage it with `git add .`
3. Figure out how to unstage it (use `git status` for hints!)
4. Delete the file
5. Stage and commit something else instead

**Exploration: Branch Basics**

Look up what these commands do (you don't have to run them yet):
- `git branch`
- `git branch <branch-name>`
- `git checkout <branch-name>`

Write a few sentences about what you think branches are used for.

## 📖 Resources for Review

- [Git Workflow Guide](./steps/git-workflow.md) - Step-by-step Git commands
- [GitHub Git Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf) - Quick reference
- [Git Documentation](https://git-scm.com/doc) - Official Git docs

## ✅ What You Should Know After This Class

- ✅ What a Git repository is and why we use it
- ✅ The difference between `git add .` and `git add filename.html`
- ✅ What `.` and `..` mean in terminal commands
- ✅ Why spaces matter in commands
- ✅ How to use `-h` and `--help` flags
- ✅ What "staging" means in Git
- ✅ How to commit changes with a message
- ✅ What remotes are and what `origin` means
- ✅ The difference between `main` and `master` branches
- ✅ How to push code to GitHub

## 🔜 Next Class

In our next class, we'll:
- Complete Render deployment setup for everyone
- Build the "About Me" page
- Practice the full workflow: code → Git → GitHub → Render deployment

---

← [Class 4 - Media and Links](./class4-media-and-links.md) | [Class 6 - TBD](./class6-tbd.md) →

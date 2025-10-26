# Class 07 - Deploy Your First Complete Web Page

**Lead:** Kiley  
**Assistant:** Timotej  
**Date:** October 14, 2025

> **Note:** Class 6 (October 9) was skipped due to lack of attendance.

---

## 🎯 Class Goals

Today we bring everything together! You'll see your code go live on the internet.

1. **Verify Render deployment** - Make sure everyone's Render is connected and working
2. **Build your "About Me" page** - Create a complete, professional HTML page
3. **Master the full workflow** - Code → Git (or push.bat) → GitHub → Render → Live!
4. **Troubleshoot like a developer** - Learn to fix common deployment issues

---

## 📝 What You Already Know

Before we start, let's recognize how much you've learned:

### From Class 1: HTML Tag Types
- ✅ 5 types of tags: wrappers, text, boxes, media, user input
- ✅ Common elements: `<p>`, `<h1>-<h6>`, `<div>`, `<span>`, `<img>`, `<a>`
- ✅ Attributes: `id`, `class`, `src`, `href`

### From Class 2: Developer Tools & Automation
- ✅ VS Code shortcuts (Ctrl+Arrow, Ctrl+S, Tab indent, etc.)
- ✅ `push.bat` automation script for quick Git workflow
- ✅ All accounts set up: GitHub, Render, etc.

### From Class 3: HTML Structure
- ✅ Proper HTML5 document structure
- ✅ Semantic elements: `<header>`, `<main>`, `<footer>`, `<section>`
- ✅ Lists: `<ul>`, `<ol>`, `<li>`

### From Class 4: Paths & Links
- ✅ Absolute vs relative paths
- ✅ Linking to images, videos, and other pages
- ✅ File structure navigation

### From Class 5: Git Fundamentals
- ✅ The **post office metaphor** for Git
- ✅ Git commands: `init`, `add`, `status`, `commit`, `push`, `log`
- ✅ Why spacing and syntax matter (`git add.` vs `git add .`)
- ✅ What `origin` means and how remotes work

---

## 📚 Today's Class Structure

### Part 1: Verify Render Deployment (15-20 minutes)

Let's make sure everyone's deployment pipeline is working.

#### What to Check:
1. **GitHub Repository**
   - Go to your GitHub repo
   - Verify you have an `index.html` file
   - Make sure it has some HTML content

2. **Render Connection**
   - Log in to [render.com](https://render.com)
   - Find your web service in the dashboard
   - Check that it's connected to your GitHub repository
   - Verify the branch is set to `main`

3. **Test Deployment**
   - Make a small change to your `index.html` (add a comment or change text)
   - Use one of these methods to deploy:
     - **Option A:** Run `push.bat` (Windows users)
     - **Option B:** Manual Git workflow:
       ```bash
       git add .
       git commit -m "Test deployment"
       git push origin main
       ```
   - Watch Render deploy automatically (check the "Events" tab)
   - Visit your live URL to see the change

**Troubleshooting Guide:** [render-deployment-check.md](./render-deployment-check.md)

---

### Part 2: Build Your "About Me" Page (30-40 minutes)

Time to create something you're proud of!

#### Required Elements:
Your "About Me" page must include:

- [ ] Proper HTML5 structure (`<!DOCTYPE html>`, `<html>`, `<head>`, `<body>`)
- [ ] Semantic structure (`<header>`, `<main>`, `<footer>`)
- [ ] Multiple sections with `<section>` tags
- [ ] Headings (`<h1>`, `<h2>`, etc.)
- [ ] Paragraphs describing yourself
- [ ] At least one list (`<ul>` or `<ol>`)
- [ ] At least two links (`<a href="">`)
- [ ] Descriptive `<title>` in the head

#### Suggested Structure:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>About [Your Name]</title>
</head>
<body>
    <header>
        <h1>About Me</h1>
    </header>

    <main>
        <section>
            <h2>Introduction</h2>
            <p>Hi! I'm [Your Name]...</p>
        </section>

        <section>
            <h2>My Interests</h2>
            <ul>
                <li>Learning web development</li>
                <li>[Your hobby]</li>
                <li>[Another interest]</li>
            </ul>
        </section>

        <section>
            <h2>My Goals</h2>
            <ol>
                <li>Build my own website</li>
                <li>Learn CSS and JavaScript</li>
                <li>[Your goal]</li>
            </ol>
        </section>

        <section>
            <h2>Connect With Me</h2>
            <p>
                <a href="mailto:your@email.com">Email me</a> | 
                <a href="https://github.com/yourusername" target="_blank">GitHub</a>
            </p>
        </section>
    </main>

    <footer>
        <p>&copy; 2025 [Your Name]. Built in Borders:None Web Dev class.</p>
    </footer>
</body>
</html>
```

**Full Guide:** [html-about-page.md](../01-most-common-tags/steps/html-about-page.md)

---

### Part 3: Deploy and See It Live! (20-30 minutes)

This is where the magic happens!

#### Workflow Options:

**Option A: Using push.bat (Quick & Easy)**
1. Save your HTML file in VS Code (Ctrl+S)
2. Double-click `push.bat` or run it from terminal
3. Wait for Render to deploy (check the dashboard)
4. Visit your live URL!

**Option B: Manual Git Workflow (Understanding Each Step)**
1. Save your HTML file
2. Open terminal/command prompt
3. Run these commands:
   ```bash
   git status              # See what changed
   git add .              # Stage all changes
   git commit -m "Add complete About Me page"
   git push origin main   # Push to GitHub
   ```
4. Render automatically detects the push and deploys
5. Visit your live URL!

**Remember:** Each `git push` triggers a new deployment on Render automatically!

---

### Part 4: Mini-Challenge (If Time Permits)

Enhance your page with one of these:

1. **Add an image** - Your photo or something that represents you
2. **Add a table** - Show your skills, schedule, or favorites
3. **Add a video** - Embed a YouTube video you like
4. **Add a form** - Simple contact form (won't send yet, just practice)

**Ideas & Examples:** [mini-challenge.md](../01-most-common-tags/steps/mini-challenge.md)

---

## 🏠 Homework & Practice

### Required Practice

**1. Complete Your About Me Page**

If you didn't finish in class, complete all required elements:
- Proper structure
- Multiple sections
- Lists
- Links
- Personal content

**2. Practice the Full Workflow 3 Times**

Make three different small changes and deploy each one:

**Change 1:** Add a new section or paragraph
- Save → `push.bat` (or Git workflow) → Check live site

**Change 2:** Add an image or link
- Save → `push.bat` (or Git workflow) → Check live site

**Change 3:** Update your footer or add more interests
- Save → `push.bat` (or Git workflow) → Check live site

**3. Master Git Status Checking**

At each step of your workflow, check the status:

```bash
# After making changes (before adding)
git status

# After staging (before committing)
git add .
git status

# After committing (before pushing)
git commit -m "Your message"
git status

# After pushing
git push origin main
git status
```

Notice how the status changes at each step!

---

### Extra Credit (Optional)

**Challenge 1: Add All Three Enhancements**
- An image
- A table
- A video or form

**Challenge 2: Create a Multi-Page Site**
- Create a second page (`projects.html` or `contact.html`)
- Add navigation links between pages
- Deploy both pages

**Challenge 3: Experiment with VS Code Shortcuts**
- Practice using Ctrl+Arrow keys for navigation
- Use Tab/Shift+Tab for indentation
- Challenge yourself to code without using the mouse

---

## 📖 Resources

### Guides for Today
- [Render Deployment Check](./render-deployment-check.md) - Troubleshooting deployment
- [Git Workflow Guide](../05-git-workflow/git-workflow.md) - Detailed Git commands
- [HTML About Page](../01-most-common-tags/steps/html-about-page.md) - Building your page
- [Mini-Challenge](../01-most-common-tags/steps/mini-challenge.md) - Enhancement ideas

### Tools Reference
- [push.bat script](../02-setup-&-vscode/push.bat) - Automation script
- [VS Code Shortcuts](../02-setup-&-vscode/vscode-shorcuts.txt) - Keyboard shortcuts

### Online References
- [MDN - HTML Structure](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Document_and_website_structure)
- [GitHub Git Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf)
- [W3C HTML Validator](https://validator.w3.org/) - Check your HTML

---

## ✅ What You Should Know After This Class

By the end of today, you should:

- ✅ Understand the full development workflow: Code → Git → GitHub → Render → Live Site
- ✅ Know how to verify Render deployment is working
- ✅ Be able to build a complete, well-structured HTML page from scratch
- ✅ Use either `push.bat` or manual Git commands confidently
- ✅ Troubleshoot basic deployment issues
- ✅ Understand that every `git push` triggers automatic deployment
- ✅ Check `git status` at different workflow stages
- ✅ Have a live website URL you can share with others!

---

## 🔜 Next Class

In our next class, we'll begin learning **CSS** - the styling language that makes websites beautiful!

We'll cover:
- What CSS is and how it works with HTML
- Adding colors, fonts, and backgrounds
- Making your About Me page look professional
- Basic layout and spacing

---

## 🎓 You're a Web Developer Now!

Once you have a live website on the internet, you're officially a web developer. Congratulations!

Your site might be simple now, but:
- You understand HTML structure
- You know Git version control
- You can deploy to the cloud
- You have a foundation to build on

**These are professional skills** that developers use every single day.

---

← [Class 5 - Git & Build, Edit, Publish](../05-git-workflow/) | [Class 8 - About Me Page & CSS Intro](../08-css-text/) →

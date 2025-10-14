# Class 6 - Deploy Your First Page

**Lead:** Kiley  
**Assistant:** Timotej  
**Date:** October 14, 2025

## 🎯 Class Goals

In this class, we'll complete the deployment workflow and build your first complete web page!

1. **Complete Render deployment setup** - Ensure everyone's deployment is working
2. **Build the "About Me" page** - Create your first complete, structured HTML page
3. **Practice the full workflow** - Code → Git → GitHub → Render deployment

## 📚 Class Structure

### 1. Confirm Render Deployment

We'll start by making sure everyone's Render deployment is working correctly.

**What We'll Check:**
- GitHub repository contains `index.html`
- Render service is connected to the correct repository
- Deployment completes successfully
- Live site URL loads your HTML page

[→ Render Deployment Check Guide](./steps/render-deployment-check.md)

### 2. Build Your "About Me" Page

Time to create your first complete web page! We'll build an "About Me" page that includes:

- A proper HTML5 structure
- Headings and paragraphs
- Lists of your interests or hobbies
- Links to your social media or projects
- At least one image (optional)

[→ HTML About Page Guide](./steps/html-about-page.md)

### 3. Practice the Git Workflow

Put everything we learned in Class #5 into practice:

```bash
# Stage your changes
git add .

# Commit with a descriptive message
git commit -m "Add About Me page"

# Push to GitHub (triggers Render deployment)
git push origin main
```

[→ Git Workflow Guide](./steps/git-workflow.md)

### 4. Mini-Challenge (If Time Permits)

Once your About Me page is live, enhance it by adding one of the following:

- An embedded video
- A contact form
- A table with information about yourself

[→ Mini-Challenge Guide](./steps/mini-challenge.md)

---

## 🏠 Homework & Practice

Practice what we learned today! Complete these exercises to reinforce your knowledge.

### Required Practice

**1. Complete Your About Me Page**

If you didn't finish in class, complete your About Me page with:
- All required sections (introduction, background, interests, goals)
- Proper semantic HTML structure
- At least one list (ordered or unordered)
- At least two links

**2. Practice the Full Workflow**

Make a small change to your page and practice the complete workflow:

1. Edit your `about.html` or `index.html` file
2. Save the file
3. Stage with `git add`
4. Commit with a descriptive message
5. Push to GitHub
6. Wait for Render to deploy
7. Check your live site to see the changes

**3. Experiment with Git Status**

Practice checking your repository status at each step:

```bash
# After making a change (before staging)
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

**4. Add One Enhancement**

Choose one enhancement from the mini-challenge and add it to your page:
- A video (YouTube embed or HTML5 video)
- A contact form
- A table

### Extra Credit (Optional)

**Challenge: Add Multiple Enhancements**

Add all three enhancements to your page:
- A video that represents your interests
- A contact form for people to reach you
- A table with organized information about yourself

**Exploration: Customize Your Footer**

Create a creative footer for your page that includes:
- Copyright information
- Links to your social media
- A fun fact or quote about yourself
- The date you created the page

**Advanced: Create Multiple Pages**

Create a second page and link between them:
1. Create `projects.html` with a list of things you want to build
2. Add a navigation menu to both pages that links between them
3. Practice deploying multiple pages

---

## 📖 Resources for Review

- [HTML About Page Guide](./steps/html-about-page.md) - Step-by-step page building
- [Git Workflow Guide](./steps/git-workflow.md) - Git commands reference
- [Render Deployment Check](./steps/render-deployment-check.md) - Deployment troubleshooting
- [Mini-Challenge Guide](./steps/mini-challenge.md) - Enhancement ideas
- [MDN - HTML Structure](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Document_and_website_structure) - Official docs

---

## ✅ What You Should Know After This Class

- ✅ How to verify your Render deployment is working
- ✅ How to build a complete, well-structured HTML page
- ✅ The full workflow: Code → Git → GitHub → Render
- ✅ How to add semantic structure to your pages
- ✅ How to use lists, links, and other HTML elements effectively
- ✅ How changes in your code become live on the internet
- ✅ How to troubleshoot deployment issues
- ✅ The importance of commit messages
- ✅ How to check the status of your Git repository

---

## 🔜 Next Class

In our next class, we'll:
- Introduce CSS for styling your pages
- Learn how to add colors, fonts, and layout
- Make your pages look beautiful!

---

← [Class 5 - Build, Edit, and Publish](./class5-build-edit-publish.md) | [Class 7 - TBD](./class7-tbd.md) →

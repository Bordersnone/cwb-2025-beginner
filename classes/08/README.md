# Class 8 - Build Your About Me Page & Intro to CSS

**Lead:** Timotej  
**Assistant:** Kiley  
**Date:** October 16, 2025

> **Note:** This class is being taught via video. Please follow the step-by-step instructions below at your own pace. Each section has a YouTube video to help you understand the concepts.

> **📺 [View All Video Tutorials](../../resources/video-tutorials.md)** - Complete library of curated YouTube videos for all topics

---

## 🎯 Class Goals

Today you'll complete your first real web page and make it look beautiful!

1. **Practice the deployment workflow** - Make changes and see them go live on Render
2. **Build your "About Me" page** - Create a complete HTML page about yourself
3. **Learn CSS basics** - Add colors, fonts, and styling to your page
4. **Deploy your styled page** - Push it to GitHub and see it live on Render

---

## 📝 What Happened in Class 7

In our last class, we:
- ✅ Configured Git author details (name and email)
- ✅ Got everyone's Render accounts connected to GitHub
- ⏰ Ran out of time before practicing deployment and learning CSS

**Today we'll complete what we didn't finish!**

---

## 📚 Today's Step-by-Step Guide

> **IMPORTANT:** Take your time with each step. Don't rush. If you get stuck, watch the video again or ask for help.

---

### Part 1: Practice the Full Deployment Workflow (15-20 minutes)

Let's practice making small changes and watching them deploy to Render.

#### Step 1.1: Make a Small Change to Your index.html

1. Open VS Code
2. Open your `index.html` file (or create one if you don't have it)
3. Add this line inside the `<body>` tag:
   ```html
   <p>Testing deployment - Class 8!</p>
   ```
4. Save the file (Ctrl+S or Cmd+S)

#### Step 1.2: Push to GitHub Using Git Commands

Open your terminal (in VS Code or separate) and run these commands **one at a time**:

```bash
git status
```
👉 You should see `index.html` listed as modified

```bash
git add .
```
👉 This stages all your changes

```bash
git status
```
👉 Now `index.html` should be listed under "Changes to be committed"

```bash
git commit -m "Test deployment for Class 8"
```
👉 This creates a commit with your changes

```bash
git push origin main
```
👉 This pushes your changes to GitHub

**📺 Watch this video if you need help:** [Git Add, Commit, Push Tutorial (5 min)](https://www.youtube.com/watch?v=-GZrhTtvKMU)

#### Step 1.3: Watch Render Deploy Your Changes

1. Go to [render.com](https://render.com) and log in
2. Click on your web service
3. Click the **"Events"** tab
4. You should see a new deployment starting (it will say "Deploy started")
5. Wait 1-2 minutes for it to finish
6. Once it says "Deploy live", click on your live URL
7. **You should see your new paragraph!**

**🎉 Congratulations! You just deployed to the internet!**

---

#### Step 1.4: Practice Again (Optional but Recommended)

Make 2 more small changes to practice the workflow:

**Change #2:** Add a heading
```html
<h1>Welcome to My Page</h1>
```
Then: `git add .` → `git commit -m "Add welcome heading"` → `git push origin main`

**Change #3:** Add a list
```html
<ul>
  <li>I am learning web development</li>
  <li>This is my first website</li>
</ul>
```
Then: `git add .` → `git commit -m "Add list"` → `git push origin main`

**Check Render each time to confirm your changes appear live!**

---

### Part 2: Build Your Complete About Me Page (30-40 minutes)

Now let's build a proper HTML page about yourself!

#### What Your Page Must Include:

- [ ] Proper HTML5 structure (`<!DOCTYPE html>`, `<html>`, `<head>`, `<body>`)
- [ ] A `<title>` in the `<head>` section
- [ ] Semantic structure: `<header>`, `<main>`, `<footer>`
- [ ] At least 3 sections using `<section>` tags
- [ ] Multiple headings (`<h1>`, `<h2>`, etc.)
- [ ] At least 3 paragraphs with `<p>` tags
- [ ] At least one list (ordered `<ol>` or unordered `<ul>`)
- [ ] At least 2 links using `<a>` tags

#### Step 2.1: Start with Proper HTML Structure

📺 **Watch first:** [HTML Structure Tutorial (10 min)](https://www.youtube.com/watch?v=qz0aGYrrlhU)

Replace everything in your `index.html` with this template:

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
        <!-- You'll add sections here -->
    </main>

    <footer>
        <p>&copy; 2025 [Your Name]. Built in Borders:None Web Dev class.</p>
    </footer>
</body>
</html>
```

**Replace `[Your Name]` with your actual name!**

#### Step 2.2: Add an Introduction Section

📺 **Watch first:** [HTML Semantic Elements (8 min)](https://www.youtube.com/watch?v=Vg44TfKZB1M)

Inside the `<main>` tag, add this section:

```html
<section>
    <h2>Introduction</h2>
    <p>Hi! My name is [Your Name]. I am learning web development at Borders:None.</p>
    <p>I am excited to build my first website and learn how to code!</p>
</section>
```

#### Step 2.3: Add Your Interests

Add another section with a list:

```html
<section>
    <h2>My Interests</h2>
    <ul>
        <li>Learning web development</li>
        <li>[Your hobby]</li>
        <li>[Another interest]</li>
        <li>[One more interest]</li>
    </ul>
</section>
```

#### Step 2.4: Add Your Goals

Add a section with an ordered list:

```html
<section>
    <h2>My Goals</h2>
    <ol>
        <li>Build my own website</li>
        <li>Learn CSS and make beautiful pages</li>
        <li>Learn JavaScript</li>
        <li>[Your personal goal]</li>
    </ol>
</section>
```

#### Step 2.5: Add a Contact Section with Links

```html
<section>
    <h2>Connect With Me</h2>
    <p>
        <a href="mailto:your@email.com">Email me</a> | 
        <a href="https://github.com/yourusername" target="_blank">My GitHub</a>
    </p>
</section>
```

**Replace with your actual email and GitHub username!**

#### Step 2.6: Save and Deploy!

1. Save your file (Ctrl+S or Cmd+S)
2. Run the Git commands:
   ```bash
   git add .
   git commit -m "Complete About Me page structure"
   git push origin main
   ```
3. Wait for Render to deploy
4. Check your live site!

**📺 Need help with the full page?** [Create About Me Page Tutorial (15 min)](https://www.youtube.com/watch?v=E5PO4yEwJI4)

---

### Part 3: Introduction to CSS (30-40 minutes)

Now let's make your page look beautiful with CSS (Cascading Style Sheets)!

#### What is CSS?

- **HTML** = Structure (the skeleton)
- **CSS** = Style (the appearance)

CSS lets you change colors, fonts, spacing, layouts, and much more!

📺 **Watch first:** [What is CSS? (5 min)](https://www.youtube.com/watch?v=yfoY53QXEnI) - Watch first 5 minutes only

#### Step 3.1: Three Ways to Add CSS

📺 **Watch:** [Inline vs Internal vs External CSS (7 min)](https://www.youtube.com/watch?v=TM88Xo4GIBs)

There are 3 ways to add CSS to your HTML:

1. **Inline CSS** - Style directly on an element (not recommended for large sites)
2. **Internal CSS** - Style in a `<style>` tag in the `<head>` (good for small sites)
3. **External CSS** - Style in a separate `.css` file (best for large sites)

**Today we'll use Internal CSS** because it's easier to learn.

#### Step 3.2: Add a Style Section

In your `index.html`, add this `<style>` tag inside the `<head>` section (after the `<title>` tag):

```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>About [Your Name]</title>
    
    <style>
        /* Your CSS will go here */
    </style>
</head>
```

**Note:** The `/* */` is a CSS comment. It doesn't affect your code.

#### Step 3.3: Style the Body

📺 **Watch:** [CSS Colors and Fonts (6 min)](https://www.youtube.com/watch?v=UO0ZPL8yMpU)

Add these styles inside the `<style>` tag:

```css
body {
    font-family: Arial, sans-serif;
    background-color: #f4f4f4;
    color: #333;
    line-height: 1.6;
    padding: 20px;
}
```

**What this does:**
- `font-family`: Changes the font to Arial
- `background-color`: Makes the background light gray
- `color`: Makes the text dark gray
- `line-height`: Adds spacing between lines
- `padding`: Adds space around the edges

#### Step 3.4: Style the Header

```css
header {
    background-color: #4CAF50;
    color: white;
    text-align: center;
    padding: 20px;
    border-radius: 8px;
}
```

**What this does:**
- `background-color`: Makes the header green
- `color`: Makes the text white
- `text-align`: Centers the text
- `padding`: Adds space inside the header
- `border-radius`: Rounds the corners

#### Step 3.5: Style Sections

```css
section {
    background-color: white;
    margin: 20px 0;
    padding: 20px;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}
```

**What this does:**
- `background-color`: Makes sections white
- `margin`: Adds space between sections
- `padding`: Adds space inside sections
- `border-radius`: Rounds the corners
- `box-shadow`: Adds a subtle shadow

#### Step 3.6: Style Headings

```css
h1 {
    margin: 0;
    font-size: 2.5em;
}

h2 {
    color: #4CAF50;
    border-bottom: 2px solid #4CAF50;
    padding-bottom: 5px;
}
```

#### Step 3.7: Style Links

```css
a {
    color: #4CAF50;
    text-decoration: none;
    font-weight: bold;
}

a:hover {
    text-decoration: underline;
}
```

**What this does:**
- `color`: Makes links green
- `text-decoration: none`: Removes the underline
- `font-weight: bold`: Makes links bold
- `a:hover`: Adds underline when you hover over a link

#### Step 3.8: Style the Footer

```css
footer {
    text-align: center;
    margin-top: 40px;
    padding: 20px;
    background-color: #333;
    color: white;
    border-radius: 8px;
}
```

#### Step 3.9: Your Complete CSS

Here's all the CSS together. Your `<style>` section should look like this:

```html
<style>
    body {
        font-family: Arial, sans-serif;
        background-color: #f4f4f4;
        color: #333;
        line-height: 1.6;
        padding: 20px;
    }

    header {
        background-color: #4CAF50;
        color: white;
        text-align: center;
        padding: 20px;
        border-radius: 8px;
    }

    h1 {
        margin: 0;
        font-size: 2.5em;
    }

    main {
        margin-top: 20px;
    }

    section {
        background-color: white;
        margin: 20px 0;
        padding: 20px;
        border-radius: 8px;
        box-shadow: 0 2px 4px rgba(0,0,0,0.1);
    }

    h2 {
        color: #4CAF50;
        border-bottom: 2px solid #4CAF50;
        padding-bottom: 5px;
    }

    a {
        color: #4CAF50;
        text-decoration: none;
        font-weight: bold;
    }

    a:hover {
        text-decoration: underline;
    }

    footer {
        text-align: center;
        margin-top: 40px;
        padding: 20px;
        background-color: #333;
        color: white;
        border-radius: 8px;
    }
</style>
```

#### Step 3.10: Save, Test Locally, Then Deploy!

1. **Save your file** (Ctrl+S or Cmd+S)
2. **Open in browser** - Right-click `index.html` in VS Code and choose "Open with Live Server" or just double-click the file
3. **Check how it looks** - You should see colors, nice spacing, and styled text!
4. **Deploy to GitHub:**
   ```bash
   git add .
   git commit -m "Add CSS styling to About Me page"
   git push origin main
   ```
5. **Check Render** - Wait for deployment and visit your live URL
6. **Celebrate!** 🎉 You just built and styled your first website!

---

### Part 4: Experiment and Customize (Optional)

Want to make your page unique? Try changing:

#### Colors
Change `#4CAF50` (green) to other colors:
- `#2196F3` - Blue
- `#FF5722` - Orange
- `#9C27B0` - Purple
- `#E91E63` - Pink

📺 **Learn about colors:** [CSS Colors Tutorial (8 min)](https://www.youtube.com/watch?v=Ddc-IIrIot0)

#### Fonts
Change the font family:
```css
font-family: 'Georgia', serif;  /* Classic look */
font-family: 'Courier New', monospace;  /* Typewriter look */
font-family: 'Comic Sans MS', cursive;  /* Casual look */
```

#### Spacing
Make things bigger or smaller by changing:
- `padding` - Space inside elements
- `margin` - Space outside elements
- `font-size` - Size of text

**Experiment! You can't break anything. If you mess up, just use Git to undo!**

---

## 🏠 Homework & Practice

### Required Practice

**1. Use CSS Properties and Selectors**

Apply as many of the CSS properties and selectors discussed in class as possible within your HTML file:
- Experiment with properties: `color`, `border`, `background`, `box-shadow`, `font-weight`, `text-align`, `font-family`, `line-height`, and `vertical-align`
- Apply inline CSS to style your web page
- Practice using **class and ID selectors** to target specific elements for styling

**2. Add and Style Images**

- Add images to your page (if you haven't already)
- Experiment with styling them:
  - Adjust `width` and `height`
  - Try different alignment options
  - Add borders or other styling

**3. Use Browser Developer Tools**

- Open your page in a browser
- Right-click and select "Inspect" (or press F12)
- Practice using the developer tools to:
  - Live-edit CSS and test your changes
  - Experiment safely before committing changes
  - See how different properties affect your page

**4. Deploy Your Updated Project**

Submit your work by:
1. Save all your changes
2. Push to GitHub: `git add .` → `git commit -m "Add CSS styling"` → `git push origin main`
3. Ensure your site is deployed and accessible via Render
4. Test your live site to confirm everything works

**5. Prepare for Next Class**

We'll be building more structured layouts using advanced CSS concepts (external CSS files, Flexbox, and responsive design) in the next class!

---

### Extra Credit (Optional)

**Challenge 1: Add More CSS Properties**

Research and try these CSS properties:
- `text-shadow` - Add shadow to text
- `border` - Add borders around elements
- `background-image` - Use an image as background

**Challenge 2: Create a Second Page**

Create a `hobbies.html` page and link to it from your `index.html`.

**Challenge 3: Mobile Responsive**

Research "CSS media queries" and make your page look good on phones.

---

## 📖 Resources

### Videos for Today's Class

**HTML Structure:**
- [HTML Crash Course (1 hour)](https://www.youtube.com/watch?v=qz0aGYrrlhU) - Comprehensive HTML tutorial
- [HTML Semantic Elements (8 min)](https://www.youtube.com/watch?v=Vg44TfKZB1M) - Header, main, footer explained

**CSS Basics:**
- [CSS Crash Course (1.5 hours)](https://www.youtube.com/watch?v=yfoY53QXEnI) - Complete CSS introduction
- [Inline vs Internal vs External CSS (7 min)](https://www.youtube.com/watch?v=TM88Xo4GIBs) - CSS methods explained
- [CSS Colors and Fonts (6 min)](https://www.youtube.com/watch?v=UO0ZPL8yMpU) - Styling text
- [CSS Colors Tutorial (8 min)](https://www.youtube.com/watch?v=Ddc-IIrIot0) - Deep dive into colors

**Git & Deployment:**
- [Git Add, Commit, Push (5 min)](https://www.youtube.com/watch?v=-GZrhTtvKMU) - Quick workflow tutorial
- [Git Basics Explained (10 min)](https://www.youtube.com/watch?v=qYrsPP4Wnjw) - Understanding Git commands

**Project-Based:**
- [Create About Me Page (15 min)](https://www.youtube.com/watch?v=E5PO4yEwJI4) - Full project walkthrough

### Written Resources

- [MDN - HTML Structure](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Document_and_website_structure)
- [MDN - CSS First Steps](https://developer.mozilla.org/en-US/docs/Learn/CSS/First_steps)
- [W3Schools - CSS Tutorial](https://www.w3schools.com/css/)
- [CSS Color Picker](https://htmlcolorcodes.com/) - Find color codes

---

## ✅ What You Should Know After This Class

By the end of today, you should:

- ✅ Confidently use the Git workflow: save → add → commit → push
- ✅ Understand how Render automatically deploys when you push to GitHub
- ✅ Build a complete HTML page with proper structure
- ✅ Use semantic HTML elements: header, main, footer, section
- ✅ Understand what CSS is and why we use it
- ✅ Add internal CSS to an HTML page using `<style>` tags
- ✅ Style text, colors, backgrounds, and spacing
- ✅ Know the difference between inline, internal, and external CSS
- ✅ Have a live, styled "About Me" page you're proud of!

---

## 🔜 Next Class

In Class 9, we'll dive deeper into CSS:
- CSS Box Model (margin, padding, border)
- Page layouts with Flexbox
- Creating navigation menus
- More advanced styling techniques

---

## 💡 Tips for Success

### If You Get Stuck:

1. **Watch the video again** - Sometimes you need to see it twice
2. **Check for typos** - One missing character can break everything
3. **Use git status** - See what Git thinks is happening
4. **Ask for help** - Message the class group chat
5. **Take breaks** - Step away and come back with fresh eyes

### Common Mistakes to Avoid:

- ❌ Forgetting to save your file before running Git commands
- ❌ Missing closing tags (`</section>`, `</style>`, etc.)
- ❌ Typos in CSS property names
- ❌ Forgetting the semicolon `;` at the end of CSS lines
- ❌ Not checking Render to confirm deployment

### Remember:

- **Everyone learns at their own pace** - Don't compare yourself to others
- **Making mistakes is how you learn** - Every error teaches you something
- **Git is your safety net** - You can always undo changes
- **Your website is YOURS** - Make it reflect who you are!

---

## 🎓 You're Building Real Skills!

The work you're doing today is exactly what professional web developers do:

- Writing clean, structured HTML ✅
- Styling with CSS ✅
- Version control with Git ✅
- Deploying to the cloud ✅

These are valuable, marketable skills. Keep practicing and be proud of your progress!

---

← [Class 7 - Deploy Your First Page](../7class-deploy-your-first-page/class7-deploy-your-first-page.md) | [Class 9 - CSS Layouts & Flexbox](../9class-css-layouts-and-flexbox/class9-css-layouts.md) →

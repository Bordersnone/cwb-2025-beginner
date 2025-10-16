# Class 9 - External CSS, Layouts & Flexbox

**Lead:** Timotej  
**Date:** October 21, 2025

> **Note:** This class builds on what we learned in Class 8. Make sure you've completed your styled About Me page before starting!

> **📺 [View All Video Tutorials](../../resources/video-tutorials.md)** - Complete library of curated YouTube videos for all topics

---

## 🎯 Class Goals

Today we'll take our CSS skills to the next level and learn professional layout techniques!

1. **Move CSS to external files** - Organize your code like a professional
2. **Master the CSS Box Model** - Understand margin, padding, and borders
3. **Learn Flexbox** - Create modern, responsive layouts
4. **Build a navigation menu** - Add a real navigation bar to your page
5. **Deploy your improved page** - Push it to GitHub and see it live

---

## 📝 What Happened in Class 8

In our last class, we:
- ✅ Completed our "About Me" pages with proper HTML structure
- ✅ Learned CSS basics (colors, fonts, spacing)
- ✅ Used internal CSS with `<style>` tags
- ✅ Deployed our styled pages to Render

**Today we'll improve our styling and learn professional layout techniques!**

---

## 📚 Today's Step-by-Step Guide

> **IMPORTANT:** We'll be modifying the page you created in Class 8. Make sure you have it open in VS Code!

---

### Part 1: Move CSS to an External File (15-20 minutes)

Right now, your CSS is in a `<style>` tag inside your HTML. Professional developers keep CSS in separate files.

#### Why Use External CSS?

- **Organization** - Keeps HTML and CSS separate
- **Reusability** - Use the same CSS file for multiple pages
- **Maintainability** - Easier to find and edit styles
- **Performance** - Browsers can cache CSS files

📺 **Watch first:** [External CSS Files Explained (6 min)](https://www.youtube.com/watch?v=Tfjd5yzCaxk)

#### Step 1.1: Create a CSS File

1. In VS Code, create a new folder called `css` in your project root
2. Inside the `css` folder, create a file called `style.css`

Your project structure should now look like:
```
your-project/
├── index.html
└── css/
    └── style.css
```

#### Step 1.2: Move Your CSS

1. **Copy** all the CSS code from inside your `<style>` tags in `index.html`
2. **Paste** it into your new `style.css` file
3. **Save** `style.css`

Your `style.css` should now contain all your CSS rules (body, header, section, etc.)

#### Step 1.3: Link to Your CSS File

In your `index.html`, **replace** the entire `<style>` section with this single line:

```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>About [Your Name]</title>
    
    <link rel="stylesheet" href="css/style.css">
</head>
```

**Note:** The `<link>` tag tells the browser to load your external CSS file.

#### Step 1.4: Test It!

1. Save both files
2. Open `index.html` in your browser
3. **It should look exactly the same!** If it doesn't, check:
   - Is the `css` folder in the right place?
   - Is the filename spelled correctly (`style.css`)?
   - Did you save both files?

#### Step 1.5: Deploy Your Changes

```bash
git status
git add .
git commit -m "Move CSS to external file"
git push origin main
```

Check Render to confirm it deployed successfully!

---

### Part 2: The CSS Box Model (20-25 minutes)

Every HTML element is a "box". Understanding the box model is crucial for layouts!

📺 **Watch first:** [CSS Box Model Explained (8 min)](https://www.youtube.com/watch?v=rIO5326FgPE)

#### What is the Box Model?

Every element has four parts (from inside to outside):
1. **Content** - The actual text or image
2. **Padding** - Space between content and border
3. **Border** - The edge around the padding
4. **Margin** - Space outside the border (between elements)

```
┌─────────────────────────────┐
│         MARGIN              │
│  ┌────────────────────────┐ │
│  │      BORDER            │ │
│  │  ┌──────────────────┐  │ │
│  │  │    PADDING       │  │ │
│  │  │  ┌────────────┐  │  │ │
│  │  │  │  CONTENT   │  │  │ │
│  │  │  └────────────┘  │  │ │
│  │  └──────────────────┘  │ │
│  └────────────────────────┘ │
└─────────────────────────────┘
```

#### Step 2.1: Add a Visual Border to Understand Boxes

Add this to your `style.css` **temporarily** (we'll remove it later):

```css
/* Temporary - helps visualize boxes */
* {
    outline: 1px solid red;
}
```

Save and refresh your browser. **Everything has a red outline!** This helps you see the boxes.

#### Step 2.2: Experiment with Padding

Padding adds space **inside** an element. Let's modify your sections:

```css
section {
    background-color: white;
    margin: 20px 0;
    padding: 40px;  /* Changed from 20px - notice the difference! */
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}
```

**Refresh your browser.** The sections should have more space inside them!

#### Step 2.3: Experiment with Margin

Margin adds space **outside** an element. Try this:

```css
section {
    background-color: white;
    margin: 40px 0;  /* Changed from 20px - more space between sections */
    padding: 40px;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}
```

**Refresh.** More space between sections!

#### Step 2.4: Understanding Margin/Padding Shorthand

CSS has shortcuts for margin and padding:

```css
/* One value - applies to all sides */
padding: 20px;  /* top, right, bottom, left = 20px */

/* Two values - vertical, horizontal */
padding: 20px 40px;  /* top/bottom = 20px, left/right = 40px */

/* Four values - clockwise from top */
padding: 10px 20px 30px 40px;  /* top, right, bottom, left */
```

Try adding more padding on the sides of your sections:

```css
section {
    padding: 30px 50px;  /* 30px top/bottom, 50px left/right */
}
```

#### Step 2.5: Remove the Red Outlines

Delete or comment out the temporary outline rule:

```css
/* Temporary - helps visualize boxes */
/* * {
    outline: 1px solid red;
} */
```

---

### Part 3: Introduction to Flexbox (30-40 minutes)

Flexbox is a modern way to create layouts. It makes aligning and spacing elements super easy!

📺 **Watch first:** [Flexbox in 15 Minutes](https://www.youtube.com/watch?v=fYq5PXgSsbE) - Watch first 10 minutes

#### What is Flexbox?

Flexbox lets you:
- Align items horizontally or vertically
- Distribute space evenly between elements
- Change the order of elements
- Make responsive layouts easily

#### Step 3.1: Create a Navigation Bar

Let's add a navigation menu to your page! Add this **inside your `<header>`** section:

```html
<header>
    <nav>
        <a href="#intro">Home</a>
        <a href="#interests">Interests</a>
        <a href="#goals">Goals</a>
        <a href="#contact">Contact</a>
    </nav>
    <h1>About Me</h1>
</header>
```

**Also add IDs to your sections** so the links work:

```html
<section id="intro">
    <h2>Introduction</h2>
    ...
</section>

<section id="interests">
    <h2>My Interests</h2>
    ...
</section>

<section id="goals">
    <h2>My Goals</h2>
    ...
</section>

<section id="contact">
    <h2>Connect With Me</h2>
    ...
</section>
```

Save and refresh. The links should work now (they'll scroll to each section)!

#### Step 3.2: Style the Navigation with Flexbox

Add this to your `style.css`:

```css
nav {
    display: flex;
    justify-content: center;
    gap: 30px;
    margin-bottom: 20px;
}

nav a {
    color: white;
    text-decoration: none;
    font-weight: bold;
    padding: 10px 20px;
    background-color: rgba(255, 255, 255, 0.2);
    border-radius: 5px;
    transition: background-color 0.3s;
}

nav a:hover {
    background-color: rgba(255, 255, 255, 0.3);
}
```

**What this does:**
- `display: flex` - Turns the nav into a flex container
- `justify-content: center` - Centers the links horizontally
- `gap: 30px` - Adds space between links (easier than margins!)
- The links are styled with padding, background, and a hover effect

**Refresh your browser!** You should have a nice navigation menu!

#### Step 3.3: Create a Skills Section with Flexbox

Let's add a new section to practice Flexbox. Add this to your HTML (before the footer):

```html
<section id="skills">
    <h2>My Skills</h2>
    <div class="skills-container">
        <div class="skill-card">
            <h3>HTML</h3>
            <p>Building web page structure</p>
        </div>
        <div class="skill-card">
            <h3>CSS</h3>
            <p>Styling and layouts</p>
        </div>
        <div class="skill-card">
            <h3>Git</h3>
            <p>Version control</p>
        </div>
        <div class="skill-card">
            <h3>Deployment</h3>
            <p>Publishing to the web</p>
        </div>
    </div>
</section>
```

Now style it with Flexbox in your `style.css`:

```css
.skills-container {
    display: flex;
    justify-content: space-between;
    gap: 20px;
    flex-wrap: wrap;  /* Wraps to next line on small screens */
}

.skill-card {
    flex: 1;  /* Cards grow to fill space */
    min-width: 150px;  /* Minimum width before wrapping */
    background-color: #f0f0f0;
    padding: 20px;
    border-radius: 8px;
    text-align: center;
    border: 2px solid #4CAF50;
}

.skill-card h3 {
    color: #4CAF50;
    margin-top: 0;
    border-bottom: none;  /* Remove the border from h3 */
}

.skill-card p {
    margin-bottom: 0;
    color: #666;
}
```

**What this does:**
- Creates a row of skill cards
- `justify-content: space-between` - Distributes cards evenly
- `flex-wrap: wrap` - Cards wrap to next line on small screens
- `flex: 1` - Cards grow to fill available space
- Cards look like distinct boxes with borders

**Refresh!** You should see a nice row of skill cards!

---

### Part 4: Responsive Design with Flexbox (20 minutes)

Let's make your page look good on phones too!

📺 **Watch:** [CSS Media Queries (10 min)](https://www.youtube.com/watch?v=yU7jJ3NbPdA)

#### Step 4.1: Add Mobile Styles

Add this at the **end** of your `style.css`:

```css
/* Mobile Responsive Styles */
@media (max-width: 768px) {
    body {
        padding: 10px;
    }
    
    nav {
        flex-direction: column;  /* Stack links vertically */
        gap: 10px;
    }
    
    .skills-container {
        flex-direction: column;  /* Stack skill cards on mobile */
    }
    
    section {
        padding: 20px;
    }
}
```

**What this does:**
- `@media (max-width: 768px)` - Applies styles only on screens smaller than 768px
- Changes flexbox direction from row to column on mobile
- Reduces padding on smaller screens

#### Step 4.2: Test Mobile View

In your browser:
1. Right-click and choose "Inspect" (or press F12)
2. Click the device icon (toggle device toolbar)
3. Choose "iPhone 12 Pro" or another phone
4. **See how your page looks on mobile!**

Your navigation and skill cards should stack vertically on small screens.

---

### Part 5: Polish and Deploy (15-20 minutes)

Let's add some final touches!

#### Step 5.1: Add a Max Width for Better Readability

Add this to your `body` styles:

```css
body {
    font-family: Arial, sans-serif;
    background-color: #f4f4f4;
    color: #333;
    line-height: 1.6;
    padding: 20px;
    max-width: 1200px;  /* NEW */
    margin: 0 auto;  /* NEW - centers the content */
}
```

This prevents your content from being too wide on large screens.

#### Step 5.2: Add Smooth Scrolling

When you click navigation links, make the scrolling smooth:

```css
html {
    scroll-behavior: smooth;
}
```

#### Step 5.3: Final Review

Check your page:
- ✅ Navigation works and looks good
- ✅ Skills section displays in a row (desktop) or column (mobile)
- ✅ Sections have good spacing
- ✅ Page looks good on both desktop and mobile

#### Step 5.4: Deploy Your Improved Page!

```bash
git status
git add .
git commit -m "Add Flexbox layouts, navigation, and responsive design"
git push origin main
```

Wait for Render to deploy, then check your live site!

**Try it on your phone too!** Share your URL with friends!

---

## 🏠 Homework & Practice

### Required Practice

**1. Customize Your Color Scheme**

Choose a different color scheme for your page:
- Pick a main color (not green)
- Update all instances of `#4CAF50` in your CSS
- Update navigation background colors
- Make sure text is still readable!

**Resources:**
- [Coolors.co](https://coolors.co/) - Color palette generator
- [Adobe Color](https://color.adobe.com/) - Color wheel tool

**2. Add More Skill Cards**

Add at least 2 more skill cards:
- Think of skills you're learning or want to learn
- Follow the same HTML structure
- The Flexbox layout will automatically adjust!

**3. Experiment with Flexbox Properties**

Try changing these Flexbox properties in `.skills-container`:
- `justify-content: center` - What happens?
- `align-items: center` - What changes?
- `gap: 40px` - More or less space?

**Document what each property does** in a comment in your CSS!

---

### Extra Credit (Optional)

**Challenge 1: Create a Two-Column Layout**

Make your introduction section have two columns:
- Left: Your text
- Right: An image (add a photo of yourself or placeholder)

Use Flexbox to create the layout!

**Challenge 2: Add a Projects Section**

Create a new section showcasing projects:
- Use Flexbox for the layout
- Include a title, description, and link for each project
- Style them as cards similar to the skills section

**Challenge 3: Add Animations**

Research CSS animations and add:
- Fade-in effect when page loads
- Scale effect when hovering over skill cards
- Slide-in effect for sections

---

## 📖 Resources

### Videos for Today's Class

**External CSS:**
- [External CSS Files Explained (6 min)](https://www.youtube.com/watch?v=Tfjd5yzCaxk)
- [CSS File Organization (12 min)](https://www.youtube.com/watch?v=tNOSN3kDzk4)

**CSS Box Model:**
- [CSS Box Model Explained (8 min)](https://www.youtube.com/watch?v=rIO5326FgPE)
- [Margin vs Padding (5 min)](https://www.youtube.com/watch?v=Azfj1efPAH0)

**Flexbox:**
- [Flexbox in 15 Minutes](https://www.youtube.com/watch?v=fYq5PXgSsbE)
- [Flexbox Tutorial (30 min)](https://www.youtube.com/watch?v=JJSoEo8JSnc) - Comprehensive guide
- [Flexbox Froggy](https://flexboxfroggy.com/) - Interactive game to learn Flexbox!

**Responsive Design:**
- [CSS Media Queries (10 min)](https://www.youtube.com/watch?v=yU7jJ3NbPdA)
- [Mobile-First CSS (8 min)](https://www.youtube.com/watch?v=0ohtVzCSHqs)

### Written Resources

- [MDN - CSS Box Model](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Box_Model)
- [MDN - Flexbox Guide](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox)
- [CSS-Tricks - Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [W3Schools - Flexbox](https://www.w3schools.com/css/css3_flexbox.asp)

### Interactive Learning

- [Flexbox Froggy](https://flexboxfroggy.com/) - Learn Flexbox by playing a game
- [Flexbox Defense](http://www.flexboxdefense.com/) - Tower defense game using Flexbox

---

## ✅ What You Should Know After This Class

By the end of today, you should:

- ✅ Understand why external CSS files are better than internal CSS
- ✅ Know how to link an external CSS file to HTML
- ✅ Understand the CSS Box Model (content, padding, border, margin)
- ✅ Use margin and padding effectively
- ✅ Understand Flexbox and when to use it
- ✅ Use key Flexbox properties: `display: flex`, `justify-content`, `gap`, `flex-direction`
- ✅ Create a navigation menu with Flexbox
- ✅ Make layouts responsive with media queries
- ✅ Test your page on different screen sizes
- ✅ Have a professional-looking, responsive website!

---

## 🔜 Next Class

In Class 10, we'll explore:
- CSS Grid for more complex layouts
- Advanced selectors and pseudo-classes
- CSS variables for easier theming
- Building a multi-page website

---

## 💡 Tips for Success

### Common Flexbox Mistakes:

- ❌ Forgetting `display: flex` on the parent element
- ❌ Applying Flexbox properties to the wrong element
- ❌ Not understanding which element is the "container" vs "items"
- ❌ Forgetting to test on mobile

### Debugging Tips:

1. **Use browser DevTools** - Inspect elements and see computed styles
2. **Add borders temporarily** - See where elements are
3. **Start simple** - Get basic layout working before adding complexity
4. **Check one property at a time** - Don't change everything at once

### Remember:

- **Flexbox is powerful** - Many layout problems can be solved with just a few lines
- **Mobile-first** - Always test on small screens
- **Practice makes perfect** - Flexbox feels weird at first but becomes natural
- **Resources are your friend** - Refer to guides and documentation often

---

## 🎓 Professional Skills Unlocked!

You're now using the same tools professional developers use daily:

- External CSS files ✅
- Flexbox layouts ✅
- Responsive design ✅
- Mobile-first thinking ✅

These skills are in high demand. Keep building and practicing!

---

← [Class 8 - About Me & CSS Intro](../8class-about-me-page-and-css-intro/class8-about-me-and-css.md) | [Class 10 - TBD] →

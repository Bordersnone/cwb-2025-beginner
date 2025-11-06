# Class 13 - CSS Grid & Responsive Design

**Lead:** Salem  
**Assistant:** Timotej  
**Date:** November 4, 2025

---

## 📋 Background

This content was originally prepared for Class 11 (October 28, 2025), but that class was canceled due to low attendance. Class 12 focused on reinforcing CSS fundamentals to ensure students were ready for advanced layout topics. Now that students have a solid foundation, we're ready to dive into CSS Grid!

---

## 📂 Class Materials

> **📁 [View Example Files](./class-files/)**
>
> Comprehensive examples for CSS Grid and responsive design. We'll work through these together in today's class!

**What's Available:**
- **`example1.html`** - Responsive photo gallery with auto-fit
- **`example2.html`** - Product grid with auto-fill
- **`example3.html`** - Grid item placement examples
- **`task1.html`, `task2.html`, `task3.html`** - Practice exercises

Feel free to explore these files on your own, but don't worry if you don't understand them yet - we'll learn this together in today's class!

---

## 📚 What We'll Cover Today

> **Overview:** This class covers CSS Grid for two-dimensional layouts, media queries for responsive design, modern layout patterns, and CSS custom properties (variables) for maintainable code.

### Topic 1: CSS Grid Fundamentals

**Focus:** Understanding CSS Grid for creating two-dimensional layouts (rows AND columns).

📺 **Watch if you need help:** [CSS Grid Tutorial (20 min)](https://www.youtube.com/watch?v=EFafSYg-PkI)

#### When to Use Grid vs Flexbox

**Flexbox:**
- One-dimensional layouts (row OR column)
- Navigation bars, card rows, simple layouts
- Items can wrap but maintain single direction

**Grid:**
- Two-dimensional layouts (rows AND columns simultaneously)
- Page layouts, galleries, dashboards
- Precise control over both axes

#### Basic Grid Setup

**Creating a Grid Container:**
```css
.container {
    display: grid;
    grid-template-columns: 200px 200px 200px;  /* 3 columns, each 200px */
    grid-template-rows: 100px 100px;  /* 2 rows, each 100px */
    gap: 20px;  /* Space between grid items */
}
```

**Key Grid Properties:**

**`grid-template-columns`** - Defines column structure
```css
.grid {
    /* Fixed width columns */
    grid-template-columns: 200px 300px 200px;
    
    /* Flexible columns using fr (fraction) */
    grid-template-columns: 1fr 2fr 1fr;  /* Middle column is 2x wider */
    
    /* Repeat pattern */
    grid-template-columns: repeat(3, 1fr);  /* 3 equal columns */
    
    /* Mix units */
    grid-template-columns: 200px 1fr 200px;  /* Fixed sides, flexible middle */
}
```

**`grid-template-rows`** - Defines row structure
```css
.grid {
    grid-template-rows: 100px auto 100px;  /* Header, content, footer */
}
```

**`gap`** (or `grid-gap`)** - Spacing between items
```css
.grid {
    gap: 20px;  /* Equal gap for rows and columns */
    gap: 20px 40px;  /* Row gap, column gap */
}
```

#### Grid Item Placement

**Spanning Columns and Rows:**
```css
.item {
    grid-column: 1 / 3;  /* Span from column line 1 to 3 (2 columns) */
    grid-row: 1 / 2;  /* Occupy row 1 */
}

/* Shorthand */
.item {
    grid-column: span 2;  /* Span 2 columns from current position */
    grid-row: span 3;  /* Span 3 rows */
}
```

**Named Grid Areas:**
```css
.container {
    display: grid;
    grid-template-columns: 200px 1fr;
    grid-template-rows: auto 1fr auto;
    grid-template-areas:
        "header  header"
        "sidebar main"
        "footer  footer";
}

.header  { grid-area: header; }
.sidebar { grid-area: sidebar; }
.main    { grid-area: main; }
.footer  { grid-area: footer; }
```

#### Auto-Fit and Auto-Fill

**Responsive grids without media queries:**
```css
.gallery {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 20px;
}
```

→ Creates as many columns as fit, each at least 250px  
→ Items automatically wrap to new rows  
→ Columns stretch to fill available space

### Topic 2: Responsive Design with Media Queries

**Focus:** Making layouts adapt to different screen sizes.

📺 **Watch if you need help:** [CSS Media Queries (15 min)](https://www.youtube.com/watch?v=yU7jJ3NbPdA)

#### What Are Media Queries?

Media queries allow you to apply different CSS based on device characteristics (primarily screen width).

**Basic Syntax:**
```css
/* Mobile styles (default - mobile-first approach) */
.container {
    padding: 10px;
}

/* Tablet and up */
@media (min-width: 768px) {
    .container {
        padding: 20px;
    }
}

/* Desktop and up */
@media (min-width: 1024px) {
    .container {
        padding: 40px;
    }
}
```

#### Common Breakpoints

**Standard breakpoints:**
- **Mobile:** `< 768px` (default, no media query needed)
- **Tablet:** `768px - 1023px`
- **Desktop:** `1024px+`
- **Large Desktop:** `1440px+`

```css
/* Small devices (phones) */
/* No media query - this is the default */

/* Medium devices (tablets) */
@media (min-width: 768px) {
    /* Styles for tablets and up */
}

/* Large devices (desktops) */
@media (min-width: 1024px) {
    /* Styles for desktops and up */
}

/* Extra large devices */
@media (min-width: 1440px) {
    /* Styles for large screens */
}
```

#### Mobile-First Approach

**Best practice:** Start with mobile styles, then add complexity for larger screens.

```css
/* Mobile (default) */
.grid {
    display: grid;
    grid-template-columns: 1fr;  /* Single column */
}

/* Tablet - 2 columns */
@media (min-width: 768px) {
    .grid {
        grid-template-columns: repeat(2, 1fr);
    }
}

/* Desktop - 3 columns */
@media (min-width: 1024px) {
    .grid {
        grid-template-columns: repeat(3, 1fr);
    }
}
```

#### Responsive Navigation Pattern

```css
/* Mobile - vertical stack */
nav ul {
    display: flex;
    flex-direction: column;
}

/* Desktop - horizontal */
@media (min-width: 768px) {
    nav ul {
        flex-direction: row;
        justify-content: space-between;
    }
}
```

#### Testing Responsive Design

**In DevTools:**
1. Open DevTools (F12 or Cmd+Option+I)
2. Click the device toolbar icon (phone/tablet icon)
3. Choose different device presets or set custom width
4. Test your breakpoints

### Topic 3: CSS Custom Properties (Variables)

**Focus:** Using CSS variables for maintainable, themeable code.

📺 **Watch if you need help:** [CSS Variables Tutorial (8 min)](https://www.youtube.com/watch?v=oZPR_78wCnY)

#### Why Use CSS Variables?

- **Maintainability** - Change values in one place
- **Consistency** - Ensure colors/spacing are uniform
- **Theming** - Easy light/dark mode switching
- **Dynamic updates** - Can be changed with JavaScript

#### Declaring Variables

**In `:root` (global variables):**
```css
:root {
    /* Colors */
    --primary-color: #3498db;
    --secondary-color: #2ecc71;
    --text-color: #333;
    --bg-color: #fff;
    
    /* Spacing */
    --spacing-sm: 8px;
    --spacing-md: 16px;
    --spacing-lg: 24px;
    --spacing-xl: 32px;
    
    /* Typography */
    --font-main: 'Arial', sans-serif;
    --font-heading: 'Georgia', serif;
    
    /* Breakpoints (for use with calc or JavaScript) */
    --breakpoint-tablet: 768px;
    --breakpoint-desktop: 1024px;
}
```

#### Using Variables

**With `var()` function:**
```css
.button {
    background-color: var(--primary-color);
    padding: var(--spacing-md);
    font-family: var(--font-main);
}

.heading {
    color: var(--primary-color);
    margin-bottom: var(--spacing-lg);
    font-family: var(--font-heading);
}
```

**With fallback values:**
```css
.element {
    color: var(--text-color, #333);  /* Falls back to #333 if variable not defined */
}
```

#### Scoped Variables

Variables can be scoped to specific elements:
```css
.dark-theme {
    --text-color: #fff;
    --bg-color: #222;
}

.light-theme {
    --text-color: #333;
    --bg-color: #fff;
}

.content {
    color: var(--text-color);
    background-color: var(--bg-color);
}
```

#### Practical Example: Theme System

```css
:root {
    /* Light theme (default) */
    --bg: #ffffff;
    --text: #333333;
    --accent: #3498db;
}

[data-theme="dark"] {
    --bg: #1a1a1a;
    --text: #f0f0f0;
    --accent: #5dade2;
}

body {
    background-color: var(--bg);
    color: var(--text);
}

.button {
    background-color: var(--accent);
    color: var(--bg);
}
```

### Topic 4: Modern Layout Patterns

**Focus:** Combining Grid, Flexbox, and responsive design for real-world layouts.

#### The Holy Grail Layout

Classic three-column layout with header and footer:
```css
.page {
    display: grid;
    grid-template-columns: 200px 1fr 200px;
    grid-template-rows: auto 1fr auto;
    grid-template-areas:
        "header  header  header"
        "sidebar main    aside"
        "footer  footer  footer";
    min-height: 100vh;
}

/* Mobile - stack everything */
@media (max-width: 768px) {
    .page {
        grid-template-columns: 1fr;
        grid-template-areas:
            "header"
            "main"
            "sidebar"
            "aside"
            "footer";
    }
}
```

#### Card Grid with Auto-Fit

```css
.card-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: var(--spacing-lg);
    padding: var(--spacing-lg);
}

.card {
    background: var(--bg-color);
    border: 1px solid var(--border-color);
    border-radius: 8px;
    padding: var(--spacing-md);
}
```

#### Sidebar Layout with Grid

```css
.layout {
    display: grid;
    grid-template-columns: 250px 1fr;
    gap: 20px;
}

/* Mobile - sidebar becomes full-width */
@media (max-width: 768px) {
    .layout {
        grid-template-columns: 1fr;
    }
}
```

### 💡 Key Concepts

- ✅ **Grid is for 2D layouts** - Use when you need control over rows AND columns
- ✅ **Mobile-first approach** - Start small, add complexity for larger screens
- ✅ **Use variables for consistency** - Colors, spacing, fonts should be centralized
- ✅ **Test at multiple sizes** - Use DevTools device emulation constantly
- ✅ **`fr` units in Grid** - More flexible than percentages
- ✅ **`auto-fit` and `minmax()`** - Create responsive grids without media queries
- ✅ **Combine Grid + Flexbox** - Use the right tool for each part of your layout

---

## 🏠 Practice Exercises

> **💡 TIP:** Try building these from scratch before looking at solutions!

---

### Exercise 1: Simple Grid Gallery (20 minutes)

Create a responsive image gallery that adjusts columns based on screen size.

**Goal:** Build a grid that shows 1 column on mobile, 2 on tablet, 3 on desktop.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Grid Gallery</title>
    <style>
        :root {
            --gap: 20px;
        }
        
        .gallery {
            display: grid;
            grid-template-columns: 1fr;  /* Mobile: 1 column */
            gap: var(--gap);
            padding: var(--gap);
        }
        
        /* TODO: Add media query for tablet (2 columns) */
        
        /* TODO: Add media query for desktop (3 columns) */
        
        .gallery-item {
            background-color: #e0e0e0;
            height: 200px;
            border-radius: 8px;
        }
    </style>
</head>
<body>
    <div class="gallery">
        <div class="gallery-item">1</div>
        <div class="gallery-item">2</div>
        <div class="gallery-item">3</div>
        <div class="gallery-item">4</div>
        <div class="gallery-item">5</div>
        <div class="gallery-item">6</div>
    </div>
</body>
</html>
```

📺 **Watch if you need help:** [CSS Grid Gallery (12 min)](https://www.youtube.com/watch?v=qOO3ooXjf8k)

---

### Exercise 2: Holy Grail Layout (30 minutes)

Build the classic web layout with header, sidebar, main content, and footer.

**Goal:** Create a full-page layout that stacks on mobile and uses grid on desktop.

**Structure needed:**
- Header at top (full width)
- Sidebar on left (200px)
- Main content in center (flexible)
- Footer at bottom (full width)

**Requirements:**
- Use CSS Grid with `grid-template-areas`
- Mobile: Stack all sections vertically
- Desktop: Classic sidebar layout
- Use CSS variables for colors

📺 **Watch if you need help:** [Holy Grail Layout (15 min)](https://www.youtube.com/watch?v=qm0IfG1GyZU)

---

### Exercise 3: Auto-Fit Card Grid (20 minutes)

Create a card grid that automatically adjusts columns without media queries.

```css
.card-container {
    display: grid;
    /* TODO: Use repeat(auto-fit, minmax(...)) to create responsive grid */
    gap: 20px;
}
```

**Goal:** Cards should be at least 250px wide and grow to fill space.

**Experiment with:**
- `auto-fit` vs `auto-fill` - what's the difference?
- Different `minmax()` values
- Adding more cards to see wrapping behavior

---

### Exercise 4: Theme Switcher with CSS Variables (25 minutes)

Create a light/dark theme toggle using CSS custom properties.

**Goal:** Define two color schemes and switch between them.

```css
:root {
    /* Light theme colors */
    --bg-color: #ffffff;
    --text-color: #333333;
    --card-bg: #f5f5f5;
}

/* TODO: Add [data-theme="dark"] with dark colors */

body {
    background-color: var(--bg-color);
    color: var(--text-color);
    transition: background-color 0.3s, color 0.3s;
}
```

**Bonus:** Add a button that toggles `data-theme` attribute with JavaScript:
```javascript
document.querySelector('#theme-toggle').addEventListener('click', () => {
    const root = document.documentElement;
    const currentTheme = root.getAttribute('data-theme');
    root.setAttribute('data-theme', currentTheme === 'dark' ? 'light' : 'dark');
});
```

📺 **Watch if you need help:** [Dark Mode Toggle (10 min)](https://www.youtube.com/watch?v=wodWDIdV9BY)

---

### Exercise 5: Responsive Navigation (20 minutes)

Build a navigation that changes from vertical (mobile) to horizontal (desktop).

**Goal:** Nav items stack vertically on mobile, display horizontally on desktop.

```html
<nav>
    <ul class="nav-list">
        <li><a href="#home">Home</a></li>
        <li><a href="#about">About</a></li>
        <li><a href="#services">Services</a></li>
        <li><a href="#contact">Contact</a></li>
    </ul>
</nav>
```

**Requirements:**
- Mobile: Flexbox column
- Desktop: Flexbox row
- Use CSS variables for spacing
- Smooth transitions

---

## 🏠 Homework & Practice

### Required Practice

**1. Complete All Exercises**

Finish Exercises 1-5 to demonstrate understanding of:
- CSS Grid basics
- Responsive design with media queries
- CSS custom properties
- Modern layout patterns

**2. Build a Complete Responsive Page**

Create a single-page website with:
- Responsive navigation
- Grid-based content section (cards or gallery)
- Sidebar layout (desktop only, stacks on mobile)
- Footer
- Light/dark theme toggle
- CSS variables throughout

**3. Experiment with Grid**

Create test files exploring:
- Different `grid-template-columns` patterns
- `grid-template-areas` for named layouts
- `auto-fit` vs `auto-fill`
- Combining Grid container with Flexbox items

**4. Test Responsiveness**

For your practice projects:
- Test at 375px (mobile)
- Test at 768px (tablet)
- Test at 1024px (desktop)
- Test at 1440px (large desktop)
- Take screenshots at each breakpoint

---

### Extra Credit (Optional)

**Challenge 1: Dashboard Layout**

Create a dashboard with:
- Sidebar navigation
- Header with user info
- Grid of stat cards (2x2 on desktop, 1 column on mobile)
- Chart area (full width below cards)
- All using Grid and responsive

**Challenge 2: Magazine Layout**

Build a complex magazine-style layout:
- Feature article spans 2 columns
- Sidebar with smaller articles
- Image grid gallery
- Different layouts for mobile/tablet/desktop

**Challenge 3: Advanced Theming**

Create a theme system with:
- 3+ color themes (light, dark, high contrast)
- Save theme preference to localStorage
- Smooth transitions between themes
- Theme affects all components

---

## 📖 Learning Resources

### 📺 Video Tutorials

**CSS Grid:**
- [CSS Grid Tutorial (20 min)](https://www.youtube.com/watch?v=EFafSYg-PkI) - Comprehensive introduction
- [CSS Grid Layout Crash Course (30 min)](https://www.youtube.com/watch?v=jV8B24rSN5o)
- [Grid vs Flexbox (12 min)](https://www.youtube.com/watch?v=RSIclWvNTdQ)

**Responsive Design:**
- [CSS Media Queries (15 min)](https://www.youtube.com/watch?v=yU7jJ3NbPdA)
- [Mobile First Design (10 min)](https://www.youtube.com/watch?v=0ohtVzCSHqs)
- [Responsive Web Design Tutorial (45 min)](https://www.youtube.com/watch?v=srvUrASNj0s)

**CSS Variables:**
- [CSS Variables Tutorial (8 min)](https://www.youtube.com/watch?v=oZPR_78wCnY)
- [CSS Custom Properties Deep Dive (20 min)](https://www.youtube.com/watch?v=PHO6TBq_auI)
- [Dark Mode with CSS Variables (10 min)](https://www.youtube.com/watch?v=wodWDIdV9BY)

### 📄 Written Documentation

- [MDN - CSS Grid Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout)
- [CSS-Tricks - Complete Guide to Grid](https://css-tricks.com/snippets/css/complete-guide-grid/)
- [MDN - Using Media Queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)
- [MDN - CSS Custom Properties](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties)
- [Web.dev - Responsive Design](https://web.dev/responsive-web-design-basics/)

### 🎮 Interactive Learning

- [Grid Garden](https://cssgridgarden.com/) - Learn CSS Grid through a game
- [Grid by Example](https://gridbyexample.com/) - Grid patterns and examples
- [CSS Grid Generator](https://cssgrid-generator.netlify.app/) - Visual Grid builder

---

## ✅ What You Should Know After This Class

**By the end of today, you should be able to:**

- ✅ Understand when to use CSS Grid vs Flexbox
- ✅ Create basic grid layouts with `grid-template-columns` and `grid-template-rows`
- ✅ Use `fr` units for flexible grid sizing
- ✅ Implement `gap` for grid spacing
- ✅ Span items across multiple columns/rows
- ✅ Use `grid-template-areas` for named layouts
- ✅ Create responsive grids with `auto-fit` and `minmax()`
- ✅ Write media queries for different screen sizes
- ✅ Follow mobile-first responsive design approach
- ✅ Declare and use CSS custom properties (variables)
- ✅ Create maintainable color and spacing systems with variables
- ✅ Combine Grid, Flexbox, and responsive design for real layouts
- ✅ Test responsive designs in DevTools

---

## 🔜 Coming Up Next

**Class 12 will likely cover:**
- Advanced CSS techniques
- Transitions and animations
- Form styling
- CSS best practices and architecture
- Final project work

---

## 💡 Tips for Success

### 🆘 If You Get Stuck

1. **Use DevTools Grid Inspector** - Visualizes grid lines and areas
2. **Start simple** - Get basic grid working before adding complexity
3. **Test responsive early** - Don't wait until the end to check mobile
4. **Draw your layout** - Sketch grid structure on paper first
5. **Use CSS Grid Generator** - Tool to visualize and generate grid code

### ⚠️ Common Mistakes

- ❌ **Forgetting viewport meta tag** - Required for responsive design: `<meta name="viewport" content="width=device-width, initial-scale=1.0">`
- ❌ **Using px for breakpoints** - Consider using `em` for better accessibility
- ❌ **Too many breakpoints** - Start with 2-3, add more only if needed
- ❌ **Grid for everything** - Use Flexbox for simpler 1D layouts
- ❌ **Forgetting `--` prefix** - CSS variables must start with `--`
- ❌ **Not testing on real devices** - DevTools is good but test on actual phones/tablets

### 🎯 Remember

- **Grid lines are 1-indexed** - First line is 1, not 0
- **Mobile-first saves code** - Easier to add complexity than remove it
- **Variables cascade** - Scoped variables override root variables
- **Grid + Flexbox is powerful** - Use Grid for page layout, Flexbox for components
- **DevTools is essential** - Use grid inspector to understand what's happening
- **`fr` is your friend** - More intuitive than percentages for flexible sizing

---

## 🎓 Professional Skills Unlocked!

You now have the complete CSS layout toolkit:

- **Flexbox** for 1D layouts ✅
- **Grid** for 2D layouts ✅
- **Responsive design** with media queries ✅
- **Maintainable code** with CSS variables ✅
- **Modern patterns** for real-world sites ✅

These skills are what professional developers use every single day. You can now build any layout imaginable!

---

## 🔗 Class Navigation

← [Class 12 - CSS Fundamentals Review & Practice](../12-css-fundamentals-review/README.md) | [Class 14 - Coming Soon] →

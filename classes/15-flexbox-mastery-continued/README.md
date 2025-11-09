# Class 15 - Flexbox Mastery & Catch-Up Workshop

**Lead:** Timotej & Kiley  
**Date:** Tuesday, November 11, 2025

---

## 📋 Class Overview

**This is a special combined session:**
1. **Catch-up workshop** for those who missed Class 13's Flexbox practice
2. **Flexbox mastery** content for everyone building real-world layouts

**Goal:** Ensure everyone is comfortable with Flexbox before moving to CSS Grid.

---

## 📹 Class Recording

> **🎥 [Watch Class Recording](#)** ← *Link will be added within 24 hours*
>
> Missed class or want to review? Watch the full recording!

---

## 🎯 Today's Structure

### Part 1: Catch-Up & Review (First 45 minutes)
**Led by Timotej**

For students who missed Class 13 or need additional support:
- Review of Grid vs Flexbox concepts
- Walk-through of converting grid examples to Flexbox
- Understanding why HTML structure must change
- Individual assistance with the example conversions

**Assignment Review:**
- `example1.html` → Flexbox (photo gallery layout)
- `example2.html` → Flexbox (card layout)
- `example3.html` → Flexbox (navigation layout)

### Part 2: Flexbox Mastery for Everyone (Second 45 minutes)
**Led by Kiley**

Building common layout patterns:
- Navigation bars with logo and links
- Responsive card grids that wrap automatically
- Full-page layouts with header, sidebar, and footer
- GitHub and Render deployment support

---

## 📂 Class Materials

> **📁 [View Class 15 Files](./class-files/)**
>
> Working examples and practice tasks:
> - **Conversion examples** (solutions to Class 13 assignments)
> - **Navigation bar patterns**
> - **Responsive card grids**
> - **Full-page layout examples**
> - **Practice challenges**

---

## 📝 Part 1: Grid to Flexbox Conversions

### Understanding the Assignment

**Original Task:** Convert three grid-based layouts to use Flexbox instead, maintaining the same visual appearance.

### Why This Exercise Matters

**Grid vs Flexbox:**
- **Grid** = 2D layouts (controls both rows AND columns)
- **Flexbox** = 1D layouts (one direction: row OR column)

**The Challenge:** Recreate a 2D layout (Grid) using a 1D tool (Flexbox) by:
- Changing HTML structure
- Using nested Flexbox containers
- Leveraging `flex-wrap` for responsive behavior

---

### Example 1: Photo Gallery Conversion

**Original (Grid):**
```css
.photo-gallery {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 20px;
}
```

**Flexbox Solution:**
```css
.photo-gallery {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
}

.photo {
    flex: 1 1 200px;  /* grow, shrink, minimum basis */
}
```

**Key Differences:**
- Grid: Parent defines the grid, items just fill in
- Flexbox: Items control their own sizing with `flex` property
- Both can be responsive, but with different approaches

---

### Example 2: Card Layout Conversion

**When HTML Structure Must Change:**

Grid can place items anywhere in a 2D space. Flexbox flows in one direction, so complex layouts might need:
- Additional wrapper divs
- Nested Flexbox containers
- Different semantic structure

**Example: Three-column layout with header**

Grid approach (simpler HTML):
```html
<div class="grid-container">
    <header class="header">Header</header>
    <div class="item1">Item 1</div>
    <div class="item2">Item 2</div>
    <div class="item3">Item 3</div>
</div>
```

Flexbox approach (needs nesting):
```html
<div class="flex-container">
    <header class="header">Header</header>
    <div class="flex-row">
        <div class="item1">Item 1</div>
        <div class="item2">Item 2</div>
        <div class="item3">Item 3</div>
    </div>
</div>
```

---

### Example 3: Navigation Layout

**Best Use Case for Flexbox:**

Navigation bars are actually PERFECT for Flexbox (better than Grid):

```css
nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 20px;
}

.nav-links {
    display: flex;
    gap: 15px;
}
```

**Why Flexbox Wins Here:**
- Items flow naturally in one direction
- Easy alignment with `align-items`
- Simple spacing with `gap`
- Natural responsive behavior

---

## 💡 Part 2: Flexbox Mastery Patterns

### Pattern 1: Professional Navigation Bar

**What We're Building:**
```
┌────────────────────────────────────────┐
│ LOGO    Home  About  Services  Contact │
└────────────────────────────────────────┘
```

**Complete Code:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 40px;
            background: #333;
            color: white;
        }
        
        .logo {
            font-size: 24px;
            font-weight: bold;
        }
        
        .nav-links {
            display: flex;
            gap: 30px;
            list-style: none;
        }
        
        .nav-links a {
            color: white;
            text-decoration: none;
            transition: color 0.3s;
        }
        
        .nav-links a:hover {
            color: #64ffda;
        }
    </style>
</head>
<body>
    <nav>
        <div class="logo">LOGO</div>
        <ul class="nav-links">
            <li><a href="#home">Home</a></li>
            <li><a href="#about">About</a></li>
            <li><a href="#services">Services</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
    </nav>
</body>
</html>
```

**Key Flexbox Properties Used:**
- `justify-content: space-between` - Logo left, links right
- `align-items: center` - Vertically center everything
- `gap: 30px` - Space between nav links (cleaner than margins)
- Nested Flexbox - Nav is flex, nav-links is also flex

---

### Pattern 2: Responsive Card Grid

**What We're Building:**
```
┌─────────┐ ┌─────────┐ ┌─────────┐
│  Card 1 │ │  Card 2 │ │  Card 3 │
└─────────┘ └─────────┘ └─────────┘
(automatically wraps on smaller screens)
```

**The Magic Formula:**

```css
.card-container {
    display: flex;
    flex-wrap: wrap;      /* Allow wrapping to new lines */
    gap: 20px;            /* Space between cards */
    padding: 20px;
}

.card {
    flex: 1 1 250px;      /* THE KEY LINE! */
    padding: 20px;
    background: #f0f0f0;
    border-radius: 8px;
}
```

**Understanding `flex: 1 1 250px`:**
- **First `1`** (flex-grow) = Can grow to fill extra space
- **Second `1`** (flex-shrink) = Can shrink if needed
- **`250px`** (flex-basis) = Minimum width before wrapping to new line

**Result:** Cards automatically adjust! Wide screen = more per row, narrow screen = fewer per row.

---

### Pattern 3: Holy Grail Layout (Full Page)

**What We're Building:**
```
┌──────────────────────┐
│       Header         │
├─────┬────────────────┤
│Side │   Main Content │
│ bar │                │
├─────┴────────────────┤
│       Footer         │
└──────────────────────┘
```

**The Secret: Nested Flexbox + Flex-Direction**

```css
body {
    margin: 0;
    display: flex;
    flex-direction: column;   /* Vertical stack */
    min-height: 100vh;        /* Full viewport height */
}

header, footer {
    background: #333;
    color: white;
    padding: 20px;
}

.main-container {
    display: flex;            /* Horizontal layout */
    flex: 1;                  /* Grow to fill remaining space */
}

aside {
    width: 200px;             /* Fixed sidebar width */
    background: #f0f0f0;
    padding: 20px;
}

main {
    flex: 1;                  /* Main content takes remaining space */
    padding: 20px;
}
```

**Why Footer Sticks to Bottom:**
1. Body is `min-height: 100vh` (full viewport height)
2. Main container has `flex: 1` (grows to fill remaining vertical space)
3. Even with little content, footer stays at bottom!

---

## 🏋️ Practice Challenges

### Challenge 1: Photo Gallery (20 minutes)

**Requirements:**
- Minimum 200px per image
- Images wrap to new lines responsively
- Hover effect (e.g., scale or opacity)
- Smooth transition

**Starter Code:**
```html
<div class="gallery">
    <img src="https://via.placeholder.com/300" alt="Photo 1">
    <img src="https://via.placeholder.com/300" alt="Photo 2">
    <img src="https://via.placeholder.com/300" alt="Photo 3">
    <!-- Add more images -->
</div>
```

**CSS to Complete:**
```css
.gallery {
    display: flex;
    /* Add flex-wrap, gap, padding */
}

.gallery img {
    flex: /* Set appropriate values */;
    /* Add hover effects */
}
```

---

### Challenge 2: Pricing Cards (25 minutes)

**Requirements:**
- 3 pricing tiers side-by-side
- All cards equal height
- Button at bottom of each card
- Highlight "Popular" card differently
- Cards stack on mobile (we'll add media queries later)

**Hints:**
- Container: `display: flex; justify-content: center;`
- Cards: `display: flex; flex-direction: column;`
- To push button to bottom: Put features in a div with `flex-grow: 1`

---

### Challenge 3: Dashboard Header (Advanced)

**Build a search bar interface:**
```
┌────────────────────────────────────────┐
│ Logo   [   Search Box   ]   Profile   │
└────────────────────────────────────────┘
```

**Requirements:**
- Logo: fixed 50px width
- Search bar: grows to fill available space
- Profile icon: fixed 40px width
- All vertically centered
- 20px gap between items

**Hint:** Use `flex: 1` on the search bar container!

---

## 🏠 Homework & Practice

### Required Assignments

**1. Complete Grid-to-Flexbox Conversions**
- Finish converting all three examples from Class 13
- Create `-flexbox` versions of each file
- Push to your GitHub repository
- Deploy to Render and share the URL

**2. Build Your Own Navigation**
- Create a navigation bar for your personal website
- Include logo/site name on left
- Navigation links on right
- Add hover effects with transitions
- Must look professional!

**3. Create a Card Grid**
- Build a product or portfolio showcase
- At least 6 cards
- Responsive wrapping (test by resizing browser)
- Include images, titles, and descriptions
- Add subtle hover effects

**4. Holy Grail Layout**
- Build a full-page layout with header, sidebar, main, footer
- Test that footer sticks to bottom even with little content
- Add actual content (don't just use placeholder text)
- Style it professionally

---

### Extra Credit (Optional)

**Challenge: Complete Dashboard**
Build a mini dashboard with:
- Top navigation (logo, search, profile)
- Sidebar with menu items
- Main content area with cards showing stats
- Responsive behavior
- Professional styling

---

## 📖 Resources

### Flexbox Learning

**Interactive Games:**
- [Flexbox Froggy](https://flexboxfroggy.com/) - Learn Flexbox through gameplay
- [Flexbox Defense](http://www.flexboxdefense.com/) - Tower defense with Flexbox

**Visual Guides:**
- [CSS-Tricks - Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [Flexbox Patterns](https://flexboxpatterns.com/) - Common layout patterns

**Video Tutorials:**
- [Flexbox in 20 Minutes](https://www.youtube.com/watch?v=JJSoEo8JSnc)
- [Wes Bos - What the Flexbox?](https://flexbox.io/) - Free video course

### Documentation

- [MDN - Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout)
- [MDN - flex Property](https://developer.mozilla.org/en-US/docs/Web/CSS/flex)
- [Can I Use - Flexbox](https://caniuse.com/flexbox) - Browser compatibility

### Grid vs Flexbox

- [CSS-Tricks - Grid vs Flexbox](https://css-tricks.com/quick-whats-the-difference-between-flexbox-and-grid/)
- [MDN - Relationship of Grid to Other Layout Methods](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout/Relationship_of_Grid_Layout)

---

## ✅ What You Should Know After This Class

By the end of today, you should be able to:

- ✅ Explain when to use Grid vs Flexbox
- ✅ Convert grid-based layouts to Flexbox
- ✅ Understand why HTML structure sometimes needs to change
- ✅ Build navigation bars with Flexbox
- ✅ Create responsive card grids with `flex-wrap`
- ✅ Use `flex: 1 1 [basis]` effectively for responsive design
- ✅ Build full-page layouts with nested Flexbox
- ✅ Make footers stick to the bottom
- ✅ Use `gap` for spacing between flex items
- ✅ Apply hover effects with smooth transitions
- ✅ Debug layouts using browser DevTools

**Most Important:** You should feel confident building common layouts with Flexbox and know when Flexbox is the right tool for the job!

---

## 💡 Key Takeaways

### 1. Grid and Flexbox Complement Each Other
- **Grid** = 2D layouts (precise row AND column control)
- **Flexbox** = 1D layouts (flowing content in one direction)
- **Use both!** Grid for page structure, Flexbox for components

### 2. Flexbox is Perfect For:
- Navigation bars
- Card layouts that need to wrap
- Centering content
- Distributing space between items
- Aligning items vertically and horizontally

### 3. The `flex` Shorthand is Powerful
- `flex: 1` = "grow to fill space"
- `flex: 1 1 250px` = "grow, shrink, but minimum 250px wide"
- Master this and responsive layouts become easy!

### 4. Nested Flexbox = Complex Layouts
A flex container can also be a flex item. This allows you to create sophisticated layouts by combining multiple flex containers.

### 5. `gap` is Your Friend
`gap: 20px` is cleaner and more maintainable than adding margins to every item.

### 6. Always Test by Resizing
A truly responsive Flexbox layout works at any screen size. Constantly resize your browser while building!

---

## 🔜 Next Class

**Class 16** will introduce CSS Grid in depth, now that you're comfortable with Flexbox.

**Preview:**
- Grid template columns and rows
- Grid areas for named layouts
- auto-fit and minmax for responsive grids
- Combining Grid + Flexbox in real projects
- When to choose Grid over Flexbox

---

## 🎓 Remember

> "Flexbox is like LEGO blocks - once you understand the basic pieces, you can build anything!"

The patterns we learned today (navigation, cards, full-page layouts) are the foundation for 90% of web layouts. Practice these until they become second nature!

---

← [Class 14 - Flexbox Practice Check-In](../14-flexbox-mastery/README.md) | [Class 16 - CSS Grid & Responsive Design] →

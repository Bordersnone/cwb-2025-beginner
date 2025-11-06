# Class 14 - Flexbox Mastery & Layout Patterns

**Lead:** Kiley  
**Assistant:** Timotej  
**Date:** November 6, 2025

---

## 📋 Background

Based on student progress in Class 13, we're dedicating this class to mastering Flexbox through hands-on practice. Before diving into CSS Grid, we want to ensure everyone is confident with Flexbox - the tool you'll use most often for layouts.

**Philosophy:** Practice makes perfect. Today is about building real layouts, not just learning theory.

---

## 📹 Class Recording

> **🎥 [Watch Class Recording](#)** ← *Link will be added within 24 hours*
>
> Missed class or want to review? Watch the full recording to see us build layouts together!

---

## 📂 Class Materials

> **📁 [View Example Files](./class-files/)**
>
> Working examples and practice tasks are available:
> - **`navbar-example.html`** - Navigation bar pattern
> - **`card-grid-example.html`** - Responsive card grid
> - **`holy-grail-example.html`** - Full page layout
> - **`practice-task1.html`** - Photo gallery challenge
> - **`practice-task2.html`** - Pricing cards challenge

---

## 📚 Quick Links

- [What We'll Cover](#-what-well-cover)
- [Practice Exercises](#-practice-exercises)
- [Learning Resources](#-resources)
- [What You Should Know](#-what-you-should-know-after-this-class)

---

## 🎯 Today's Focus

**Goal:** Build confidence with Flexbox through hands-on practice with real-world layout patterns.

We'll build three common layouts together:
1. **Navigation Bar** - Horizontal navigation with logo and links
2. **Card Grid** - Responsive cards that wrap automatically
3. **Holy Grail Layout** - Full page with header, sidebar, main content, and footer

Then you'll practice with challenges on your own!

---

## 📝 What We'll Cover

### Quick Review: Block vs Inline vs Inline-Block

From Class 13, let's quickly recap:

**Block Elements** (`<div>`, `<p>`, `<h1>`):
- Take full width available
- Start on new line
- Accept width and height

**Inline Elements** (`<span>`, `<a>`, `<strong>`):
- Only take needed width
- Stay in same line
- Don't accept width/height

**Inline-Block**:
- Stay in line like inline
- Accept width/height like block
- Perfect for buttons, nav items

---

### Quick Review: Positioning

**Relative Positioning:**
```css
.element {
    position: relative;
    top: 10px;  /* Offset from original position */
}
```
- Element stays in normal flow
- Can be offset from where it would normally be
- Creates positioning context for absolute children

**Absolute Positioning:**
```css
.parent {
    position: relative;  /* Creates context */
}

.child {
    position: absolute;
    top: 20px;
    right: 20px;  /* Positioned relative to .parent */
}
```
- Element removed from normal flow
- Positioned relative to nearest positioned ancestor
- Common for overlays, badges, tooltips

---

### Pattern 1: Flexbox Navigation Bar

**What We're Building:**
```
┌────────────────────────────────────────┐
│ LOGO    Home  About  Services  Contact │
└────────────────────────────────────────┘
```

**Key Flexbox Properties:**

```css
nav {
    display: flex;                    /* Make it flexbox */
    justify-content: space-between;   /* Logo left, links right */
    align-items: center;              /* Vertically center */
    gap: 30px;                        /* Space between items */
}

.nav-links {
    display: flex;                    /* Nested flexbox! */
    gap: 20px;                        /* Space between links */
}
```

**Why This Works:**
- `space-between` pushes items to edges
- Nested flexbox (nav is flex, nav-links is also flex)
- `gap` is easier than margins for spacing
- `align-items: center` handles vertical alignment

📺 **Example:** [navbar-example.html](./class-files/navbar-example.html)

---

### Pattern 2: Responsive Card Grid

**What We're Building:**
```
┌─────────┐ ┌─────────┐ ┌─────────┐
│  Card 1 │ │  Card 2 │ │  Card 3 │
└─────────┘ └─────────┘ └─────────┘
(wraps to new line on smaller screens)
```

**The Magic Formula:**

```css
.card-container {
    display: flex;
    flex-wrap: wrap;      /* Allow wrapping */
    gap: 20px;            /* Space between cards */
}

.card {
    flex: 1 1 250px;      /* The key to responsive cards! */
}
```

**Understanding `flex: 1 1 250px`:**
- **First `1`** = Can grow to fill space
- **Second `1`** = Can shrink if needed
- **`250px`** = Minimum width before wrapping to new line

**Result:** Cards automatically wrap when screen gets too narrow!

📺 **Example:** [card-grid-example.html](./class-files/card-grid-example.html)

---

### Pattern 3: Holy Grail Layout

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

**The Secret: Nested Flexbox**

```css
/* Outer container - vertical layout */
body {
    display: flex;
    flex-direction: column;
    min-height: 100vh;      /* Full viewport height */
}

/* Middle section - horizontal layout */
.main-container {
    display: flex;           /* Now horizontal (default) */
    flex: 1;                /* Grow to fill space */
}

aside {
    width: 200px;           /* Fixed sidebar width */
}

main {
    flex: 1;                /* Main content takes remaining space */
}
```

**Why Footer Sticks to Bottom:**
1. Body is `min-height: 100vh` (full viewport)
2. Main container has `flex: 1` (grows to fill remaining space)
3. Footer stays at bottom even with little content!

📺 **Example:** [holy-grail-example.html](./class-files/holy-grail-example.html)

---

## 🏋️ Practice Exercises

### Exercise 1: Photo Gallery (20 minutes)

**Challenge:** Build a responsive image gallery using Flexbox.

**Requirements:**
- Images wrap to new lines when screen narrows
- Minimum 200px per image
- Images grow to fill space
- Add hover effect (your choice!)
- Smooth transitions

**Starter File:** [practice-task1.html](./class-files/practice-task1.html)

**Hints:**
- Use `flex-wrap: wrap`
- Use `flex: 1 1 200px` on gallery items
- Add `transition` for hover effects

---

### Exercise 2: Pricing Cards (25 minutes)

**Challenge:** Create pricing cards with equal heights and buttons at bottom.

**Requirements:**
- Cards side-by-side (centered)
- All cards same height
- Button always at bottom of card
- Hover effect on cards
- Use flexbox inside cards too!

**Starter File:** [practice-task2.html](./class-files/practice-task2.html)

**Hints:**
- Container: `display: flex; justify-content: center;`
- Cards: `display: flex; flex-direction: column;`
- Features list: `flex-grow: 1` (pushes button to bottom)

---

### Exercise 3: Build Your Own Navigation

**Challenge:** Create a navigation bar for your personal website.

**Requirements:**
- Logo or site name on left
- Navigation links on right
- Hover effects
- Responsive (we'll improve with media queries later)

**Start from scratch** or copy `navbar-example.html` and customize it!

---

### Exercise 4: Dashboard Header (Advanced)

**Challenge:** Build a dashboard header with three sections.

**Layout:**
```
┌────────────────────────────────────────┐
│ Logo   [   Search Bar   ]   Profile   │
└────────────────────────────────────────┘
```

**Requirements:**
- Logo: fixed size
- Search bar: grows to fill available space
- Profile: fixed size
- All vertically centered

**Hint:** Use `flex: 1` on the search bar!

---

## 🏠 Homework & Practice

### Required Assignments

**1. Complete Both Practice Tasks**

Finish `practice-task1.html` and `practice-task2.html`:
- Photo gallery with responsive wrapping
- Pricing cards with equal heights
- Push to GitHub when complete

**2. Build a Navigation Bar**

Create a professional navigation for your personal website:
- Logo on left, links on right
- Hover effects with transitions
- Clean, professional styling
- Test by resizing browser

**3. Holy Grail Layout Practice**

Recreate the full-page layout from class:
- Header, sidebar, main content, footer
- Footer sticks to bottom
- Test with different amounts of content
- Take screenshots showing it works

**4. Flexbox Patterns Study**

Create `flexbox-experiments.html` and try:
- Different `justify-content` values
- Different `align-items` values
- Different `flex-direction` values
- Nested flexbox patterns
- Document what each property does (in comments)

---

### Extra Credit (Optional)

**Challenge 1: Product Cards**

Build a product showcase with:
- Product image
- Title and description
- Price
- "Add to Cart" button at bottom
- 3 cards per row on desktop, 1 on mobile

**Challenge 2: Team Member Grid**

Create a team page with:
- Member photos (circular with `border-radius: 50%`)
- Name and title
- Social media links
- Responsive grid layout

**Challenge 3: Feature Sections**

Build alternating feature sections:
- Image on left, text on right
- Text on left, image on right (next section)
- Responsive (stack on mobile)

---

## 📖 Learning Resources

### Flexbox Resources

**Interactive Practice:**
- [Flexbox Froggy](https://flexboxfroggy.com/) - Learn through a game (highly recommended!)
- [Flexbox Defense](http://www.flexboxdefense.com/) - Tower defense game teaching Flexbox

**Visual Guides:**
- [CSS-Tricks - Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/) - Best visual reference
- [Flexbox Patterns](https://flexboxpatterns.com/) - Copy-paste common patterns

**Video Tutorials:**
- [Flexbox in 20 Minutes](https://www.youtube.com/watch?v=JJSoEo8JSnc)
- [Flexbox Tutorial for Beginners](https://www.youtube.com/watch?v=fYq5PXgSsbE)

**Documentation:**
- [MDN - Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout) - Complete docs
- [MDN - flex Property](https://developer.mozilla.org/en-US/docs/Web/CSS/flex) - Deep dive into flex shorthand

### Layout Inspiration

- [Every Layout](https://every-layout.dev/) - Modern layout patterns
- [Dribbble](https://dribbble.com/search/web-layout) - Design inspiration

---

## ✅ What You Should Know After This Class

By the end of today, you should be able to:

- ✅ Build a navigation bar with Flexbox
- ✅ Create responsive card grids that wrap automatically
- ✅ Understand `flex: 1 1 [basis]` and use it effectively
- ✅ Build full-page layouts with nested Flexbox
- ✅ Make footers stick to bottom of page
- ✅ Use `gap` for spacing between flex items
- ✅ Apply hover effects with transitions
- ✅ Debug Flexbox layouts with DevTools
- ✅ Know when to use block, inline, and inline-block
- ✅ Use positioning for overlays and special layouts

**Most Important:** You should feel confident building common layouts with Flexbox!

---

## 💡 Key Takeaways

### 1. Flexbox is for One Direction
Row OR column. For layouts that need both rows AND columns precisely controlled, that's when Grid comes in (next class!).

### 2. Nested Flexbox is Powerful
A flex container can also be a flex item. Use this for complex layouts (nav bar with links, page with sections, etc.).

### 3. The Flex Shorthand is Your Friend
`flex: 1 1 250px` = grow, shrink, minimum basis. Master this and responsive layouts become easy.

### 4. Gap is Better Than Margin
`gap: 20px` is cleaner than adding margins to every item. Use it!

### 5. Always Test by Resizing
A truly responsive layout works at any size. Resize your browser constantly while building.

### 6. DevTools Shows Everything
Use the Flexbox inspector in DevTools to see exactly what's happening with your layouts.

---

## 🔜 Coming Up Next

**Class 15** will cover CSS Grid - the tool for 2D layouts. Now that you're comfortable with Flexbox, you'll understand when Grid is the better choice.

**Preview:**
- When to use Grid vs Flexbox
- Grid template columns and rows
- Auto-fit and minmax for responsive grids
- Grid areas for complex layouts
- Combining Grid + Flexbox

---

## 🎓 Remember

> "The best way to learn Flexbox is to build with it. Don't just read - code!"

Today is about hands-on practice. Build the examples, try the challenges, experiment and break things. That's how you learn!

---

← [Class 13 - Flexbox Practice & CSS Fundamentals Q&A](../13-flexbox-practice-fundamentals/README.md) | [Class 15 - CSS Grid & Responsive Design] →

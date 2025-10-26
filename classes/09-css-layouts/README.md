# Class 09 - Intro to Flexbox & Layout Techniques

**Lead:** Timotej
**Assistant:** None
**Date:** October 21, 2025

---

## 📹 Class Recording

> **🎥 [Watch Class Recording](#)** ← *Add link here when available*
>
> Missed class or want to review? Watch the full recording to see Flexbox concepts demonstrated live.

---

## 📂 Class Example File

> **📄 [View Class Example](./class-files/index.html)**
>
> Timotej created a working example during class that demonstrates:
> - Flexbox sidebar layout with sticky positioning
> - Overflow handling in scrollable containers
> - Flex properties for responsive footers
> - Gap spacing between flex items
>
> Open this file in your browser to see it in action, then inspect the code to understand how it works!

---

## 📚 Quick Links

- [What We Covered](#-what-we-actually-covered)
- [Practice Exercises](#-practice-exercises)
- [Video Resources](#-resources)
- [What You Should Know](#-what-you-should-know-after-this-class)

---

## 📝 What We Actually Covered

> **Overview:** Introduction to Flexbox as the primary tool for creating modern CSS layouts. Demonstrated practical layouts including sidebars with sticky positioning, overflow handling, and flexible footer designs.

### Topic 1: Flexbox Fundamentals

**Focus:** Understanding how Flexbox works and when to use it.

#### What is Flexbox?

**Flexbox (Flexible Box Layout)** is a CSS layout system designed for:
- Arranging items in rows or columns
- Distributing space between items
- Aligning items vertically and horizontally
- Creating responsive layouts without complex calculations

#### Core Flexbox Concept: Container & Items

**Container (Parent):**
```css
.container {
    display: flex;  /* This activates Flexbox */
}
```

**Items (Children):**
- Direct children of a flex container automatically become flex items
- Flex properties control how items behave within the container

#### Key Properties Demonstrated

**`display: flex`** - Activates Flexbox on a container  
→ Example from class: `.wrap { display: flex; }` creates a horizontal layout

**`flex-direction`** - Controls the main axis direction  
→ Example: `.sidebar-content { flex-direction: column; }` stacks items vertically
- `row` (default) - horizontal left to right
- `column` - vertical top to bottom

**`gap`** - Adds space between flex items (modern, clean approach)  
→ Example: `gap: 12px;` creates consistent spacing without margins

**`flex`** - Shorthand for flex-grow, flex-shrink, and flex-basis  
→ Example from footer: `flex: 1 1 0;` makes items grow equally to fill space

### Topic 2: Position Sticky

**Focus:** Creating elements that stick to the viewport while scrolling.

**`position: sticky`** - Hybrid between relative and fixed positioning  
→ Example: `.sidebar-content { position: sticky; top: 0; }`

**How it works:**
- Element is positioned relative until a scroll threshold is met
- Then it "sticks" at the specified position (`top: 0`)
- Remains sticky within its parent container

**Common use cases:**
- Sticky navigation headers
- Sidebar menus that follow scrolling
- Table headers in long tables

### Topic 3: Overflow Handling

**Focus:** Managing content that exceeds container dimensions.

**`overflow-y: auto`** - Adds vertical scrollbar when needed  
→ Example: Sidebar content can scroll independently from main content

**Overflow values:**
- `visible` (default) - Content extends beyond container
- `hidden` - Content is clipped, no scrollbar
- `scroll` - Always shows scrollbar
- `auto` - Shows scrollbar only when needed

**Why this matters:**
- Fixed-height containers need overflow handling
- Prevents content from breaking layout
- Creates scrollable areas within the page

### Topic 4: Practical Layout Pattern

**Focus:** Building a common web layout (sidebar + main content).

#### Structure from Class Example:

```html
<div class="wrap">  <!-- Flex container -->
    <div class="sidebar">  <!-- Flex item 1 -->
        <div class="sidebar-content">  <!-- Sticky, scrollable -->
            <!-- Navigation items -->
        </div>
    </div>
    <div class="main">  <!-- Flex item 2 -->
        <!-- Main content -->
    </div>
</div>
```

#### CSS Pattern:

```css
.wrap {
    display: flex;  /* Horizontal layout */
}

.sidebar {
    width: 10%;
    min-width: 300px;  /* Ensures sidebar doesn't get too narrow */
}

.sidebar-content {
    position: sticky;  /* Sticks to top */
    top: 0;
    height: 100vh;  /* Full viewport height */
    overflow-y: auto;  /* Scrollable if content is long */
    display: flex;
    flex-direction: column;  /* Stack items vertically */
    gap: 12px;  /* Space between items */
}
```

### 💡 Key Concepts from Class

- ✅ **Flexbox is the modern standard** for layouts (replaces older float-based techniques)
- ✅ **Container vs Items** - Always identify which element is the flex container and which are the items
- ✅ **Gap property** - Cleaner than using margins on individual items
- ✅ **Position sticky + overflow** - Powerful combination for sidebar navigation
- ✅ **`flex: 1 1 0`** - Makes items grow equally to fill available space

---

## 🏠 Practice Exercises

> **💡 TIP:** Start by studying the [class example file](./class-files/index.html) to see these concepts in action!

> **📺 [View All Video Tutorials](../../resources/video-tutorials.md)** - Complete library of curated YouTube videos

---

### Exercise 1: Understand the Class Example (15-20 minutes)

Before building your own, study what was demonstrated in class.

**Steps:**
1. Open `./class-files/index.html` in your browser
2. Observe:
   - The sidebar stays visible while scrolling
   - The sidebar content is scrollable independently
   - The footer items distribute evenly
3. Open the file in VS Code and find:
   - Where `display: flex` is used (line 30 for `.wrap`, line 14 for `.sidebar-content`)
   - The `position: sticky` on `.sidebar-content` (line 18)
   - The `overflow-y: auto` that makes sidebar scrollable (line 63)
   - The `flex: 1 1 0` on footer items (line 37)
4. Use browser DevTools to inspect and toggle these properties on/off

---

### Exercise 2: Build a Simple Flexbox Layout (20-30 minutes)

Create your own simple sidebar layout using the concepts from class.

**Goal:** Build a two-column layout with a sidebar and main content area.

**Steps:**
1. Create a new HTML file called `flexbox-practice.html`
2. Add this basic structure:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Flexbox Practice</title>
    <style>
        body {
            margin: 0;
            font-family: sans-serif;
        }
        
        .container {
            display: flex;
            /* TODO: Add your flex properties here */
        }
        
        .sidebar {
            width: 250px;
            background-color: #f0f0f0;
            padding: 20px;
            /* TODO: Try making this sticky */
        }
        
        .main {
            flex: 1;
            padding: 20px;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="sidebar">
            <h2>Navigation</h2>
            <p>Link 1</p>
            <p>Link 2</p>
            <p>Link 3</p>
        </div>
        <div class="main">
            <h1>Main Content</h1>
            <p>Add several paragraphs here...</p>
        </div>
    </div>
</body>
</html>
```

3. **Experiment with:**
   - Adding `position: sticky; top: 0;` to `.sidebar`
   - Adding `height: 100vh;` to `.sidebar` 
   - Using `flex-direction: column;` in `.sidebar` to stack links
   - Adding `gap` property to create spacing

📺 **Watch if you need help:** [Flexbox in 15 Minutes](https://www.youtube.com/watch?v=fYq5PXgSsbE)

---

### Exercise 3: Experiment with Overflow (15 minutes)

Practice using overflow to handle content that's too long for a container.

**Steps:**
1. Modify your sidebar from Exercise 2
2. Add a fixed height: `height: 400px;`
3. Add lots of content (many paragraphs)
4. Observe what happens (content overflows)
5. Fix it by adding: `overflow-y: auto;`

**Experiment with different overflow values:**
- `overflow-y: visible` (default)
- `overflow-y: hidden`
- `overflow-y: scroll`
- `overflow-y: auto`

**Which one is best for a sidebar? Why?**

---

### Exercise 4: Recreate the Footer from Class (10 minutes)

The class example showed a flexible footer. Try to recreate it!

**Goal:** Create a footer with 3 items that distribute evenly.

```html
<footer style="display: flex; gap: 10px; padding: 12px;">
    <div class="footer-item">Contact</div>
    <div class="footer-item">About Us</div>
    <div class="footer-item">Portfolio</div>
</footer>
```

**CSS to add:**
```css
.footer-item {
    flex: 1 1 0;  /* What does this do? */
    padding: 12px;
    background-color: #e7e9eb;
    text-align: center;
}
```

**Questions to explore:**
- What happens if you remove `flex: 1 1 0`?
- What if you change it to `flex: 2 1 0` on just one item?
- What does each number in `flex: 1 1 0` mean?

---

### Exercise 5: Study and Modify (Optional)

Take the class example file and experiment:

1. Change `flex-direction: column` to `row` on `.sidebar-content` - what happens?
2. Remove `position: sticky` - how does behavior change?
3. Change the `gap` values - see the spacing adjust
4. Add `justify-content: center` to `.sidebar-content` - what changes?

**Document your findings** in comments in your code!

---

## 🏠 Homework & Practice

### Required Practice

**1. Complete All Practice Exercises**

Make sure you've completed Exercises 1-4 above. These demonstrate understanding of:
- Basic Flexbox container/item relationship
- Sticky positioning
- Overflow handling
- Flexible layouts

**2. Build Your Own Layout**

Create a simple page with:
- A header
- A two-column layout (sidebar + main content) using Flexbox
- A footer with at least 3 evenly-distributed items
- Use `gap` for spacing
- Make the sidebar sticky

**3. Play Flexbox Froggy**

Complete at least the first 12 levels of [Flexbox Froggy](https://flexboxfroggy.com/) to reinforce the concepts.

**4. Document Your Understanding**

In a comment at the top of your practice file, answer:
- What does `display: flex` do?
- What's the difference between `flex-direction: row` and `column`?
- When would you use `position: sticky`?
- What's the purpose of `overflow-y: auto`?

---

### Extra Credit (Optional)

**Challenge 1: Combine Sticky + Overflow**

Create a layout where:
- The sidebar is sticky
- The sidebar has a fixed height (`100vh`)
- The sidebar content is scrollable independently
- The main content can scroll freely

**Challenge 2: Experiment with `flex` Shorthand**

Create 3 boxes in a flex container and experiment:
- `flex: 1 1 0` on all (equal distribution)
- `flex: 2 1 0` on one box (takes more space)
- `flex: 0 0 200px` on one box (fixed width)

Document what each value means!

**Challenge 3: Nested Flexbox**

Create a flexbox container that has items which are also flexbox containers. For example:
- Main container: horizontal flex
- Each item: vertical flex with multiple elements inside

---

## 📖 Resources

### 📺 Video Tutorials

**Flexbox Basics:**
- [Flexbox in 15 Minutes](https://www.youtube.com/watch?v=fYq5PXgSsbE) - Quick intro
- [Flexbox Tutorial (30 min)](https://www.youtube.com/watch?v=JJSoEo8JSnc) - Comprehensive guide
- [Flexbox Crash Course](https://www.youtube.com/watch?v=3YW65K6LcIA) - Visual examples

**Position Sticky:**
- [CSS Position Sticky Explained (6 min)](https://www.youtube.com/watch?v=NzjU1GmKosQ)
- [Sticky Positioning Tutorial (10 min)](https://www.youtube.com/watch?v=B6xQvF0vBo0)

**Overflow:**
- [CSS Overflow Property (5 min)](https://www.youtube.com/watch?v=VGJm0N0P-5g)

### 📄 Written Documentation

- [MDN - Flexbox Guide](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox) - Complete reference
- [CSS-Tricks - Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/) - Visual guide with examples
- [MDN - Position Sticky](https://developer.mozilla.org/en-US/docs/Web/CSS/position#sticky)
- [MDN - Overflow](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow)

### 🎮 Interactive Learning

- [Flexbox Froggy](https://flexboxfroggy.com/) - Learn Flexbox through a fun game (highly recommended!)
- [Flexbox Defense](http://www.flexboxdefense.com/) - Tower defense game using Flexbox
- [Flexbox Zombies](https://mastery.games/flexboxzombies/) - Story-based Flexbox game

---

## ✅ What You Should Know After This Class

**By the end of today, you should be able to:**

- ✅ Understand what Flexbox is and why it's the modern standard for layouts
- ✅ Identify the flex container vs flex items in a layout
- ✅ Use `display: flex` to create horizontal and vertical layouts
- ✅ Use `flex-direction` to control the main axis (row vs column)
- ✅ Use `gap` to add consistent spacing between flex items
- ✅ Understand the `flex` shorthand property (e.g., `flex: 1 1 0`)
- ✅ Use `position: sticky` to create elements that stick while scrolling
- ✅ Handle content overflow with `overflow-y: auto`
- ✅ Build a basic sidebar + main content layout
- ✅ Explain when to use Flexbox vs other layout methods

---

## 🔜 Next Class

**Class 10 - Advanced Flexbox & Box Model:**
- Deep dive into flex-grow, flex-shrink, and flex-basis
- Complete understanding of the box model (margin, padding, borders)
- Display properties: inline, inline-block, block, flex
- CSS units: relative (rem, em, %) vs absolute (px)
- Navigation best practices with unordered lists

---

## 💡 Tips for Success

### 🆘 If You Get Stuck

1. **Study the class example first** - It demonstrates all the key concepts
2. **Use browser DevTools** - Inspect the flexbox container to see how items behave
3. **Add temporary borders** - `outline: 1px solid red;` helps visualize flex items
4. **Check the parent** - Make sure `display: flex` is on the container, not the items
5. **Test one property at a time** - Don't change multiple things at once

### ⚠️ Common Mistakes

- ❌ **Forgetting `display: flex`** on the container element
- ❌ **Confusing container vs items** - Flex properties apply to items, not the container
- ❌ **Wrong element has sticky** - `position: sticky` goes on the element you want to stick
- ❌ **Missing overflow** - Fixed-height containers need `overflow` to handle long content
- ❌ **Using margins instead of gap** - `gap` is cleaner for flex spacing

### 🎯 Remember

- **Container vs Items is crucial** - Always identify which is which
- **Flexbox replaces floats** - The modern way to create layouts
- **Sticky needs a scroll container** - Won't work without scrollable content
- **Play Flexbox Froggy** - Best way to internalize the concepts

---

## 🎓 Professional Skills Unlocked!

You're now using the same layout tools professional developers use daily:

- **Flexbox** for modern layouts ✅
- **Position sticky** for persistent navigation ✅
- **Overflow control** for scrollable areas ✅
- **Container/item thinking** for structure ✅

These are fundamental skills for any web developer. Keep practicing!

---

## 🔗 Class Navigation

← [Class 08 - Intro to CSS & Text/Font Properties](../08-css-text/README.md) | [Class 10 - Advanced Flexbox & Box Model](../10-css-layouts-2/README.md) →

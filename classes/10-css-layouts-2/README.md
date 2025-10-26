# Class 10 - Advanced Flexbox & The Box Model

**Lead:** Timotej  
**Assistant:** None  
**Date:** October 23, 2025

---

## 📹 Class Recording

> **🎥 [Watch Class Recording](https://app.read.ai/analytics/meetings/01K88WSZ6S004VV60B3R7RPJ1S)**
>
> Missed class or want to review? Watch the full recording to see advanced Flexbox and Box Model concepts demonstrated live.

---

## 📂 Class Example Files

> **📁 [View Class Examples](./class-files/)**
>
> Timotej created multiple demonstration files during class:
> - **`flex-overflow.html`** - Horizontal overflow with flex-shrink
> - **`inline-block.html`** - Display inline-block behavior
> - **`Document.html`** through **`Document10.html`** - Various flex property demonstrations
>
> Open these files in your browser and inspect the code to understand each concept!

---

## 📚 Quick Links

- [What We Covered](#-what-we-actually-covered)
- [Practice Exercises](#-practice-exercises)
- [Learning Resources](#-resources)
- [What You Should Know](#-what-you-should-know-after-this-class)

---

## 📝 What We Actually Covered

> **Overview:** Deep dive into Flexbox properties (flex-grow, flex-shrink, flex-basis), complete coverage of the CSS Box Model, display properties, and CSS units. This class built significantly on the Flexbox introduction from Class 09.

### Topic 1: Advanced Flexbox Properties

**Focus:** Understanding the `flex` shorthand and how flex items grow, shrink, and size themselves.

#### The `flex` Shorthand

**Syntax:** `flex: [flex-grow] [flex-shrink] [flex-basis]`

Example: `flex: 1 1 0` means:
- **`flex-grow: 1`** - Item can grow to fill available space
- **`flex-shrink: 1`** - Item can shrink if needed
- **`flex-basis: 0`** - Starting size before growing/shrinking

#### flex-grow

**Purpose:** Controls how items expand to fill available space.

```css
.item1 { flex-grow: 1; }  /* Takes 1 unit of space */
.item2 { flex-grow: 2; }  /* Takes 2 units of space (twice as much) */
```

→ If there's 300px of extra space and two items have `flex-grow: 1`:
  - Each gets 150px
→ If one has `flex-grow: 2` and one has `flex-grow: 1`:
  - First gets 200px, second gets 100px

#### flex-shrink

**Purpose:** Controls how items shrink when container is too small.

```css
.item { flex-shrink: 1; }  /* Can shrink (default) */
.item-fixed { flex-shrink: 0; }  /* Won't shrink */
```

→ Demonstrated in `flex-overflow.html` - items with `flex-shrink: 0` maintain their width even when container is smaller

#### flex-basis

**Purpose:** Sets the initial size of a flex item before growing/shrinking.

```css
.item { flex-basis: 200px; }  /* Starts at 200px */
.item { flex-basis: 50%; }  /* Starts at 50% of container */
.item { flex-basis: 0; }  /* Ignores content size, only growth matters */
```

**Common pattern:** `flex: 1 1 0` makes items share space equally regardless of content

### Topic 2: Alignment in Flexbox

**Focus:** Controlling horizontal and vertical alignment of flex items.

#### justify-content (Main Axis - usually horizontal)

Controls spacing **between** and **around** items:

```css
.container {
    display: flex;
    justify-content: flex-start;  /* Default - items at start */
    justify-content: center;  /* Items centered */
    justify-content: space-between;  /* Space between items */
    justify-content: space-around;  /* Space around items */
    justify-content: space-evenly;  /* Equal space everywhere */
}
```

#### align-items (Cross Axis - usually vertical)

Controls how items align vertically within the container:

```css
.container {
    display: flex;
    align-items: stretch;  /* Default - fill height */
    align-items: center;  /* Center vertically */
    align-items: flex-start;  /* Align to top */
    align-items: flex-end;  /* Align to bottom */
}
```

#### gap

Modern way to add spacing between flex items:

```css
.container {
    display: flex;
    gap: 10px;  /* 10px between all items */
    gap: 10px 20px;  /* 10px vertical, 20px horizontal */
}
```

→ **Best practice:** Use `gap` instead of margins on individual items

### Topic 3: The CSS Box Model

**Focus:** Understanding how spacing, borders, and sizing work on all elements.

#### Box Model Components

Every element has four layers (inside to outside):

```
┌────────────────────────────┐
│       MARGIN (outside)     │
│  ┌──────────────────────┐  │
│  │   BORDER             │  │
│  │  ┌────────────────┐  │  │
│  │  │  PADDING       │  │  │
│  │  │  ┌──────────┐  │  │  │
│  │  │  │ CONTENT  │  │  │  │
│  │  │  └──────────┘  │  │  │
│  │  └────────────────┘  │  │
│  └──────────────────────┘  │
└────────────────────────────┘
```

1. **Content** - The actual text, image, etc.
2. **Padding** - Space between content and border
3. **Border** - The edge/outline of the element
4. **Margin** - Space outside the border (between elements)

#### Padding

Adds space **inside** an element:

```css
.box {
    padding: 10px;  /* All sides */
    padding: 10px 20px;  /* top/bottom, left/right */
    padding: 10px 20px 30px 40px;  /* top, right, bottom, left (clockwise) */
    
    /* Or individual sides */
    padding-top: 10px;
    padding-right: 20px;
    padding-bottom: 30px;
    padding-left: 40px;
}
```

→ Padding **expands** the element's visible size
→ Background color extends into padding area

#### Margin

Adds space **outside** an element:

```css
.box {
    margin: 20px;  /* All sides */
    margin: 20px 0;  /* top/bottom, left/right */
    
    /* Auto margins for centering */
    margin: 0 auto;  /* Centers block element horizontally */
    margin-left: auto;  /* Pushes element to the right (in flexbox) */
}
```

**Important:** 
- Margins **collapse** - adjacent vertical margins combine (take the larger value)
- Auto margins in flexbox consume available space

#### Borders

Adds a visible edge around padding:

```css
.box {
    border: 2px solid black;  /* Shorthand */
    
    /* Or specify each part */
    border-width: 2px;
    border-style: solid;  /* solid, dashed, dotted, etc. */
    border-color: black;
    
    /* Individual sides */
    border-top: 1px solid red;
    border-radius: 8px;  /* Rounded corners */
}
```

**Border styles:**
- `solid` - Single solid line
- `dashed` - Dashed line
- `dotted` - Dotted line
- `double` - Double line
- `none` - No border

### Topic 4: Display Properties

**Focus:** Understanding how different display values affect element behavior.

#### display: block

**Behavior:**
- Takes full width available
- Starts on new line
- Can set width and height
- Respects all margins and padding

**Examples:** `<div>`, `<p>`, `<h1>`, `<section>`

```css
.block-element {
    display: block;
    width: 50%;  /* Works */
    margin: 20px auto;  /* Centering works */
}
```

#### display: inline

**Behavior:**
- Only takes as much width as content needs
- Stays on same line with other inline elements
- **Cannot** set width or height
- Vertical margin/padding don't work properly

**Examples:** `<span>`, `<a>`, `<strong>`

```css
.inline-element {
    display: inline;
    width: 200px;  /* Ignored! */
    padding: 10px 20px;  /* Horizontal works, vertical doesn't */
}
```

#### display: inline-block

**Behavior:**
- Stays on same line (like inline)
- **Can** set width and height (like block)
- Respects all margins and padding
- Good for layouts mixing text and blocks

**Use cases:** Navigation items, tags, badges

```css
.inline-block-element {
    display: inline-block;
    width: 150px;  /* Works! */
    height: 50px;  /* Works! */
    margin: 10px;  /* All margins work */
}
```

→ Demonstrated in `inline-block.html`

#### display: flex

**Behavior:**
- Creates flex container
- Direct children become flex items
- Enables all flex properties
- **Modern standard** for layouts

```css
.flex-container {
    display: flex;
    gap: 10px;
    justify-content: space-between;
}
```

### Topic 5: CSS Units

**Focus:** Understanding relative vs absolute units.

#### Relative Units

**Depend on other values:**

**`%` (percent)** - Relative to parent element
```css
.child {
    width: 50%;  /* 50% of parent's width */
}
```

**`em`** - Relative to element's font-size
```css
.element {
    font-size: 16px;
    padding: 1em;  /* 16px */
    margin: 2em;  /* 32px */
}
```

**`rem`** - Relative to root element's font-size
```css
:root { font-size: 16px; }
.element {
    padding: 1rem;  /* Always 16px */
    font-size: 2rem;  /* Always 32px */
}
```

→ **Best practice:** Use `rem` for consistent sizing

#### Absolute Units

**Always the same size:**

**`px` (pixels)** - Most common
```css
.element {
    width: 300px;  /* Always 300 pixels */
}
```

**Other absolute units:**
- `cm`, `mm` - Centimeters, millimeters (for print)
- `in` - Inches (for print)
- `pt` - Points (for print, 1pt = 1/72 inch)

→ **Use `px` for screens, `cm`/`mm`/`in` for print/PDFs**

### Topic 6: Navigation Best Practices

**Focus:** Using unordered lists for semantic navigation.

#### Why Use `<ul>` for Navigation?

- **Semantic meaning** - Indicates a list of navigation items
- **Accessibility** - Screen readers announce it as navigation
- **Convention** - Industry standard, looks good in code

#### Pattern for Navigation

```html
<nav>
    <ul>
        <li><a href="#home">Home</a></li>
        <li><a href="#about">About</a></li>
        <li><a href="#contact">Contact</a></li>
    </ul>
</nav>
```

```css
/* Remove default list styling */
nav ul {
    list-style-type: none;  /* Removes bullets */
    margin: 0;
    padding: 0;
    display: flex;  /* Horizontal layout */
    gap: 20px;
}

nav a {
    text-decoration: none;  /* Remove underline */
    color: inherit;
}
```

→ Could use divs, but `<ul>`/`<li>` is more semantic

### 💡 Key Concepts from Class

- ✅ **`flex: 1 1 0` is your friend** - Makes items share space equally
- ✅ **Box model affects total size** - padding and border add to width/height
- ✅ **Auto margins in flexbox** - Consume available space (useful for alignment)
- ✅ **Display changes behavior** - block, inline, inline-block, flex all work differently
- ✅ **Use rem for consistency** - Relative to root, not parent
- ✅ **Margin collapse** - Vertical margins between elements combine
- ✅ **Float is old** - Flexbox is the modern replacement

---

## 🏠 Practice Exercises

> **💡 TIP:** Study the [class example files](./class-files/) first to see these concepts in action!

---

### Exercise 1: Explore the Class Examples (20 minutes)

Before building your own, understand what was demonstrated.

**Steps:**
1. Open each file in `./class-files/` in your browser
2. For `flex-overflow.html`:
   - Observe how items with `flex-shrink: 0` behave
   - Try removing `flex-shrink: 0` - what happens?
   - Add `overflow-x: scroll` to see horizontal scrolling
3. For `inline-block.html`:
   - Note the two div's side-by-side
   - Change `display: inline-block` to `display: block` - what changes?
   - Try `display: flex` on the parent - how is it different?
4. Use DevTools to inspect and modify properties

---

### Exercise 2: Build a Flexible Card Layout (30 minutes)

Create a row of cards that resize appropriately.

**Goal:** 3 cards that share space equally, but one can be emphasized.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Flex Cards</title>
    <style>
        .container {
            display: flex;
            gap: 20px;
            padding: 20px;
        }
        
        .card {
            flex: 1 1 0;  /* Equal distribution */
            padding: 20px;
            background: #f0f0f0;
            border: 2px solid #333;
            border-radius: 8px;
        }
        
        .card.featured {
            flex: 2 1 0;  /* Takes twice the space */
            background: #fff3cd;
            border-color: #856404;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="card">
            <h2>Card 1</h2>
            <p>Regular card</p>
        </div>
        <div class="card featured">
            <h2>Featured Card</h2>
            <p>This takes more space!</p>
        </div>
        <div class="card">
            <h2>Card 3</h2>
            <p>Regular card</p>
        </div>
    </div>
</body>
</html>
```

**Experiment:**
- Change `flex: 2 1 0` to `flex: 3 1 0` on featured - what happens?
- Set `flex-shrink: 0` on one card - resize the window
- Try `flex-basis: 300px` instead of `0`

---

### Exercise 3: Master the Box Model (20 minutes)

Create boxes to understand padding, margin, and borders.

**Steps:**
1. Create an HTML file with 3 div's
2. Give each a different background color
3. Experiment with:
   - `padding: 20px` - content moves away from edges
   - `margin: 20px` - space between boxes
   - `border: 5px solid black` - adds visible edge
4. Use DevTools to inspect the box model diagram
5. Try `box-sizing: border-box` - how does sizing change?

```css
.box {
    width: 200px;
    padding: 20px;
    border: 5px solid black;
    margin: 20px;
    /* Total width = 200 + (20*2) + (5*2) = 250px */
}

.box-border-box {
    box-sizing: border-box;  /* padding/border included in width */
    width: 200px;
    padding: 20px;
    border: 5px solid black;
    /* Total width = 200px */
}
```

---

### Exercise 4: Display Property Comparison (15 minutes)

See the difference between display values.

```html
<div class="container">
    <span class="inline">Inline</span>
    <span class="inline">Inline</span>
    
    <div class="block">Block</div>
    <div class="block">Block</div>
    
    <div class="inline-block">Inline-block</div>
    <div class="inline-block">Inline-block</div>
</div>
```

```css
.inline { background: lightblue; }
.block { background: lightcoral; }
.inline-block { display: inline-block; background: lightgreen; width: 100px; }
```

**Observe:**
- Inline elements stay on same line
- Block elements start new lines
- Inline-block combines both behaviors

---

### Exercise 5: Navigation with Flexbox (20 minutes)

Build a proper navigation using `<ul>`.

```html
<nav>
    <ul class="nav-list">
        <li><a href="#home">Home</a></li>
        <li><a href="#about">About</a></li>
        <li><a href="#services">Services</a></li>
        <li class="nav-right"><a href="#contact">Contact</a></li>
    </ul>
</nav>
```

```css
.nav-list {
    display: flex;
    list-style: none;
    gap: 30px;
    margin: 0;
    padding: 20px;
    background: #333;
}

.nav-list a {
    color: white;
    text-decoration: none;
    padding: 10px 15px;
}

.nav-list a:hover {
    background: #555;
    border-radius: 4px;
}

/* Push last item to the right */
.nav-right {
    margin-left: auto;
}
```

**Questions to answer:**
- Why does `margin-left: auto` push the item right?
- What if you used `justify-content: space-between` instead?
- How would you center all navigation items?

---

## 🏠 Homework & Practice

### Required Practice

**1. Complete All Exercises**

Finish Exercises 1-5 to demonstrate understanding of:
- Flex-grow, flex-shrink, flex-basis
- Box model (padding, margin, border)
- Display properties
- CSS units

**2. Build a Complete Layout**

Create a page with:
- Navigation using `<ul>` and flexbox
- Header with title and description
- Content area with 3 cards (use `flex: 1 1 0`)
- Footer with flex items
- Proper spacing using padding, margin, and gap

**3. Box Model Practice**

Create 5 boxes and document:
- What happens when you add padding?
- How margin affects spacing between boxes?
- The difference between `box-sizing: content-box` and `border-box`
- Take screenshots showing the DevTools box model diagram

**4. Experiment with Units**

Create elements using different units:
- One with `px`
- One with `rem`
- One with `%`
- One with `em`

Change the root font-size - which elements change?

---

### Extra Credit (Optional)

**Challenge 1: Recreate a Real Layout**

Find a website you like and recreate its header/navigation using only Flexbox and the box model. No copying code - build it from scratch!

**Challenge 2: Flex Growth Visualization**

Create a visualization that shows how `flex-grow` distributes space:
- 3 items: flex-grow 1, 2, and 3
- Display the actual widths using JavaScript
- Add labels showing the ratios

**Challenge 3: Auto Margin Magic**

Create these layouts using only `margin: auto`:
- Centered block element
- Navigation with last item pushed right
- Flexbox with items at start and end
- Vertically centered content (hint: flex + auto margins)

---

## 📖 Learning Resources

### 📺 Video Tutorials

**Flexbox Deep Dive:**
- [Flexbox Tutorial (30 min)](https://www.youtube.com/watch?v=JJSoEo8JSnc) - Comprehensive guide
- [Understanding Flex-Grow, Flex-Shrink, Flex-Basis (12 min)](https://www.youtube.com/watch?v=G7EIAgfkhmg)
- [Flexbox Alignment (8 min)](https://www.youtube.com/watch?v=EFmVzv2XJ0g)

**Box Model:**
- [CSS Box Model Explained (8 min)](https://www.youtube.com/watch?v=rIO5326FgPE)
- [Box Model Deep Dive (15 min)](https://www.youtube.com/watch?v=Azfj1efPAH0)
- [Box-Sizing Explained (6 min)](https://www.youtube.com/watch?v=WlGQdgy-M6w)

**Display Properties:**
- [Block vs Inline vs Inline-Block (10 min)](https://www.youtube.com/watch?v=x_i2gga-sYg)
- [CSS Display Property (12 min)](https://www.youtube.com/watch?v=Qf-wVa9y9V4)

### 📄 Written Documentation

- [MDN - Flexbox Guide](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox)
- [CSS-Tricks - Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [MDN - Box Model](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/The_box_model)
- [MDN - Display Property](https://developer.mozilla.org/en-US/docs/Web/CSS/display)
- [MDN - CSS Values and Units](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Values_and_units)

### 🎮 Interactive Learning

- [Flexbox Froggy](https://flexboxfroggy.com/) - Practice flex properties
- [Flexbox Defense](http://www.flexboxdefense.com/) - Tower defense game
- [CSS Box Model Game](https://www.bryanbraun.com/checkboxland/docs/demos/box-model/) - Learn box model interactively

---

## ✅ What You Should Know After This Class

**By the end of today, you should be able to:**

- ✅ Explain what `flex: 1 1 0` means and does
- ✅ Use `flex-grow`, `flex-shrink`, and `flex-basis` independently
- ✅ Understand the CSS box model (content, padding, border, margin)
- ✅ Use `padding` and `margin` shorthand effectively
- ✅ Explain the difference between `block`, `inline`, `inline-block`, and `flex`
- ✅ Choose appropriate display values for different situations
- ✅ Use relative units (`rem`, `em`, `%`) vs absolute units (`px`)
- ✅ Create navigation with `<ul>` and flexbox
- ✅ Use auto margins for alignment in flexbox
- ✅ Understand margin collapse and how to avoid it

---

## 🔜 Coming Up Next

**Class 11 will cover:**
- CSS Grid for two-dimensional layouts
- Responsive design and media queries
- Modern layout patterns
- CSS custom properties (variables)

---

## 💡 Tips for Success

### 🆘 If You Get Stuck

1. **Review class example files** - They demonstrate all key concepts
2. **Use DevTools box model diagram** - Visual representation of padding/margin/border
3. **Test one property at a time** - Don't change multiple things simultaneously
4. **Draw it out** - Sketch flex containers and items on paper
5. **Compare display values** - Create test files with different display properties

### ⚠️ Common Mistakes

- ❌ **Confusing flex properties** - `flex-grow` on items, not container
- ❌ **Forgetting box-sizing** - `border-box` makes sizing predictable
- ❌ **Wrong display for the job** - inline-block for layouts is old practice
- ❌ **Mixing units inconsistently** - Pick `rem` or `px` and stick with it
- ❌ **Not removing list styles** - `list-style: none` for navigation `<ul>`

### 🎯 Remember

- **The box model adds up** - Total size = content + padding + border (unless box-sizing: border-box)
- **Flexbox is the default** - Use it for most layouts
- **rem is usually best** - Scales with root font-size
- **Auto margins are powerful** - Especially in flexbox
- **Semantic HTML matters** - Use `<ul>` for navigation

---

## 🎓 Professional Skills Unlocked!

You now understand the fundamental building blocks of CSS layouts:

- **Complete Flexbox mastery** ✅
- **Box model control** ✅
- **Display property knowledge** ✅
- **Unit understanding** ✅
- **Semantic navigation** ✅

These skills form the foundation of all modern CSS layouts. Master these and you can build anything!

---

## 🔗 Class Navigation

← [Class 09 - Intro to Flexbox & Layout Techniques](../09-css-layouts/README.md) | [Class 11 - TBD] →
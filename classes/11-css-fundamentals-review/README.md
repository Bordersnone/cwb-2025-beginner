# Class 12 - CSS Fundamentals Review & Practice

**Lead:** Kiley  
**Assistant:** Timotej  
**Date:** October 30, 2025

---

## 📋 Important: Baseline Quiz Today!

> **📝 [Take the Quiz](./quiz.md)** - 20 questions covering Classes 1-10
>
> This quiz helps us understand where everyone is with the fundamentals. It's **not graded** - it's diagnostic to help us teach better!
>
> **After class:** Quiz answers will be available in [quiz-answers.md](./quiz-answers.md) for studying.

---

## 📹 Class Recording

> **🎥 [Watch Class Recording](#)** ← *Link will be added after class*
>
> Missed class or want to review? Watch the full recording to see CSS fundamentals practiced live.

---

## 📚 Quick Links

- [What We'll Cover](#-what-well-cover)
- [Practice Exercises](#-practice-exercises)
- [Take the Quiz](./quiz.md)
- [Learning Resources](#-resources)
- [What You Should Know](#-what-you-should-know-after-this-class)

---

## 🎯 Today's Focus

**Why This Class?** After reviewing student work and progress, we realized we need to slow down and make sure everyone really understands CSS fundamentals before moving to advanced topics like Grid. Today is about **depth, not breadth** - we'll practice and reinforce concepts you've touched but may not fully understand yet.

**Philosophy:** Understanding beats coverage. It's okay to move slowly if it means you truly get it.

---

## 📝 What We'll Cover

### Topic 1: CSS Methods - Inline, Internal, External

**You've used these, but do you really understand the differences?**

#### The Three Ways to Add CSS

**1. Inline CSS**
```html
<p style="color: blue; font-size: 18px;">Styled directly on the element</p>
```
- ✅ Good for: Quick tests, one-off styles
- ❌ Avoid for: Real projects (hard to maintain)

**2. Internal CSS**
```html
<head>
    <style>
        p { color: blue; font-size: 18px; }
    </style>
</head>
```
- ✅ Good for: Single-page sites, testing
- ❌ Avoid for: Multi-page sites (can't reuse)

**3. External CSS** ⭐ **PROFESSIONAL STANDARD**
```html
<head>
    <link rel="stylesheet" href="css/style.css">
</head>
```
- ✅ Good for: Everything! Reusable, maintainable, organized
- ⚠️ Common mistakes: Wrong file path, typo in filename

**Which one wins if you use multiple methods?** We'll find out!

---

### Topic 2: The CSS Cascade & Specificity

**Why doesn't my CSS work? Understanding what beats what.**

#### The Cascade

When multiple CSS rules target the same element:
1. **Later rules override earlier rules** (if specificity is equal)
2. **More specific rules beat less specific rules**

#### Specificity Hierarchy (from weakest to strongest)

```
element < class < id < inline style
```

**Example:**
```css
p { color: blue; }           /* Specificity: 1 */
.intro { color: green; }     /* Specificity: 10 */
#welcome { color: red; }     /* Specificity: 100 */
```

If a paragraph has all three applied, **red wins** because ID is most specific!

#### How to See This in Action

1. Open DevTools (F12 or Cmd+Option+I)
2. Inspect an element
3. Look at the Styles panel
4. Crossed-out styles = overridden by something more specific

**Practice:** We'll create conflicting rules and predict which style will win!

---

### Topic 3: Hover Effects & Transitions

**Making your site feel alive and interactive.**

#### Hover Works on ANYTHING

Not just links! Try:
```css
/* Hover on images */
img:hover {
    opacity: 0.8;
    cursor: pointer;
}

/* Hover on cards */
.card:hover {
    box-shadow: 0 4px 8px rgba(0,0,0,0.2);
    transform: translateY(-2px);
}

/* Hover on buttons */
button:hover {
    background-color: #056074;
    color: white;
}
```

#### Making Hover Smooth with Transitions

```css
.card {
    transition: all 0.3s ease;
}

.card:hover {
    transform: scale(1.05);
}
```

**The `transition` property:**
- `all` = which properties to animate (or specify: `background-color`, `transform`, etc.)
- `0.3s` = duration (300 milliseconds)
- `ease` = timing function (smooth start and end)

**Common Patterns:**
- Change color on hover
- Add/increase shadow
- Slight scale up (`transform: scale(1.05)`)
- Change opacity
- Add underline to text

---

### Topic 4: Working with Images

**Local vs remote images, and making them look good.**

#### Image Sources

**Local Images (your files):**
```html
<img src="images/photo.jpg" alt="My photo">
<img src="./img/logo.png" alt="Logo">
```

**Remote Images (from the web):**
```html
<img src="https://example.com/image.jpg" alt="Description">
```

#### Making Images Look Good

```css
img {
    /* Responsive - never bigger than container */
    max-width: 100%;
    height: auto;
    
    /* Prevent stretching */
    object-fit: cover;
    
    /* Rounded corners */
    border-radius: 8px;
    
    /* Add border */
    border: 2px solid #333;
}
```

**Common Properties:**
- `max-width: 100%` - responsive sizing
- `object-fit: cover` - fills space without stretching
- `border-radius` - rounded corners
- `display: block; margin: 0 auto;` - center an image

---

### Topic 5: Flexbox Review

**You've used it, but let's really understand it.**

#### Flexbox Properties Explained

**On the parent (container):**
```css
.container {
    display: flex;                /* Turn on flexbox */
    flex-direction: row;          /* or column */
    justify-content: space-between; /* Align along main axis */
    align-items: center;          /* Align along cross axis */
    gap: 20px;                    /* Space between items */
    flex-wrap: wrap;              /* Allow wrapping */
}
```

**Key Concepts:**
- **Main axis** = direction items flow (horizontal if `row`, vertical if `column`)
- **Cross axis** = perpendicular to main axis
- `justify-content` = alignment along main axis
- `align-items` = alignment along cross axis
- `gap` = easier than using margins!

**Common Pattern:**
```css
/* Horizontal nav on desktop */
nav {
    display: flex;
    flex-direction: row;
    gap: 20px;
}

/* Vertical nav on mobile */
@media (max-width: 768px) {
    nav {
        flex-direction: column;
        gap: 10px;
    }
}
```

---

### Topic 6: Media Queries Basics

**Making your site work on phones.**

#### What is a Media Query?

A media query applies styles only when certain conditions are met (like screen width).

**Basic Pattern:**
```css
/* Desktop styles (default) */
.container {
    display: flex;
    flex-direction: row;
    padding: 40px;
}

/* Mobile styles (when screen is 768px or smaller) */
@media (max-width: 768px) {
    .container {
        flex-direction: column;
        padding: 20px;
    }
}
```

#### Common Breakpoint

**768px** = where phones end and tablets begin
- Smaller than 768px = mobile phone
- Larger than 768px = tablet/desktop

#### Testing Your Media Queries

1. Open DevTools (F12)
2. Click the device toolbar icon (phone/tablet icon)
3. Drag to resize and watch your styles change
4. Try different device presets

**Common Mobile Changes:**
- Stack horizontal layouts vertically (`flex-direction: column`)
- Reduce padding/margins
- Make font sizes smaller
- Hide non-essential elements
- Make navigation vertical

---

## 🏋️ Practice Exercises

### Exercise 1: CSS Specificity Challenge (15 min)

Create a test page with conflicting CSS rules:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <style>
        p { color: blue; }
        .intro { color: green; }
        #welcome { color: red; }
    </style>
</head>
<body>
    <p class="intro" id="welcome">What color will I be?</p>
</body>
</html>
```

**Tasks:**
1. Predict which color will show
2. Open the file and check your prediction
3. Open DevTools and see the crossed-out styles
4. Try different combinations of element, class, and id selectors
5. Document what you learned

---

### Exercise 2: Hover Effect Collection (20 min)

Create a page with at least 5 different hover effects:

```html
<div class="card">Hover me!</div>
<img src="image.jpg" alt="Hover image">
<button>Hover button</button>
<a href="#">Hover link</a>
<div class="box">Creative effect</div>
```

**Requirements:**
- Each element has a different hover effect
- All use `transition` for smoothness
- At least one uses `transform`
- At least one changes `box-shadow`
- At least one changes `opacity`

**Bonus:** Add `cursor: pointer` to non-link elements that have hover effects.

---

### Exercise 3: Responsive Navigation (25 min)

Build a navigation that changes from horizontal to vertical:

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
- Desktop: horizontal with `display: flex` and `flex-direction: row`
- Mobile: vertical with `flex-direction: column`
- Use media query at 768px
- Add hover effects to links
- Test in DevTools device mode

---

### Exercise 4: Image Styling Practice (15 min)

Create a page with 3 images styled differently:

**Requirements:**
- One local image
- One remote image (from the web)
- Apply different styles to each:
  - Rounded corners
  - Border
  - Hover effect (opacity or scale)
  - Make all responsive with `max-width: 100%`

---

### Exercise 5: Enhance Your Personal Page (30 min)

**Go to your personal website and add:**

1. **At least 3 hover effects** on different elements
2. **Smooth transitions** on all hover effects  
3. **One media query** that makes something responsive
4. **Test in DevTools** to verify it works on mobile

---

## 🏠 Homework

### Required Assignments

**1. Quiz Review**
- Review the quiz you took today
- Study any questions you got wrong
- Check [quiz-answers.md](./quiz-answers.md) after class
- Bring questions to next class

**2. Hover Effects Portfolio**

Create `hover-effects.html` with at least 5 different hover effects:
- Image opacity change
- Card with shadow increase
- Button color change
- Element with scale transform
- Your own creative effect

All must use `transition` for smoothness.

**3. Specificity Test Page**

Create `specificity-test.html`:
- One element with conflicting CSS rules
- Use element, class, and ID selectors
- Document in comments which one wins and why
- Use DevTools to verify

**4. Responsive Enhancement**

Add to your personal site:
- At least one media query
- Change layout or spacing on mobile
- Test at 375px width (phone) and 1024px (desktop)
- Take screenshots showing it works

---

## 📖 Learning Resources

### CSS Fundamentals
- [MDN - CSS Specificity](https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity) - How specificity works
- [CSS-Tricks - The Cascade](https://css-tricks.com/the-c-in-css-the-cascade/) - Understanding CSS cascade
- [W3Schools - CSS How To](https://www.w3schools.com/css/css_howto.asp) - Three ways to add CSS

### Hover Effects & Transitions
- [MDN - :hover](https://developer.mozilla.org/en-US/docs/Web/CSS/:hover) - Hover pseudo-class
- [MDN - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions) - Smooth animations
- [CSS-Tricks - Hover Effects](https://css-tricks.com/css-link-hover-effects/) - Creative ideas

### Flexbox
- [Flexbox Froggy](https://flexboxfroggy.com/) - Game to learn flexbox
- [CSS-Tricks - Flexbox Guide](https://css-tricks.com/snippets/css/a-guide-to-flexbox/) - Complete reference
- [MDN - Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox) - Comprehensive guide

### Responsive Design
- [MDN - Media Queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries) - How to use them
- [Web.dev - Responsive Design](https://web.dev/responsive-web-design-basics/) - Best practices

### General Learning
- [freeCodeCamp CSS](https://www.freecodecamp.org/learn/2022/responsive-web-design/) - Free hands-on course
- [Web.dev - Learn CSS](https://web.dev/learn/css/) - Comprehensive free course

---

## ✅ What You Should Know After This Class

By the end of today, you should be able to:

- ✅ Explain the difference between inline, internal, and external CSS
- ✅ Understand how CSS cascade and specificity work
- ✅ Use DevTools to see which CSS rules are being applied
- ✅ Add hover effects to any element (not just links)
- ✅ Use the `transition` property for smooth animations
- ✅ Understand flexbox properties: `flex-direction`, `justify-content`, `align-items`, `gap`
- ✅ Write a basic media query to make layouts responsive
- ✅ Test responsive designs in DevTools device mode
- ✅ Know when to use local vs remote images
- ✅ Make images responsive and styled properly

**Most Important:** You should feel more confident with CSS basics, not overwhelmed by advanced concepts you don't fully understand yet.

---

## 💡 Key Takeaways

### 1. External CSS is Professional
- Always use external stylesheets for real projects
- Keep your styles organized and reusable
- Check file paths carefully!

### 2. Specificity Determines Winners
- More specific selectors override less specific ones
- ID > Class > Element
- Use DevTools to see what's being overridden

### 3. Hover + Transition = Professional Feel
- Add hover effects to make sites feel interactive
- Always use `transition` for smoothness
- Test your hover effects as you build

### 4. Flexbox is Your Layout Friend
- Use for navigation, card layouts, simple arrangements
- Remember: `justify-content` for main axis, `align-items` for cross axis
- `gap` makes spacing easy

### 5. Media Queries Make Mobile Work
- Start with one breakpoint (768px) and expand from there
- Common pattern: row → column on mobile
- Always test in DevTools device mode

### 6. DevTools is Essential
- Use it to inspect styles
- See which rules are being applied
- Test responsive layouts
- Debug why styles aren't working

---

## 🔜 Coming Up Next

**Class 13** will finally cover CSS Grid and more advanced responsive design patterns - but only after we've solidified these fundamentals!

**Preview:**
- CSS Grid for 2D layouts
- Advanced media queries
- CSS custom properties (variables)
- Complex layout patterns

---

## 🎓 Remember

> "It's better to understand 5 concepts deeply than to barely grasp 20 concepts."

Today is about making sure you really *get* CSS fundamentals. Don't rush. Ask questions. Practice. It's okay if things don't click immediately - that's what we're here for!

---

← [Class 11 - CSS Grid (Canceled)](../11-css-grid-responsive/README.md) | [Class 13 - Coming Soon] →

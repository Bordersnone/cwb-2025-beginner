# Class 08 – Intro to CSS & Text/Font Properties

**Lead:** Timotej  
**Assistant:** Kiley  
**Date:** 18 Oct 2025

---

## 📹 Class Recording

> **🎥 [Watch Class Recording](#)** ← *Add link here when available*
>
> Missed class or want to review? Watch the full recording to see all the concepts demonstrated live.

---

## 📚 Quick Links

- [What We Covered](#-what-we-actually-covered)
- [Homework & Practice](#-homework--practice)
- [Learning Resources](#-learning-resources)
- [What You Should Know](#-what-you-should-know-after-this-class)
- [Tips for Success](#-tips-for-success)

---

## 📝 What We Actually Covered

> **Overview:** Introduced CSS, the cascade/inheritance/specificity model, CSS syntax, and the most common text & font properties. Used the provided HTML snippet to demonstrate inline vs class vs id styles and typical pitfalls.

### Topic 1: CSS Basics & Syntax

**Focus:** How CSS targets elements and how declarations are parsed and applied.

#### Key Concepts
- **Rule structure** – `selector { property: value; }`  
  Example used: `.red-text { color: red; font-size: 14px; }`
- **Selectors** – element (`p`), class (`.red-text`), id (`#sfaskf421`), descendant (`nav a`), compound (`.btn-util.btn-outline-red`)
- **Where CSS can live** – external stylesheet, `<style>` in `<head>`, inline `style=""` on elements (discouraged for maintainability)
- **Cascade & order** – later declarations win when specificity ties; demonstrated with duplicate `color` in the same inline style of `<span class="... red-text" style="color: #23da12; color: red; font-size: 12px;">`
- **Specificity** – inline > id > class/attribute/pseudo-class > element; more selectors increase weight (`.btn-util.btn-outline-red` beats `.btn-nav .btn-outline-red` for the same element)
- **Inheritance** – many text properties inherit (e.g., `color`, `font-family`, `line-height`), while layout/border generally do not

### Topic 2: Text & Font Properties

**Focus:** Practical tour of common properties using the snippet.

#### Key Concepts
- **`color`** – text color; demonstrated conflicts between `.red-text`, inline styles, and `section[style="color: blue"]`
- **`font-family`** – stacks and fallbacks; example: global `p { font-family: sans-serif; }` vs `.p-with-serif-font { font-family: 'Times New Roman', Times, serif; }`
- **`font-size`** – units (`px`, `rem`, `em`, `%`); observed inline `font-size: 12px` overriding class `14px`
- **`font-weight`** – numeric (100–900) or keywords; example: `#sfaskf421 { font-weight: 600; }`
- **`font-style`** – `normal | italic | oblique` (not shown; discussed)
- **`line-height`** – unitless recommended; example used `line-height: 50px` on `#sfaskf421` and why unitless scales better
- **`letter-spacing`** – used in `.btn-nav { letter-spacing: 10px; }`
- **`word-spacing`** – discussed (not shown)
- **`text-align`** – `left | right | center | justify`; example: `#horizontally-aligned-paragraph { text-align: center; }`
- **`vertical-align`** – inline-level/baseline alignment; example shows `vertical-align: top` on `#sfaskf421` and why it only affects inline/inline-block/table-cell contexts
- **`text-decoration`** – control links underlines; discussed how to override `nav a { color: red; }` and add `text-decoration`
- **`text-transform`** – `uppercase | lowercase | capitalize`; discussed (not shown)
- **`white-space`** – collapse/wrapping behavior; `.btn-nav { white-space: nowrap; }` example
- **`text-shadow` vs `box-shadow`** – snippet has a commented `text-shadow` and an active `box-shadow` on text; clarified that `box-shadow` draws a box shadow around the element box, not the glyphs

### 💡 Key Moments from Class

- ✅ **Specificity conflict resolved**: why inline `style="color: red"` wins over `.red-text { color: red }` and `section[style="color: blue"]`
- ✅ **Duplicate declarations**: last declaration wins within the same block (`color: #23da12; color: red;`)
- ✅ **Inheritance boundaries**: `nav a { color: red; }` affects links inside `<nav>` but not elsewhere

---

## 🏠 Homework & Practice

> **📺 [View All Video Tutorials](../../resources/video-tutorials.md)** - Complete library of curated YouTube videos

> **💡 TIP:** Use your provided HTML snippet as the base. Make edits exactly where specified. Take your time with each step!

---

### Required Exercises

#### Exercise 1: Normalize Colors and Remove Inline Overrides

**Goal:** Move all color definitions to the stylesheet and resolve conflicts.

**Steps:**
1. In the `<style>` block, add a rule `.section-body { color: #1a1a1a; }`.
2. In the HTML, on `<section style="color: blue;">`, **remove** the `style` attribute and **add** `class="section-body"`.
3. In the `<span class="your-class-name-1 red-text" style="color: #23da12; color: red; font-size: 12px;">`, **remove** the entire `style` attribute so `.red-text` controls color/size.
4. In the `<style>` block, adjust `.red-text` to `font-size: 0.875rem;` (14px ≈ 0.875rem) to prefer relative units.

📺 **Watch if you need help:** [CSS Colors and Fonts (6 min)](https://www.youtube.com/watch?v=UO0ZPL8yMpU)

#### Exercise 2: Establish a Typographic Scale

**Goal:** Create consistent font sizes using reusable classes.

**Steps:**
1. In the `<style>` block, add:
   ```css
   :root { font-size: 16px; }
   .text-xs { font-size: 0.75rem; }   /* 12px */
   .text-sm { font-size: 0.875rem; }  /* 14px */
   .text-base { font-size: 1rem; }    /* 16px */
   .text-lg { font-size: 1.125rem; }  /* 18px */
   ```

#### Exercise 3: Image Height Control (Optional)

**Goal:** Make images fully fill the height of a fixed-height container without using flexbox or grid.

<details>
  <summary>Steps:</summary>
  
1. In the `<style>` block, add:
   ```css
   .img-box { height: 120px; }              /* choose any fixed height appropriate for your layout */
   .img-fill-y { height: 100%; width: auto; display: block; }
   .img-cover { width: 100%; height: 100%; object-fit: cover; display: block; }
   ```
2. In the HTML, wrap each `<img>` in a container `div`:
   - For the first image, wrap with `<div class="img-box"> ... </div>`.
   - For the second image, wrap with `<div class="img-box"> ... </div>`.
3. On the `<img>` elements:
   - Remove inline width declarations like `style="width: 100px;"`.
   - Add `class="img-fill-y"` if you want to preserve aspect ratio by expanding only the height (may leave horizontal space).
   - Or add `class="img-cover"` if you want the image to fill both dimensions and crop as needed.
4. Do not introduce flexbox or grid. Keep the images as block-level elements inside the `.img-box`.
  
</details>

#### Exercise 4: Practice All CSS Text Properties

**Goal:** Demonstrate deliberate use of all CSS properties introduced in class.

**Properties to experiment with:**
- `color`, `font-family`, `font-size`, `font-weight`, `font-style`
- `line-height`, `letter-spacing`, `word-spacing`
- `text-align`, `vertical-align`, `text-decoration`, `text-transform`
- `white-space`, `text-shadow`, `box-shadow`

#### Exercise 5: Master Browser Developer Tools

**What to do:**
1. Open your HTML page in a browser
2. Right-click on any element and select **"Inspect"** (or press `F12`)
3. Practice using DevTools to:
   - Live-edit CSS and see changes in real-time
   - Experiment safely before committing changes
   - Inspect which styles are being applied
   - Debug specificity conflicts
   - Test different color values and font sizes

📺 **Watch:** [Chrome DevTools Tutorial (10 min)](https://www.youtube.com/watch?v=x4q86IjJFag)

#### Exercise 6: Deploy Your Changes

**Submit your work:**
1. **Save** all your changes in VS Code
2. **Push to GitHub** with these commands:
   ```bash
   git add .
   git commit -m "Apply CSS text properties from Class 08"
   git push origin main
   ```
3. **Check Render** - Wait for automatic deployment to complete
4. **Test your live site** - Visit your URL and confirm everything works

📺 **Need help with Git?** [Git Add, Commit, Push (5 min)](https://www.youtube.com/watch?v=-GZrhTtvKMU)

---

### 🌟 Extra Credit (Optional)

#### Challenge 1: Advanced Text Styling

Research and try these CSS properties we discussed:
- `text-shadow` - Add shadow to text (review the example in class)
- `text-transform` - Convert text to uppercase/lowercase/capitalize
- Custom `font-family` using Google Fonts

#### Challenge 2: Experiment with Specificity

Create intentional CSS conflicts and resolve them:
- Try styling the same element with class, id, and element selectors
- Use descendant selectors like `nav a` vs just `a`
- Practice compound selectors like `.btn-util.btn-outline-red`

#### Challenge 3: Inheritance Investigation

Test which properties inherit and which don't:
- Set `color` on a parent, observe child elements
- Try the same with `border`, `padding`, `margin`
- Document your findings

---

## 📖 Learning Resources

### 📺 Video Tutorials

#### CSS Fundamentals
- [CSS Crash Course (1.5 hours)](https://www.youtube.com/watch?v=yfoY53QXEnI) - Complete CSS introduction
- [Inline vs Internal vs External CSS (7 min)](https://www.youtube.com/watch?v=TM88Xo4GIBs) - CSS methods explained
- [CSS Specificity Explained (8 min)](https://www.youtube.com/watch?v=CHyPGSpIhSs) - Understanding specificity
- [CSS Colors and Fonts (6 min)](https://www.youtube.com/watch?v=UO0ZPL8yMpU) - Styling text
- [CSS Colors Tutorial (8 min)](https://www.youtube.com/watch?v=Ddc-IIrIot0) - Deep dive into colors

#### Developer Tools
- [Chrome DevTools Tutorial (10 min)](https://www.youtube.com/watch?v=x4q86IjJFag) - Inspect and debug CSS

#### Git & Deployment
- [Git Add, Commit, Push (5 min)](https://www.youtube.com/watch?v=-GZrhTtvKMU) - Quick workflow tutorial

### 📄 Written Documentation

- [MDN - CSS First Steps](https://developer.mozilla.org/en-US/docs/Learn/CSS/First_steps)
- [MDN - CSS Text Styling](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text/Fundamentals)
- [MDN - Cascade and Inheritance](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Cascade_and_inheritance)
- [MDN - CSS Specificity](https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity)
- [W3Schools - CSS Tutorial](https://www.w3schools.com/css/)
- [CSS Color Picker](https://htmlcolorcodes.com/) - Find color codes
- [CSS Specificity Calculator](https://specificity.keegan.st/) - Calculate selector specificity

---

## ✅ What You Should Know After This Class

**By the end of today, you should be able to:**

- ✅ Understand CSS syntax: `selector { property: value; }`
- ✅ Know the different types of selectors: element, class, id, descendant, compound
- ✅ Understand where CSS can live: inline, internal (`<style>`), external (`.css` file)
- ✅ Understand the cascade: later declarations win when specificity ties
- ✅ Understand specificity: inline > id > class > element
- ✅ Know which properties inherit and which don't
- ✅ Be comfortable with text & font properties: `color`, `font-family`, `font-size`, `font-weight`, `line-height`
- ✅ Understand alignment: `text-align` vs `vertical-align`
- ✅ Know how to use browser DevTools to inspect and debug CSS

---

## 🔜 Coming Up Next

**Class 09 - CSS Layouts:**
- CSS Box Model (margin, padding, border)
- Display properties and positioning  
- Introduction to modern layouts
- More advanced styling techniques

---

## 💡 Tips for Success

### 🆘 If You Get Stuck

1. **Watch the video again** - Sometimes you need to see it twice
2. **Check for typos** - One missing character can break everything
3. **Use browser DevTools** - Inspect your elements to see what styles are being applied
4. **Check specificity** - More specific selectors override less specific ones
5. **Ask for help** - Message the class group chat or instructor
6. **Take breaks** - Step away and come back with fresh eyes

### ⚠️ Common Mistakes to Avoid

- ❌ Forgetting the semicolon `;` at the end of CSS declarations
- ❌ Misspelling CSS property names (e.g., `colour` instead of `color`)
- ❌ Missing closing braces `}` in CSS rules
- ❌ Using inline styles when you should use classes
- ❌ Not understanding specificity conflicts
- ❌ Forgetting to save your file before testing

### 🎯 Remember

- **Everyone learns at their own pace** - Don't compare yourself to others
- **Making mistakes is how you learn** - Every error teaches you something
- **DevTools are your friend** - Use them to experiment and debug
- **Specificity takes practice** - It's one of the trickiest parts of CSS

---

## 🎓 You're Building Real Skills!

The work you're doing today is exactly what professional web developers do:

- Writing clean, maintainable CSS ✅
- Understanding specificity and the cascade ✅
- Using browser DevTools for debugging ✅
- Version control with Git ✅

These are valuable, marketable skills. Keep practicing and be proud of your progress!


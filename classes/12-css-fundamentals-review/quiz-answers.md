# Class 12 - Quiz Answers & Explanations

> **Note:** This file contains all the correct answers to the baseline quiz. Use this to study and understand concepts you may have missed!

---

## HTML Fundamentals (Questions 1-5)

### Question 1: What does HTML stand for?
**Answer: A) Hyper Text Markup Language**

**Explanation:** HTML stands for Hyper Text Markup Language. "Hyper Text" refers to links that connect web pages, and "Markup Language" means it uses tags to structure content.

---

### Question 2: Which tag is used to create a clickable link?
**Answer: B) `<a>`**

**Explanation:** The `<a>` tag (anchor tag) creates hyperlinks. Example: `<a href="https://example.com">Click here</a>`

The `<link>` tag is for linking external resources like CSS files, not for creating clickable links.

---

### Question 3: What is the correct HTML structure for a basic page?
**Answer:** `<!DOCTYPE html>`, `<html>`, `<head>`, `<body>`

**Explanation:** Every HTML page should have:
```html
<!DOCTYPE html>
<html>
    <head>
        <!-- Meta info, title, CSS links -->
    </head>
    <body>
        <!-- Visible content -->
    </body>
</html>
```

---

### Question 4: True or False: The `<head>` section is where visible content goes.
**Answer: False**

**Explanation:** The `<head>` section contains metadata, the page title, and links to stylesheets - not visible content. Visible content goes in the `<body>` section.

---

### Question 5: What attribute do you use to add alternative text to an image?
**Answer: B) `alt`**

**Explanation:** The `alt` attribute provides alternative text for images, used by screen readers and shown if the image fails to load.

```html
<img src="photo.jpg" alt="A description of the photo">
```

The `title` attribute shows a tooltip on hover, but `alt` is specifically for alternative text.

---

## CSS Fundamentals (Questions 6-10)

### Question 6: What are the three ways to add CSS to HTML?
**Answer:** Inline CSS, Internal CSS, External CSS

**Explanation:**
1. **Inline CSS:** `<p style="color: blue;">Text</p>`
2. **Internal CSS:** `<style>` tag in the `<head>` section
3. **External CSS:** Separate `.css` file linked with `<link>` tag

---

### Question 7: Which CSS method is generally considered best practice?
**Answer: C) External CSS**

**Explanation:** External CSS is best for multiple pages because:
- It's reusable across pages
- It keeps HTML clean and focused on structure
- It's easier to maintain and update
- It allows better organization

Inline CSS is only good for quick tests. Internal CSS can work for single-page sites but isn't reusable.

---

### Question 8: What does `.header p` target?
**Answer: B) All `<p>` tags inside an element with class "header"**

**Explanation:** This is a descendant selector. It targets all paragraph tags that are inside any element with the class "header".

```html
<div class="header">
    <p>This paragraph is targeted</p>
    <div>
        <p>This nested paragraph is also targeted</p>
    </div>
</div>
<p>This paragraph is NOT targeted</p>
```

---

### Question 9: In the CSS box model, what is the order from inside to outside?
**Answer: B) content → padding → border → margin**

**Explanation:** The box model layers are:
1. **Content** - The actual content (text, images)
2. **Padding** - Space inside the border, around content
3. **Border** - The border around padding and content
4. **Margin** - Space outside the border, between elements

Think of it like a picture frame: the picture (content) has matting (padding), then a frame (border), then space from the wall (margin).

---

### Question 10: True or False: `margin` creates space inside an element's border.
**Answer: False**

**Explanation:** `margin` creates space **outside** the border, between elements. `padding` creates space **inside** the border, around the content.

```css
.box {
    margin: 20px;    /* Space outside the border */
    padding: 10px;   /* Space inside the border */
    border: 2px solid black;
}
```

---

## Flexbox & Layout (Questions 11-15)

### Question 11: What CSS property creates a flex container?
**Answer: B) `display: flex`**

**Explanation:** Setting `display: flex` on a parent element turns it into a flex container, making its direct children flex items.

```css
.container {
    display: flex;  /* This creates a flex container */
}
```

---

### Question 12: Which property controls arrangement along the main axis?
**Answer: B) `justify-content`**

**Explanation:**
- `justify-content` - Aligns items along the **main axis** (horizontal if row, vertical if column)
- `align-items` - Aligns items along the **cross axis** (perpendicular to main axis)
- `flex-direction` - Sets which direction is the main axis

Common values: `flex-start`, `center`, `space-between`, `space-around`

---

### Question 13: What does `flex-direction: column` do?
**Answer: A) Makes items stack vertically**

**Explanation:** `flex-direction: column` changes the main axis to vertical, so items stack from top to bottom.

```css
.container {
    display: flex;
    flex-direction: column;  /* Items stack vertically */
}
```

Default is `flex-direction: row` which arranges items horizontally.

---

### Question 14: True or False: Flexbox is best for 2-dimensional layouts.
**Answer: False**

**Explanation:** Flexbox is for **1-dimensional** layouts - either a row OR a column. CSS Grid is for **2-dimensional** layouts where you control both rows AND columns simultaneously.

Use Flexbox for: navigation bars, card rows, simple stacking
Use Grid for: page layouts, complex galleries, dashboard layouts

---

### Question 15: Which property makes a flex item grow to fill space?
**Answer: A) `flex-grow`**

**Explanation:** `flex-grow` determines how much a flex item should grow relative to other items to fill available space.

```css
.item {
    flex-grow: 1;  /* This item will grow to fill available space */
}
```

`flex-grow: 0` means it won't grow. `flex-grow: 2` means it grows twice as much as items with `flex-grow: 1`.

---

## Tools & Workflow (Questions 16-20)

### Question 16: What does "git commit" do?
**Answer: B) Saves a snapshot of your changes locally**

**Explanation:** `git commit` saves a snapshot of your staged changes to your local repository. It doesn't upload anything to GitHub - that's what `git push` does.

Think of it like saving a checkpoint in a video game - it's saved on your computer, but not yet synced to the cloud.

---

### Question 17: How do you open DevTools?
**Answer: B) Press F12 (or Cmd+Option+I)**

**Explanation:** 
- **Windows/Linux:** F12 or Ctrl+Shift+I
- **Mac:** Cmd+Option+I or F12

You can also right-click anywhere on a page and select "Inspect" or "Inspect Element".

---

### Question 18: What can you do with "Inspect Element"?
**Answer: C) View and temporarily modify both HTML and CSS**

**Explanation:** DevTools lets you:
- View the HTML structure
- See all CSS applied to elements
- Temporarily edit HTML and CSS to test changes
- See which CSS rules are being overridden

**Important:** Changes in DevTools are temporary - they don't save to your files! They're great for testing before making real changes.

---

### Question 19: What does `./images/photo.jpg` mean?
**Answer: B) Look in the images folder in the current directory**

**Explanation:** 
- `./` means "current directory" (the folder your HTML file is in)
- `./images/photo.jpg` = look in the images subfolder of the current directory

Other path prefixes:
- `../` = go up one level (parent directory)
- `/` = go to root directory
- No prefix or `./` = current directory

---

### Question 20: True or False: Last rule wins if two rules conflict (equal specificity)?
**Answer: True**

**Explanation:** When two CSS rules have equal specificity and target the same element, the one that appears **last** in the CSS file wins. This is part of the "cascade" in Cascading Style Sheets.

```css
p { color: blue; }
p { color: red; }  /* Red wins - it's last */
```

However, if specificity is different, the more specific rule wins regardless of order:

```css
#intro { color: blue; }  /* This wins - ID is more specific */
p { color: red; }
```

---

## How to Study These Answers

1. **For questions you got wrong:** Read the explanation carefully
2. **Test your understanding:** Try to explain the concept in your own words
3. **Practice:** Create small test files to verify how concepts work
4. **Use DevTools:** Inspect real websites to see these concepts in action
5. **Ask questions:** If anything is unclear, bring it up in the next class!

---

## Additional Resources for Topics You Struggled With

### If you struggled with HTML basics:
- [MDN - HTML Basics](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/HTML_basics)
- [freeCodeCamp - HTML Course](https://www.freecodecamp.org/learn/2022/responsive-web-design/)

### If you struggled with CSS methods or cascade:
- [MDN - CSS Cascade](https://developer.mozilla.org/en-US/docs/Web/CSS/Cascade)
- [CSS-Tricks - Specificity](https://css-tricks.com/specifics-on-css-specificity/)

### If you struggled with the Box Model:
- [MDN - Box Model](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/The_box_model)
- [CSS-Tricks - Box Model](https://css-tricks.com/the-css-box-model/)

### If you struggled with Flexbox:
- [Flexbox Froggy](https://flexboxfroggy.com/) - Interactive game
- [CSS-Tricks - Flexbox Guide](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)

### If you struggled with Git:
- [Git Basics Video](https://www.youtube.com/watch?v=HVsySz-h9r4)
- [GitHub Guides](https://guides.github.com/)

### If you struggled with DevTools:
- [Chrome DevTools Tutorial](https://developer.chrome.com/docs/devtools/)
- Practice opening DevTools on any website and exploring!

---

## Remember

Getting some answers wrong is **completely normal** and **expected**! This quiz showed us:
- What you already know well (great job!)
- What needs more practice (that's why we're here!)
- What to focus on in future classes

Keep this file handy for studying. The more you practice these fundamentals, the more confident you'll become!

---

[← Back to Class 12 README](./README.md) | [Take the Quiz Again](./quiz.md)

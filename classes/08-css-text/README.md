# Class 08 – Intro to CSS & Text/Font Properties

**Lead:** Timotej  
**Assistant:** Killey  
**Date:** 18 Oct 2025

## 📝 What We Actually Covered

> Brief: Introduced CSS, the cascade/inheritance/specificity model, CSS syntax, and the most common text & font properties. Used the provided HTML snippet to demonstrate inline vs class vs id styles and typical pitfalls.

### Topic 1 — CSS Basics & Syntax

Brief: How CSS targets elements and how declarations are parsed and applied.

#### Key Concepts
- **Rule structure** – `selector { property: value; }`  
  Example used: `.red-text { color: red; font-size: 14px; }`
- **Selectors** – element (`p`), class (`.red-text`), id (`#sfaskf421`), descendant (`nav a`), compound (`.btn-util.btn-outline-red`)
- **Where CSS can live** – external stylesheet, `<style>` in `<head>`, inline `style=""` on elements (discouraged for maintainability)
- **Cascade & order** – later declarations win when specificity ties; demonstrated with duplicate `color` in the same inline style of `<span class="... red-text" style="color: #23da12; color: red; font-size: 12px;">`
- **Specificity** – inline > id > class/attribute/pseudo-class > element; more selectors increase weight (`.btn-util.btn-outline-red` beats `.btn-nav .btn-outline-red` for the same element)
- **Inheritance** – many text properties inherit (e.g., `color`, `font-family`, `line-height`), while layout/border generally do not

### Topic 2 — Text & Font Properties

Brief: Practical tour of common properties using the snippet.

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

### Key Moments
- ✅ Resolved a **specificity conflict**: why the inline `style="color: red"` wins over `.red-text { color: red }` and over `section[style="color: blue"]`  
- ✅ Demonstrated **duplicate declarations**: last declaration wins within the same declaration block (`color: #23da12; color: red;`)  
- ✅ Clarified **inheritance boundaries**: `nav a { color: red; }` affects links inside `<nav>` but not links elsewhere in the document

---

## 🏠 Homework & Practice

Use your provided HTML as the base. Make edits exactly where specified.

### Required Practice

**1. Normalize Colors and Remove Inline Overrides**

Goal: move all color definitions to the stylesheet and resolve conflicts.

Steps:
1. In the `<style>` block, add a rule `.section-body { color: #1a1a1a; }`.
2. In the HTML, on `<section style="color: blue;">`, **remove** the `style` attribute and **add** `class="section-body"`.
3. In the `<span class="your-class-name-1 red-text" style="color: #23da12; color: red; font-size: 12px;">`, **remove** the entire `style` attribute so `.red-text` controls color/size.
4. In the `<style>` block, adjust `.red-text` to `font-size: 0.875rem;` (14px ≈ 0.875rem) to prefer relative units.

**2. Establish a Typographic Scale**

Goal: consistent sizes via classes.

Steps:
1. In the `<style>` block, add:
   ```css
   :root { font-size: 16px; }
   .text-xs { font-size: 0.75rem; }   /* 12px */
   .text-sm { font-size: 0.875rem; }  /* 14px */
   .text-base { font-size: 1rem; }    /* 16px */
   .text-lg { font-size: 1.125rem; }  /* 18px */
    ```
**3. (optional) Make the images take up 100% height of their boxes, without flexbox or grid**

Goal: images should fully fill the height of a fixed-height container.

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


**4. Use all the rest of the intruduced properties as desired**

Goal: demonstrate deliberate use of all the introduced CSS properties from class 08.


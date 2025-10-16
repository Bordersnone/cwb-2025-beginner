# Building Your "About Me" HTML Page

Let's create a complete, well-structured "About Me" page that showcases what you've learned!

## What We're Building

An "About Me" page is a personal introduction page that typically includes:

- Your name and a brief introduction
- Information about your background or interests
- A list of hobbies, skills, or goals
- Links to your social media or projects (optional)
- An image (optional)

## Full Example

Here's a complete example you can use as a starting point. See the full example at [about-page-example.html](../../../examples/about-page-example.html).

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>About Me - Your Name</title>
</head>
<body>
    <header>
        <h1>About Me</h1>
    </header>

    <main>
        <section>
            <h2>Hello, I'm [Your Name]!</h2>
            <p>
                Welcome to my page! I'm a student learning web development 
                with Borders:None. This is my first HTML page, and I'm excited 
                to share a little about myself.
            </p>
        </section>

        <section>
            <h2>My Background</h2>
            <p>
                I'm from [Your City/Country] and I'm currently [studying/working/etc.]. 
                I've always been interested in technology and how websites work, 
                which is why I joined this class.
            </p>
        </section>

        <section>
            <h2>My Interests</h2>
            <p>Here are some things I enjoy:</p>
            <ul>
                <li>Learning to code</li>
                <li>Playing soccer</li>
                <li>Reading science fiction</li>
                <li>Listening to music</li>
            </ul>
        </section>

        <section>
            <h2>Goals</h2>
            <p>What I hope to achieve:</p>
            <ol>
                <li>Build my own website from scratch</li>
                <li>Learn CSS to make beautiful designs</li>
                <li>Eventually learn JavaScript for interactive pages</li>
                <li>Create a portfolio of my work</li>
            </ol>
        </section>

        <section>
            <h2>Connect With Me</h2>
            <p>Feel free to reach out!</p>
            <ul>
                <li>Email: <a href="mailto:your@email.com">your@email.com</a></li>
                <li>GitHub: <a href="https://github.com/yourusername" target="_blank">@yourusername</a></li>
            </ul>
        </section>
    </main>

    <footer>
        <p>&copy; 2025 [Your Name]. Built with HTML in Borders:None class.</p>
    </footer>
</body>
</html>
```

## Understanding Each Tag

Let's break down what each part does:

### Document Structure

```html
<!DOCTYPE html>
```
Tells the browser this is an HTML5 document.

```html
<html lang="en">
```
The root element. `lang="en"` specifies the language is English.

### The Head Section

```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>About Me - Your Name</title>
</head>
```

- `<meta charset="UTF-8">` - Sets character encoding for proper text display
- `<meta name="viewport"...>` - Makes the page responsive on mobile devices
- `<title>` - Shows in the browser tab and search results

### The Body Section

```html
<body>
```
Contains all the visible content of your page.

### Semantic Structure Tags

```html
<header>
    <h1>About Me</h1>
</header>
```
The `<header>` element contains introductory content. Usually includes the main heading.

```html
<main>
    <!-- Your main content goes here -->
</main>
```
The `<main>` element contains the primary content of the page.

```html
<section>
    <h2>Section Title</h2>
    <p>Section content...</p>
</section>
```
The `<section>` element groups related content together.

```html
<footer>
    <p>&copy; 2025 Your Name</p>
</footer>
```
The `<footer>` typically contains copyright info, contact details, or links.

### Content Tags

```html
<h1>, <h2>, <h3>...
```
Headings - `<h1>` is the most important, `<h6>` is the least.

```html
<p>
```
Paragraph - for blocks of text.

```html
<ul> and <li>
```
Unordered list (bullet points).

```html
<ol> and <li>
```
Ordered list (numbered).

```html
<a href="URL">Link Text</a>
```
Creates a link. Add `target="_blank"` to open in a new tab.

## Step-by-Step Instructions

### 1. Create the File

In your project directory, create a new file called `about.html` (or modify your existing `index.html`).

### 2. Add the Basic Structure

Start with the DOCTYPE, html, head, and body tags.

### 3. Fill in the Head

Add your meta tags and a descriptive title.

### 4. Build Your Content

Add sections for:
- Introduction
- Background
- Interests
- Goals
- Contact information

### 5. Use Semantic HTML

Use `<header>`, `<main>`, `<section>`, and `<footer>` to structure your content properly.

### 6. Add Lists

Use `<ul>` for your interests and `<ol>` for your goals.

### 7. Add Links

Include links to your email, GitHub, or social media using `<a>` tags.

### 8. Preview Your Page

Open the HTML file in your browser to see how it looks.

### 9. Customize

Replace all the placeholder text with your own information!

## Tips for Customization

- **Be yourself** - This is your page, make it reflect who you are
- **Keep it simple** - Don't overcomplicate things yet
- **Use proper grammar** - This is a public page representing you
- **Test your links** - Make sure all your links work
- **Check your spelling** - Typos look unprofessional

## Optional Enhancements

Want to add more? Try these:

### Add an Image

```html
<img src="path/to/your-photo.jpg" alt="Photo of me" width="300">
```

### Add More Sections

```html
<section>
    <h2>My Favorite Quote</h2>
    <blockquote>
        "The only way to do great work is to love what you do."
        <footer>- Steve Jobs</footer>
    </blockquote>
</section>
```

### Add Strong and Emphasis

```html
<p>
    I <strong>really</strong> love coding, and I'm <em>especially</em> 
    interested in web design.
</p>
```

## Common Mistakes to Avoid

- ❌ Forgetting to close tags
- ❌ Nesting tags incorrectly (e.g., `<p><h2>Title</h2></p>`)
- ❌ Missing the `<!DOCTYPE html>` declaration
- ❌ Forgetting to add `alt` text for images
- ❌ Using multiple `<h1>` tags (should only have one per page)

## Validation

To make sure your HTML is correct, you can use the [W3C HTML Validator](https://validator.w3.org/). Just paste your code or upload your file.

---

[← Back to Class 7](../../07/)

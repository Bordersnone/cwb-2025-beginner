# Mini-Challenge: Enhance Your Page

Now that you have a working "About Me" page, it's time to level up! Choose one (or more) of the following enhancements to add to your page.

## Challenge Options

### Option 1: Add a Video

Embed a video that represents you or your interests. This could be:

- A YouTube video of your favorite music
- A TED talk that inspires you
- A tutorial that got you interested in coding
- Any other video that's meaningful to you

**See the example:** [video-example.html](../../../examples/video-example.html)

#### Using YouTube Embed

1. Go to the YouTube video you want to embed
2. Click the "Share" button
3. Click "Embed"
4. Copy the `<iframe>` code
5. Paste it into your HTML

```html
<section>
    <h2>A Video I Love</h2>
    <iframe 
        width="560" 
        height="315" 
        src="https://www.youtube.com/embed/VIDEO_ID" 
        title="YouTube video player" 
        frameborder="0" 
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
        allowfullscreen>
    </iframe>
</section>
```

#### Using HTML5 Video

If you have a video file:

```html
<section>
    <h2>My Video</h2>
    <video width="560" height="315" controls>
        <source src="path/to/your-video.mp4" type="video/mp4">
        Your browser does not support the video tag.
    </video>
</section>
```

---

### Option 2: Add a Contact Form

Create a simple contact form where people can send you messages.

**See the example:** [basic-form-example.html](../../../examples/basic-form-example.html)

```html
<section>
    <h2>Contact Me</h2>
    <form action="#" method="post">
        <div>
            <label for="name">Name:</label>
            <input type="text" id="name" name="name" required>
        </div>
        
        <div>
            <label for="email">Email:</label>
            <input type="email" id="email" name="email" required>
        </div>
        
        <div>
            <label for="message">Message:</label>
            <textarea id="message" name="message" rows="5" required></textarea>
        </div>
        
        <div>
            <button type="submit">Send Message</button>
        </div>
    </form>
</section>
```

**Note:** This form won't actually send emails yet (we'll learn about that later). For now, it's just for practice with form elements.

#### Form Elements Explained

- `<form>` - Container for all form elements
- `<label>` - Text description for an input (the `for` attribute links it to the input's `id`)
- `<input>` - Single-line text field
- `type="text"` - Regular text
- `type="email"` - Email format (includes validation)
- `<textarea>` - Multi-line text field
- `required` - Makes the field mandatory
- `<button>` - Submit button

---

### Option 3: Add a Table

Create a table to display organized information about yourself.

**See the example:** [table-example.html](../../../examples/table-example.html)

#### Example 1: Skills Table

```html
<section>
    <h2>My Skills</h2>
    <table border="1">
        <thead>
            <tr>
                <th>Skill</th>
                <th>Experience Level</th>
                <th>Learning Since</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>HTML</td>
                <td>Beginner</td>
                <td>September 2025</td>
            </tr>
            <tr>
                <td>Git</td>
                <td>Beginner</td>
                <td>September 2025</td>
            </tr>
            <tr>
                <td>English</td>
                <td>Fluent</td>
                <td>Since childhood</td>
            </tr>
        </tbody>
    </table>
</section>
```

#### Example 2: Schedule Table

```html
<section>
    <h2>My Typical Week</h2>
    <table border="1">
        <thead>
            <tr>
                <th>Day</th>
                <th>Morning</th>
                <th>Afternoon</th>
                <th>Evening</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>Monday</td>
                <td>Classes</td>
                <td>Study</td>
                <td>Coding practice</td>
            </tr>
            <tr>
                <td>Tuesday</td>
                <td>Classes</td>
                <td>Web dev class</td>
                <td>Homework</td>
            </tr>
            <!-- Add more rows as needed -->
        </tbody>
    </table>
</section>
```

#### Table Elements Explained

- `<table>` - Container for the entire table
- `<thead>` - Table header section
- `<tbody>` - Table body section
- `<tr>` - Table row
- `<th>` - Table header cell (bold and centered by default)
- `<td>` - Table data cell
- `border="1"` - Adds borders (we'll style this better with CSS later)

---

## Bonus Challenges

If you finish quickly and want an extra challenge:

### Add Multiple Enhancements

Combine two or all three options above!

### Add Images

Include photos or graphics on your page:

```html
<section>
    <h2>Photo Gallery</h2>
    <img src="path/to/image1.jpg" alt="Description" width="300">
    <img src="path/to/image2.jpg" alt="Description" width="300">
</section>
```

### Create a Navigation Menu

Add links to different sections of your page:

```html
<nav>
    <ul>
        <li><a href="#about">About</a></li>
        <li><a href="#interests">Interests</a></li>
        <li><a href="#contact">Contact</a></li>
    </ul>
</nav>

<!-- Then add id attributes to your sections -->
<section id="about">
    <h2>About Me</h2>
    <!-- content -->
</section>
```

### Add More Semantic HTML

Use additional semantic elements:

```html
<article>
    <h3>Blog Post Title</h3>
    <p>Blog post content...</p>
</article>

<aside>
    <h3>Fun Fact</h3>
    <p>An interesting tidbit about yourself</p>
</aside>
```

---

## Tips for Success

1. **Start small** - Pick one option and get it working first
2. **Use the examples** - Check out the sample files in `/examples/`
3. **Test frequently** - Preview your page in the browser after each change
4. **Don't be afraid to experiment** - You can always undo changes
5. **Ask for help** - If you get stuck, ask your instructor or classmates

## Submission Checklist

Before you consider the challenge complete:

- ✅ Added at least one enhancement (video, form, or table)
- ✅ Tested that everything displays correctly in the browser
- ✅ Checked that all HTML tags are properly closed
- ✅ Committed your changes with a descriptive message
- ✅ Pushed to GitHub
- ✅ Verified the changes appear on your live Render site

---

[← Back to Class 7](../../07-deploy-page/)

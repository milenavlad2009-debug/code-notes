# code-notes
My personal notes while learning HTML, CSS;
### My Learning Notes

## HTML (started 23 February 2026)

### Day 1 – Basic tags


```html

 <h1> to <h6> – headings
  <p> – paragraph
  <a href="..."> – link
  <img src="..." alt="...">– image


Example:

<h1>Hello</h1>
<p>This is a paragraph</p>
<a href="https://freecodecamp.org">Click here</a>
## HTML – link element

### Syntax:



The <link> element is used to connect external resources to an HTML page. Most commonly, it links to external CSS stylesheets.

```html
<link rel="stylesheet" href="styles.css">
rel – specifies the relationship (e.g., "stylesheet")
· href – the path to the external file

Notes:

· Placed inside the <head> section
· In HTML5, the trailing slash is optional: <link ...> or <link ... /> both work
· Can also link to favicons, fonts, etc.

Example:

<!DOCTYPE html>
<html>
<head>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <h1>Hello</h1>
</body>
</html>

---

Day 2:



### HTML Boilerplate (24 February 2026)

The HTML boilerplate is the basic structure that every HTML document should have.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <!-- content goes here -->
</body>
</html>




### UTF-8 (24 February 2026)

<meta charset="UTF-8"> tells the browser to use UTF-8 character encoding.

Why it's important:
- Supports all languages (English, Romanian, Russian, Ukrainian, etc.)
- Supports emojis and special symbols
- Prevents mojibake (garbage text like "ÐÑÐ¸Ð²ÐµÑ")

Where to put it:
Inside <head>, before <title>.

Example:
```html
<head>
    <meta charset="UTF-8">
    <title>My Website</title>
</head>


## HTML Div Element (24 February 2026)

### What is a <div>?

The <div> element is a block-level container that is used to group other HTML elements together.  
It doesn't add any visual style by itself — it's just a "box" for structuring content.

### Syntax:
```html
<div>
  <h2>Title</h2>
  <p>Some text here...</p>
  <img src="image.jpg" alt="example">
</div>


When should you use it?

· To group elements for styling with CSS
· To layout sections of a page (header, footer, sidebar, cards)
· To apply JavaScript to a group of elements
· To structure content without affecting the flow

Example:
<div class="card">
  <h3>Card Title</h3>
  <p>This is a card description.</p>
</div>

Important:

· <div> is a block-level element (takes full width)
· Use CSS classes or ids to style it
· Don't overuse <div> when semantic tags (<section>, <article>, <nav>) are more appropriate

Notes for myself:

· I will use <div> when I need a box for layout
· Later I will learn how to style them with CSS


## HTML IDs and Classes (24 February 2026)

### What are IDs and Classes?

Both `id` and `class` are **attributes** used to target HTML elements for styling with CSS or manipulation with JavaScript.

### ID (`id`)

- **Unique** — can only be used **once per page**
- Used to identify **one specific element**
- In CSS, it's written with `#`

**Example:**
```html
<div id="header">This is the header</div>
#header {
  background-color: lightblue;
}

Class (class)

· Reusable — can be used on multiple elements
· Used to apply the same styles to many elements
· In CSS, it's written with .

Example:
<p class="highlight">First paragraph</p>
<p class="highlight">Second paragraph</p>
.highlight {
  color: red;
  font-weight: bold;
}

When should you use them?

Use ID when... Use Class when...
You have one unique element (e.g., header, footer, logo) You want to style multiple elements the same way
You need to link to a specific part of the page (e.g., #section2) You want to reuse styles
You need JavaScript to target one specific element You're building a component that appears many times (cards, buttons)

Important notes:

· ID must be unique — don't use the same ID twice
· You can have multiple classes on one element: <div class="class1 class2">
· An element can have both an ID and a class
· IDs are more specific in CSS — they override class styles

Example with both:
<div id="main-content" class="container dark-theme">
  <p class="highlight">Hello world</p>
</div>

Summary for myself:

· Use id for unique things (header, footer, special sections)
· Use class for repeating styles (buttons, cards, text styles)


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

## HTML Entities (24 February 2026)

### What are HTML Entities?

HTML entities are special codes used to display characters that are reserved in HTML or not available on a standard keyboard.

For example, if you want to show < or > on a webpage, you can't just type them — the browser will think it's HTML code. That's when you use entities.

### Syntax:

All entities start with & and end with ;.

Example:
- &lt; → <
- &gt; → >
- &amp; → &

### Common HTML Entities:

| Character | Entity Name | Entity Number | Description |
|-----------|-------------|---------------|-------------|
| <       | &lt;      | &#60;       | less than |
| >       | &gt;      | &#62;       | greater than |
| &       | &amp;     | &#38;       | ampersand |
| "       | &quot;    | &#34;       | double quote |
| '       | &apos;    | &#39;       | apostrophe (not supported in all browsers) |
|   (space) | &nbsp;  | &#160;      | non-breaking space |
| ©       | &copy;    | &#169;      | copyright |
| ®       | &reg;     | &#174;      | registered trademark |
| €       | &euro;    | &#8364;     | euro currency |
| £       | &pound;   | &#163;      | pound currency |
| ¥       | &yen;     | &#165;      | yen currency |
| °       | &deg;     | &#176;      | degree symbol |
| ±       | &plusmn;  | &#177;      | plus-minus |

### Example in HTML:

```html
<p>To display a <div> tag in text, write: &lt;div&gt;</p>
<p>Copyright &copy; 2026 My Website</p>
<p>Price: 10&euro; or 10&pound;</p>

When to use them?

· When you need to display reserved characters (<, >, &, ")
· When you want to add special symbols (©, ®, €, °, ±)
· To prevent line breaks with &nbsp;
· To make your HTML valid and safe

Notes for myself:

· Always use &lt; and &gt; when showing HTML tags in text
· &nbsp; is useful for keeping words together (e.g., "New York")
· If I forget an entity, I can always Google "HTML entity for [symbol]"



## HTML Script Element (24 February 2026)

### What is the <script> element?

The <script> element is used to embed or reference JavaScript code in an HTML document. JavaScript makes web pages interactive (buttons, animations, forms, etc.).

### Two ways to use it:

#### 1. Internal JavaScript (inside HTML)

You write the JavaScript code directly between <script> and </script> tags.

Example:
```html
<script>
  function showMessage() {
    alert('Hello!');
  }
</script>

<button onclick="showMessage()">Click me</button>


2. External JavaScript (linking to a separate file)

You write JavaScript in a separate .js file and link it to HTML.

Example of external file (script.js):
function showMessage() {
  alert('Hello from external file!');
}

In HTML:
<script src="script.js"></script>
<button onclick="showMessage()">Click me</button>

Where to place the <script> tag?

Placement Effect
In <head> Script loads before the page content (can slow down display)
At the end of <body> Page loads first, then script runs (better for performance)
With defer attribute Downloads in background, runs after HTML is parsed
With async attribute Downloads and runs as soon as ready (may interrupt parsing)

Example with defer:
<head>
  <script src="script.js" defer></script>
</head>

Important notes:

· You can have multiple <script> tags on one page
· External files are better for reusing code across multiple pages
· Always close the <script> tag — it's not a self-closing tag
· If you use src attribute, anything between <script> and </script> is ignored

Summary for myself:

· Use internal <script> for small, page-specific code
· Use external .js files for larger projects and reusability
· Place scripts at the bottom of <body> for better performance
· Use defer when script needs to run after page loads



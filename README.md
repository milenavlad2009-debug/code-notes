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
----

---
## Meta Description & Open Graph Tags (24 February 2026)

### What is the role of the meta description, and how does it affect SEO?

The **meta description** is an HTML attribute that provides a **brief summary** of a webpage's content. It appears under the page title in search engine results.

**Example:**
```html
<head>
  <meta name="description" content="Learn about bioengineering, neuroengineering, and how to apply to top universities in Korea and the USA.">
</head>

How it affects SEO:

· It doesn't directly improve rankings, but it increases click-through rate (CTR)
· A good description makes people want to click on your link
· Should be unique for each page
· Ideal length: 150–160 characters
· Include relevant keywords naturally

Best practices:

· Write for humans first, search engines second
· Include a call to action (e.g., "Learn more", "Apply now")
· Don't duplicate descriptions across pages
· Avoid generic text like "Welcome to my website"

---

What is the role of open graph tags, and how do they affect SEO?

Open Graph (OG) tags are special meta tags that control how your webpage appears when shared on social media platforms (Facebook, LinkedIn, Twitter, etc.).

Example:
<head>
  <meta property="og:title" content="My Bioengineering Portfolio">
  <meta property="og:description" content="Projects, notes, and journey to becoming a bioengineer">
  <meta property="og:image" content="https://mywebsite.com/preview.jpg">
  <meta property="og:url" content="https://mywebsite.com">
  <meta property="og:type" content="website">
</head>

How they affect SEO:

· They don't directly improve Google rankings
· But they improve social sharing → more traffic → better engagement → indirect SEO benefit
· They make your site look professional and trustworthy

Common OG tags:

Tag Purpose
og:title Title of the page (when shared)
og:description Short description for social media
og:image Image shown in the share preview
og:url Canonical URL of the page
og:type Type of content (website, article, etc.)

Twitter also uses its own tags:
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content="...">
<meta name="twitter:description" content="...">
<meta name="twitter:image" content="...">

Why they matter:

· Without OG tags, social platforms just guess what to show
· With OG tags, you control how your site looks when shared
· Better preview = more clicks = more visibility

Summary for myself:

· Use meta description to get people to click from Google
· Use Open Graph tags to control how my site looks on social media
· Both are easy to add and make my site look professional

`

---
---
## HTML Audio and Video Elements (24 February 2026)

### What are they?

The `<audio>` and `<video>` elements are used to embed **media files** directly into a webpage without needing third‑party plugins (like Flash).

---

### The `<video>` element

**Basic syntax:**
```html
<video src="movie.mp4" controls>
  Your browser does not support the video tag.
</video>

Common attributes:

Attribute Description
src Path to the video file
controls Shows play/pause/volume/fullscreen buttons
autoplay Video starts playing automatically (often blocked by browsers)
loop Video repeats after it ends
muted Mutes the audio by default
poster Image shown while video is loading
width / height Sets dimensions (in pixels)

Example with multiple sources (better compatibility):
<video controls width="400">
  <source src="movie.mp4" type="video/mp4">
  <source src="movie.webm" type="video/webm">
  <p>Your browser doesn't support video. <a href="movie.mp4">Download it</a>.</p>
</video>

---

The <audio> element

Basic syntax:
<audio src="song.mp3" controls>
  Your browser does not support the audio element.
</audio>

Common attributes:

Attribute Description
src Path to the audio file
controls Shows play/pause/volume buttons
autoplay Starts playing automatically (usually blocked)
loop Repeats the audio
muted Starts muted
preload Hint how much to download (none, metadata, auto)

Example with multiple sources:
<audio controls>
  <source src="song.mp3" type="audio/mpeg">
  <source src="song.ogg" type="audio/ogg">
  <p>Your browser doesn't support audio. <a href="song.mp3">Download</a>.</p>
</audio>

---

Supported formats

Browser Video Audio
Chrome MP4, WebM, Ogg MP3, WAV, Ogg
Firefox MP4, WebM, Ogg MP3, WAV, Ogg
Safari MP4 (H.264) only MP3, MP4 audio

Best practice: always provide at least MP4 (video) and MP3/OGG (audio) + a fallback message.

---

Important rules

· Always include the controls attribute, otherwise the user can't start playback
· Don't rely on autoplay – browsers block it if there's sound
· Use the <source> element inside <video>/<audio> for multiple file formats
· Provide a fallback text for very old browsers
· For accessibility, add captions/subtitles (using the <track> element)

---

Example with <track> (subtitles)
<video controls>
  <source src="video.mp4" type="video/mp4">
  <track src="subtitles_en.vtt" kind="subtitles" srclang="en" label="English">
  <track src="subtitles_ro.vtt" kind="subtitles" srclang="ro" label="Română">
</video>

---

Summary for myself

· Use <video> and <audio> to embed media
· Always include controls
· Provide multiple source formats for compatibility
· Use muted + autoplay if you really want auto‑play video
· Subtitles go in <track> inside the media element

`

---

---
## Media Optimisation, Image Licences & SVGs (24 February 2026)

### What are common ways to optimise media assets?

Optimising media (images, video, audio) means making files **smaller** without losing too much quality. This makes websites load faster.

**For images:**
- Use the right format:
  - **JPEG** – photos, complex images
  - **PNG** – graphics with transparency, logos
  - **WebP** – modern format, smaller than JPEG/PNG (supported in most browsers)
  - **AVIF** – even smaller, but newer
- Compress images:
  - Tools: TinyPNG, Squoosh, ImageOptim
  - Or use CMS plugins that auto-compress
- Resize images to the actual size needed on the page (don't load a 4000px image for a 200px thumbnail)
- Use **responsive images** with `srcset`:

```html
<img src="small.jpg"
     srcset="medium.jpg 1000w, large.jpg 2000w"
     alt="description">

For video/audio:

· Compress with tools like HandBrake (video) or Audacity (audio)
· Use modern formats: MP4 (H.264/HEVC), WebM for video; MP3, AAC for audio
· Consider streaming instead of embedding large files
· Lazy load media that's not immediately visible

For fonts:

· Use only the font weights you need
· Consider system fonts if possible
· Use font-display: swap to avoid invisible text

---

What are the different types of image licence, and how do they work?

When you use images that aren't yours, you need to understand the licence.

1. Public Domain

· No copyright, free to use for anything
· Examples: very old art, works released into public domain by author

2. Royalty-Free

· Pay once, use many times (but terms vary)
· You don't own the image, just have a licence to use it
· Examples: Shutterstock, iStock, Unsplash (Unsplash is free)

3. Rights-Managed

· You pay for specific use (time, place, medium)
· More expensive, more control for the creator

4. Creative Commons (CC)
Free licences with different conditions:

Licence What you can do Conditions
CC0 Anything, no attribution needed None
CC BY Use, modify, even commercially Must credit the creator
CC BY-SA Use, modify, share Credit + share under same licence
CC BY-ND Use, but no modifications Credit + no changes
CC BY-NC Use, modify, but non‑commercial only Credit
CC BY-NC-SA Non‑commercial, share alike Credit + same licence
CC BY-NC-ND Non‑commercial, no changes Most restrictive

How to check:

· Look for licence text on the website where you found the image
· Common sources: Unsplash (CC0), Flickr (filter by licence), Wikimedia Commons

---

What are SVGs, and when should you use them?

SVG = Scalable Vector Graphics

Unlike JPEG/PNG (which are made of pixels), SVGs are made of maths – lines, curves, shapes.

Advantages:

· Infinite scaling – they stay sharp at any size
· Small file size (for simple graphics)
· Can be styled with CSS and manipulated with JavaScript
· Animated
· Editable in code or vector tools (Illustrator, Figma, Inkscape)

When to use SVGs:

· Logos
· Icons
· Illustrations
· Charts / diagrams
· Any graphic that needs to be sharp on all screens

When NOT to use SVGs:

· Complex photos (JPEG/WebP are better)
· Very detailed images with thousands of paths (file can get huge)

How to use SVG in HTML:

Inline (editable with CSS/JS):
<svg width="100" height="100">
  <circle cx="50" cy="50" r="40" fill="red" />
</svg>

As an image:
<img src="logo.svg" alt="Logo">

As a background in CSS:
.logo {
  background-image: url('logo.svg');
}

Summary for myself:

· Use SVG for logos, icons, simple graphics
· Use JPEG/WebP for photos
· Use srcset to serve different sizes
· Always check the licence before using someone else's image
· Compress everything to make my sites fast

`

---

---
## Replaced Elements & Iframe Embeds (24 February 2026)

### What are replaced elements, and what are some examples?

**Replaced elements** are HTML elements whose content is **replaced by an external resource** (like an image, video, or embedded document). The browser doesn't render their content directly from the HTML — it replaces them with something else.

**Characteristics:**
- They have intrinsic dimensions (width, height) that come from the external resource
- They can be styled with CSS, but their internal content is outside the scope of the HTML document
- They behave differently from normal elements (e.g., `img` can be resized without losing quality if vector)

**Common examples of replaced elements:**

| Element | What it does |
|---------|--------------|
| `<img>` | Displays an image from an external source |
| `<video>` | Embeds a video file |
| `<audio>` | Embeds an audio file |
| `<iframe>` | Embeds another HTML page |
| `<embed>` | Embeds external content (like a PDF) |
| `<object>` | Embeds external resources (deprecated in many cases) |
| `<input type="image">` | An image that acts as a submit button |

**Example:**
```html
<img src="photo.jpg" alt="A replaced element">
<video controls>
  <source src="movie.mp4" type="video/mp4">
</video>
<iframe src="https://example.com"></iframe>

Note: CSS properties like ::before and ::after don't work on replaced elements because they don't have a "content" box in the same way.

---

How do you embed videos onto your page using the iframe element?

The <iframe> (inline frame) element is used to embed another HTML page inside your current page. This is how you embed YouTube, Vimeo, or other external videos.

Basic syntax:
<iframe src="URL" width="560" height="315"></iframe>

Example embedding a YouTube video:
<iframe width="560" height="315"
        src="https://www.youtube.com/embed/dQw4w9WgXcQ"
        title="YouTube video player"
        frameborder="0"
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
        allowfullscreen>
</iframe>

Common attributes:

Attribute Purpose
src The URL of the page to embed (for YouTube, use the embed link: https://www.youtube.com/embed/VIDEO_ID)
width / height Size of the iframe in pixels
title Accessibility – describes the content
allow Controls what the iframe can do (fullscreen, camera, etc.)
allowfullscreen Allows the video to go fullscreen
frameborder Removes border (0 = no border, deprecated but still used)
loading="lazy" Delays loading until the iframe is near the viewport (better performance)

Responsive iframe trick (keeps aspect ratio):
<div style="position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden;">
  <iframe src="https://www.youtube.com/embed/..."
          style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"
          allowfullscreen>
  </iframe>
</div>

(56.25% = 16:9 aspect ratio)

Where to get embed codes:

· YouTube: Share → Embed → copy <iframe> code
· Vimeo: Share → Embed → copy
· Other platforms usually have similar options

Security tip:
Only embed from trusted sources. Malicious iframes can harm your users.

---

Summary for myself:

· Replaced elements = content from outside (images, videos, iframes)
· Use <iframe> to embed videos from YouTube, Vimeo, etc.
· Always use title for accessibility
· Make iframes responsive with the padding trick
· Check embed options on the video platform

`

---



DAY 3



---
## Semantic HTML – Why It Matters (25 February 2026)

### Why should you care about semantic HTML?

Semantic HTML means using **meaningful tags** that describe the **content** inside them, not just how it looks.

Examples: `<header>`, `<footer>`, `<article>`, `<section>`, `<nav>` instead of generic `<div>`.

**Why it matters:**

| Reason | Explanation |
|--------|-------------|
| **Accessibility** | Screen readers and assistive technologies rely on semantic tags to navigate the page. Blind users can jump from `<main>` to `<nav>` to `<article>` easily. |
| **SEO** | Search engines (Google) understand the structure better. They know what's the main content, what's navigation, what's an article. This can improve ranking. |
| **Readability** | Your code becomes easier to read and maintain. Other developers (or future you) will instantly understand the purpose of each section. |
| **Future-proofing** | Browsers and standards evolve, but semantic tags are built to last. |
| **Styling** | You can target semantic elements with CSS without adding extra classes (e.g., `article p` vs `.article p`). |

---

### Why is it important to have good structural hierarchy?

Good structural hierarchy means using headings (`<h1>` to `<h6>`) in a **logical order** and nesting content properly.

**Why it matters:**

- **Accessibility:** Screen readers use headings to create an outline of the page. Users can jump from section to section. If headings are out of order (e.g., `<h3>` right after `<h1>`), it's confusing.
- **SEO:** Search engines give more weight to content under higher‑level headings.
- **Readability:** A clear hierarchy makes the page easier to scan for humans too.
- **Maintainability:** When you come back to your code, the structure tells you what's important.

**Example of bad hierarchy:**
```html
<h1>Main Title</h1>
<h3>Subsection</h3>  <!-- skipped h2 -->
<h4>Details</h4>     <!-- skipped h3 -->

Good hierarchy:
<h1>Main Title</h1>
<h2>Subsection</h2>
<h3>Details</h3>

---

What is the difference between presentational and semantic HTML?

Presentational HTML (old way) uses tags that describe how things look, not what they mean.

Examples:

· <font> – sets font size/color (obsolete)
· <center> – centers content (obsolete)
· <b> – makes text bold (presentational)
· <i> – makes text italic (presentational)
· <br> – line break (presentational, but still used)
· <hr> – horizontal rule (presentational)

Semantic HTML uses tags that describe the meaning of the content.

Examples:

· <strong> – indicates strong importance (usually bold, but meaning is "important")
· <em> – indicates emphasis (usually italic, but meaning is "emphasized")
· <header>, <footer>, <article>, <section> – describe page structure
· <nav> – navigation links
· <main> – main content of the page
· <aside> – sidebar or related content
· <figure>, <figcaption> – images with captions

Key difference:

Presentational Semantic
<b> <strong>
<i> <em>
<div class="header"> <header>
<div class="nav"> <nav>
Describes appearance Describes meaning
Bad for accessibility Good for accessibility
Old, often obsolete Modern, recommended

Example:

Presentational:
<div class="header">
  <div class="title">My Blog</div>
  <div class="nav">
    <a href="/">Home</a>
    <a href="/about">About</a>
  </div>
</div>

Semantic:
<header>
  <h1>My Blog</h1>
  <nav>
    <a href="/">Home</a>
    <a href="/about">About</a>
  </nav>
</header>

---

Summary for myself:

· Use semantic tags whenever possible – they make my site accessible, SEO‑friendly, and maintainable
· Keep a logical heading hierarchy (h1 → h2 → h3...)
· Avoid old presentational tags like <font>, <center>; use CSS for styling
· Semantic HTML is about meaning, not appearance
· Screen readers and Google will thank me 😊

`

---


---
## Semantic HTML – Emphasis, Strong, and Description Lists (25 February 2026)

### When Should You Use the Emphasis Element (`<em>`) Over the Idiomatic Text Element (`<i>`)?

Both `<em>` and `<i>` usually make text **italic**, but they have different meanings.

| Element | Meaning | When to use |
|---------|---------|-------------|
| `<em>` | **Emphasis** – stress emphasis on a word or phrase | When you want to change the meaning of a sentence by stressing a word. Screen readers will read it with emphasis. |
| `<i>` | **Idiomatic text** – text that is set off from the normal prose (technical terms, foreign words, thoughts, etc.) | When the text is just stylistically different, but not emphasized. |

**Examples:**

```html
<p>I <em>really</em> need to finish this project.</p>
<!-- Means: "I REALLY need to finish this" (strong feeling) -->

<p>The word <i>aloha</i> means both hello and goodbye.</p>
<!-- Foreign word, no emphasis -->

Rule of thumb:

· If the meaning changes with stress → <em>
· If it's just a convention (foreign word, thought, technical term) → <i>

---

When Should You Use the Strong Element (<strong>) Over the Bring Attention To Element (<b>)?

Both <strong> and <b> usually make text bold, but they have different purposes.

Element Meaning When to use
<strong> Strong importance – the content is very important (serious, urgent) For warnings, alerts, key points. Screen readers may announce it with stronger tone.
<b> Bring attention – stylistically different, but not important For keywords, product names, or any text you just want to highlight without implying importance.

Examples:
<p><strong>Warning:</strong> Do not touch the hot surface.</p>
<!-- Important, urgent -->

<p>This phone is available in <b>midnight blue</b> and <b>starlight</b>.</p>
<!-- Just highlighting color names, no extra importance -->

Rule of thumb:

· If the text is truly important (safety, key message) → <strong>
· If you just want it to stand out visually → <b> (and use CSS for styling)

---

What Are Description Lists, and When Should You Use Them?

Description lists (<dl>) are used for lists of terms and their descriptions (like a dictionary, FAQ, or metadata).

Structure:

· <dl> – the list container
· <dt> – term (definition term)
· <dd> – description (definition description)

Example:
<dl>
  <dt>HTML</dt>
  <dd>HyperText Markup Language – the structure of web pages.</dd>

  <dt>CSS</dt>
  <dd>Cascading Style Sheets – the styling of web pages.</dd>

  <dt>JavaScript</dt>
  <dd>A programming language that adds interactivity to web pages.</dd>
</dl>

When to use them:

· Glossaries / dictionaries
· FAQs (question as <dt>, answer as <dd>)
· Metadata (e.g., author, date, genre)
· Any list of name-value pairs

Example (metadata for a recipe):
<dl>
  <dt>Prep time</dt>
  <dd>15 minutes</dd>

  <dt>Cook time</dt>
  <dd>30 minutes</dd>

  <dt>Servings</dt>
  <dd>4</dd>
</dl>

Why use them?

· Semantic – they clearly describe the relationship between terms and descriptions
· Accessibility – screen readers can navigate them properly
· Styling – you can target <dt> and <dd> separately with CSS

Don't use <dl> for:

· Simple lists of items (use <ul> or <ol>)
· Dialogues (use <p> or other tags)

---

Summary for myself:

· <em> = stress emphasis (changes meaning)
· <i> = idiomatic / foreign / technical (just style)
· <strong> = serious importance
· <b> = visual attention only
· <dl> + <dt> + <dd> = perfect for glossaries, FAQs, metadata
· Always choose meaning over appearance – that's semantic HTML!

`

---
---
## HTML – Quotes, Abbreviations, Addresses, and Dates (25 February 2026)

### How Do Block and Inline Quotes Work in HTML?

HTML has two types of quotes: **block quotes** (for long quotations) and **inline quotes** (for short, in‑text quotes).

**1. Block Quotes (`<blockquote>`)**

Used for longer quotations that should be displayed as a separate block.

**Example:**
```html
<blockquote cite="https://example.com/source">
  <p>The only limit to our realization of tomorrow is our doubts of today.</p>
  <footer>— Franklin D. Roosevelt</footer>
</blockquote>

· The cite attribute can contain the URL of the source (optional)
· Browsers usually indent <blockquote> by default
· You can add a <footer> or <cite> inside to credit the author

2. Inline Quotes (<q>)

Used for short quotations that are part of a sentence.

Example:
<p>As Marie Curie said, <q>Nothing in life is to be feared, it is only to be understood.</q></p>

· Browsers automatically add quotation marks around the text
· Some browsers add language‑specific quotes (e.g., « » for French)

Difference:

<blockquote> <q>
Long quotations Short, inline quotations
Displayed as a separate block Displayed inside a sentence
No automatic quotes Automatic quotes added
Can have cite attribute Can have cite attribute too

---

How Do You Display Abbreviations in HTML?

Use the <abbr> element to mark up abbreviations or acronyms.

Example:
<p><abbr title="HyperText Markup Language">HTML</abbr> is the standard language for web pages.</p>

· The title attribute expands the abbreviation (appears on hover)
· Screen readers can announce the full form when the title is present
· Good for accessibility and SEO

Common use cases:

· Technical terms (HTML, CSS, JS)
· Organizations (NASA, WHO, FBI)
· Units (kg, cm, mph)

Note: For very common abbreviations (like "e.g." or "i.e."), you don't always need <abbr>, but it's still a nice touch.

---

How Do You Display Addresses in HTML?

Use the <address> element to mark up contact information for a person, organization, or page.

Example:
<address>
  Written by <a href="mailto:milena@example.com">Milena Vlad</a><br>
  Bucharest, Romania<br>
  Phone: +40 123 456 789
</address>

What <address> is for:

· Physical addresses
· Email addresses
· Phone numbers
· Social media links (if relevant)
· Author information

What <address> is NOT for:

· Postal addresses that are just data (use a <p> or a custom class instead)
· Every address on the page – only the one that is relevant to the document (author, contact)

Styling: Usually displayed in italics by default, but you can change it with CSS.

---

How Do You Display Times and Dates in HTML?

Use the <time> element to mark up dates, times, or durations in a machine‑readable format.

Example:
<p>The conference starts on <time datetime="2026-10-15">October 15, 2026</time>.</p>

<p>The event is at <time datetime="20:00">8:00 PM</time>.</p>

<p>The course takes <time datetime="P6W">6 weeks</time> to complete.</p>

The datetime attribute:

· Uses the ISO 8601 format
· For dates: YYYY-MM-DD (e.g., 2026-10-15)
· For times: HH:MM:SS (e.g., 20:00)
· For durations: P[n]Y[n]M[n]DT[n]H[n]M[n]S (e.g., P6W = 6 weeks, P1D = 1 day)

Why use <time>?

· Accessibility: Screen readers can announce dates consistently
· SEO: Search engines understand the date better
· Browsers: Can offer calendar integration, reminders, etc.
· Semantic: Clearly marks content as a date/time

Example with both date and time:
<p>The webinar is on <time datetime="2026-11-05T15:00">November 5 at 3:00 PM</time>.</p>

---

Summary for myself:

· Use <blockquote> for long quotes, <q> for short inline quotes
· <abbr> with title explains abbreviations (great for accessibility)
· <address> = contact info for the page/author (not just any address)
· <time> with datetime makes dates machine‑readable (SEO, accessibility, future‑proof)
· All these tags make my HTML more semantic and useful

`

---
---
## HTML – Math, Code, Styling, and Annotations (26 February 2026)

### How Do You Display Mathematical Equations and Chemical Formulas in HTML?

For simple formulas, you can use **subscript** (`<sub>`) and **superscript** (`<sup>`). For complex equations, consider **MathML**.

**1. Subscript (`<sub>`) and Superscript (`<sup>`)**

| Element | Use |
|---------|-----|
| `<sub>` | Subscript (H₂O, CO₂) |
| `<sup>` | Superscript (x², E=mc²) |

**Examples:**
```html
<p>H<sub>2</sub>O – water</p>
<p>E = mc<sup>2</sup> – Einstein's equation</p>
<p>x<sup>2</sup> + y<sup>2</sup> = z<sup>2</sup> – Pythagorean theorem</p>

2. Chemical formulas
<p>CO<sub>2</sub> – carbon dioxide</p>
<p>C<sub>6</sub>H<sub>12</sub>O<sub>6</sub> – glucose</p>
<p>Na<sup>+</sup> and Cl<sup>-</sup> – ions</p>

3. MathML (for complex equations)

MathML is a special language for mathematical notation.

Example:
<math xmlns="http://www.w3.org/1998/Math/MathML">
  <msup>
    <mi>x</mi>
    <mn>2</mn>
  </msup>
  <mo>+</mo>
  <msup>
    <mi>y</mi>
    <mn>2</mn>
  </msup>
  <mo>=</mo>
  <msup>
    <mi>z</mi>
    <mn>2</mn>
  </msup>
</math>

Note: MathML is powerful but verbose. For most web use, <sub>/<sup> + Unicode symbols (√, ∫, ∑, π) are enough.

---

How Do You Represent Computer Code in HTML?

HTML provides several elements for displaying code, each with a specific meaning.

Element Purpose Example
<code> Inline code <code>print()</code>
<pre> Preformatted text (preserves spaces/line breaks) <pre>function() { ... }</pre>
<kbd> Keyboard input <kbd>Ctrl + C</kbd>
<samp> Sample output from a program <samp>Error: file not found</samp>
<var> Variable name in math/programming <var>x</var> = 5

Examples:
<p>Use the <code>console.log()</code> function to print to the console.</p>

<pre>
function hello() {
  console.log("Hello, world!");
}
</pre>

<p>Press <kbd>Ctrl</kbd> + <kbd>S</kbd> to save.</p>

<p>The program returned: <samp>Hello, world!</samp></p>

<p>The equation <var>E</var> = <var>m</var><var>c</var><sup>2</sup> is famous.</p>

Combining with CSS:
You can style these elements to look like real code:
code, pre {
  background-color: #f4f4f4;
  padding: 0.2em 0.4em;
  border-radius: 3px;
  font-family: monospace;
}
pre {
  padding: 1em;
  overflow-x: auto;
}

---
What Are the <u>, <s>, and <ruby> Elements Used For, and How Do They Work?

1. <u> (Unarticulated Annotation)

Used for text that is stylistically different but not emphasized or important. Often displayed as underlined.

Common uses:

· Misspelled words
· Proper names in some languages
· Any text that needs to be underlined without implying importance

Example:
<p>This word is <u>misspelled</u>.</p>

Note: Don't use <u> just to underline text (use CSS text-decoration: underline instead). Use it when the underlining has meaning.

---

2. <s> (Strikethrough)

Represents text that is no longer accurate or relevant. Displayed with a line through it.

Common uses:

· Old prices in sales
· Completed tasks
· Corrections

Example:
<p>Original price: <s>$100</s> Now: $50</p>

Note: <s> is for content that is no longer correct. For edits in a document, use <del> and <ins>.

---

3. <ruby> (Ruby Annotations)

Used for small annotations above or next to text, common in East Asian languages (like furigana in Japanese or pinyin in Chinese).

Structure:

· <ruby> – container
· <rb> – base text (optional in modern HTML)
· <rt> – ruby text (the annotation)
· <rp> – parentheses for browsers that don't support ruby

Example (Japanese):
<ruby>
  漢 <rp>(</rp><rt>Kan</rt><rp>)</rp>
  字 <rp>(</rp><rt>ji</rt><rp>)</rp>
</ruby>

Example (Chinese pinyin):
<ruby>
  你 <rp>(</rp><rt>nǐ</rt><rp>)</rp>
  好 <rp>(</rp><rt>hǎo</rt><rp>)</rp>
</ruby>

How it looks:

· In supported browsers: small text above the base characters
· In older browsers: the fallback rp shows parentheses around the annotation

When to use:

· Language learning content
· Proper pronunciation guides
· Any text where you need small annotations

---

Summary for myself:

· Use <sub> and <sup> for simple formulas; MathML for complex ones
· <code>, <pre>, <kbd>, <samp>, <var> make code readable and semantic
· <u> = underlined but not important (use CSS for generic underlines)
· <s> = strikethrough for outdated content
· <ruby> + <rt> = annotations for East Asian languages (or any small notes)

`

---


DAY 4



---

# code-notes
My personal notes while learning HTML, CSS;
### My Learning Notes

## HTML (started 23 February 2026)

### Day 1 – Basic tags

  <h1> to <h6> – headings
  <p> – paragraph
  <a href="..."> – link
  <img src="..." alt="...">– image


Example:
```html
<h1>Hello</h1>
<p>This is a paragraph</p>
<a href="https://freecodecamp.org">Click here</a>
## HTML – link element



The <link> element is used to connect external resources to an HTML page. Most commonly, it links to external CSS stylesheets.


### Syntax:
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

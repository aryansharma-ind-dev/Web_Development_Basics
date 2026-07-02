# HTML Basics — Notes

## 1. What HTML actually is
HTML (HyperText Markup Language) isn't a programming language — it's a *markup* language. It describes structure and meaning ("this is a heading," "this is a list"), not logic or behavior. The browser reads your HTML and builds the DOM (Document Object Model) from it, which is what actually gets displayed.

## 2. Basic document structure
Every HTML page starts with this skeleton:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>My Page</title>
</head>
<body>
  <!-- everything visible on the page goes here -->
</body>
</html>
```

- `<!DOCTYPE html>` — tells the browser "this is HTML5," not some older/weird HTML version. Must be the first line.
- `<html lang="en">` — the root element. `lang` matters for screen readers and SEO.
- `<head>` — metadata, nothing in here is visible on the page itself (title, charset, links to CSS, etc.)
- `<meta charset="UTF-8">` — sets character encoding so special characters (é, emoji, etc.) render correctly.
- `<meta name="viewport"...>` — makes the page behave properly on mobile screens.
- `<title>` — text shown in the browser tab.
- `<body>` — everything the user actually sees.

## 3. Tags, elements, attributes — the vocabulary
- **Tag**: `<p>` or `</p>` — the markup itself.
- **Element**: `<p>Hello</p>` — opening tag + content + closing tag.
- **Attribute**: extra info inside the opening tag. `<a href="https://google.com">` — `href` is the attribute, `"https://google.com"` is its value.
- Some tags are **self-closing / void elements** — no closing tag needed: `<img>`, `<br>`, `<hr>`, `<input>`.

## 4. Headings and paragraphs
```html
<h1>Main title — only one per page</h1>
<h2>Section heading</h2>
<h3>Sub-section heading</h3>
<p>A paragraph of text.</p>
```
Rule: headings go in order (`h1` → `h2` → `h3`), don't skip levels just to make text smaller — that's what CSS is for. `<h1>` is also important for SEO and accessibility, not just visual size.

## 5. Text formatting
```html
<strong>Important text (bold, semantic)</strong>
<em>Emphasized text (italic, semantic)</em>
<b>Bold text (visual only, no meaning)</b>
<i>Italic text (visual only, no meaning)</i>
<br>       <!-- line break -->
<hr>       <!-- horizontal line/divider -->
```
`<strong>`/`<em>` carry *meaning* (screen readers announce them differently). `<b>`/`<i>` are purely visual — use `<strong>`/`<em>` unless you specifically don't want semantic weight.

## 6. Links
```html
<a href="https://example.com">Visit Example</a>
<a href="https://example.com" target="_blank">Opens in new tab</a>
<a href="about.html">Link to another page in your project</a>
<a href="#section2">Jumps to an element with id="section2" on the same page</a>
```
- `href` = where it goes.
- `target="_blank"` = opens in a new tab (best practice: also add `rel="noopener noreferrer"` for security).

## 7. Images
```html
<img src="cat.jpg" alt="A gray cat sitting on a windowsill" width="300">
```
- `src` = path to the image file.
- `alt` = describes the image — required for accessibility, and it's what shows if the image fails to load. Never leave it empty unless the image is purely decorative (`alt=""`).

## 8. Lists
```html
<ul>
  <li>Unordered item</li>
  <li>Another item</li>
</ul>

<ol>
  <li>Ordered item one</li>
  <li>Ordered item two</li>
</ol>
```
`<ul>` = bullets, no inherent order. `<ol>` = numbered, order matters.

## 9. Divs and spans (generic containers)
```html
<div>Block-level container — takes up full width, starts on a new line</div>
<span>Inline container — only takes up as much width as its content</span>
```
These have **no semantic meaning** — they're just boxes for grouping things so you can style/position them with CSS later. Overusing `<div>` for everything is called "div soup" — avoid it once you learn semantic tags.

## 10. Basic semantic tags (structure with meaning)
```html
<header>Top of the page — logo, nav, etc.</header>
<nav>Navigation links</nav>
<main>The main content of the page</main>
<section>A thematic grouping of content</section>
<article>Self-contained content (a blog post, a card)</article>
<footer>Bottom of the page — copyright, links, etc.</footer>
```
Same visual behavior as `<div>` by default, but they tell the browser/screen readers/search engines *what* the content is. Use these instead of `<div>` wherever the meaning fits.

## 11. Comments
```html
<!-- this is a comment, not visible on the page -->
```

## 12. Basic form elements (just to recognize them today)
```html
<form>
  <label for="name">Name:</label>
  <input type="text" id="name" name="name">
  <button type="submit">Submit</button>
</form>
```
`label`'s `for` must match the input's `id` — that's what makes clicking the label focus the input (and matters a lot for accessibility).

---


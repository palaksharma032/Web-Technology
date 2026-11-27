# 01 · Introduction to HTML

> **Level:** 🟢 Beginner &nbsp;|&nbsp; **Prerequisites:** None

---

## 📑 Contents

1. [What is HTML?](#1-what-is-html)
2. [A Short History](#2-a-short-history)
3. [How the Web Delivers a Page](#3-how-the-web-delivers-a-page)
4. [How a Browser Reads HTML](#4-how-a-browser-reads-html)
5. [HTML, CSS and JavaScript: Who Does What?](#5-html-css-and-javascript-who-does-what)
6. [Anatomy of an HTML Element](#6-anatomy-of-an-html-element)
7. [Attributes](#7-attributes)
8. [The HTML Boilerplate, Line by Line](#8-the-html-boilerplate-line-by-line)
9. [`<head>` vs `<body>`](#9-head-vs-body)
10. [Nesting and Document Tree](#10-nesting-and-document-tree)
11. [Comments](#11-comments)
12. [Whitespace and Case Rules](#12-whitespace-and-case-rules)
13. [Your First Page](#13-your-first-page)
14. [Common Mistakes](#14-common-mistakes)
15. [Quick Summary](#15-quick-summary)
16. [Interview Angle](#16-interview-angle)

---

## 1. What is HTML?

**HTML** stands for **HyperText Markup Language**. It is the standard language used to create the **structure and content** of web pages.


| Word | Meaning |
|------|---------|
| **HyperText** | Text that contains links to other text or pages. Clicking a link takes you somewhere else. |
| **Markup** | Labels (called *tags*) added around content to tell the browser what that content *is*: a heading, a paragraph, an image, a link. |
| **Language** | A set of rules and keywords the browser understands. |

> ⚠️ **HTML is not a programming language.** It has no logic: no variables, loops or conditions. It only **describes** content. Programming logic comes from JavaScript. It is a static language, means it does not provide interactive features but can be combined with CSS for styling and JavaScript for interactivity.

### A simple way to think about it

If a web page were a human body:

- **HTML** is the skeleton (structure)
- **CSS** is the skin and clothes (appearance)
- **JavaScript** is the muscles and nerves (behavior)

### Example

```html
<h1>Welcome</h1>
<p>This is my first web page.</p>
```

Here `<h1>` tells the browser "this is the main heading" and `<p>` says "this is a paragraph". The browser then decides how to display each.

---


## 2. A Short History

| Year | Milestone |
|------|-----------|
| 1989–1991 | Tim Berners-Lee, working at CERN, invents the World Wide Web and the first version of HTML |
| 1995 | HTML 2.0, the first formal standard |
| 1997 | HTML 3.2 and HTML 4.0 |
| 1999 | HTML 4.01, long the dominant version |
| 2000s | XHTML, a stricter XML-based version, was introduced |
| 2014 | **HTML5** became an official W3C Recommendation |
| Today | HTML is maintained as a continuously updated **HTML Living Standard** by WHATWG |

**Why HTML5 mattered:** it added semantic tags (`<header>`, `<nav>`, `<article>`), native `<audio>` and `<video>`, `<canvas>`, better form inputs, and APIs like local storage and geolocation, which removed the need for plugins like Flash.

---

## 3. How the Web Delivers a Page

When you type a URL and press Enter:

```
You (Browser)  ──── 1. Request page ────▶  Web Server
               ◀─── 2. Sends HTML ───────
Browser reads HTML, finds CSS/JS/images, requests those too
Browser ──── 3. Renders the page on screen
```

1. The browser sends an **HTTP request** to the server.
2. The server responds with an **HTML file** (plus status code like `200 OK`).
3. The browser reads the HTML, and for every linked file (CSS, JS, images) it makes **more requests**.
4. The browser combines everything and **renders** the page.

> An HTML file is just a **plain text file** with the extension `.html` (or `.htm`). You can write one in any text editor.

---

## 4. How a Browser Reads HTML

The browser does not show your code. It **parses** it and builds an internal model.

```
HTML  ──parse──▶  DOM (tree of objects)
CSS   ──parse──▶  CSSOM (tree of styles)
DOM + CSSOM  ──▶  Render Tree  ──▶  Layout  ──▶  Paint
```

| Step | What happens |
|------|--------------|
| **Parse HTML** | Converts text into the **DOM** (Document Object Model), a tree of nodes |
| **Parse CSS** | Builds the **CSSOM**, a tree of style rules |
| **Render tree** | Combines DOM and CSSOM, including only visible elements |
| **Layout** | Calculates the size and position of each element |
| **Paint** | Draws pixels on the screen |

**Key idea:** JavaScript works with the **DOM**, not with your original HTML text. (This is the foundation of Part 2: DHTML.)

### Browsers are forgiving

If you forget to close a tag, the browser tries to guess your intent and fix it silently. This is why broken HTML often "still works", but it can behave differently across browsers. Always write clean, valid HTML.

---

## 5. HTML, CSS and JavaScript: Who Does What?

| Technology | Role | Example |
|------------|------|---------|
| **HTML** | Structure and content | "This is a button" |
| **CSS** | Presentation and layout | "The button is blue with rounded corners" |
| **JavaScript** | Behavior and interactivity | "When the button is clicked, show a message" |

```html
<!-- HTML: structure -->
<button id="btn">Click me</button>

<!-- CSS: presentation -->
<style>
  #btn { background: royalblue; color: white; border-radius: 6px; }
</style>

<!-- JavaScript: behavior -->
<script>
  document.getElementById("btn").onclick = () => alert("Hello!");
</script>
```

> **Best practice:** keep them in **separate files** (`index.html`, `style.css`, `script.js`) as projects grow. This is called **separation of concerns**.

---

## 6. Anatomy of an HTML Element

```html
<p class="intro">Hello, world!</p>
```

```
 ┌────────── Opening tag ──────────┐ ┌─ Content ─┐ ┌ Closing tag ┐
 <p  class="intro">                  Hello, world!      </p>
     └─ attribute ─┘
 └─────────────────────── Element (everything together) ──────────────┘
```

| Part | Meaning |
|------|---------|
| **Opening tag** | `<p>`: name of the element in angle brackets |
| **Content** | What goes inside: text or other elements |
| **Closing tag** | `</p>`: same name with a forward slash |
| **Element** | Opening tag + content + closing tag |
| **Attribute** | Extra information inside the opening tag |

> **Tag vs Element:** a *tag* is just the `<p>` or `</p>` marker. An *element* is the whole thing. People use the words loosely, but in interviews the difference is worth knowing.

### Void (empty) elements

Some elements have **no content and no closing tag**:

```html
<br>              <!-- line break -->
<hr>              <!-- horizontal line -->
<img src="a.png" alt="A picture">
<input type="text">
<meta charset="UTF-8">
<link rel="stylesheet" href="style.css">
```

Writing `<br />` (with a slash) is also valid in HTML5, but not required.

---

## 7. Attributes

Attributes give **extra information** about an element. They always go in the **opening tag** as `name="value"` pairs.

```html
<a href="https://example.com" target="_blank" title="Visit Example">Click here</a>
<img src="cat.jpg" alt="A sleeping cat" width="300">
```

### Rules

- Written as `name="value"`; use **double quotes** (the convention).
- Multiple attributes are separated by **spaces**.
- Some are **boolean attributes**: their presence means `true`.
  ```html
  <input type="checkbox" checked>
  <button disabled>Can't click</button>
  ```

### Attributes you will use everywhere (global attributes)

| Attribute | Purpose |
|-----------|---------|
| `id` | A **unique** identifier for one element in the page |
| `class` | A label shared by **many** elements (used for styling and selecting) |
| `style` | Inline CSS |
| `title` | Tooltip text on hover |
| `lang` | Language of the content |
| `hidden` | Hides the element |

---

## 8. The HTML Boilerplate, Line by Line

This is the minimum structure every HTML page should start with:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>My First Page</title>
</head>
<body>
  <h1>Hello, World!</h1>
</body>
</html>
```

### Explanation

| Line | What it does | Why it matters |
|------|--------------|----------------|
| `<!DOCTYPE html>` | Tells the browser: "this is an HTML5 document". | Without it, browsers switch to **quirks mode** (old, inconsistent rendering). It is *not* an HTML tag. |
| `<html lang="en">` | The **root element**; everything else lives inside it. `lang` declares the page language. | Helps screen readers, search engines and translation tools. |
| `<head>` | Container for **metadata**: information *about* the page. Not displayed. | Holds title, character set, CSS links, SEO tags. |
| `<meta charset="UTF-8">` | Sets the character encoding. | Ensures symbols, emojis and non-English text display correctly. Should be near the top of `<head>`. |
| `<meta name="viewport" ...>` | Controls page scaling on mobile devices. | Required for **responsive design**; without it mobile browsers show a zoomed-out desktop layout. |
| `<title>` | The text in the browser tab. | Used for bookmarks and search results; important for SEO. |
| `<body>` | Container for **everything visible** on the page. | All content goes here. |

> 💡 In VS Code, type `!` and press **Tab** to generate this boilerplate automatically (Emmet shortcut).

---

## 9. `<head>` vs `<body>`

| | `<head>` | `<body>` |
|---|----------|----------|
| **Contains** | Metadata and resources | Visible content |
| **Visible to user?** | No (except `<title>` in the tab) | Yes |
| **Typical children** | `<title>`, `<meta>`, `<link>`, `<style>`, `<script>` | `<h1>`–`<h6>`, `<p>`, `<img>`, `<a>`, `<div>`, etc. |
| **How many?** | Exactly one | Exactly one |

```html
<head>
  <title>Page title</title>
  <link rel="stylesheet" href="style.css">   <!-- connect CSS -->
  <script src="script.js" defer></script>    <!-- connect JS -->
</head>
```

---

## 10. Nesting and Document Tree

Elements can be placed **inside** other elements. This is called **nesting**.

```html
<body>
  <div>
    <h2>Title</h2>
    <p>Some <strong>important</strong> text.</p>
  </div>
</body>
```

Terminology (same as a family tree):

```
html
├── head
│   └── title
└── body
    └── div
        ├── h2
        └── p
            └── strong
```

- `body` is the **parent** of `div`
- `h2` and `p` are **siblings**
- `strong` is a **descendant** of `div`

### The golden rule of nesting

Close tags in the **reverse order** you opened them.

```html
<!-- ✅ Correct -->
<p>This is <strong>bold <em>and italic</em></strong></p>

<!-- ❌ Wrong: tags overlap -->
<p>This is <strong>bold <em>and italic</strong></em></p>
```

---

## 11. Comments

Comments are notes for developers. The browser ignores them.

```html
<!-- This is a comment -->
<p>Visible text</p>

<!--
  Comments can
  span multiple lines
-->
```

Shortcut in VS Code: **Ctrl + /** (Windows) or **Cmd + /** (Mac).

> ⚠️ Comments are still visible in "View Source". Never put passwords or secrets in them.

---

## 12. Whitespace and Case Rules

### Whitespace collapsing

Browsers collapse multiple spaces, tabs and line breaks into **one single space**.

```html
<p>Hello          World
   from        HTML</p>
```
Displays as: `Hello World from HTML`

To force a line break use `<br>`. To keep spacing exactly as written use `<pre>`. To add extra visible space use `&nbsp;` (non-breaking space), though CSS is the better tool for spacing.

### Case sensitivity

- Tag and attribute names are **case-insensitive** (`<P>` equals `<p>`).
- **Convention: always write them in lowercase.**
- Attribute **values** such as `id` and `class` **are** case-sensitive.

### Indentation

Indent nested elements (2 or 4 spaces). It does not change the output but makes code far easier to read.

---

### 13. HTML Document
- An HTML document is a text-only file containing Hyper Text Markup Language (HTML) code with a .HTML or .html extension, used to structure and display content, such as text, images, and links, on a webpage.
- It uses tags enclosed in angle brackets (<>) to provide instructions to a web browser.
- HTML documents are also called web pages.

### How it works
```
You write HTML Code in a text editor  ────▶ You save the file with the .html or .HTML extension ────▶ You open this file in a web browser  ────▶ The browser reads the HTML code, interprets the tags and renders the structured content on the screen.

```
### A simple HTML Document 
```
<!DOCTYPE HTML>
<html>
    <head>
        <title>
            My First Webpage
        </title>
    </head>
    <body>
        <h1> Welcome to my Web page</h1>
        <p>Glad to see you here</p>
    </body>
</html>

Here;
- <!DOCTYPE HTML> tells version of HTML.
- <html> </html> is HTML root element.
- <head> </head> used to contain page HTML metadata.
- <title> </title> is title of HTML page.
- <body> </body> Holds the content of HTML.
- <h1> </h1> is HTML heading tag.

```

### Creating an HTML document
 <p>Following are the steps to create and HTML document</p>
 <ol>
   <li>**Open a Plain Text Editor** : Use a basic text editor such as Notepad, TextEdit or more advanced code editor like VS Code or Sublime Text. Avoid word processors like Microsoft Word, as they can add formatting that interferes with HTML.</li>
   <li>**Write the HTML Code** : Begin with the fundamental structure of an HTML document.</li>
   <li>**Save the file** :
     <ol>
    <li> Go to "File" > "Save As.." in your text editor.</li>
   <li>Choose a location to save the file.</li>
   <li>Enter a file name, for example, index.html or hello.html</li>
   <li>Ensure the file extension is .html or .HTML</li></li>
     </ol>
   <li>**Open in a Web browser** :
   <ol>
     <li>Navigate to the location where you saved the HTML Document.</li>
     <li>Double-click the file. It should open automatically in your default web browser.</li>
      <li>Alternatively, open your web browser and drag the HTML File directly into the browser window.
   </ol>
   </li>
   
 </ol>


## 14. Your First Page

**Step 1.** Create a folder `my-first-page` and, inside it, a file named `index.html`.

> 💡 Why `index.html`? Web servers automatically serve a file named `index.html` as the default page of a folder.

**Step 2.** Paste this code:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>My First Page</title>
</head>
<body>
  <h1>Hello, World!</h1>
  <p>I am learning <strong>HTML</strong>.</p>
  <!-- More content coming soon -->
</body>
</html>
```

**Step 3.** Open the file in a browser (double-click it, or use the **Live Server** extension in VS Code).

**Step 4.** Right-click the page and choose **Inspect** to see the DOM in DevTools. This is a habit worth building from day one.

---

## 15. Common Mistakes

| Mistake | Problem | Fix |
|---------|---------|-----|
| Missing `<!DOCTYPE html>` | Browser enters quirks mode | Always put it on the first line |
| Forgetting closing tags | Layout breaks in unexpected ways | Close every non-void element |
| Overlapping tags | `<b><i>text</b></i>` is invalid | Close in reverse order |
| Missing `lang` on `<html>` | Poor accessibility and SEO | Add `lang="en"` |
| Missing `charset` | Strange characters appear (`â€™`) | Add `<meta charset="UTF-8">` |
| Missing viewport meta | Page looks tiny on phones | Add the viewport tag |
| Using `<br>` for spacing | Messy, hard-to-maintain markup | Use CSS margin and padding |
| Duplicate `id` values | Selectors and JS behave unpredictably | Each `id` must be unique |
| Unquoted or mismatched quotes | Attributes get cut off | Always quote attribute values |
| Content placed in `<head>` | It won't display properly | Visible content goes in `<body>` |

---

## 16. Quick Summary

- **HTML** = HyperText Markup Language; it describes the **structure and content** of a web page. It is a markup language, not a programming language.
- **HTML + CSS + JS:** structure + style + behavior.
- A browser **parses** HTML into the **DOM**, combines it with the CSSOM, then lays out and paints the page.
- An **element** = opening tag + content + closing tag. **Void elements** (`<br>`, `<img>`, `<input>`) have no closing tag.
- **Attributes** go in the opening tag as `name="value"`.
- Every page needs: `<!DOCTYPE html>`, `<html lang>`, `<head>` (with `charset`, `viewport`, `title`) and `<body>`.
- `<head>` = invisible metadata. `<body>` = visible content.
- Nest properly: close tags in **reverse order**.
- Browsers collapse extra whitespace; tag names are case-insensitive (write them lowercase).
- Current standard: **HTML5**, maintained as a living standard.

---

## 17. Interview Angle

Questions commonly asked from this topic (answers to be covered in `interview-questions.md`):

1. What is HTML? Is it a programming language?
2. What is the difference between HTML, CSS and JavaScript?
3. What is the purpose of `<!DOCTYPE html>`? What happens if it is missing?
4. What is the difference between a **tag**, an **element** and an **attribute**?
5. What are **void (self-closing) elements**? Give examples.
6. What is the difference between `<head>` and `<body>`?
7. Why do we use `<meta charset="UTF-8">` and the viewport meta tag?
8. What is the DOM, and how is it different from the HTML source code?
9. What is HTML5? What new features did it introduce?
10. What is quirks mode vs standards mode?
11. How does the browser render a web page?

---

⬅️ [Back to HTML & DHTML README](../../README.md) &nbsp;|&nbsp; ➡️ Next: `02-text-and-formatting`

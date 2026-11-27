# 🧱 HTML & DHTML

> Learn how web pages are structured (HTML) and how they come alive in the browser (DHTML), then revise it all for interviews.

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![DOM](https://img.shields.io/badge/DOM-Dynamic_HTML-orange?style=for-the-badge)

---

## 📖 About This Section

This section has two parts:

- **HTML (HyperText Markup Language)**: the standard language for creating the structure and content of web pages: text, links, images, forms, tables and more.
- **DHTML (Dynamic HTML)**: not a separate language, but the combination of **HTML + CSS + JavaScript + the DOM**, used to make pages interactive and change them without reloading.

> 💡 Part 1 teaches you to build static pages. Part 2 teaches you to make them respond to the user.

---

## 🔁 How to Study Each Topic

| Step | What to do | File |
|------|-----------|------|
| 1. Learn | Read the notes and understand the concept | `notes.md` |
| 2. See it | Open the example in your browser and change it | `index.html` |
| 3. Practice | Solve the exercises without looking at the notes | `exercises.md` |
| 4. Revise | Answer the interview questions out loud | `interview-questions.md` |

---

## 🗂️ Folder Structure

```
01-HTML-and-DHTML/
├── README.md
│
├── Part-1-HTML/
│   ├── 01-introduction-and-boilerplate/
│   ├── 02-text-and-formatting/
│   ├── 03-links-images-and-media/
│   ├── 04-lists/
│   ├── 05-tables/
│   ├── 06-forms-and-inputs/
│   ├── 07-semantic-html/
│   ├── 08-block-inline-and-attributes/
│   ├── 09-meta-tags-and-seo/
│   ├── 10-accessibility/
│   ├── 11-script-loading-defer-async/
│   ├── 12-web-storage/
│   └── 13-html5-apis/
│
└── Part-2-DHTML/
    ├── 01-what-is-dhtml-and-dom-tree/
    ├── 02-selecting-elements/
    ├── 03-changing-content-and-attributes/
    ├── 04-dynamic-styling/
    ├── 05-creating-and-removing-elements/
    ├── 06-events/
    ├── 07-event-bubbling-and-delegation/
    ├── 08-form-handling-and-validation/
    ├── 09-timers/
    └── 10-mini-projects/
```

Each topic folder contains:

```
notes.md  |  index.html  |  exercises.md  |  interview-questions.md
```

---

## 🧭 Topics

### Part 1: HTML

| # | Topic | What you will learn | Level |
|---|-------|---------------------|-------|
| 01 | Introduction and boilerplate | What HTML is, document structure, `<!DOCTYPE>`, `<head>` vs `<body>`, how browsers render a page | 🟢 Beginner |
| 02 | Text and formatting | Headings, paragraphs, `<strong>` vs `<b>`, `<em>` vs `<i>`, line breaks, entities | 🟢 Beginner |
| 03 | Links, images and media | Anchor tags, absolute vs relative paths, `<img>`, `<audio>`, `<video>`, `<iframe>` | 🟢 Beginner |
| 04 | Lists | Ordered, unordered, description lists, nesting | 🟢 Beginner |
| 05 | Tables | Rows, cells, headers, `colspan`/`rowspan`, table semantics | 🟢 Beginner |
| 06 | Forms and inputs | `<form>`, input types, labels, `GET` vs `POST`, built-in validation attributes | 🟡 Intermediate |
| 07 | Semantic HTML | `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>`, why semantics matter | 🟡 Intermediate |
| 08 | Block, inline and attributes | Block vs inline elements, `<div>` vs `<span>`, global attributes, `data-*` | 🟡 Intermediate |
| 09 | Meta tags and SEO | `<meta>` tags, viewport, charset, Open Graph, SEO basics | 🟡 Intermediate |
| 10 | Accessibility | Alt text, ARIA roles, keyboard navigation, screen readers | 🟡 Intermediate |
| 11 | Script loading | `<script>` placement, `defer` vs `async` | 🟡 Intermediate |
| 12 | Web storage | `localStorage`, `sessionStorage`, cookies and their differences | 🟡 Intermediate |
| 13 | HTML5 APIs | Canvas, SVG, geolocation, drag and drop | 🔴 Advanced |

### Part 2: DHTML

| # | Topic | What you will learn | Level |
|---|-------|---------------------|-------|
| 01 | What is DHTML and the DOM tree | What DHTML means, DOM vs HTML source, nodes and the tree structure | 🟢 Beginner |
| 02 | Selecting elements | `getElementById`, `querySelector`, `querySelectorAll`, live vs static collections | 🟢 Beginner |
| 03 | Changing content and attributes | `textContent`, `innerHTML`, `innerText`, `setAttribute` | 🟢 Beginner |
| 04 | Dynamic styling | `element.style`, `classList`, toggling themes | 🟡 Intermediate |
| 05 | Creating and removing elements | `createElement`, `appendChild`, `remove`, `DocumentFragment` | 🟡 Intermediate |
| 06 | Events | `addEventListener`, event object, common events (click, input, submit, keydown) | 🟡 Intermediate |
| 07 | Event bubbling and delegation | Capturing vs bubbling, `stopPropagation`, event delegation | 🔴 Advanced |
| 08 | Form handling and validation | Reading values, `preventDefault`, custom validation, error messages | 🟡 Intermediate |
| 09 | Timers | `setTimeout`, `setInterval`, clearing timers | 🟡 Intermediate |
| 10 | Mini projects | Apply everything in small, real pages | 🟡 Intermediate |

> ℹ️ DHTML uses JavaScript. Topics here focus on **how JavaScript works with the page**. Deeper language concepts (closures, promises, prototypes) are covered in the [JavaScript](../03-JavaScript) section.

---

## 🏗️ Mini Projects (Part 2)

- [ ] Light/dark theme toggle
- [ ] To-do list (add, delete, mark done)
- [ ] Form with live validation
- [ ] Image gallery or slideshow with timers
- [ ] Accordion / FAQ section
- [ ] Digital clock

---

## ✅ Progress Tracker

### Part 1: HTML
- [ ] 01 Introduction and boilerplate
- [ ] 02 Text and formatting
- [ ] 03 Links, images and media
- [ ] 04 Lists
- [ ] 05 Tables
- [ ] 06 Forms and inputs
- [ ] 07 Semantic HTML
- [ ] 08 Block, inline and attributes
- [ ] 09 Meta tags and SEO
- [ ] 10 Accessibility
- [ ] 11 Script loading (`defer` vs `async`)
- [ ] 12 Web storage
- [ ] 13 HTML5 APIs

### Part 2: DHTML
- [ ] 01 What is DHTML and the DOM tree
- [ ] 02 Selecting elements
- [ ] 03 Changing content and attributes
- [ ] 04 Dynamic styling
- [ ] 05 Creating and removing elements
- [ ] 06 Events
- [ ] 07 Event bubbling and delegation
- [ ] 08 Form handling and validation
- [ ] 09 Timers
- [ ] 10 Mini projects

---

## 🎤 Most Asked Interview Topics From This Section

- Semantic vs non-semantic HTML
- `<b>` vs `<strong>`, `<i>` vs `<em>`
- Block vs inline vs inline-block
- `defer` vs `async`
- `localStorage` vs `sessionStorage` vs cookies
- What is the DOM? DOM vs HTML source
- `innerHTML` vs `textContent`
- `querySelector` vs `getElementById`
- Event bubbling, capturing and delegation
- `preventDefault` vs `stopPropagation`
- What is DHTML?

---

## 🧰 Tools Needed

- A code editor (VS Code recommended)
- A modern browser (Chrome or Edge) with DevTools
- *Optional:* the **Live Server** extension for VS Code to auto-refresh the page

---

⬅️ [Back to main README](../README.md) &nbsp;|&nbsp; ➡️ Next: [CSS](../02-CSS)
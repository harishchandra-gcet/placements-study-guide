© 2025 Geethanjali Group of Institutions. All Rights Reserved. Unauthorized use or distribution is prohibited.

# HTML5 Study Guide

## 1. What is HTML5?
HTML5 is the latest version of the HyperText Markup Language used to structure web content. It introduces semantic elements, multimedia support, improved form controls, and APIs for enhanced web applications.

---
## 2. HTML5 Document Structure
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>HTML5 Structure</title>
</head>
<body>

</body>
</html>
```
`<!DOCTYPE html>` is mandatory to declare HTML5.
`<meta viewport>` is required for responsive design.

---
## 3. Semantic Tags (Important for Exam)
| Tag | Purpose |
|------|---------|
| `<header>` | Defines heading section or navigation |
| `<nav>` | Contains navigation links |
| `<section>` | Defines thematic grouping of content |
| `<article>` | Independent, self-contained content |
| `<aside>` | Sidebar content, ads, related links |
| `<footer>` | Bottom section of page |
| `<main>` | Main unique content of page |
| `<figure>`, `<figcaption>` | Images with captions |

**Gotcha:** Semantic tags improve accessibility & SEO but do NOT change layout.

---
## 4. Forms in HTML5
### New Input Types
```
email, url, tel, date, time, number, range, color, search
```
### Example
```html
<form>
  <input type="email" required>
  <input type="date">
  <input type="range" min="1" max="10">
  <input type="submit">
</form>
```
### New Form Attributes
| Attribute | Meaning |
|-----------|---------|
| `required` | Field must not be empty |
| `placeholder` | Hint text |
| `pattern` | Regex validation |
| `autocomplete` | On/Off suggestion |
| `novalidate` | Disables HTML form validation |

**Gotcha:** Browser handles validation automatically when using proper `type`.

---
## 5. Multimedia Tags
### Audio
```html
<audio controls>
  <source src="file.mp3" type="audio/mpeg">
</audio>
```
### Video
```html
<video width="400" controls>
  <source src="movie.mp4" type="video/mp4">
</video>
```
No need for Flash (HTML5 built-in playback)
Use multiple `<source>` tags for compatibility

---
## 6. Graphics
| Element | Usage |
|---------|-------|
| `<canvas>` | Dynamic 2D graphics via JS |
| `<svg>` | Resolution-independent vector graphics |

```html
<canvas id="paint"></canvas>
```

---
## 7. Global Attributes
| Attribute | Description |
|-----------|-------------|
| `id` | Unique identifier |
| `class` | CSS class name |
| `data-*` | Custom attributes for JS |
| `contenteditable` | Allows inline editing |
| `hidden` | Hides element visually |
| `draggable` | Enables drag and drop |

**Gotcha:** `data-*` attributes allow attaching metadata without affecting layout.

---
## 8. HTML5 APIs (Theory Questions!)
| API | Use |
|-----|-----|
| Geolocation API | Get device location |
| Web Storage (localStorage / sessionStorage) | Client-side storage |
| Web Workers | Background thread support |
| Fetch API | Promised-based HTTP requests |
| Drag and Drop API | Enables draggable UI elements |
| History API | SPA navigation support |

---
## 9. Common Interview/MCQ Questions
Is `<b>` same as `<strong>`? → No, `<strong>` conveys semantic importance.
Difference between block and inline elements? → Block takes full width, inline only required width.
Is HTML case-sensitive? → No (but attribute values may be).
Can `<input>` be closed? → Yes or no: `<input />` is optional self-close.

---
## 10. Quick Revision Checklist
- [ ] Know all semantic tags & purpose
- [ ] Learn new form input types
- [ ] Understand multimedia tags usage
- [ ] Study HTML5 APIs basics
- [ ] Practice writing HTML5 structure by hand


© 2025 Geethanjali Group of Institutions. All Rights Reserved. Unauthorized use or distribution is prohibited.

# CSS3 Study Guide

## 1. What is CSS3?
CSS3 (Cascading Style Sheets Level 3) is the latest evolution of CSS used for styling web pages. It introduces modules, new selectors, media queries, animations, gradients, and improved layout features like Flexbox & Grid.

---
## 2. CSS Selectors (Very Important)
### Basic Selectors
| Selector | Example | Meaning |
|----------|---------|---------|
| Element | `p` | Selects all `<p>` elements |
| Class | `.btn` | Selects all elements with class `btn` |
| ID | `#main` | Selects element with id `main` |
| Universal | `*` | Selects all elements |
| Group | `h1, h2` | Selects multiple selectors |

### Attribute Selectors
| Selector | Example | Meaning |
|----------|---------|---------|
| `[type]` | `input[type]` | Elements with `type` attribute |
| `[type="text"]` | Exact match selector |
| `[title^="pro"]` | Starts with |
| `[title$="end"]` | Ends with |
| `[title*="mid"]` | Contains substring |

### Combinators
| Selector | Meaning |
|----------|---------|
| `A B` | Descendant selector |
| `A > B` | Direct child |
| `A + B` | Adjacent sibling |
| `A ~ B` | General sibling |

**Gotcha:** ID has higher specificity than class.

---
## 3. CSS Box Model
```
+-----------------------+
|      Margin           |
|  +------------------+ |
|  |     Border       | |
|  | +--------------+ | |
|  | |   Padding    | | |
|  | | +----------+ | | |
|  | | | Content | | | |
```
### Box Model Properties
| Property | Description |
|----------|-------------|
| `width` / `height` | Content area size |
| `padding` | Space inside border |
| `border` | Visible edge around element |
| `margin` | Space outside border |

Use `box-sizing: border-box;` to include padding + border inside width.

---
## 4. CSS3 Properties + Examples
### Colors
```css
color: rgb(255,0,0);
color: rgba(0,0,0,0.5);
color: hsl(120, 50%, 40%);
```

### Shadows
```css
box-shadow: 2px 2px 5px #333;
text-shadow: 1px 1px 2px black;
```

### Borders & Radius
```css
border-radius: 10px;
border: 2px dashed red;
```

### Gradients
```css
background: linear-gradient(to right, red, yellow);
background: radial-gradient(circle, blue, white);
```

---
## 5. Responsive Web Design (RWD)
### Media Query Syntax
```css
@media (max-width: 600px) {
  body { font-size: 14px; }
}
```
Used to adjust layout for screens, tablets, mobiles.

### Units for RWD
| Unit | Meaning |
|-------|---------|
| `vw` | % of viewport width |
| `vh` | % of viewport height |
| `rem` | Relative to root (`html`) font-size |
| `em` | Relative to parent font-size |

Prefer `rem` over `px` for accessibility.

---
## 6. Flexbox (Exam Favorite)
```css
.container {
  display: flex;
  justify-content: center; /* Main axis */
  align-items: center;     /* Cross axis */
  flex-direction: row;
}
```
| Property | Meaning |
|----------|---------|
| `justify-content` | left/center/right/space-between |
| `align-items` | top/center/bottom |
| `flex-wrap` | wrap elements |
| `gap` | spacing between items |

Flexbox is 1‑dimensional (row OR column)

---
## 7. CSS Grid (If asked)
```css
.container {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  gap: 10px;
}
```
Grid = 2‑dimensional layout system.

---
## 8. CSS Animation
```css
@keyframes slide {
  from { transform: translateX(0); }
  to { transform: translateX(100px); }
}
.box {
  animation: slide 2s infinite alternate;
}
```
| Property | Meaning |
|----------|---------|
| `animation-duration` | Time taken |
| `animation-iteration-count` | loops |
| `animation-timing-function` | ease, linear, etc. |

---
## 9. CSS Specificity (Very Important for MCQ)
```
Inline style     = 1000
ID selector      = 100
Class selector   = 10
Element selector = 1
```
`!important` overrides all (avoid using in real code).

---
## 10. Common Interview/MCQ Questions
Which is more specific: `#id .class p` or `.class p`? → First one.
What is the default `display` of `<div>`? → `block`
What is the default `position` value? → `static`
Difference between `visibility: hidden` and `display: none`?
- Hidden keeps layout space, display removes element completely.

---
## 11. Quick Revision Checklist
- [ ] Know all selector types
- [ ] Know box model exactly
- [ ] Understand media queries + units
- [ ] Practice flexbox & grid basics
- [ ] Learn specificity rules


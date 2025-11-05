© 2025 Geethanjali Group of Institutions. All Rights Reserved. Unauthorized use or distribution is prohibited.

# JavaScript Study Guide

## 1. What is JavaScript?
JavaScript is a lightweight, interpreted, dynamic programming language used to make web pages interactive. It runs in the browser and supports functional, procedural, and object-oriented programming.

---
## 2. Variables & Data Types
```js
var x = 10;      // function-scoped (avoid)
let y = 20;      // block-scoped
const z = 30;    // constant reference
```
### Primitive Types
```
string, number, boolean, null, undefined, bigint, symbol
```
`typeof null` → `object` (JS bug)
`NaN` is of type `number`

---
## 3. Operators
| Type | Examples |
|------|----------|
| Arithmetic | `+ - * / % **` |
| Comparison | `== != === !== > < >= <=` |
| Logical | `&& || !` |
| Ternary | `cond ? a : b` |
| Spread | `[...arr]`, `{...obj}` |
| Nullish coalescing | `x ?? defaultValue` |

**Gotcha:** `==` does type coercion, `===` does not.

---
## 4. Control Flow
```js
if (x > 10) {}
else if (x === 10) {}
else {}

switch(day) {
  case "Mon": break;
  default: break;
}

for (let i = 0; i < 5; i++) {}
while (count > 0) {}
do {} while(false);
```

`for...of` → iterates values
`for...in` → iterates keys (objects)

---
## 5. Functions
```js
function add(a,b) { return a+b; }          // declaration
const sub = function(a,b){ return a-b; }   // expression
const mul = (a,b) => a*b;                 // arrow
```
Arrow functions do **not** bind `this`
Functions are first-class citizens (can be passed as arguments)

### Callback Example
```js
setTimeout(() => console.log("Hi"), 1000);
```

---
## 6. Arrays & Objects
```js
let arr = [1,2,3];
arr.push(4);
arr.map(x => x*2);

let user = {name:"A", age:20};
console.log(user.name);
```
Common Array methods: `map`, `filter`, `reduce`, `find`, `includes`, `slice`, `splice`

`slice()` does not modify original array, `splice()` does

---
## 7. DOM Manipulation
```js
const btn = document.getElementById("btn");
const boxes = document.querySelectorAll(".box");

btn.textContent = "Click me";
btn.style.color = "red";

const div = document.createElement("div");
document.body.appendChild(div);
```
`querySelector` returns first match, `querySelectorAll` returns NodeList
`.innerHTML` parses HTML string (security risk: XSS)

---
## 8. Event Handling
```js
btn.addEventListener("click", function(e) {
  console.log("clicked", e.target);
});
```
| Event | Trigger |
|--------|---------|
| `click` | mouse click |
| `input` | text change |
| `keydown` | key press |
| `submit` | form submit |

Always prefer `addEventListener` over inline events (`onclick="..."`)

---
## 9. ES6+ Features
| Feature | Example |
|---------|---------|
| Template literals | ``Hello ${name}`` |
| Destructuring | `const {a,b} = obj` |
| Default params | `function f(x=1){}` |
| Promise | `new Promise((res,rej)=>{})` |
| Async/Await | `await fetch()` |
| Modules | `export`, `import` |

---
## 10. Basic Browser APIs (Exam Relevant)
### 1. Local Storage
```js
localStorage.setItem("k","v");
localStorage.getItem("k");
localStorage.removeItem("k");
```
Persistent even after browser close

### 2. Session Storage
Same API, but cleared when tab closes.

### 3. Fetch API
```js
fetch("https://api.example.com")
  .then(res => res.json())
  .then(data => console.log(data))
  .catch(err => console.error(err));
```
Replaces `XMLHttpRequest`

### 4. Geolocation API
```js
navigator.geolocation.getCurrentPosition(pos => {
  console.log(pos.coords.latitude);
});
```
Requires user permission

---
## 11. Common Gotchas
| Gotcha | Explanation |
|--------|-------------|
| `[] == ![]` → `true` | weird coercion rules |
| `typeof NaN` → `number` | historical bug |
| `this` depends on call-site | not lexical in normal functions |
| `const` doesn't freeze object | only prevents re-assignment |
| `0.1 + 0.2 !== 0.3` | floating point precision issue |

---
## 12. Sample Output MCQ
```js
console.log([] + []);        // ""
console.log({} + []);        // "[object Object]"
console.log(5 + "5");       // "55"
console.log(5 - "5");       // 0
```
`+` triggers string concat if any operand is string

---
## 13. Quick Revision Checklist
- [ ] Know let/const vs var
- [ ] Understand event loop, callbacks, promises
- [ ] Be able to manipulate DOM: select, change, create, remove
- [ ] Practice output questions on coercion & equality
- [ ] Know fetch, localStorage & event handling basics

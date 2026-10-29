# 📚 CSS-Only Mobile Hamburger Menu

## 🧭 1. Concept Map

Your journey to mastering pure CSS mobile menus builds step-by-step from foundational HTML to advanced interactive pseudo-classes:


```text
 01 ── 🟢 [ HTML Structure ]
       │
 02 ── 🟢 [ Media Queries ]
       │
 03 ── 🟢 [ CSS Positioning ]
       │
 04 ── ✨ [ Focus Pseudo-Class ]
       │
 05 ── ✨ [ Adjacent Sibling Combinator ]
       │
 06 ── ✨ [ Focus-Within Pseudo-Class ]
       │
 🚀 ── 🎯 [ Hamburger Menu ]

```


---

## 📖 2. Concept Lessons

### Concept 1: HTML Structure & Semantics (`<button>` and Wrappers)

* **WHAT is it?**
The foundational skeleton of a web page using semantic interactive tags like `<button>` instead of plain `<div>` elements for clickable items.
* *Analogy:* Like building a proper doorknob instead of a flat piece of wall so people instantly know it's meant to be grabbed and pulled.
* *Example:* 1 container wrapper holding 1 button and 1 menu list.


* **WHY does it exist?**
It makes elements natively interactive, accessible, and responsive to keyboard navigation and focus states. Without it, screen readers and keyboard users cannot interact with or focus the menu toggle.
* **HOW does it work?**
Wrap the hamburger lines inside `<button class="hamburger-btn">` and group it with the dropdown menu inside a parent container.
* *Formula:* `<div class="container"><button></button><div class="menu"></div></div>`


* **WHEN do I use it?**
Whenever you need user interaction without relying on JavaScript.
* *Signal words:* `"wrap the hamburger icon in a button"`, `"accessible toggle"`


* ⚠️ **Common Mistake:** Using a `<div>` or `<span>` for the clickable trigger instead of a native `<button>`, which strips away default focus behavior.

---

### Concept 2: Media Queries (`@media`)

* **WHAT is it?**
A CSS rule that applies specific style blocks only when certain device conditions (such as screen width) are met.
* *Analogy:* Like a home thermostat that automatically turns on heating only when the room temperature drops below a certain number.
* *Example:* `@media (max-width: 767px)` applies styles when the screen width is $767\text{px}$ or less.


* **WHY does it exist?**
It makes websites responsive across different devices and screen sizes. Without it, desktop layouts would crowd mobile screens or mobile items would spill onto desktop views.
* **HOW does it work?**
Write `@media (condition) { selector { property: value; } }`, where `@media` initiates the rule, `max-width` sets the screen limit threshold, and the code block holds conditional styles.
* **WHEN do I use it?**
When building responsive layouts that change design based on screen dimensions.
* *Signal words:* `"for mobile view only"`, `"responsive layout"`


* ⚠️ **Common Mistake:** Forgetting the viewport meta tag (`<meta name="viewport" content="width=device-width, initial-scale=1.0">`) in HTML, causing media queries to fail on mobile browsers.

---

### Concept 3: CSS Positioning (`position: relative` and `absolute`)

* **WHAT is it?**
Rules that control where an element sits on the page relative to its normal flow or its closest positioned ancestor.
* *Analogy:* Like pinning a sticky note relative to a bulletin board rather than floating randomly across the entire room.
* *Example:* An absolute menu positioned `top: 40px` and `right: 0` relative to its container.


* **WHY does it exist?**
It pops elements (like dropdowns and tooltips) out of the normal document flow so they float cleanly over other content. Without it, the dropdown would awkwardly push page content down.
* **HOW does it work?**
Set the parent container to `position: relative;` and the child menu to `position: absolute; top: [value]; right: [value];`, where `position` changes layout behavior and coordinates (`top`, `right`) set exact placement.
* **WHEN do I use it?**
For overlapping layouts, dropdown menus, and modal dialog boxes.
* *Signal words:* `"position absolute on the right side of the screen"`


* ⚠️ **Common Mistake:** Forgetting to give the parent container `position: relative`, which causes the absolute child to position itself relative to the entire body or viewport window instead.

---

### Concept 4: Focus Pseudo-Class (`:focus`)

* **WHAT is it?**
A CSS state selector that targets an element when it is clicked, tapped, or selected via keyboard navigation.
* *Analogy:* Like a light bulb turning on only when a light switch is actively pressed down.
* *Example:* `.hamburger-btn:focus` styles the button while it is held in focus.


* **WHY does it exist?**
It tracks user interaction state purely through CSS without writing JavaScript event listeners. Without it, you cannot detect taps or clicks using stylesheets alone.
* **HOW does it work?**
Append `:focus` to your selector (`selector:focus { property: value; }`), where `:` denotes a pseudo-class state and `focus` specifies the active interaction state.
* **WHEN do I use it?**
For pure-CSS interactivity triggered by user clicks or keyboard tabs.
* *Signal words:* `"use focus pseudo class to track if the button is in focus"`


* ⚠️ **Common Mistake:** Relying on `:hover` instead of `:focus`, which closes the menu the moment a mobile user lifts their finger from the screen.

---

### Concept 5: Adjacent Sibling Combinator (`+`)

* **WHAT is it?**
A CSS selector symbol that targets an element that immediately follows another specific sibling element.
* *Analogy:* Like saying "the person standing directly right next in line behind John."
* *Example:* `.hamburger-btn:focus + .mobile-menu` selects the `.mobile-menu` `div` that sits directly next to the button.


* **WHY does it exist?**
It styles an element based on the state or existence of a preceding sibling element. Without it, you cannot target a dropdown menu that sits adjacent to a toggle button.
* **HOW does it work?**
Combine two selectors with a plus sign (`SelectorA + SelectorB`), where `+` means "immediately preceded by", `SelectorA` is the preceding sibling, and `SelectorB` is the target sibling directly after it.
* **WHEN do I use it?**
When style changes on Element B depend on actions happening to Element A right before it.
* *Signal words:* `"style element A by focusing on some other element B"`


* ⚠️ **Common Mistake:** Using a general sibling combinator (`~`) when you needed an adjacent one (`+`), or placing an unstyled wrapper element between them that breaks direct adjacency.

---

### Concept 6: Focus-Within Pseudo-Class (`:focus-within`)

* **WHAT is it?**
A CSS pseudo-class that applies to a parent container if the container itself *or any of its child elements* currently has focus.
* *Analogy:* Like a room's security light staying on as long as anyone is inside the room.
* *Example:* `.hamburger-container:focus-within` stays active while clicking inside the menu links.


* **WHY does it exist?**
It prevents dropdown menus from instantly closing when a user moves their focus from the toggle button to a link inside the menu. Without it, clicking a menu link causes the button to lose focus and the menu to vanish instantly.
* **HOW does it work?**
Add `:focus-within` to the parent container (`.container:focus-within .menu { display: block; }`), where `:` is the pseudo-class and `focus-within` checks descendants.
* **WHEN do I use it?**
For dropdown menus, navigation bars, and popups where clicking inside child elements should keep the parent container open.
* *Signal words:* `"keep menu open when interacting with child items"`


* ⚠️ **Common Mistake:** Applying `:focus` only to the button instead of using `:focus-within` on the parent container, which breaks interactivity when clicking menu items.
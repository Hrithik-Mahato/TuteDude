# Laundry Service Hero Section - Learning & Concepts Guide

A beginner-friendly educational guide explaining every HTML element, CSS property, positioning concept, and design strategy used in building the Laundry Service Hero Section without using CSS Flexbox or Grid.

---

## 📌 Table of Contents
1. [Project Overview](#project-overview)
2. [Key Constraints & Challenge](#key-constraints--challenge)
3. [HTML Structure Walkthrough](#html-structure-walkthrough)
4. [CSS Concepts Deep-Dive](#css-concepts-deep-dive)
   - [1. Universal Reset & Typography](#1-universal-reset--typography)
   - [2. Viewport-Based Units (vw & vh)](#2-viewport-based-units-vw--vh)
   - [3. Display Inline vs. Inline-Block](#3-display-inline-vs-inline-block)
   - [4. Vertical Alignment & Line-Height Alignment](#4-vertical-alignment--line-height-alignment)
   - [5. White-Space Handling](#5-white-space-handling)
5. [Section-by-Section CSS Breakdown](#section-by-section-css-breakdown)
   - [Navbar Layout](#navbar-layout)
   - [Hero Left Section (Typography & CTA)](#hero-left-section-typography--cta)
   - [Hero Right Section (Image Handling)](#hero-right-section-image-handling)
6. [Key Bugs & Recommended Fixes](#key-bugs--recommended-fixes)

---

## 🛠 Project Overview
This project displays a responsive landing page header and hero section for a laundry service application. It includes:
- A top navigation bar with a logo, horizontal navigation links, and a highlighted username profile badge.
- A hero section split into two side-by-side columns: a copy block (heading, paragraph, CTA button) and a brand graphic.

---

## 🎯 Key Constraints & Challenge
The primary layout constraint for this challenge was:
- **No Flexbox (`display: flex`) or CSS Grid (`display: grid`) allowed.**
- All positioning and column alignment must rely strictly on traditional inline-block properties (`display: inline-block`, `vertical-align`, `text-align`, and line heights).

---

## 🏗 HTML Structure Walkthrough

The document follows a semantic structure containing two main sections within the `<body>`:

```html
<nav class="navbar">
  <div class="logo">LOGO</div>
  <ul class="nav-links">...</ul>
  <div class="user-profile">...</div>
</nav>

<section class="hero-section">
  <div class="hero-left-div">...</div>
  <div class="hero-right-div">...</div>
</section>
```

### Why this structure?
1. **`<nav>` Element:** Semantic wrapper identifying the main site navigation.
2. **Three Navbar Children:** Split into three horizontal sections (Logo on left, Links in middle, User badge on right).
3. **`<section class="hero-section">`:** Holds the primary hero message.
4. **Two Hero Divisions:** `.hero-left-div` (48% width) and `.hero-right-div` (50% width) sit side-by-side to form a 2-column layout.

---

## 💡 CSS Concepts Deep-Dive

### 1. Universal Reset & Typography
```css
* { 
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  font-family: cursive;
}
```
- **Universal Selector (`*`):** Applies rules to *every single HTML element*.
- **`box-sizing: border-box`:** Modifies the CSS box model so that padding and border widths are included inside an element's total width and height calculations rather than expanding them outward.
- **`margin: 0; padding: 0;`:** Resets built-in browser default margins/paddings (e.g., default `<body>` margin or `<ul>` padding).

---

### 2. Viewport-Based Units (vw & vh)
Instead of hardcoded pixels (`px`), this layout relies heavily on dynamic viewport units:
- **`vw` (Viewport Width):** $1\text{vw} = 1\%$ of the browser window's current width.
- **`vh` (Viewport Height):** $1\text{vh} = 1\%$ of the browser window's current height.

**Usage in Code:**
- Navbar height = `10vh` (takes $10\%$ of total screen height).
- Hero section height = `88vh` (takes $88\%$ of screen height).
- Total vertical screen height used = $10\text{vh} + 88\text{vh} = 98\text{vh}$ (fits on screen without scrolling).

---

### 3. Display Inline vs. Inline-Block

| Property | Sits Side-by-Side? | Accepts Custom `width` & `height`? | Respects Vertical Margins? |
| :--- | :---: | :---: | :---: |
| `display: block` | ❌ No (stacks vertically) | ✅ Yes | ✅ Yes |
| `display: inline` | ✅ Yes | ❌ No | ❌ No |
| `display: inline-block` | ✅ Yes | ✅ Yes | ✅ Yes |

**Why `inline-block` is critical here:**
Since Flexbox is not allowed, setting elements like `.logo`, `.nav-links`, `.user-profile`, `.hero-left-div`, and `.hero-right-div` to `display: inline-block` allows them to sit side-by-side horizontally while still allowing explicit width percentages (`20%`, `58%`, `48%`, `50%`).

---

### 4. Vertical Alignment & Line-Height Alignment

#### Vertical Alignment (`vertical-align: middle`)
`display: inline-block` elements align along the baseline of text by default, often causing mismatched tops and bottoms. Adding `vertical-align: middle` forces adjacent inline-blocks to line up evenly centered along a shared horizontal axis.

#### Line-Height Vertical Centering
```css
.navbar {
  height: 10vh;
  line-height: 10vh; 
}
```
Setting `line-height` equal to the element's parent `height` automatically centers single-line text and inline child elements vertically without needing padding hacks or flex alignments.

---

### 5. White-Space Handling
```css
.hero-section {
  white-space: nowrap; 
}

.hero-left-div, .hero-right-div {
  white-space: normal; 
}
```
- **`white-space: nowrap;`** on `.hero-section`: Prevents the two child divs (`48%` + `50%`) from accidental line wrapping if browser width changes slightly or inline HTML white-space gaps add extra pixels.
- **`white-space: normal;`** on the inner divs: Restores normal text line-wrapping inside the content blocks so headings and paragraphs wrap properly across multiple lines.

---

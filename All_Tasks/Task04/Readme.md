# CSS Layout & Units Guide: Viewport Units & Box Model Constraints
## 📌 Project Overview
This exercise focuses on understanding **CSS Viewport Units** (`vw`, `vh`), the **CSS Box Model**, and standard block-level flow layout without relying on modern layout modes like Flexbox or positioning hacks.

### Expected Result

* **Top / Bottom Spacing:** `10vh` (10% of screen height)

* **Left / Right Spacing:** `25vw` (25% of screen width)

* **Content Width:** `50vw`

* **Content Height:** `85vh`

* **No Scrollbars:** Strict viewport bounds managed via `box-sizing: border-box`.

## 💡 Key Concepts Learned

### 1. Viewport Units (`vw` & `vh`)

* **`1vw`** = 1% of the total viewport width.

* **`1vh`** = 1% of the total viewport height.

Unlike percentage lengths (`%`), which calculate relative to the **parent element's dimension**, viewport units (`vw`/`vh`) always calculate relative to the **root viewport window size**.

### 2. Layout Math without Flexbox or Positioning

To create a centered block that occupies 50% of the screen width and 80% of the screen height without Flexbox, we use simple margin math:

```
Total Width (100vw) = Left Margin (25vw) + Card Width (50vw) + Right Margin (25vw)
Total Height (100vh) = Top Margin (10vh) + Card Height (80vh) + Bottom Margin (10vh)

```

```css
div.image-container {
    margin: 10vh 25vw;
    width: 50vw;
    height: 50vh;
    
    border: 1px solid black;
}

```

### 3. Preventing Scrollbars without `overflow: hidden`

By default, adding borders or padding to an element adds to its total rendered width and height, causing unexpected scrollbars.

Using the universal box-sizing reset ensures borders stay inside the explicit dimensions:

```css
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

```

* **`box-sizing: border-box;`**: Includes `padding` and `border` inside the specified `width` and `height`.

* Setting `margin: 0` on `body` removes browser default spacing that would otherwise push `100vh` + `100vw` out of bounds.


#### Aspect Ratio Management with `object-fit`

To prevent the landscape image from distorting inside a fixed height viewport block:

```css
img {
    width: 100%;
    height: 85%;
    display: block;
    object-fit: cover;
}

```

* **`display: block;`**: Eliminates the inline gap beneath `<img>` elements.

* **`object-fit: cover;`**: Scales image proportionately to fill the element box without stretching.

## 🛠️ File Structure

```
Task/
├── index.html   # Main structure
└── style.css    # Styles adhering to box model & viewport rules

```

## 📋 Rule Checklist & Constraints Refresher


| **Rule / Constraint** | **Implemented Via** |
| --- | --- | 
| **25% Horizontal Spacing** | `margin-left: 25vw; margin-right: 25vw;` | 
| **10% Vertical Spacing** | `margin-top: 10vh; margin-bottom: 10vh;` | 
| **No Flexbox (`display: flex`)** | Standard block model calculation | 
| **No Positioning (`position: absolute/relative`)** | Standard normal layout flow | 
| **No `overflow: hidden`** | Precise viewport unit calculations and `border-box` | 
| **Gradient Button** | `linear-gradient(to right, ...)` | 

## 🚀 How to Test

1. Open `index.html` in any web browser.

2. Resize the browser window in both dimensions.

3. Observe how the content resizes dynamically while maintaining the `25vw` side margins and `10vh` top/bottom margins without triggering scrollbars!
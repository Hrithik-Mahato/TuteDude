# Task 04: CSS Units, Box Model, and Fonts

## 📚 Project Overview

This project demonstrates how to create a webpage using HTML and CSS. It contains a heading, an image container, an image, and a button.

The CSS controls the layout, spacing, element dimensions, image cropping, button appearance, and typography.

The main learning objective is to understand how CSS units, the CSS box model, element selectors, image-fitting properties, and font properties work together to create a webpage layout.

### Technologies Used

- **HTML5:** Defines the structure and content of the webpage.
- **CSS3:** Controls the appearance, sizing, spacing, and layout.
- **External image URL:** Loads an image hosted on another website.

---

# 1. Concept Map

The following concepts are arranged from the most basic to the most advanced. Each concept builds on the previous one.


| Order | Concept                                            | Status               |
| ----- | -------------------------------------------------- | -------------------- |
| 1     | HTML Document Structure                            | 🟢           |
| 2     | HTML Elements, Tags, and Attributes                | 🟢           |
| 3     | Linking HTML with External CSS                     | 🟢           |
| 4     | CSS Syntax and Declarations                        | 🟢           |
| 5     | CSS Selectors and Specificity Basics               | 🆕                |
| 6     | The CSS Cascade and Universal Reset                | 🆕                |
| 7     | The CSS Box Model                                  | 🆕                |
| 8     | CSS Units: Pixels, Percentages, and Viewport Units | 🆕                |
| 9     | Width, Height, Margin, and Padding                 | 🟢  |
| 10    | Block-Level Elements and `display`                 | 🆕                |
| 11    | Image Sizing and `object-fit`                      | 🆕                |
| 12    | CSS Borders and Their Effect on Layout             | 🆕                |
| 13    | CSS Gradients and Colors                           | 🆕                |
| 14    | Typography: Font Size, Family, and Weight          | 🆕                |
| 15    | Text Alignment and Decoration                      | 🆕                |
| 16    | Cursor Styling and Basic Interaction Cues          | 🆕                |
| 17    | Combining CSS Properties into a Complete Layout    | 🆕                |

*Status is a suggested starting point, not a test result. Mark a concept as  only when you can explain and use it independently.*

## Concept Chain

HTML document structure → HTML elements and attributes → External CSS → CSS syntax → Selectors → Cascade and reset → Box model → CSS units → Dimensions and spacing → Display behavior → Image fitting → Borders → Colors and gradients → Typography → Text styling → Cursor styling → Complete webpage layout → **Task 04**

## How the Concepts Connect

1. HTML creates the webpage's structure.
2. The stylesheet connects to the HTML document and selects the elements that need styling.
3. CSS declarations assign properties such as width, height, margin, and font size.
4. Selectors and the cascade determine which styles apply.
5. The box model explains how an element's content, padding, borders, and margins affect its size and position.
6. CSS units determine how measurements are calculated.
7. Display and image-fitting properties control how elements occupy space and how images appear inside their containers.
8. Colors, gradients, fonts, and text properties provide the visual design.
9. Combining these concepts produces the final webpage.

---

# 2. Concept Lessons

## CONCEPT 1: HTML Document Structure

### WHAT is it?

HTML document structure is the standard arrangement of elements that tells a browser what kind of document it is and where its content belongs.

**Analogy:** Think of a restaurant building. The building has an overall structure, a management area, and a customer area. Similarly, an HTML document has a root element, a head section, and a body section.

Example:

```
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Task 04</title>
</head>
<body>
    <h1>Task 04: CSS Units, Box Models, Fonts</h1>
</body>
</html>
```

**Tiny number example:** If a document has 1 `<head>` and 1 `<body>`, these two sections serve different purposes: the head contains document information, while the body contains the main page content.

### WHY does it exist?

A browser needs to understand how to interpret a document and distinguish its metadata from its visible content.

Without a proper structure, browsers may still display some HTML, but the document can be less predictable, less maintainable, or interpreted using compatibility behavior.

### HOW does it work?

- `<!DOCTYPE html>` tells the browser to use modern HTML standards mode.
- `<html lang="en">` is the root element and identifies English as the document's language.
- `<head>` contains metadata, the title, and stylesheet references.
- `<body>` contains the content displayed in the webpage.

The browser parses the HTML and constructs a Document Object Model (DOM), a tree-like representation of the document.

### WHEN do I use it?

Use this structure whenever creating an HTML webpage. Questions containing phrases such as "create an HTML page," "define the document structure," or "set up an HTML file" signal this concept.

### Common mistake

Placing visible webpage content inside `<head>` instead of `<body>`.

---

## CONCEPT 2: HTML Elements, Tags, and Attributes

### WHAT is it?

An HTML element represents a piece of webpage content or structure. Tags mark the beginning and, where required, the end of an element. Attributes provide additional information or configuration.

**Analogy:** An element is a parcel, tags define its boundaries, and attributes are the instructions attached to it.

Example from this project:

```
<img
    src="https://example.com/image.jpg"
    alt="A descriptive image"
    class="image"
>
```

**Tiny number example:** One `<img>` element has 3 attributes: `src`, `alt`, and `class`.

- `src` specifies the image location.
- `alt` provides alternative text.
- `class` assigns a reusable CSS classification.

### WHY does it exist?

Browsers need to know what kind of content each element represents and how to locate or describe it.

Without attributes, you could not conveniently specify an image source, attach a CSS class, or provide alternative text.

### HOW does it work?

Consider this heading:

```
<h1 class="page-title">Task 04</h1>
```

- `<h1>` is the opening tag.
- `class="page-title"` is an attribute.
- `Task 04` is the text content.
- `</h1>` is the closing tag.
- The complete combination forms an HTML element.

In this project, the image uses `src`, `alt`, and `class`, while the button uses a class:

```
<button class="button">Click Me</button>
```

### WHEN do I use it?

Use elements and attributes when adding headings, images, buttons, forms, lists, or other webpage content. Questions that mention "insert an image," "assign a class," or "add alternative text" signal this concept.

### Common mistake

Confusing a class attribute with a CSS class selector: `class="image"` belongs in HTML, while `.image` is the CSS selector used to target it.

---

## CONCEPT 3: Linking HTML with External CSS

### WHAT is it?

External CSS means storing styling rules in a separate `.css` file and connecting that file to an HTML document.

**Analogy:** HTML is the restaurant's floor plan, while CSS is the interior-design plan. They are separate documents that work together.

Your HTML contains:

```
<link rel="stylesheet" href="style.css">
```

**Tiny number example:** One HTML file can link to one `style.css` file containing 20 or more styling rules.

### WHY does it exist?

Separating structure from presentation makes projects easier to maintain, reuse, and debug.

If all styling were written directly into HTML, a large page could become difficult to read and update. External CSS also allows multiple HTML pages to share the same stylesheet.

### HOW does it work?

The browser reads the `<link>` element and requests the CSS file specified by `href`.

- `link` creates a relationship with an external resource.
- `rel="stylesheet"` tells the browser that the resource is a stylesheet.
- `href="style.css"` identifies the file to load.

Because `style.css` is a relative path, the browser normally looks for it relative to the HTML document's URL.

Your project should have this structure:

```
Task-04/
├── index.html
├── style.css
└── README.md
```

### WHEN do I use it?

Use an external stylesheet when a task asks you to link CSS, create a separate `style.css`, or keep HTML and styling in separate files.

### Common mistake

Using the wrong filename or folder path in `href`, causing the browser to load the HTML without the intended styles.

---

## CONCEPT 4: CSS Syntax and Declarations

### WHAT is it?

CSS syntax is the set of rules used to write styling instructions. A CSS rule contains a selector and a declaration block.

**Analogy:** A selector identifies which restaurant table needs attention, and declarations specify what changes to make to that table.

Example:

```
.button {
    color: white;
    font-size: 2rem;
    cursor: pointer;
}
```

**Tiny number example:** This rule contains 1 selector and 3 declarations.

### WHY does it exist?

CSS needs a consistent format so the browser can identify the target elements, properties, and values.

Without this syntax, the browser would not reliably know which elements to style or which values to apply.

### HOW does it work?

The general pattern is:

```
selector {
    property: value;
}
```

- **Selector:** Identifies the target element or elements.
- **Property:** Names the characteristic being changed.
- **Value:** Specifies the desired setting.
- **Colon (`:`):** Separates the property from its value.
- **Semicolon (`;`):** Ends a declaration.
- **Braces (`{}`):** Enclose the declarations belonging to a rule.

For example:

```
font-size: 2rem;
```

The property is `font-size`, and the value is `2rem`.

### WHEN do I use it?

Use CSS declarations whenever you need to change color, size, spacing, layout, borders, or fonts. Phrases such as "style the element," "set the width," and "change the font" signal this concept.

### Common mistake

Writing invalid property names or values, such as `text-color: red`; the correct property for text color is `color: red;`.

# Selectors, Cascade, Box Model, and CSS Units

## CONCEPT 5: CSS Selectors and Specificity Basics

### WHAT is it?

A CSS selector identifies which HTML elements should receive a particular set of styles.

**Analogy:** Imagine a teacher calling students by different criteria: everyone in the classroom, only students wearing a particular uniform, or one student by name. CSS selectors work in a similar way.

Examples from your project:

```
* {
    box-sizing: border-box;
}

.button {
    color: white;
}

h1 {
    text-align: center;
}

div.image-container img {
    object-fit: cover;
}
```

**Tiny number example:** If a page contains 1 heading, 1 image, and 1 button, the selector `h1` targets the heading, while `.button` targets the button.

### WHY does it exist?

A webpage may contain hundreds of elements. Writing separate styles for every individual element would be repetitive.

Selectors let developers target elements by tag name, class, ID, or relationships with other elements.

### HOW does it work?

Common selector types:

| Selector              | Meaning                                            | Example                                 |
| --------------------- | -------------------------------------------------- | --------------------------------------- |
| `h1`                  | Selects elements by tag name                       | `h1 { color: blue; }`                   |
| `.button`             | Selects elements with a class                      | `.button { color: white; }`             |
| `#main`               | Selects an element with an ID                      | `#main { width: 80%; }`                 |
| `*`                   | Selects all elements                               | `* { box-sizing: border-box; }`         |
| `div img`             | Selects images descended from a `div`              | `div img { width: 100%; }`              |
| `div.image-container` | Selects a `div` having the class `image-container` | `div.image-container { height: 50vh; }` |

The space in `div.image-container img` is important. It means: select an `img` element that is somewhere inside a `div` whose class is `image-container`.

#### What is specificity?

Specificity helps the browser decide between competing CSS rules that target the same element and property.

For example:

```
h1 {
    color: blue;
}

.page-title {
    color: red;
}
```

If the same heading has `class="page-title"`, the class selector normally wins because its specificity is higher than that of the type selector, assuming there are no other overriding factors.

The basic specificity order is:

**ID selectors → class/attribute/pseudo-class selectors → type/pseudo-element selectors.**

The universal selector `*` contributes no specificity.

### WHEN do I use it?

Use selectors when the task says "style the heading," "target the image inside the container," "apply a class," or "select all elements."

### Common mistake

Using `.image` when the HTML element does not have `class="image"`, or assuming a descendant selector only targets direct children.

---

## CONCEPT 6: The CSS Cascade and Universal Reset

### WHAT is it?

The CSS cascade is the process browsers use to determine which CSS declarations apply when multiple rules could affect the same element.

A CSS reset is a collection of rules that removes or normalizes default browser styling to give developers a more predictable starting point.

**Analogy:** The cascade is like deciding which instruction takes priority when several people give instructions. A reset is like clearing a worktable before beginning a new project.

Your stylesheet begins with:

```
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}
```

**Tiny number example:** This rule sets the initial margin and padding of all selected elements to `0`, rather than leaving their usual browser defaults.

### WHY does it exist?

Browsers apply default styles to many HTML elements. For example, headings commonly have margins, and the body usually has a default margin.

These defaults can make a layout harder to calculate precisely.

Developers often use a reset to reduce unexpected spacing differences and establish consistent box-sizing behavior.

However, resetting everything also removes useful defaults, such as list indentation. A reset should be chosen deliberately rather than treated as a requirement for every project.

### HOW does it work?

Your reset contains three declarations:

- `box-sizing: border-box;` changes how an element's declared width and height are calculated.
- `margin: 0;` removes the element's external spacing.
- `padding: 0;` removes the space between the content and border.

The universal selector `*` matches all elements. The reset therefore applies these declarations broadly.

The cascade considers several factors, including origin, importance, cascade layers, specificity, and source order. It is not simply a rule that the last declaration always wins.

### WHEN do I use it?

Use a reset when a task requires precise spacing or when you want to establish consistent starting styles. Phrases such as "remove default spacing," "normalize browser styles," and "make layout calculations predictable" signal this concept.

### Common mistake

Assuming a universal reset makes every element behave identically; it does not remove every browser default or eliminate differences in element behavior.

---

## CONCEPT 7: The CSS Box Model

### WHAT is it?

The CSS box model explains how a browser represents an element's size and spacing using four layers:

1. Content
2. Padding
3. Border
4. Margin

**Analogy:** Think of a framed photograph. The picture is the content, the inner mat is the padding, the frame is the border, and the empty space around the frame is the margin.

Your project uses the box model in:

```
div.image-container {
    margin: 10vh 25vw;
    width: 50vw;
    height: 50vh;
    border: 1px solid black;
}
```

**Tiny number example:** Suppose an element has a content width of `100px`, horizontal padding of `10px` on each side, and a `2px` border on each side. Under the default `content-box` model, its outer border-box width is:

```math
(100 + 10 + 10 + 2 + 2 = 124\text{px})
```

With `border-box`, a declared width of `100px` includes the padding and border.

### WHY does it exist?

An element needs more than content space. Text and images may need inner spacing, visible boundaries, and separation from neighboring elements.

Without understanding the box model, developers may expect an element to occupy `100px` but find that padding and borders make it wider.

### HOW does it work?

The four layers are:

- **Content:** The text, image, or other content.
- **Padding:** Space inside the border, surrounding the content.
- **Border:** The visible boundary around the content and padding.
- **Margin:** Space outside the border, separating the element from other elements.

The default sizing model is `content-box`.

Under `content-box`:

```math
\text{Outer width} =\
\text{Content width} + \text{Padding} + \text{Borders}\
```

Under `border-box`, the declared width includes content, padding, and borders.

**Important:** Margin is outside the border in both models. It is not included in the declared width.

### WHEN do I use it?

Use the box model when calculating element dimensions, aligning containers, adding borders, or diagnosing unexpected gaps. Questions containing "box model," "total width," "padding," or "margin" signal this concept.

### Common mistake

Confusing margin with padding: padding creates space inside an element's border, while margin creates space outside it.

---

## CONCEPT 8: CSS Units — Pixels, Percentages, and Viewport Units

### WHAT is it?

CSS units describe how large a measurement should be. Different units use different reference points.

Your stylesheet uses `vw`, `vh`, `%`, and `rem`.

**Analogy:** You could measure a table using centimeters, measure a room as a percentage of a floor plan, or describe a position relative to the entire building. CSS units also provide different ways to express measurements.

**Tiny number example:** If the viewport is `1000px` wide, then `10vw` equals `100px`. If the viewport is `800px` tall, then `10vh` equals `80px`.

### WHY does it exist?

Different layouts need different sizing behavior.

A fixed measurement may be useful for a thin border, but a layout that should adapt to the screen needs measurements tied to the available space.

CSS offers several units so developers can choose the appropriate reference rather than relying on one measurement system.

### HOW does it work?

#### A. Pixels (`px`)

A CSS pixel is a CSS reference unit, not necessarily one physical screen pixel.

```
border: 1px solid black;
```

The border is specified as `1px` thick.

**Why use it?** Pixels are useful for small, precise details such as borders.

#### B. Percentages (`%`)

A percentage expresses a size relative to a reference determined by the property and layout context.

```
img {
    width: 100%;
}
```

For an image inside a container with a content width of `500px`, `width: 100%` generally makes the image's content width `500px`, provided no other constraints interfere.

**Why use it?** Percentages are useful when an element should scale with its containing block.

#### C. Viewport width (`vw`)

`1vw` represents 1% of the viewport width.

Your code:

```
width: 50vw;
margin: 10vh 25vw;
```

|Values |Meaning |
|---|---|
|margin: 10px;|all four sides|
|margin: 10vh 25vw;|top/bottom + left/right|
|margin: 10px 20px 30px;|top + left/right + bottom|
|margin: 10px 20px 30px 40px;|top + right + bottom + left|
---

If the viewport is `1200px` wide:

```math
50vw = \frac{50}{100}\times1200 = 600\text{px}\
```

Likewise:

```math
25vw = \frac{25}{100}\times1200 = 300\text{px}\
```

**Why use it?** Viewport units are useful when a measurement should scale with the browser's visible area.

#### D. Viewport height (`vh`)

`1vh` represents 1% of the viewport height.

Your code:

```
height: 50vh;
margin: 10vh 25vw;
```

If the viewport is `800px` tall:

```math
50vh = \frac{50}{100}\times800 = 400\text{px}\
```

And:
```math
10vh = \frac{10}{100}\times800 = 80\text{px}\

```

**Why use it?** Viewport height units help create sections whose heights respond to the available screen height.

#### E. Root em (`rem`)

`1rem` is based on the computed font size of the root element, usually `<html>`.

Your button uses:

```
font-size: 2rem;
```

If the root font size is `16px`:

```math
2rem = 2\times16 = 32\text{px}\
```

**Why use it?** `rem` makes text sizing relative to the root font size, helping maintain consistent typography and allowing scaling when that root size changes.

### WHEN do I use it?

Use these units when a question asks for responsive sizing, spacing relative to the viewport, a percentage-based image, or scalable text.

Signals in your assignment include "25% of the width," "10% of the viewport height," and "font size."

### Common mistake

Treating `vw`, `vh`, `%`, and `rem` as interchangeable; each uses a different reference, so the same number can produce very different sizes.

# Dimensions, Display, Images, Borders, and Gradients

## CONCEPT 9: Width, Height, Margin, and Padding

### WHAT is it?

These CSS properties control an element's dimensions and spacing.

**Analogy:** When arranging furniture, width and height describe the furniture's dimensions, margin separates it from other furniture, and padding creates space inside a container around its contents.

Your CSS:

```
div.image-container {
    margin: 10vh 25vw;
    width: 50vw;
    height: 50vh;
}
```

**Tiny number example:** If a container's width is `500px`, its content area can accommodate an image with a width of `500px` when the image uses `width: 100%` and the containing block has a `500px` content width.

### WHY does it exist?

Developers need to control how much space elements occupy and how much distance separates them.

Without these properties, a browser's default sizing and spacing may not match the intended design.

### HOW does it work?

#### Width and height

```
width: 50vw;
height: 50vh;
```

- `width` specifies the element's width.
- `height` specifies its height.
- `50vw` means 50% of the viewport width.
- `50vh` means 50% of the viewport height.

#### Margin shorthand

```
margin: 10vh 25vw;
```

When two values are provided, CSS interprets them as:

```
margin-top: 10vh;
margin-bottom: 10vh;
margin-right: 25vw;
margin-left: 25vw;
```

The first value applies to the top and bottom; the second applies to the left and right.

This shorthand is equivalent to:

```
margin: 10vh 25vw 10vh 25vw;
```

The four-value shorthand follows the order **top → right → bottom → left**.

#### Padding

Your reset includes:

```
padding: 0;
```

This removes the inner spacing from the selected elements. Padding can instead be assigned a nonzero value when content needs breathing room.

### WHEN do I use it?

Use these properties when positioning a container, sizing an image, creating space around content, or matching dimensions in a reference screenshot.

### Common mistake

Assuming `margin: 10vh 25vw` means 10% spacing on every side; it means 10vh vertically and 25vw horizontally.

---

## CONCEPT 10: Block-Level Elements and `display`

### WHAT is it?
[CSS Display Property | Sigma Web Development Course - Tutorial #23](https://youtu.be/hRHV5cjEB1w?si=dexOrsc4re3DI2fy)

The `display` property controls how an element participates in layout.

Your code uses:

```
img {
    display: block;
}

.button {
    display: block;
}

h1 {
    display: block;
}
```

**Analogy:** Think of a queue. A block-level element normally starts on a new line and occupies the available width of its containing block, while inline elements generally flow alongside text.

**Tiny number example:** If two block-level elements appear in normal flow, they typically occupy two separate lines rather than sharing one line.

### WHY does it exist?

Different content needs different layout behavior. A heading generally belongs on its own line, while a word inside a paragraph often belongs inline with the surrounding text.

The `display` property allows developers to control these behaviors.

### HOW does it work?

Common values include:

- `block`: Creates a block-level box.
- `inline`: Participates in inline flow.
- `inline-block`: Flows inline but supports box dimensions in ways ordinary inline boxes do not.
- `flex`: Creates a flex formatting context.
- `grid`: Creates a grid formatting context.
- `none`: Removes the element's box from layout.

For example:

```
img {
    display: block;
}
```

Images are inline by default. Making the image block-level can eliminate the baseline gap that sometimes appears beneath inline images and makes it easier to stack the image with the button.

**Important distinction:** `display: block` does not automatically make an element fill its parent's height. It affects layout participation, not the element's entire sizing behavior.

### WHEN do I use it?

Use `display` when elements appear on unexpected lines, images have unwanted gaps, or a task requires block, inline, flex, or grid behavior.

### Common mistake

Assuming `display: block` automatically centers an element or gives it a specific height.

---

## CONCEPT 11: Image Sizing and `object-fit`

### WHAT is it?

Image sizing controls the dimensions of an image element, while `object-fit` determines how the image content fits inside that element's box.

Your CSS:

```
div.image-container img {
    width: 100%;
    height: 85%;
    display: block;
    object-fit: cover;
}
```

**Analogy:** Imagine fitting a photograph into a frame. You can stretch it, leave empty space, or enlarge and crop it so the frame is completely filled.

**Tiny number example:** Suppose an image is `800px` wide and `600px` tall. Its aspect ratio is (800:600 = 4:3). If the display box is `500px` wide and `250px` tall, `object-fit: cover` scales the image until the box is filled, cropping part of the image if necessary.

### WHY does it exist?

Images often have a different aspect ratio from the box in which they must appear.

Without `object-fit`, an image may look distorted if both its width and height are forced to dimensions that do not preserve its original aspect ratio.

### HOW does it work?

#### Step 1: Set the element's dimensions

```
width: 100%;
height: 85%;
```

The image is set to the full content width of its containing block and 85% of its containing block's height, subject to normal CSS sizing constraints.

#### Step 2: Choose how the image content fits

```
object-fit: cover;
```

Common values:

- `cover`: Fills the box while preserving the image's aspect ratio. Some image content may be cropped.
- `contain`: Shows the whole image while preserving its aspect ratio. Empty space may remain.
- `fill`: Fills the box, potentially distorting the image.
- `none`: Displays the image at its intrinsic size, subject to other sizing constraints.

Your use of `cover` is appropriate when the goal is to fill the image area rather than show every part of the original image.

### WHEN do I use it?

Use `object-fit` when the task says "fit the image inside a container," "prevent image distortion," "crop the image to fill the box," or "maintain the aspect ratio."

### Common mistake

Using `object-fit: cover` while expecting the entire image to remain visible; cropping is part of how `cover` works.

---

## CONCEPT 12: CSS Borders and Their Effect on Layout

### WHAT is it?

A border is a visible line surrounding an element's content and padding.

Your code:

```
div.image-container {
    border: 1px solid black;
}

.button {
    border: 2px solid black;
}
```

**Analogy:** A border is like a frame around a photograph. It visually separates the photograph from the surrounding wall.

**Tiny number example:** A `2px` border on both the left and right sides contributes `4px` to an element's total width under `content-box`, unless another sizing rule changes the calculation.

### WHY does it exist?

Borders help define boundaries, improve visual separation, and make interfaces easier to scan.

They also affect layout dimensions unless the sizing model accounts for them within the declared width and height.

### HOW does it work?

The shorthand follows this pattern:

```
border: width style color;
```

For example:

```
border: 1px solid black;
```

- `1px` specifies the thickness.
- `solid` specifies a continuous line.
- `black` specifies the color.

Other border styles include `dashed`, `dotted`, and `double`.

Because your universal reset sets `box-sizing: border-box`, a declared width and height include the border and padding for ordinary elements. The border does not simply get added outside the declared dimensions.

### WHEN do I use it?

Use borders when outlining a container, button, input, card, or image. Phrases such as "add a border," "outline the container," and "create a visible boundary" signal this concept.

### Common mistake

Forgetting that border thickness affects the space available for content, even when `box-sizing: border-box` is used.

---

## CONCEPT 13: CSS Gradients and Colors

### WHAT is it?

A CSS gradient creates a gradual transition between colors. Unlike a flat background color, it can combine multiple colors across a direction.

Your button uses:

```
background: linear-gradient(
    to right,
    rgb(8, 201, 235),
    rgba(1, 27, 1, 0.877)
);
```

**Analogy:** Imagine painting a wall so it transitions smoothly from blue on the left to dark green on the right.

**Tiny number example:** A gradient with 2 color stops transitions from the first specified color to the second.

### WHY does it exist?

Gradients provide visual depth and variation without requiring a separate background image.

They are useful for buttons, banners, cards, and decorative backgrounds. A flat color is simpler, but a gradient gives the designer more control over visual transitions.

### HOW does it work?

The general syntax is:

```
background: linear-gradient(direction, color1, color2);
```

In your example:

- `linear-gradient()` creates a linear color transition.
- `to right` specifies the direction, from left to right.
- `rgb(8, 201, 235)` specifies the first color using red, green, and blue components.
- `rgba(1, 27, 1, 0.877)` specifies the second color using red, green, blue, and an alpha component.

RGB component values generally range from `0` to `255`.

The alpha component ranges from `0` (fully transparent) to `1` (fully opaque). Thus, `0.877` represents approximately 87.7% opacity.

Because the gradient is applied to the button's background, it paints the button's background area, subject to its border and other styling.

### WHEN do I use it?

Use gradients when a task requests a gradient button, a smooth color transition, or a decorative background.

### Common mistake

Confusing a gradient's direction with the order of its color stops, or assuming an RGBA alpha value of `0.877` means 0.877% opacity.

# Typography, Text Styling, and the Complete Layout

## CONCEPT 14: Typography — Font Size, Family, and Weight

### WHAT is it?

Typography is the way text is presented, including its size, typeface, thickness, and readability.

Your CSS:

```
.button {
    font-size: 2rem;
    font-family: cursive, sans-serif;
    font-weight: 500;
}
```

**Analogy:** Typography is like choosing how a restaurant prints its menu. The words may be identical, but their size, style, and thickness affect readability and personality.

**Tiny number example:** If the root font size is `16px`, `font-size: 2rem` generally produces a font size of `32px`.

### WHY does it exist?

Text needs to be readable and visually appropriate for its purpose.

A heading should usually stand out from body text, while button text should be legible and easy to recognize. Typography properties let developers control these differences without changing the HTML content.

### HOW does it work?

#### A. `font-size`

```
font-size: 2rem;
```

Controls the size of the text.

Common units include `px`, `rem`, and `em`. The `rem` unit is relative to the root element's font size.

#### B. `font-family`

```
font-family: cursive, sans-serif;
```

Specifies a preferred font followed by fallback fonts.

- `cursive` requests a font from the cursive generic family.
- `sans-serif` provides a fallback from the sans-serif generic family if an appropriate earlier choice is unavailable.

The browser uses the first suitable available font. The actual appearance depends on the fonts installed or otherwise available to the browser.

**Why provide fallbacks?** Developers cannot assume every device has the same fonts. A fallback improves the chance that text remains readable when the preferred font is unavailable.

#### C. `font-weight`

```
font-weight: 500;
```

Controls the requested thickness of the text.

Common values include:

- `400`: Normal weight.
- `500`: Medium weight.
- `700`: Bold weight.

These numbers represent standard weight levels, but the exact appearance depends on the selected font and its available weights.

**Why use a number instead of `bold`?** Numeric values allow developers to request intermediate weights, such as `500` or `600`, when the font supports them.

### WHEN do I use it?

Use typography properties when a task asks you to change the font, make text larger, use a cursive style, or adjust font thickness.

### Common mistake

Assuming every device renders `cursive` identically or that every font has a distinct `500` weight available.

---

## CONCEPT 15: Text Alignment and Decoration

### WHAT is it?

Text alignment controls how text is positioned horizontally within its relevant formatting area. Text decoration adds visual lines, such as underlines.

Your CSS:

```
h1 {
    text-align: center;
    text-decoration: underline;
}
```

**Analogy:** Think of writing a heading on a noticeboard. You can place it in the center and draw a line underneath it to make it stand out.

**Tiny number example:** If a heading's available width is `1000px`, `text-align: center` centers its text within that available area.

### WHY does it exist?

Text needs visual organization. Centering can emphasize a page title, while underlining can distinguish a heading or create a particular visual style.

Without these properties, text generally follows the default alignment and decoration rules.

### HOW does it work?

#### `text-align`

Common values include:

- `left`: Aligns text toward the left.
- `right`: Aligns text toward the right.
- `center`: Centers text.
- `justify`: Distributes spacing to align text along both edges where applicable.

Your code:

```
text-align: center;
```

centers the heading's text inside its line box.

#### `text-decoration`

Common values include:

- `underline`: Adds a line beneath the text.
- `overline`: Adds a line above the text.
- `line-through`: Adds a line through the text.
- `none`: Removes text decoration.

Your code uses:

```
text-decoration: underline;
```

This adds an underline to the heading.

### WHEN do I use it?

Use these properties when a question says "center the heading," "underline the title," or "align text."

### Common mistake

Confusing `text-align: center` with centering the entire element; text alignment centers text inside its available area, not necessarily the element itself.

---

## CONCEPT 16: Cursor Styling and Basic Interaction Cues

### WHAT is it?

The `cursor` property changes the mouse pointer's appearance when it is over an element.

Your CSS:

```
.button {
    cursor: pointer;
}
```

**Analogy:** A sign on a door tells you that the door can be opened. A pointer cursor gives a similar visual hint that an element is interactive.

**Tiny number example:** If a page has 1 button, applying `cursor: pointer` to that button changes the pointer's appearance when the mouse moves over it.

### WHY does it exist?

Users benefit from visual cues that communicate which elements are interactive.

A pointer cursor is commonly used for clickable controls, helping distinguish them from ordinary text or decorative content.

However, a cursor is only a visual cue. It does not create click behavior.

### HOW does it work?

```
cursor: pointer;
```

This requests the browser's pointer cursor, commonly displayed as a hand.

Other values include:

- `default`: The usual pointer for ordinary content.
- `text`: Indicates a text-selection context.
- `not-allowed`: Indicates that an action is unavailable.

In your HTML:

```
<button class="button">Click Me</button>
```

the `<button>` element is already a native interactive HTML control. The cursor styling changes its appearance but does not define what happens when it is clicked.

To perform an action, the button needs suitable behavior, such as a JavaScript event handler or a form submission.

### WHEN do I use it?

Use cursor styling when a task asks you to change the pointer over buttons, clickable items, or other interactive elements.

### Common mistake

Assuming `cursor: pointer` makes an element functional; it changes the pointer appearance, not the element's behavior.

---

## CONCEPT 17: Combining CSS Properties into a Complete Layout

### WHAT is it?

Combining CSS properties means using multiple styling rules together so that an element's dimensions, position, appearance, and content fit the intended design.

Your task combines a viewport-sized body, a container, an image, a button, and a centered heading.

**Analogy:** Building a webpage is like arranging a room. Choosing the dimensions of the furniture is not enough; you must also arrange its position, spacing, appearance, and relationship with other objects.

**Tiny number example:** If a viewport is `1200px` wide, a container declared as `50vw` is `600px` wide. Two horizontal margins of `25vw` each are `300px` apiece, so the intended horizontal calculation is:

```math
300 + 600 + 300 = 1200\text{px}\
```

This fills the viewport width mathematically, before considering scrollbar behavior and other layout constraints.

### WHY does it exist?

Individual CSS properties solve individual problems. A width defines a dimension, a margin defines spacing, and a gradient defines appearance.

A complete design requires these properties to work together. Even correct individual declarations can produce an unexpected overall layout if their combined sizes exceed the available space.

### HOW does it work?

Let's combine the important rules from your stylesheet.

#### Step 1: Establish predictable sizing

```
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}
```

This removes the default margins and padding from all elements and makes declared dimensions include padding and borders.

#### Step 2: Set the body dimensions

```
body {
    width: 100vw;
    height: 100vh;
}
```

The body is assigned a width and height corresponding to the viewport dimensions.

#### Step 3: Size and position the container

```
div.image-container {
    margin: 10vh 25vw;
    width: 50vw;
    height: 50vh;
    border: 1px solid black;
}
```

The container is designed to occupy half the viewport width and half its height, with viewport-based margins.

#### Step 4: Fit the image

```
div.image-container img {
    width: 100%;
    height: 85%;
    display: block;
    object-fit: cover;
}
```

The image fills the container's content width and is assigned 85% of its content height. The `cover` value preserves its aspect ratio while allowing cropping.

#### Step 5: Style the button

```
.button {
    width: 100%;
    height: 15%;
    display: block;
    border: 2px solid black;
    background: linear-gradient(
        to right,
        rgb(8, 201, 235),
        rgba(1, 27, 1, 0.877)
    );
    color: white;
    font-size: 2rem;
    font-family: cursive, sans-serif;
    font-weight: 500;
    cursor: pointer;
}
```

The button is assigned the full container content width and 15% of its content height. It receives a gradient background, white text, a border, and a pointer cursor.

The image and button are intended to occupy 85% and 15% of the container's content height, respectively.

#### Step 6: Style the heading

```
h1 {
    text-align: center;
    text-decoration: underline;
    display: block;
}
```

The heading's text is centered and underlined. The `display: block` declaration is redundant for an ordinary `<h1>` because headings are block-level by default.

### WHEN do I use it?

Use this concept when a task asks you to reproduce a reference layout, position an image and button together, meet specific viewport-based measurements, or combine multiple CSS properties into one design.

### Common mistake

Checking each CSS declaration separately but failing to check whether the combined element sizes and margins fit inside the viewport.

---

# Important Layout Calculation for This Project

The intended design uses these dimensions:

| Element           | CSS value | Reference                |
| ----------------- | --------- | ------------------------ |
| Body width        | `100vw`   | Viewport width           |
| Body height       | `100vh`   | Viewport height          |
| Container width   | `50vw`    | Viewport width           |
| Container height  | `50vh`    | Viewport height          |
| Vertical margin   | `10vh`    | Viewport height          |
| Horizontal margin | `25vw`    | Viewport width           |
| Image height      | `85%`     | Container content height |
| Button height     | `15%`     | Container content height |
| Button font size  | `2rem`    | Root font size           |

### A worked example

Suppose the viewport measures `1200px × 800px`.

The container's intended dimensions are:

- Width: (50%\times1200=600\text{px})
- Height: (50%\times800=400\text{px})
- Horizontal margin: (25%\times1200=300\text{px}) on each side.
- Vertical margin: (10%\times800=80\text{px}) above and below.

The horizontal calculation is:

```math
300+600+300=1200\text{px}\
```

This shows why `50vw` plus two margins of `25vw` is a deliberate combination: it mathematically accounts for the full viewport width.

The vertical calculation is different. The container's `400px` height plus its two `80px` vertical margins already uses `560px`. The heading also occupies space above the container. Therefore, the entire page can exceed the viewport height even though the container itself is only `50vh` tall.

### A note about `box-sizing`

Your universal reset applies `box-sizing: border-box` to the container, image, and button.

That means the container's declared `50vh` height includes its borders. Its content height is slightly smaller than `50vh`, because the `1px` top and bottom borders occupy space within that declared height.

The image and button percentages are based on the containing block's content height. Their combined percentages add to 100%, which is the intended arrangement.

### A practical limitation

Viewport units do not guarantee that a layout fits every screen. For example:

- A very short screen may not have enough height for the heading, container, and margins.
- Browser scrollbars and viewport behavior can affect how `100vw` behaves in some environments.
- A large `rem` font size can make the button text difficult to fit on a small screen.

A responsive layout should therefore be tested at multiple screen sizes instead of relying only on the arithmetic.

# Understanding the Code as One Complete System

## 4. HTML Code: Line-by-Line Explanation

Let's examine the complete HTML and understand the purpose of each section.

### 4.1 Document declaration

```
<!DOCTYPE html>
```

This tells the browser to interpret the document using modern HTML standards mode.

**Why not skip it?** Omitting the declaration can cause some browsers to use quirks mode, where certain layout calculations and rendering behaviors differ from standards mode.

### 4.2 Root element and language

```
<html lang="en">
```

The `<html>` element is the root of the HTML document. The `lang="en"` attribute declares English as the page's primary language.

**Why use `lang`?** It helps assistive technologies, search engines, and other software understand the language of the content.

### 4.3 Metadata section

```
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="style.css">
    <title>Task 04</title>
</head>
```

Each line serves a different purpose:

- `meta charset="UTF-8"` declares the character encoding so the browser can interpret common characters correctly.
- The viewport meta tag tells mobile browsers to use the device's viewport width as the layout viewport and begin at a scale of 1.
- The `link` element connects the HTML to `style.css`.
- The `title` element supplies the document title, typically shown in the browser tab.

**Why place these inside `<head>`?** They describe or configure the document rather than representing the main content displayed in the page body.

### 4.4 Visible page content

```
<body>
    <h1>Task 04: CSS Units, Box Models, Fonts</h1>
    <div class="image-container">
        <img src="..." alt="Failed to load image" class="image">
        <button class="button">Click Me</button>
    </div>
</body>
```

The body contains the content users see:

- `<h1>` defines the page's main heading.
- `<div class="image-container">` groups the image and button into a container.
- `<img>` displays an externally hosted image.
- `<button>` creates a native interactive button.

**Why group the image and button inside a `div`?** The container provides a common parent that can control their overall dimensions and positioning.

The `div` is a generic container. It is useful here because the group does not require a more specific semantic HTML element.

### 4.5 A small accessibility improvement

The current image uses:

```
alt="Failed to load image"
```

This is not ideal because alternative text should describe the image's meaningful content, not merely report a loading failure.

A better version would be:

```
alt="A descriptive view of the image subject"
```

Replace that description with what the actual photograph shows.

If the image is purely decorative and adds no meaningful information, an empty `alt=""` may be more appropriate.

---

## 5. CSS Code: Line-by-Line Explanation

### 5.1 Universal reset

```
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}
```

This affects all elements matched by the universal selector.

The most important declaration for this assignment is `box-sizing: border-box`, because the layout relies on calculated widths and heights.

The other two declarations remove browser-default margins and padding.

**Engineering reasoning:** A consistent starting point makes it easier to reason about layout measurements, although a project may still need deliberate spacing rules later.

### 5.2 Body dimensions

```
body {
    width: 100vw;
    height: 100vh;
}
```

- `100vw` represents the viewport width.
- `100vh` represents the viewport height.

These declarations specify the body's dimensions relative to the viewport.

**Why use viewport units?** They are useful when a task specifies dimensions relative to the visible browser area.

**Important:** Setting a body's height to `100vh` does not force all its contents to fit inside that height. Content can extend beyond it and produce scrolling.

### 5.3 Container styling

```
div.image-container {
    margin: 10vh 25vw;
    width: 50vw;
    height: 50vh;
    border: 1px solid black;
}
```

The selector targets a `div` with the `image-container` class.

The properties work together:

- `margin` establishes vertical and horizontal spacing.
- `width` assigns half the viewport width.
- `height` assigns half the viewport height.
- `border` creates a thin black outline.

**Why use a class?** A class provides a reusable name for a group of elements. You can target `.image-container` without affecting every `div` on the page.

**Why use `div.image-container` rather than just `.image-container`?** Both can select this container. Including `div` makes the selector more specific to that element type, but `.image-container` is often simpler and more reusable when the class itself is sufficient.

### 5.4 Image styling

```
div.image-container img {
    width: 100%;
    height: 85%;
    display: block;
    object-fit: cover;
}
```

The selector targets images inside the designated container.

- `width: 100%` makes the image fill the container's content width.
- `height: 85%` assigns 85% of the containing block's content height.
- `display: block` makes the image participate in block layout.
- `object-fit: cover` fills the image box without distorting the image's aspect ratio, cropping when necessary.

**Why use a descendant selector?** It scopes the styling to images inside this particular container instead of changing every image on the webpage.

### 5.5 Button styling

```
.button {
    width: 100%;
    height: 15%;
    display: block;
    border: 2px solid black;
    background: linear-gradient(
        to right,
        rgb(8, 201, 235),
        rgba(1, 27, 1, 0.877)
    );
    color: white;
    font-size: 2rem;
    font-family: cursive, sans-serif;
    font-weight: 500;
    cursor: pointer;
}
```

This rule controls the button's dimensions, border, background, text, and cursor.

**Why use a class selector?** The `.button` class lets you reuse the same button styling on other buttons without tying the design to the HTML tag name alone.

The gradient makes the background transition from cyan to a dark greenish color. The white text provides a contrasting foreground, while the cursor gives a visual cue that the button is interactive.

### 5.6 Heading styling

```
h1 {
    text-align: center;
    text-decoration: underline;
    display: block;
}
```

The first declaration centers the text, the second underlines it, and the third explicitly sets the display mode.

Since `<h1>` is already block-level by default, `display: block` can be removed without changing the normal layout behavior.

**Why remove redundant declarations?** Less unnecessary CSS makes a stylesheet easier to maintain and helps you understand which rules actually change the design.

---

## 6. Engineering Decisions: Why These Choices?

| Choice                  | Why it is useful                                    | Alternative             |
| ----------------------- | --------------------------------------------------- | ----------------------- |
| External `style.css`    | Separates structure from presentation               | Internal or inline CSS  |
| Class selector          | Reusable and relatively easy to maintain            | ID or type selector     |
| `border-box`            | Includes padding and borders in declared dimensions | Default `content-box`   |
| `vw` and `vh`           | Sizes relative to the viewport                      | `px`, `%`, `rem`        |
| `object-fit: cover`     | Fills the image area without distortion             | `contain`, `fill`       |
| `linear-gradient()`     | Creates a color transition without a separate image | Flat `background-color` |
| `font-family` fallbacks | Improves compatibility across devices               | A single font family    |
| `cursor: pointer`       | Gives a visual interaction cue                      | Default cursor          |

These are design choices, not universal rules. The best option depends on the task's requirements, the content, accessibility, and how the page should behave on different devices.

---

## 7. Common Debugging Questions

### Why is my container not fitting the screen?

Check the combined width and horizontal margins. Here, `50vw + 25vw + 25vw` equals `100vw` mathematically. Unexpected horizontal overflow can still arise from scrollbar behavior or additional content and borders.

### Why is the image cropped?

Because `object-fit: cover` fills the box while preserving the aspect ratio. Switch to `contain` if showing the entire image is more important than filling every part of the box.

### Why is there vertical scrolling?

The heading, top and bottom margins, and container all consume vertical space. A `50vh` container plus `20vh` of vertical margins already uses `70vh`, before accounting for the heading and any other content.

### Why does `2rem` not always look the same on every device?

Its computed size depends on the root font size, and the actual rendered appearance depends on the chosen font and browser rendering.

### Why doesn't the button do anything when clicked?

The current HTML creates a button, and the CSS styles it, but no JavaScript click handler or form action has been specified. Visual styling and functional behavior are separate concerns.

---

## Final Learning Checklist Ask yourself.

Use this checklist to test whether you understand the concepts rather than merely recognizing the code.

- I can explain the purpose of `<!DOCTYPE html>`, `<head>`, and `<body>`.
- I can distinguish HTML elements, attributes, and CSS selectors.
- I can explain why external CSS is useful.
- I can read a CSS rule and identify its selector, property, and value.
- I can explain how the cascade and specificity affect styling.
- I can draw and explain the four layers of the CSS box model.
- I can calculate `vw`, `vh`, `%`, and `rem` values using an example.
- I can explain the difference between margin and padding.
- I can explain what `display: block` changes.
- I can explain the difference between `object-fit: cover` and `object-fit: contain`.
- I can explain why borders affect layout calculations.
- I can read a linear gradient and explain its color stops.
- I can explain `font-size`, `font-family`, and `font-weight`.
- I can distinguish text alignment from element positioning.
- I understand that `cursor: pointer` does not create click functionality.
- I can calculate the total dimensions of the container and identify potential overflow.

---

## Conclusion

This project demonstrates how HTML provides the structure of a webpage while CSS controls its presentation.

The most important lesson is that CSS properties do not work in isolation. The box model affects dimensions, units determine how measurements are calculated, selectors determine which elements receive styles, and the cascade determines which declarations apply.

Understanding these relationships allows you to move beyond copying CSS and begin predicting how a layout will behave.

[Help Youtube Video 01](https://youtu.be/APhPNDikwRE?si=rqwH83lghQf5daAr)

[Help Youtube Video 02 best](https://youtu.be/nkaAJYfRDVk?si=pKE8FRJ_l7J64NZ1)
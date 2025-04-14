# CSS Learning Guide: Beginner to Expert

Welcome to the CSS Learning Guide! This document will help you navigate through the journey of mastering CSS, from the basics to advanced concepts.

## Table of Contents

1. [Introduction to CSS](#introduction-to-css)
2. [CSS Basics](#css-basics)
3. [Intermediate CSS](#intermediate-css)
4. [Advanced CSS](#advanced-css)
5. [Projects](#projects)

---

## Introduction to CSS

### What is CSS?

CSS (Cascading Style Sheets) is used to style and layout web pages — for example, to alter the font, color, size, and spacing of your content, split it into multiple columns, or add animations and other decorative features.

### Importance of CSS in web development.

Below are major benefits of using CSS in web development.

- Enhancing Website Aesthetics
- Easy Updates
- Boosting SEO Through Code Organization
- Responsive Design for Greater Impact
- Helps Websites Load Faster
- Efficiency and Consistency
- Cross-Browser Compatibility
- Engaging User Experience

### How CSS works with HTML.

CSS can be added to HTML documents in 3 ways:

1. Inline - by using the style attribute inside HTML elements.

```html
<h1 style="color:blue;">A Blue Heading</h1>

<p style="color:red;">A red paragraph.</p>
```

2. Internal - by using a `<style>` element in the `<head>` section.

```html
<!DOCTYPE html>
<html>
  <head>
    <style>
      body {
        background-color: powderblue;
      }
      h1 {
        color: blue;
      }
      p {
        color: red;
      }
    </style>
  </head>
  <body>
    <h1>This is a heading</h1>
    <p>This is a paragraph.</p>
  </body>
</html>
```

3. External - by using a `<link>` element to link to an external CSS file.

```html
<!DOCTYPE html>
<html>
  <head>
    <link rel="stylesheet" href="styles.css" />
  </head>
  <body>
    <h1>This is a heading</h1>
    <p>This is a paragraph.</p>
  </body>
</html>
```

```css
styles.css - file body {
  background-color: powderblue;
}
h1 {
  color: blue;
}
p {
  color: red;
}
```

## CSS Basics

### CSS Syntax

```css
selector {
  property: value;
}
```

### CSS Selectors

Selectors are used to target HTML elements that you want to style. Here are some common types:

- **Universal Selector (`*`)**: Targets all elements.
  ```css
  * {
    margin: 0;
    padding: 0;
  }
  ```
- **Element Selector**: Targets all occurrences of a specific HTML element.
  ```css
  p {
    color: blue;
  }
  ```
- **Class Selector (`.`)**: Targets elements with a specific class attribute.
  ```css
  .highlight {
    background-color: yellow;
  }
  ```
- **ID Selector (`#`)**: Targets a specific element with an ID.
  ```css
  #header {
    font-size: 24px;
  }
  ```
- **Group Selector (`A, B`)**: Applies styles to multiple elements.
  ```css
  h1,
  h2,
  h3 {
    font-family: Arial, sans-serif;
  }
  ```
- **Descendant Selector (`A B`)**: Targets elements inside a specific parent element.
  ```css
  div p {
    color: green;
  }
  ```
- **Child Selector (`A > B`)**: Selects only direct children of an element.
  ```css
  div > p {
    font-weight: bold;
  }
  ```
- **Attribute Selector**:
  ```css
  input[type="text"] {
    border: 1px solid black;
  }
  ```

### Colors and Backgrounds

CSS allows you to control the appearance of elements using colors, gradients, and background images.

- Colors
  You can apply colors to text, borders, and backgrounds using different formats:

  - **Named Colors**
    ```css
    color: red;
    background-color: blue;
    ```
  - **Hex Codes**
    ```css
    color: #ff5733;
    background-color: #333;
    ```
  - **RGB and RGBA (RGBA includes transparency)**
    ```css
    color: rgb(255, 87, 51);
    background-color: rgba(0, 0, 255, 0.5); /_ 50% transparent blue _/
    ```
  - **HSL and HSLA (Hue, Saturation, Lightness, Alpha)**

    ```css
    color: hsl(200, 100%, 50%);
    background-color: hsla(120, 60%, 70%, 0.8);
    ```

- Backgrounds

  - **Solid Background Color**
    ```css
    background-color: lightgray;
    ```
  - **Background Image**
    ```css
    background-image: url("image.jpg");
    background-size: cover; /* contain | auto */
    background-position: center; /* top | bottom | left | right | center */
    background-repeat: no-repeat; /* repeat-x | repeat-y | repeat */
    ```
  - **Linear Gradient**
    ```css
    background: linear-gradient(to right, red, blue);
    ```
  - **Radial Gradient**
    ```css
    background: radial-gradient(circle, yellow, green);
    ```

- Additional Background Properties

  - **Fixed Background (Background does not scroll)**
    ```css
    background-attachment: fixed;
    ```
  - **Shorthand for Background Properties**
    ```css
    background: url("image.jpg") no-repeat center/cover;
    ```

### Box Model

Every HTML element is treated as a box. The CSS Box Model defines how the size of an element is calculated, including its content, padding, border, and margin.

#### Box Model Structure

```lua
+-----------------------------+  <-- Margin (space outside the border)
|                             |
|  +-----------------------+  |  <-- Border (element’s boundary)
|  |                       |  |
|  |   +---------------+   |  |  <-- Padding (space between content and border)
|  |   |   Content     |   |  |  <-- Actual content (text, image, etc.)
|  |   +---------------+   |  |
|  |                       |  |
|  +-----------------------+  |
|                             |
+-----------------------------+
```

#### Box Model Components

1. Content: The actual content inside the element (text, images, etc.).
   ```css
   width: 200px;
   height: 150px;
   ```
2. Padding: Space between the content and the border. It increases the size of the element without affecting surrounding elements.
   ```css
   padding: 20px; /_ Applies 20px padding on all sides _/
   padding: 10px 15px; /_ 10px top/bottom, 15px left/right _/
   ```
3. Border: A line that wraps around the padding and content.
   ```css
   border: 2px solid black;
   border-radius: 10px; /_ Rounds the corners _/
   ```
4. Margin: Space outside the border, separating the element from others.
   ```css
   margin: 30px; /_ Adds space around the element _/
   margin: 10px 15px; /_ 10px top/bottom, 15px left/right _/
   ```

#### Box Sizing

By default, an element’s width/height only includes the content area. You can use box-sizing to change this behavior:

- content-box (default): Width and height include only the content. Padding and border are added separately.

- border-box: Width and height include content, padding, and border.
  ```css
  box-sizing: border-box;
  ```

#### Example: Full Box Model

```css
.box {
  width: 200px;
  height: 100px;
  padding: 20px;
  border: 5px solid black;
  margin: 30px;
  box-sizing: border-box;
}
```

### Typography

Typography in CSS controls how text appears on a webpage, including font styles, alignment, and spacing.

#### Fonts

You can specify fonts using built-in system fonts, web-safe fonts, or custom web fonts.

- **Font Family** (Defines the font style)

  ```css
  font-family: Arial, sans-serif;
  ```

  Multiple fonts are listed as fallbacks if the preferred font is unavailable.

- **Font Size** (Adjusts text size)

  ```css
  font-size: 16px; /_ Pixels _/
  font-size: 1.2em; /_ Relative to parent element _/
  font-size: 120%; /_ Relative to default size _/
  ```

- **Font Weight** (Controls thickness)

  ```css
  font-weight: normal; /_ Default weight _/
  font-weight: bold; /_ Bold text _/
  font-weight: 300; /_ Lighter _/
  ```

- **Font Style** (Italic or normal text)

  ```css
  font-style: italic;
  ```

- **Font Variant** (Changes text to small caps)

  ```css
  font-variant: small-caps;
  ```

- **Google Fonts Example** (Using external fonts)

  ```css
  @import url("https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap");

  body {
    font-family: "Roboto", sans-serif;
  }
  ```

#### Text Alignment

Controls how text is positioned within an element.

```css
text-align: left; /_ Aligns text to the left _/
text-align: center; /_ Centers text _/
text-align: right; /_ Aligns text to the right _/
text-align: justify; /_ Stretches text to fill width _/
```

#### Text Transformations

Convert text to uppercase, lowercase, or capitalize each word

```css
text-transform: uppercase; /_ Converts text to UPPERCASE _/
text-transform: lowercase; /_ Converts text to lowercase _/
text-transform: capitalize; /_ Capitalizes the first letter of each word _/
```

#### Text Decoration

Controls the appearance of text decorations like underlines, overlines, and strikethroughs.

```css
text-decoration: underline; /_ Underlines text _/
text-decoration: overline; /_ Adds a line above the text _/
text-decoration: line-through; /_ Strikes through text _/
text-decoration: none; /_ Removes any text decoration _/
```

#### Spacing (Line Height, Letter Spacing, Word Spacing)

- **Line Height** (Spacing between lines)
  ```css
  line-height: 1.5; /_ Increases readability _/
  ```
- **Letter Spacing** (Adjusts space between letters)

  ```css
  letter-spacing: 2px;
  ```

- **Word Spacing** (Adjusts space between words)

  ```css
  word-spacing: 5px;
  ```

#### Text Shadow

Adds a shadow effect to text.

```css
text-shadow: 2px 2px 5px gray; /_ Horizontal offset, vertical offset, blur radius, color _/
```

#### Example: Applying Typography Styles

```css
p {
  font-family: "Georgia", serif;
  font-size: 18px;
  font-weight: bold;
  text-align: justify;
  line-height: 1.6;
  letter-spacing: 1px;
  text-transform: capitalize;
  text-decoration: underline;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
}
```

## Intermediate CSS

### Positioning and Layout

CSS provides several properties to control how elements are arranged and interact with one another in a layout.

#### Positioning

1. **Static** (Default)
   ```css
   position: static;
   ```

- Elements follow the normal document flow.

- Cannot be offset using top, right, bottom, or left.

2. **Relative**
   ```css
   position: relative;
   top: 10px;
   left: 20px;
   ```

- Keeps its original space but moves visually based on the offsets.

3. **Absolute**
   ```css
   position: absolute;
   top: 0;
   left: 0;
   ```

- Removed from document flow.

- Positioned relative to the nearest non-static ancestor or the <html> element if none.

4. **Fixed**
   ```css
   position: fixed;
   bottom: 0;
   right: 0;
   ```

- Positioned relative to the viewport.

- Stays in place during scrolling.

5. **Sticky**
   ```css
   position: sticky;
   top: 0;
   ```

- Behaves like relative until a scroll threshold, then becomes fixed.

> In CSS, sticky positioning allows an element to scroll with the page until it reaches a defined offset, after which it "sticks" in place within its parent container—ideal for headers or section labels. In contrast, fixed positioning keeps an element locked to a specific spot on the screen regardless of scrolling, making it useful for persistent elements like nav bars or floating buttons. The key difference is that sticky is scroll-aware and constrained by its container, while fixed is always attached to the viewport.

#### Display

The display property determines how an element is rendered in the document flow.

```css
display: block; /_ Default for div, takes full width _/
display: inline; /_ Sits in line, no width/height control _/
display: inline-block; /_ Like inline but allows box styling _/
display: none; /_ Hides the element completely _/
display: flex; /_ Enables flexbox layout _/
display: grid; /_ Enables grid layout _/
```

- Block elements stack vertically.

- Inline elements flow horizontally.

- Inline-block combines inline flow with block features.

#### Float

Float allows elements (typically images or boxes) to be taken out of the normal flow and aligned to the left or right.

```css
float: left;
float: right;
```

- Other content will flow around the floated element.

- Floats are commonly used in traditional multi-column layouts.

**Example:**

```css
img {
  float: left;
  margin-right: 10px;
}
```

#### Clear

The clear property prevents elements from wrapping around floated elements.

```css
clear: left; /_ Clears left-floated elements _/
clear: right; /_ Clears right-floated elements _/
clear: both; /_ Clears both left and right floats _/
```

**Example:**

```css
.clearfix {
  clear: both;
}
```

### **Flexbox**: Building responsive layouts.

Flexbox (Flexible Box Layout) is a one-dimensional layout model in CSS that makes it easier to design flexible and responsive layout structures. It helps distribute space within a container, even when the size of its children is unknown or dynamic.

Flexbox works along two axes:

**Main axis** – defined by flex-direction

**Cross axis** – perpendicular to the main axis

To use Flexbox, set the container’s display property to flex or inline-flex.

```css
.container {
  display: flex;
}
```

#### Container Properties

1. **flex-direction:** Defines the direction of the main axis (i.e., how flex items are placed in the flex container).

   ```css
   flex-direction: row | row-reverse | column | column-reverse;
   ```

   **row (default):** left to right (horizontal)

   **row-reverse:** right to left

   **column:** top to bottom (vertical)

   **column-reverse:** bottom to top

2. **flex-wrap:** Controls whether flex items wrap when there isn't enough space.

   ```css
   flex-wrap: nowrap | wrap | wrap-reverse;
   ```

   **nowrap (default):** All items stay on one line

   **wrap:** Items wrap onto multiple lines

   **wrap-reverse:** Items wrap in reverse order

3. **flex-flow:** A shorthand for flex-direction and flex-wrap.

   ```css
   flex-flow: row wrap;
   ```

4. **justify-content:** Aligns items along the main axis.

   ```css
   justify-content: flex-start | flex-end | center | space-between |
     space-around | space-evenly;
   ```

   **flex-start:** Align items to the start

   **flex-end:** Align items to the end

   **center:** Center items

   **space-between:** Evenly distributes items, first at start and last at end

   **space-around:** Even spacing around items

   **space-evenly:** Equal space between and around items

5. **align-items:** Aligns items along the cross axis.

   ```css
   align-items: flex-start | flex-end | center | baseline | stretch;
   ```

   **flex-start:** Align items to the start of the cross axis

   **flex-end:** Align to the end

   **center:** Center items vertically

   **baseline:** Align items by text baseline

   **stretch:** Stretch to fill container (default)

6. **align-content:** Aligns multiple lines of content along the cross axis (only applies when items wrap).

   ```css
   align-content: flex-start | flex-end | center | space-between | space-around
     | stretch;
   ```

#### Item Properties (Flex Items)

1. **order:** Controls the order of items.

   ```css
   .item {
     order: 2;
   }
   ```

   Lower values appear first

   Default is 0

2. **flex-grow:** Defines how much a flex item can grow relative to others.

   ```css
   .item {
     flex-grow: 1;
   }
   ```

   A value of 1 makes the item grow to fill available space

   If all items have flex-grow: 1, space is shared equally

3. **flex-shrink:** Defines how much a flex item can shrink when space is tight.

   ```css
   .item {
     flex-shrink: 1;
   }
   ```

   Default is 1 (items can shrink)

   Set to 0 to prevent shrinking

4. **flex-basis:** Sets the initial size of an item before flex-grow and flex-shrink are applied.

   ```css
   .item {
     flex-basis: 200px;
   }
   ```

   Can be a length or percentage

   Overrides the item’s width or height

5. **flex:** A shorthand for flex-grow, flex-shrink, and flex-basis.

   ```css
   .item {
     flex: 1 1 200px;
   }
   ```

   Common short forms: flex: 1 (grow only), flex: 0 0 auto

6. **align-self** Overrides align-items for individual flex items.

   ```css
   .item {
     align-self: center;
   }
   ```

   Same values as align-items

#### Example: Basic Flex Layout

```css
.container {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
}
.item {
  flex: 1;
  padding: 10px;
}
```

#### Why Use Flexbox?

- Easily aligns items both horizontally and vertically

- Automatically adjusts layout to fit various screen sizes

- Great for components like navbars, cards, grids, and more

### Grid

CSS Grid Layout is a powerful system for creating two-dimensional layouts on the web. Unlike Flexbox (which handles layout in one direction at a time—row or column), Grid allows for both rows and columns simultaneously, making it ideal for complex designs like galleries, dashboards, and application layouts.

#### Basic Setup

To use CSS Grid, define a container with `display: grid`:

```css
.container {
  display: grid;
}
```

This turns all direct children into grid items.

#### Core Properties

#### Container Properties (Grid Parent)

1. **grid-template-columns / grid-template-rows:** Defines the structure of columns and rows using lengths (px, %, fr, auto).

   ```css
   grid-template-columns: 1fr 2fr 1fr;
   grid-template-rows: 100px auto;
   ```

   fr unit distributes available space proportionally.

   auto fits content size.

2. **gap / row-gap / column-gap:** Defines space between grid items.

   ```css
   gap: 20px; /_ Applies to both rows and columns _/
   row-gap: 10px;
   column-gap: 15px;
   ```

3. **grid-template-areas:** Creates named areas to make layout more readable.

   ```css
   grid-template-areas:
     "header header"
     "sidebar content"
     "footer footer";
   ```

   Use grid-area in child items to assign them.

4. **grid-auto-rows / grid-auto-columns:** Sets the size for implicitly created rows/columns (if you add more items than defined).

   ```css
   grid-auto-rows: 100px;
   grid-auto-columns: 1fr;
   ```

5. **grid-auto-flow:** Controls how items are placed when you don’t manually position them.

   ```css
   grid-auto-flow: row; /_ default _/
   grid-auto-flow: column; /_ places items by column _/
   grid-auto-flow: dense; /_ fills in holes in the grid _/
   ```

#### Item Properties (Grid Children)

1. **grid-column / grid-row:** Controls where an item starts and ends.

   ```css
   grid-column: 1 / 3; /_ Spans from column line 1 to 3 _/
   grid-row: 2 / 4;
   ```

2. **grid-column-start, grid-column-end:** More explicit version of the shorthand:

   ```css
   grid-column-start: 1;
   grid-column-end: 4;
   ```

3. **grid-row-start, grid-row-end:** Same concept as above but for rows.

   ```css
   grid-row-start: 1;
   grid-row-end: 4;
   ```

4. **grid-area:** Can either name an area from grid-template-areas or define all four line values:

   ```css
   grid-area: header; /_ Matches template name _/
   grid-area: 2 / 1 / 3 / 4; /_ row-start / col-start / row-end / col-end _/
   ```

5. **justify-self:** Aligns individual items horizontally in a cell.

   ```css
   justify-self: start | end | center | stretch;
   ```

6. **align-self:** Aligns individual items vertically in a cell.

   ```css
   align-self: start | end | center | stretch;
   ```

#### Container Alignment

- **justify-items** – horizontal alignment of all items in cells.

- **align-items** – vertical alignment of all items in cells.

- **justify-content** – alignment of entire grid within the container.

- **align-content** – vertical alignment of entire grid within the container.

  ```css
  justify-items: center;
  align-items: stretch;

  justify-content: space-between;
  align-content: center;
  ```

#### Example Grid Layout

```css
.container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: auto 200px;
  gap: 20px;
}
.item1 {
  grid-column: 1 / 3;
}
.item2 {
  grid-column: 3 / 4;
}
```

#### Responsive Grids

CSS Grid pairs well with media queries to build adaptive layouts:

```css
@media (max-width: 768px) {
.container {
grid-template-columns: 1fr; /_ stack items vertically _/
}
}
```

#### When to Use Grid

- Designing complete page layouts
- Creating complex, structured arrangements
- Aligning elements in both rows and columns
- Replacing older table-based or float-based layouts

### Transitions and Animations

#### CSS Transitions – Properties

CSS Transitions allow elements to change property values smoothly (over a duration) rather than instantly. You define which properties to animate and how they behave during the transition.

1. **transition-property:** Specifies the CSS property that will be transitioned.

   ```css
   transition-property: background-color, transform;
   ```

   Can specify one or more properties.

   Use all to transition every animatable property.

2. **transition-duration:** Defines how long the transition takes.

   ```css
   transition-duration: 0.5s; /_ or 500ms _/
   ```

   Accepts time values (s or ms).

   You can specify multiple durations if transitioning multiple properties.

3. **transition-timing-function:** Describes how the speed of the transition progresses.

   ```css
   transition-timing-function: ease-in-out;
   ```

   Common values:

   **linear:** constant speed

   **ease:** starts slow, then fast, then slow

   **ease-in:** starts slow

   **ease-out:** ends slow

   **ease-in-out:** slow start and end

   **cubic-bezier(x1, y1, x2, y2):** custom acceleration curve

4. **transition-delay:** Delays the start of the transition by a specified time.

   ```css
   transition-delay: 0.2s;
   ```

5. **transition (shorthand):** Combines all transition properties into one line.

   ```css
   transition: background-color 0.5s ease-in-out 0.2s;
   ```

   Order: property duration timing-function delay

#### CSS Animations – Properties

CSS Animations are more complex than transitions and involve defining keyframes to describe styles at various points during the animation.

1. **animation-name:** Specifies the name of the @keyframes rule to apply.

   ```css
   animation-name: slideIn;
   ```

2. **animation-duration:** Specifies how long one cycle of the animation takes.

   ```css
   animation-duration: 1s;
   ```

3. **animation-timing-function:** Defines the pacing of the animation, same options as transition-timing-function.

   ```css
   animation-timing-function: ease-in-out;
   ```

4. **animation-delay:** Sets a delay before the animation starts.

   ```css
   animation-delay: 0.3s;
   ```

5. **animation-iteration-count:** Specifies how many times the animation should repeat.

   ```css
   animation-iteration-count: infinite; /_ or a number like 3 _/
   ```

6. **animation-direction:** Controls whether the animation plays forward, backward, or alternates.

   ```css
   animation-direction: alternate;
   ```

   **Options:**

   normal (default)

   reverse

   alternate (forward then backward)

   alternate-reverse

7. **animation-fill-mode:** Determines how styles are applied before and after animation.

   ```css
   animation-fill-mode: forwards;
   ```

   **Options:**

   none (default)

   forwards: keeps end style

   backwards: applies initial style during delay

   both: applies both forwards and backwards rules

8. **animation-play-state:** Allows you to pause or resume an animation.

   ```css
   animation-play-state: paused; /_ or running _/
   ```

9. **animation (shorthand):** A shorthand to set all animation properties in one line.

   ```css
   animation: slideIn 2s ease-in-out 0.5s infinite alternate forwards;
   ```

   Order: name duration timing-function delay iteration-count direction fill-mode

## Advanced CSS

### Responsive Design

Responsive design ensures your website looks and works great on all devices — from small smartphones to large desktop monitors. This is achieved using flexible layouts, scalable images, and media queries, which allow you to apply different styles depending on screen size, resolution, or other device characteristics.

#### Media Queries – What Are They?

Media queries are CSS techniques that apply styles conditionally, based on features of the user's device (like screen width, height, resolution, orientation, etc.).

##### Basic Syntax:

```css
@media media-type and (condition) {
/_ CSS rules _/
}
```

##### Example:

```css
@media screen and (max-width: 768px) {
  body {
    background-color: lightgray;
  }
}
```

This code applies the style only when the screen width is 768px or less.

Common Media Query Features and Attributes
Here are the most commonly used attributes and their meanings:

1. **min-width:** Applies styles if screen width is greater than or equal to the value.
2. **max-width:** Applies styles if screen width is less than or equal to the value.
3. **min-height:** Checks if the height is at least the given value.
4. **max-height:** Checks if the height is at most the given value.
5. **orientation:** portrait or landscape. Useful for tablets and phones.
6. **aspect-ratio:** Width-to-height ratio of the viewport (e.g. 16/9).
7. **resolution** Used for high-resolution screens (dpi or dppx).
8. **hover, pointer:** Detects input capabilities (like if a mouse or touchscreen is being used).

##### Examples

**Responsive Layouts**

```css
/_ Base (mobile-first) _/ .container {
  display: block;
}

/_ Tablet and up _/ @media (min-width: 768px) {
  .container {
    display: flex;
  }
}

/_ Desktop and up _/ @media (min-width: 1024px) {
  .container {
    justify-content: space-between;
  }
}
```

**Orientation Example**

```css
@media (orientation: landscape) {
  .gallery {
    grid-template-columns: repeat(4, 1fr);
  }
}
```

### Mobile-First Design

Mobile-first means you design and style your site for small screens first, then use media queries to enhance the experience for larger devices.

- You write base CSS for mobile (smallest screen).
- Then you add styles for larger screens with min-width media queries.

Why it's better:

- Mobile users are the majority.
- Forces you to prioritize essential content.
- Results in faster-loading pages on mobile.

**Example Flow:**

```css
/_ Mobile first _/ body {
  font-size: 16px;
}

/_ Tablets and above _/ @media (min-width: 768px) {
  body {
    font-size: 18px;
  }
}

/_ Desktops and above _/ @media (min-width: 1024px) {
  body {
    font-size: 20px;
  }
}
```

#### Best Practices

- Use relative units like `%`, `em`, `rem`, `vw`, `vh` instead of `px` where possible.
- Combine media queries with flexbox or CSS grid for powerful layouts.
- Optimize touch targets (buttons, links) for smaller screens.
- Use responsive images (via `srcset` or CSS) to improve performance.

### CSS Variables

CSS variables allow you to store values in one place and reuse them throughout your stylesheet. This makes your code easier to manage, especially when working with themes, colors, spacing, fonts, and more.

#### Declaring a Variable

CSS variables are declared using a double hyphen (--) and are typically defined inside a :root selector so they apply globally.

```css
:root {
  --main-color: #3498db;
  --padding: 16px;
  --font-stack: "Segoe UI", sans-serif;
}
```

- `:root` is a pseudo-class that represents the top-level element (`<html>`).
- Variable names are case-sensitive.

#### Using Variables

You use the `var()` function to insert the value of a variable.

```css
body {
  font-family: var(--font-stack);
  color: var(--main-color);
  padding: var(--padding);
}
```

#### Providing Fallback Values

You can provide a fallback if the variable isn’t defined.

```css
color: var(--secondary-color, #333); /_ Uses #333 if --secondary-color is missing _/
```

#### Scoped Variables

You can define variables locally within a specific selector. These will override global ones inside that scope.

```css
.card {
  --main-color: tomato;
  border: 2px solid var(--main-color);
}
```

#### Changing Variables Dynamically

One powerful feature of CSS variables is that they can be changed with JavaScript or via classes, enabling themes and dynamic styling.

**Example: Theming**

```css
:root {
  --bg: white;
  --text: black;
}

.dark-theme {
  --bg: black;
  --text: white;
}

body {
  background-color: var(--bg);
  color: var(--text);
}
```

Apply the `.dark-theme` class to `<body>` to switch the theme.

#### Benefits of Using CSS Variables

- Centralized control over styles.
- Easier to maintain and update.
- Enables theming and responsive design.
- Works with JavaScript for dynamic styling.
- Reduces repetition and errors.

## Notes

- CSS variables do not work in media queries or some older browsers like IE11.
- They differ from Sass variables, which are preprocessed and don’t live in the DOM.

**Real Example**

```css
:root {
  --primary-color: #007bff;
  --secondary-color: #6c757d;
  --font-size: 16px;
}

h1 {
  color: var(--primary-color);
  font-size: calc(var(--font-size) \* 2);
}

button {
  background-color: var(--secondary-color);
  padding: var(--font-size);
}
```

### Preprocessors

CSS Preprocessors are scripting languages that extend CSS by adding logic and functionality that regular CSS lacks. They are compiled into standard CSS before being used in the browser.

The two most popular are:

- SASS (Syntactically Awesome Style Sheets)
- LESS (Leaner Style Sheets)

**Why Use a Preprocessor?**

- Use variables for colors, spacing, fonts, etc.
- Nesting to mirror HTML structure.
- Mixins to reuse blocks of code.
- Functions and operations for calculations.
- Modularize code with partials and imports.

#### SASS (SCSS Syntax)

SASS has two syntaxes:

- `.scss` (most common, CSS-like with semicolons & braces)
- `.sass` (indentation-based, no braces or semicolons)

##### Basic Features in SASS (SCSS)

1.  **Variables**

    ```scss
    $primary-color: #3498db;
    $padding: 16px;

    body {
      background-color: $primary-color;
      padding: $padding;
    }
    ```

2.  **Nesting**

    ```scss
    nav {
      ul {
        list-style: none;

        li {
          display: inline-block;
        }
      }
    }
    ```

3.  **Mixins**

    ```scss
    @mixin flex-center {
      display: flex;
      justify-content: center;
      align-items: center;
    }

    .container {
      @include flex-center;
    }
    ```

4.  **Partials and Imports:** Split your CSS into files and import them:

    ```scss
    // \_buttons.scss
    .button {
      padding: 10px;
    }

    // main.scss
    @import "buttons";
    ```

    SASS now prefers `@use` and `@forward` over `@import`.

5.  **Operators & Functions**

    ```scss
    .container {
      width: 100% / 3;
    }

    $font-size: 16px;
    h1 {
      font-size: $font-size \* 2;
    }
    ```

#### LESS

LESS is very similar to SASS and has almost identical features.

##### Basic Features in LESS

1. **Variables**

   ```less
   @main-color: #2ecc71;

   body {
     color: @main-color;
   }
   ```

2. **Nesting**
   ```less
   nav {
     ul {
       margin: 0;
       li {
         display: inline;
       }
     }
   }
   ```
3. **Mixins**

   ```less
   .flex-center() {
     display: flex;
     justify-content: center;
     align-items: center;
   }

   .container {
     .flex-center();
   }
   ```

4. **Functions and Operations**
   ```less
   @width: 10%;
   .sidebar {
     width: @width \* 2;
   }
   ```

#### SASS vs LESS – Key Differences

| Feature           | SASS (.scss)       | LESS             |
| ----------------- | ------------------ | ---------------- |
| Syntax            | SCSS / SASS        | LESS             |
| Variables         | $variable          | @variable        |
| Compilation       | Dart Sass (modern) | Node.js based    |
| Popularity        | Very high          | Moderate         |
| Advanced Features | More extensive     | Slightly limited |

#### How to Use

SASS: Install via npm or use tools like VS Code extensions, Webpack, or CLI:

```bash
npm install -g sass
sass style.scss style.css
```

LESS:

```bash
npm install -g less
lessc style.less style.css
```

Or use online compilers like SassMeister or LESS2CSS.

### Performance Optimization

Efficient CSS helps reduce render time, improves page speed, and ensures maintainability across large projects. Below are key strategies and examples to write high-performance CSS:

1. **Use Specific and Minimal Selectors:** Avoid overly complex selectors that make the browser work harder to match elements.

   **Good:**

   ```css
   .button {
     color: white;
   }
   ```

   **Inefficient:**

   ```css
   body div.container ul li a.button {
     color: white;
   }
   ```

   Deeply nested selectors increase specificity and reduce performance. Stick to classes or IDs where possible.

2. **Avoid Universal Selectors and Heavy Combinators:** Universal (\*) and complex combinators like descendant (A B) can be expensive in large DOMs.

   **Inefficient:**

   ```css
   * {
     margin: 0;
   }
   div ul li a {
     font-size: 14px;
   }
   ```

   **Better:**

   ```css
   body {
     margin: 0;
   }
   .nav-link {
     font-size: 14px;
   }
   ```

3. **Minify Your CSS:** Minified CSS reduces file size by removing spaces, comments, and unnecessary characters.

   **Before:**

   ```css
   body {
     background-color: #fff;
     color: #000;
   }
   ```

   **After (minified):**

   ```css
   body {
     background-color: #fff;
     color: #000;
   }
   ```

   Use tools like:

   - cssnano
   - clean-css

4. **Avoid `!important` Overuse:** `!important` breaks CSS’s natural cascading rules, making debugging hard and increasing specificity unnecessarily.

   **Avoid:**

   ```css
   .button {
     color: red !important;
   }
   ```

   **Prefer:**

   ```css
   .btn-danger {
     color: red;
   }
   ```

5. **Modularize and Organize CSS:** Split CSS into modular files using preprocessors or component-based structures.

- Use partials in SASS (\_buttons.scss, \_layout.scss)
- Use component-specific styles in modern frameworks

  This improves maintainability and reduces unnecessary code.

6. **Remove Unused CSS:** Use tools to detect and remove CSS not being used in your HTML.

- PurgeCSS
- UnCSS
- Chrome DevTools > Coverage Tab

  This reduces your CSS bundle size drastically.

7. **Use Shorthand Properties:** Shorthand properties reduce file size and increase readability.

   **Use:**

   ```css
   margin: 10px 20px;
   border: 1px solid #000;
   ```

   **Instead of:**

   ```css
   margin-top: 10px;
   margin-right: 20px;
   margin-bottom: 10px;
   margin-left: 20px;
   border-width: 1px;
   border-style: solid;
   border-color: #000;
   ```

8. **Use Variables for Reusability:** Use CSS variables (or SASS variables) to avoid repetition and speed up updates.

   ```css
   :root {
     --primary: #3498db;
   }

   .button {
     background-color: var(--primary);
   }
   ```

9. **Leverage CSS Logical Properties:** For responsive, RTL-friendly designs, use logical properties.

   **Better:**

   ```css
   padding-inline: 1rem;
   margin-block: 2rem;
   ```

10. **Use DevTools to Audit Performance:** Chrome’s Performance and Lighthouse tabs

- Firefox’s Layout and Inspector tools
- These tools can help spot paint issues, layout thrashing, and unused styles.

#### Summary

Efficient CSS is clean, minimal, modular, and purposeful. You should:

- Use short, specific selectors
- Minify and modularize your code
- Remove unused styles
- Avoid !important
- Use shorthand and variables
- Audit regularly with dev tools

### CSS Frameworks

A CSS Framework is a pre-prepared library that makes styling easier and faster by providing ready-to-use styles, components, and utilities. They help in building responsive, maintainable, and consistent designs without writing every style from scratch.

#### Bootstrap (by Twitter)

##### Overview

Bootstrap is a component-based CSS + JS framework that follows a mobile-first, responsive grid system. It provides predefined classes for layout, typography, buttons, forms, modals, and more.

##### Key Features

- Responsive 12-column grid
- Prebuilt components (navbars, modals, cards, alerts, etc.)
- Utility classes (margins, padding, display, etc.)
- JavaScript plugins (tooltips, popovers, carousels)
- Customizable via Sass variables

##### Layout & Grid

```html
<div class="container">
  <div class="row">
    <div class="col-md-6">Column 1</div>
    <div class="col-md-6">Column 2</div>
  </div>
</div>
```

- `.container` / `.container-fluid` for layout containers
- `.row` to create rows
- `.col-\*` for responsive columns (`col-6`, `col-sm-4`, `col-lg-8`)

##### Utilities (selected)

| Property | Class Example               | Description                 |
| -------- | --------------------------- | --------------------------- |
| Margin   | `mt-3`, `mb-2`              | Top, bottom margin spacing  |
| Padding  | `px-4`, `py-1`              | Horizontal/vertical padding |
| Text     | `text-center`, `text-muted` | Text alignment, muted text  |
| Display  | `d-flex`, `d-none`          | Display utilities           |
| Colors   | `bg-primary`, `text-danger` | Background and text colors  |
| Buttons  | `btn`, `btn-primary`        | Styled buttons              |

##### Components

**Buttons:**

```html
<button class="btn btn-success">Save</button>
```

**Alerts:**

```html
<div class="alert alert-warning">Be careful!</div>
```

**Navbar:**

```html
<nav class="navbar navbar-expand-lg navbar-light bg-light">...</nav>
```

**Cards:**

```html
<div class="card">
  <div class="card-body">Card content</div>
</div>
```

#### Tailwind CSS

##### Overview

Tailwind is a utility-first CSS framework. Unlike Bootstrap, it doesn't give you components out of the box but provides low-level utility classes that let you build custom designs faster and more efficiently.

##### Key Features

- Utility-first approach
- Mobile-first responsive classes
- Customizable via tailwind.config.js
- Built-in dark mode support
- Supports JIT (Just-in-Time) compilation for fast builds

##### Example Usage

```html
<div class="flex justify-between items-center p-4 bg-blue-500 text-white">
  <h1 class="text-xl font-bold">Hello</h1>
  <button class="bg-white text-blue-500 px-4 py-2 rounded">Click</button>
</div>
```

##### Common Tailwind Utility Categories

| Category    | Examples                                   | Description                        |
| ----------- | ------------------------------------------ | ---------------------------------- |
| Layout      | `container`, `flex`, `grid`, `w-full`      | Layout and box sizing              |
| Spacing     | `m-4`, `p-2`, `mt-6`, `gap-4`              | Margin, padding, gaps              |
| Typography  | `text-lg`, `font-semibold`, `leading-snug` | Font styles, weights, line heights |
| Colors      | `bg-red-500`, `text-gray-700`              | Text and background colors         |
| Borders     | `border`, `border-gray-200`, `rounded-lg`  | Border styles and radius           |
| Effects     | `shadow-lg`, `opacity-75`                  | Box shadows, opacity               |
| Transitions | `transition`, `duration-300`, `ease-in`    | Smooth transitions                 |
| Responsive  | `md:flex`, `lg:hidden`                     | Responsive control by screen size  |

##### Responsive & Dark Mode

Tailwind encourages mobile-first design:

```html
<p class="text-sm md:text-lg lg:text-xl">Responsive Text</p>
```

##### Built-in dark mode:

```html
<div class="bg-white dark:bg-black text-black dark:text-white">Content</div>
```

##### Configuration File (tailwind.config.js)

Tailwind is fully customizable:

```js
module.exports = {
  theme: {
    extend: {
      colors: {
        brand: "#1DA1F2",
      },
    },
  },
  darkMode: "class",
};
```

#### Bootstrap vs Tailwind CSS

| Feature       | Bootstrap                          | Tailwind CSS                 |
| ------------- | ---------------------------------- | ---------------------------- |
| Approach      | Component-based                    | Utility-first                |
| Learning      | Curve Easier for beginners         | More flexible, steeper curve |
| Customization | Requires overriding CSS            | Highly customizable          |
| File Size     | Bigger out of the box              | Smaller with JIT and purge   |
| Popular       | Use Quick prototypes, admin panels | Design systems, modern UIs   |

#### Other CSS Frameworks to Know

- **Foundation** – Responsive front-end framework by Zurb.
- **Bulma** – Pure CSS framework based on Flexbox.
- **Materialize** – Based on Google's Material Design.
- **UIkit** – Lightweight and modular CSS + JS framework.

## Projects

### Beginner Projects

- [Personal Portfolio Page](../CSS/Projects/PersonalPortfolio/)
- [Login Page](../CSS/Projects/LoginPage/)
- Basic Landing Page
- [CSS Cards](../CSS/Projects/FashCards/)
- [Hamburger Menu](../CSS/Projects/HamburgerMenu/)
- Pricing Table
- Popup Menu
- CSS Image Slider

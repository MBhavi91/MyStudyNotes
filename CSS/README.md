# CSS Learning Guide: Beginner to Expert

Welcome to the CSS Learning Guide! This document will help you navigate through the journey of mastering CSS, from the basics to advanced concepts.

## Table of Contents

1. [Introduction to CSS](#introduction-to-css)
2. [CSS Basics](#css-basics)
3. [Intermediate CSS](#intermediate-css)
4. [Advanced CSS](#advanced-css)
5. [Projects](#projects)
6. [Resources](#resources)

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

### Typography: Fonts, text alignment, and spacing.

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
      @import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

      body {
      font-family: 'Roboto', sans-serif;
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

- **Positioning**: Static, relative, absolute, fixed, and sticky.
- **Flexbox**: Building responsive layouts.
- **Grid**: Advanced layout techniques.
- **Transitions and Animations**: Adding interactivity.

## Advanced CSS

- **Responsive Design**: Media queries and mobile-first design.
- **CSS Variables**: Reusable and maintainable styles.
- **Preprocessors**: Introduction to SASS/LESS.
- **CSS Frameworks**: Overview of Bootstrap, Tailwind, etc.
- **Performance Optimization**: Writing efficient CSS.

## Projects

### Beginner Projects

- Personal Portfolio Page – Show your skills, about section, and a contact form.
- Basic Landing Page – A simple webpage with a heading, paragraph, and an image.
- CSS Cards – Create beautiful cards using box-shadow, border-radius, and padding.
- Simple Navigation Bar – Build a horizontal navigation bar with hover effects.
- Pricing Table – Create a simple pricing table using CSS Grid or Flexbox.

## Resources

- [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/CSS)
- [CSS Tricks](https://css-tricks.com/)
- [FreeCodeCamp CSS Tutorials](https://www.freecodecamp.org/)
- [Can I Use](https://caniuse.com/)

Happy learning!

# HTML Tag Reference

## What is HTML?

HTML (HyperText Markup Language) is the standard language used to create web pages. It provides the structure of a webpage by using elements called tags. These tags tell a web browser how to display content such as text, images, links, and more.

## Key Features of HTML

✔ **Markup Language** – Uses tags (<tag>) to define elements on a page.<br>
✔ **Not a Programming Language** – It structures content but doesn’t have logic like JavaScript.<br>
✔ **Works with CSS & JavaScript** – HTML for structure, CSS for styling, JavaScript for interactivity.<br>
✔ **Platform Independent** – Works on all devices and browsers.
<br>

Below is a comprehensive list of all HTML tags grouped by category, along with their usage and examples.

## Basic Structure

| Tag          | Description                       |
| ------------ | --------------------------------- |
| `<!DOCTYPE>` | Declares the document type        |
| `<html>`     | Root element of the HTML document |
| `<head>`     | Metadata container                |
| `<title>`    | Sets the page title               |
| `<body>`     | Main content of the document      |

```
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Document Title</title>
    <meta charset="UTF-8">
</head>
<body>
    <p>This is the body content.</p>
</body>
</html>
```

## Head Elements

| Tag                                                                      | Description                     |
| ------------------------------------------------------------------------ | ------------------------------- |
| `<meta>`                                                                 | Metadata                        |
| `<meta charset="UTF-8">`                                                 | Defines the character encoding. |
| `<meta name="viewport" content="width=device-width, initial-scale=1.0">` | Responsive design.              |
| `<link>`                                                                 | External resource               |
| `<style>`                                                                | Internal CSS                    |
| `<script>`                                                               | Embeds JavaScript               |
| `<base>`                                                                 | Base URL for links              |

```
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="styles.css">
    <style>
        body { font-family: Arial, sans-serif; }
    </style>
    <script>
        console.log("Hello, World!");
    </script>
    <base href="https://example.com/">
</head>
```

## Sectioning Tags

| Tag         | Description                     |
| ----------- | ------------------------------- |
| `<header>`  | Introductory content            |
| `<nav>`     | Navigation links                |
| `<main>`    | Main content                    |
| `<section>` | Thematic content                |
| `<article>` | Self-contained content          |
| `<aside>`   | Content aside from main content |
| `<footer>`  | Footer content                  |

```
<header>
    <h1>Website Header</h1>
</header>

<nav>
    <a href="/home">Home</a>
    <a href="/about">About</a>
</nav>

<main>
    <section>
        <h2>Welcome to My Page</h2>
        <p>Enjoy your stay!</p>
    </section>
    <article>
        <h3>Latest Blog Post</h3>
        <p>This is a sample blog post.</p>
    </article>
    <aside>
        <p>Related Articles</p>
    </aside>
</main>

<footer>
    <p>Copyright © 2025</p>
</footer>
```

## Text Content

| Tag            | Description              |
| -------------- | ------------------------ |
| `<h1>–<h6>`    | Headings (levels 1 to 6) |
| `<p>`          | Paragraph                |
| `<br>`         | Line break               |
| `<hr>`         | Horizontal rule          |
| `<pre>`        | Preformatted text        |
| `<blockquote>` | Block quotation          |
| `<cite>`       | Citation                 |
| `<b>`          | Bold text                |
| `<strong>`     | Strong importance        |
| `<i>`          | Italics                  |
| `<em>`         | Emphasis                 |
| `<small>`      | Small text               |
| `<mark>`       | Highlighted text         |
| `<del>`        | Deleted text             |
| `<ins>`        | Inserted text            |
| `<code>`       | Inline code              |
| `<kbd>`        | User input               |
| `<sub>`        | Subscript text           |
| `<sup>`        | Superscript text         |

```
<h1>Main Heading</h1>
<h2>Subheading</h2>

<p>This is a paragraph with <strong>bold</strong> and <em>italic</em> text.</p>

<blockquote>This is a blockquote.</blockquote>
<cite>— Author Name</cite>

<pre>
    Code snippet:
    print("Hello, World!")
</pre>

<code>let x = 10;</code>

<p>Water formula: H<sub>2</sub>O</p>
<p>Square: x<sup>2</sup></p>
```

## List Tags

| Tag    | Description      |
| ------ | ---------------- |
| `<ul>` | Unordered list   |
| `<ol>` | Ordered list     |
| `<li>` | List item        |
| `<dl>` | Description list |
| `<dt>` | Term             |
| `<dd>` | Description      |

```
<ul>
    <li>Item 1</li>
    <li>Item 2</li>
</ul>

<ol>
    <li>First Step</li>
    <li>Second Step</li>
</ol>

<dl>
    <dt>HTML</dt>
    <dd>HyperText Markup Language</dd>
</dl>
```

## Linking and Media

| Tag        | Description        |
| ---------- | ------------------ |
| `<a>`      | Hyperlink          |
| `<img>`    | Image              |
| `<figure>` | Image with caption |
| `<video>`  | Video content      |
| `<audio>`  | Audio content      |
| `<source>` | Media source       |
| `<track>`  | Text tracks        |

```
<a href="https://example.com" target="_blank">Visit Example</a>

<img src="image.jpg" alt="Sample Image">

<figure>
    <img src="image.jpg" alt="Example Image">
    <figcaption>Image Caption</figcaption>
</figure>

<video controls width="400">
    <source src="video.mp4" type="video/mp4">
</video>

<audio controls>
    <source src="audio.mp3" type="audio/mpeg">
</audio>
```

## Canvas and SVG

| Tag        | Usage                                 |
| ---------- | ------------------------------------- |
| `<canvas>` | Used for drawing graphics on the fly. |
| `<svg>`    | Scalable Vector Graphics container.   |
| `<circle>` | Draws circles in SVG.                 |
| `<rect>`   | Draws rectangles in SVG.              |

```
<canvas id="myCanvas" width="400" height="200" style="border:1px solid #000;"></canvas>
<script>
  const canvas = document.getElementById('myCanvas');
  const ctx = canvas.getContext('2d');
  ctx.fillStyle = 'blue';
  ctx.fillRect(20, 20, 150, 100);
</script>
```

## Table Tags

| Tag         | Description     |
| ----------- | --------------- |
| `<table>`   | Table           |
| `<tr>`      | Table row       |
| `<td>`      | Table cell      |
| `<th>`      | Header cell     |
| `<caption>` | Table caption   |
| `rowspan`   | Merges rows.    |
| `colspan`   | Merges columns. |

```
<table border="1">
    <caption>Sales Report</caption>
    <tr>
        <th>Month</th>
        <th>Sales</th>
    </tr>
    <tr>
        <td>January</td>
        <td>$1000</td>
    </tr>
</table>
```

## Forms and Input

| Tag          | Description                         |
| ------------ | ----------------------------------- |
| `<form>`     | Form container                      |
| `<input>`    | Input field                         |
| `<textarea>` | Multi-line text                     |
| `<button>`   | Button                              |
| `<select>`   | Dropdown                            |
| `<label>`    | Label for input                     |
| `<fieldset>` | Field grouping                      |
| `required`   | Specifies required input fields.    |
| `pattern`    | Validates the format of user input. |

```
<form action="/submit" method="POST">
    <label for="name">Name:</label>
    <input type="text" id="name" name="name" required>

    <textarea rows="4" cols="50" placeholder="Enter your message"></textarea>

    <fieldset>
        <legend>Select Gender:</legend>
        <input type="radio" name="gender" value="male"> Male
        <input type="radio" name="gender" value="female"> Female
    </fieldset>

    <button type="submit">Submit</button>
</form>
```

## Scripting

| Tag          | Description          |
| ------------ | -------------------- |
| `<script>`   | JavaScript embedding |
| `<noscript>` | Fallback for no JS   |

```
<script>
    alert("Hello, World!");
</script>

<noscript>
    Your browser does not support JavaScript.
</noscript>
```

## Others

| Tag          | Description              |
| ------------ | ------------------------ |
| `<iframe>`   | Embeds another HTML page |
| `<embed>`    | Embeds external content  |
| `<object>`   | Embeds object            |
| `<template>` | Hidden content template  |

```
<iframe src="https://example.com" width="600" height="400"></iframe>

<object data="document.pdf" type="application/pdf" width="600" height="400"></object>

<embed src="audio.mp3" type="audio/mpeg">

<template id="myTemplate">
    <p>This is hidden template content.</p>
</template>

<script>
    let template = document.getElementById("myTemplate");
    let clone = document.importNode(template.content, true);
    document.body.appendChild(clone);
</script>
```

## Projects

1. Simple Project: Personal Profile Page
   - Create an HTML page with your name, a profile picture, a short bio, and links to your social media.
2. Simple Project: Contact Us Page
   - Create a form with Name, Email, Message, and a Submit button.
3. Final Project: Simple Portfolio Website
   - A homepage with a navbar, an about section, a projects section, and a contact form.
   - Internal linking between pages.
4. Static Recipe Page
   - Creat a HTML page to include ingredients and steps to make pancakes.
5. Single-Page CV
   - Create a single-page HTML CV to showcase your career history.

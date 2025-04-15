# HTML Learning Guide: From Beginner to Expert

Welcome to the HTML Learning Guide! This guide is designed to take you from a complete beginner to an expert in HTML. Follow the sections below to progressively build your knowledge and skills in HTML.

## Table of Contents

1. [What is HTML](#what-is-html)
2. [Key Features of HTML](#key-features-of-html)
3. [Basic Structure](#basic-structure)
4. [Head Elements](#head-elements)
5. [Sectioning Tags](#sectioning-tags)
6. [Text Content](#text-content)
7. [List Tags](#list-tags)
8. [Linking and Media](#linking-and-media)
9. [Canvas and SVG](#canvas-and-svg)
10. [Table Tags](#table-tags)
11. [Forms and Input](#forms-and-input)
12. [Scripting](#scripting)
13. [Others](#others)
14. [HTML Accessibility](#html-accessibility)
15. [HTML Best Practices](#html-best-practices)
16. [SEO and HTML](#seo-and-html)
17. [Meta Tags](#meta-tags)
18. [Projects](#projects)
19. [Resources](#resources)

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

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>Document Title</title>
    <meta charset="UTF-8" />
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

```html
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <link rel="stylesheet" href="styles.css" />
  <style>
    body {
      font-family: Arial, sans-serif;
    }
  </style>
  <script>
    console.log("Hello, World!");
  </script>
  <base href="https://example.com/" />
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

```html
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

```html
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

```html
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

```html
<a href="https://example.com" target="_blank">Visit Example</a>

<img src="image.jpg" alt="Sample Image" />

<figure>
  <img src="image.jpg" alt="Example Image" />
  <figcaption>Image Caption</figcaption>
</figure>

<video controls width="400">
  <source src="video.mp4" type="video/mp4" />
</video>

<audio controls>
  <source src="audio.mp3" type="audio/mpeg" />
</audio>
```

## Canvas and SVG

| Tag        | Usage                                 |
| ---------- | ------------------------------------- |
| `<canvas>` | Used for drawing graphics on the fly. |
| `<svg>`    | Scalable Vector Graphics container.   |
| `<circle>` | Draws circles in SVG.                 |
| `<rect>`   | Draws rectangles in SVG.              |

```html
<canvas
  id="myCanvas"
  width="400"
  height="200"
  style="border:1px solid #000;"
></canvas>
<script>
  const canvas = document.getElementById("myCanvas");
  const ctx = canvas.getContext("2d");
  ctx.fillStyle = "blue";
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

```html
<table border="1">
  <caption>
    Sales Report
  </caption>
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

```html
<form action="/submit" method="POST">
  <label for="name">Name:</label>
  <input type="text" id="name" name="name" required />

  <textarea rows="4" cols="50" placeholder="Enter your message"></textarea>

  <fieldset>
    <legend>Select Gender:</legend>
    <input type="radio" name="gender" value="male" /> Male
    <input type="radio" name="gender" value="female" /> Female
  </fieldset>

  <button type="submit">Submit</button>
</form>
```

## Scripting

| Tag          | Description          |
| ------------ | -------------------- |
| `<script>`   | JavaScript embedding |
| `<noscript>` | Fallback for no JS   |

```html
<script>
  alert("Hello, World!");
</script>

<noscript> Your browser does not support JavaScript. </noscript>
```

## Others

| Tag          | Description              |
| ------------ | ------------------------ |
| `<iframe>`   | Embeds another HTML page |
| `<embed>`    | Embeds external content  |
| `<object>`   | Embeds object            |
| `<template>` | Hidden content template  |

```html
<iframe src="https://example.com" width="600" height="400"></iframe>

<object
  data="document.pdf"
  type="application/pdf"
  width="600"
  height="400"
></object>

<embed src="audio.mp3" type="audio/mpeg" />

<template id="myTemplate">
  <p>This is hidden template content.</p>
</template>

<script>
  let template = document.getElementById("myTemplate");
  let clone = document.importNode(template.content, true);
  document.body.appendChild(clone);
</script>
```

## HTML Accessibility

### What is Accessibility?

In the context of HTML, accessibility refers to designing and coding web pages to ensure that individuals with disabilities, including those using assistive technologies like screen readers, can perceive, understand, navigate, and interact with the content effectively.

### Best Practices for Accessible HTML

- Semantic HTML: Using the correct HTML elements for their intended purpose helps assistive technologies understand the structure and context of the content.
- Alternative Text (alt text): Providing descriptive text for images, so users who cannot see the image can still understand its content.
- Language Declaration: Declaring the language of the page using the lang attribute in the `<html>` tag helps screen readers and other technologies understand and process the content correctly.
- Clear and Concise Language: Using simple, easy-to-understand language makes the content accessible to a wider audience, including those with cognitive impairments.
- Navigation and Structure: Providing clear and logical navigation, such as using headings and lists, helps users with disabilities understand the page structure and find information easily.
- ARIA Attributes: Using ARIA (Accessible Rich Internet Applications) attributes can provide additional information to assistive technologies, such as screen readers, about interactive elements and dynamic content.
- Form Accessibility: Ensuring that forms are accessible by providing labels for input fields, using ARIA attributes, and ensuring that the form can be navigated using the keyboard.
- Color Contrast: Ensuring sufficient color contrast between text and background to make content readable for users with visual impairments.
- Content Delivery: Delivering content in multiple formats, such as text-to-speech or video, can make it more accessible to users with different needs.

### ARIA (Accessible Rich Internet Applications)

ARIA attributes provide additional semantics and context to HTML elements, which can be especially helpful for elements that don't have native HTML equivalents or when the native HTML elements don't fully convey the necessary information for assistive technologies.

```html
<!-- Without ARIA -->
<div class="button">Click Me</div>

<!-- With ARIA -->
<div class="button" role="button" aria-label="Click Me">Click Me</div>
```

#### ARIA Attributes:

- aria-label: Provides a label for an element.
- aria-labelledby: References an element that provides a label for the current element.
- aria-describedby: Links an element to a description.
- aria-hidden: Hides an element from assistive technologies.
- role: Defines the purpose of an element.
- aria-selected: Indicates whether an element is selected.
- aria-expanded: Indicates whether an element is expanded or collapsed.

## HTML Best Practices

Explore best practices to write clean, maintainable, and efficient HTML code.

1.  **Always Declare a Doctype**

- Use a doctype declaration at the top of every HTML file to ensure proper rendering.

- Recommended:

  ```html
  <!DOCTYPE html>
  ```

- It tells the browser to use standards mode.

2.  **Use Meaningful `<title>` Tags**

- Titles appear in browser tabs and search engine results.

- They should clearly describe the page content.
  Example:

  ```html
  <title>Learn HTML Best Practices - WebFX</title>
  ```

3. **Use Descriptive Meta Tags**

- Help with SEO and accessibility.

- Two common ones:

  ```html
  <meta name="description" content="Detailed guide on HTML best practices." />
  <meta name="keywords" content="HTML, web design, best practices" />
  ```

4. **Use Divs to Organize Layout**

- Divide your page into clear sections (e.g., header, footer, content).

- Promotes readable and maintainable structure.

5. **Separate Content from Presentation**

- Avoid inline styles. Use external CSS for styling.

- Bad:

  ```html
  <p style="color:red;">Hello</p>
  ```

- Good:

  ```html
  <p class="error">Hello</p>
  ```

6. **Minify and Unify CSS**

- Combine multiple CSS files into one.

- Remove extra spaces, comments, etc., to reduce file size and load time.

7. **Minify, Unify, and Defer JavaScript**

- Combine and compress scripts.

- Place scripts at the bottom of the HTML page before the `</body>` tag for faster loading.

8. **Use Headings Properly (`<h1>` to `<h6>`)**

- Maintain a logical hierarchy.

- Example:

  ```html
  <h1>Main Topic</h1>
  <h2>Sub-topic</h2>
  ```

9. **Use Correct Semantic Elements**

- Use tags that reflect the purpose:

- `<em>` for emphasis, `<strong>` for strong importance
- `<ul>`, `<ol>`, `<dl>` for lists
- `<section>`, `<article>`, `<aside>`, `<footer>` for layout

10. **Avoid Overusing `<div>` Tags**

- Prefer semantic tags over generic divs.

- Use `<nav>`, `<main>`, `<header>`, etc., to define structure.

11. **Add Alt Text to Images**

- Improves accessibility and SEO.

  ```html
  <img src="logo.png" alt="Company Logo" />
  ```

12. **Keep HTML Well-Indented and Organized**

- Makes code easier to read and debug.

13. **Use Comments to Explain Complex Code**

```html
<!-- This section is for user testimonials -->
```

14. **Validate Your HTML**

- Use tools like W3C Validator to catch errors and ensure compliance with standards.

15. **Use External Resources Responsibly**

- Only include necessary fonts, icons, or scripts to avoid slow load times.

## SEO and HTML

### What is SEO?

SEO stands for Search Engine Optimization. It’s the process of optimizing a website so it ranks higher in search engine results (like Google, Bing, etc.) to increase organic (non-paid) traffic.

#### Goals of SEO:

- Increase visibility in search results
- Drive more traffic to your site
- Improve user experience
- Boost brand awareness and conversions

#### Key Components of SEO:

1. On-Page SEO: Focuses on optimizing individual pages.

- Keywords: Using the right words people search for
- Content: High-quality, relevant, and engaging content
- Meta Tags: Meta title & description help search engines understand the page
- Headings (H1, H2, etc.): Organize and structure content
- URL Structure: Clean and readable URLs (e.g., /seo-guide instead of /page?id=123)

2. Off-Page SEO: Focuses on building a website’s reputation.

- Backlinks: Links from other websites to yours
- Social Sharing: How often your content is shared on platforms
- Brand Mentions: Your brand being talked about online

3. Technical SEO: Focuses on website infrastructure.

- Site Speed: Faster loading sites rank better
- Mobile-Friendliness: Optimized for phones and tablets
- Secure Connection (HTTPS): Trusted by users and Google
- Sitemaps & Robots.txt: Help search engines crawl your site

#### Important HTML Tags for SEO:

- `<title>`: Appears in search results and browser tab (very important for SEO)
- `<meta name="description">`: Short summary for search engines
- `<h1>`, `<h2>`, `<h3>`: Headings that structure content (H1 is most important)
- `<a href="...">`: Links (internal and external)
- `<img src="..." alt="...">`: Images (the alt attribute helps with image SEO)
- `<strong>`, `<em>`: Emphasize keywords
- `<nav>`, `<footer>`, `<main>`: Help define the layout for accessibility and SEO

#### How SEO and HTML Work Together

HTML is the foundation of a webpage. SEO is the strategy to make that page perform well in search engines.

Think of it like this:

- HTML is the structure and content of a house.
- SEO is how you make sure people find and like your house (clear address, curb appeal, etc.).

For example:

```html
<title>Best Coffee Shops in New York | Local Guide</title>
<meta
  name="description"
  content="Discover the top-rated coffee shops in NYC for your next caffeine fix. Updated for 2025."
/>
<h1>Top 10 Coffee Shops in NYC</h1>
<p>If you're a coffee lover visiting New York City, don't miss these gems...</p>
```

This HTML includes:

- An SEO-friendly title and description
- A relevant H1 header with keywords
- Useful, clear content

#### Example: SEO-Optimized HTML Page

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Best Coffee Shops in New York City (2025 Guide)</title>
    <meta
      name="description"
      content="Discover the top-rated coffee shops in NYC for your next caffeine fix. Updated list for 2025 with insider tips."
    />
    <meta
      name="keywords"
      content="coffee shops NYC, best coffee New York, NYC cafes, coffee guide 2025"
    />
    <link
      rel="canonical"
      href="https://yourwebsite.com/best-coffee-shops-nyc-2025"
    />
    <meta name="robots" content="index, follow" />
  </head>
  <body>
    <header>
      <h1>Top 10 Best Coffee Shops in New York City (2025)</h1>
    </header>

    <nav>
      <ul>
        <li><a href="/">Home</a></li>
        <li><a href="/nyc-guides">NYC Guides</a></li>
        <li><a href="/contact">Contact</a></li>
      </ul>
    </nav>

    <main>
      <article>
        <p>
          Looking for a caffeine fix in NYC? We've rounded up the best coffee
          shops in the city for 2025, from cozy Brooklyn cafés to iconic
          Manhattan espresso bars.
        </p>

        <h2>1. Blue Bottle Coffee - Bryant Park</h2>
        <img
          src="blue-bottle-nyc.jpg"
          alt="Blue Bottle Coffee in Bryant Park, NYC"
        />
        <p>
          Known for its clean interior and slow-drip perfection, Blue Bottle
          tops our list for both atmosphere and quality.
        </p>

        <h2>2. Devoción - Brooklyn</h2>
        <p>
          With lush greenery and Colombian beans roasted on-site, Devoción is a
          Brooklyn staple for the true coffee connoisseur.
        </p>

        <!-- ... More listings ... -->
      </article>
    </main>

    <footer>
      <p>&copy; 2025 NYC Coffee Guide. All rights reserved.</p>
    </footer>
  </body>
</html>
```

**What’s SEO-Optimized Here?**

- Meta title: Includes keywords like Best Coffee Shops and New York City + “2025”
- Meta description: A compelling summary using search keywords
- Headings (H1, H2): Well-structured content with relevant keywords
- Alt text on image: Helps image SEO and accessibility
- Clean URL (via <link rel="canonical">)
- Mobile-friendly with viewport meta tag
- Internal links in nav for better user flow

#### On-Page SEO Checklist

Here’s a checklist you can use when building your pages:

1. Meta Tags:

- Title tag (under 60 characters, main keyword first)
- Meta description (under 160 characters, compelling, includes keywords)
- Meta keywords (optional, Google ignores but some engines still read)

2. Page Content:

- H1 tag used once with primary keyword
- H2-H3 tags for subtopics/sections
- Main keyword in the first 100 words
- Use of related keywords / synonyms (LSI keywords)
- Images with descriptive alt attributes
- Internal links to other pages on your site
- External links to trusted sources (if relevant)

3. Technical:

- Mobile-friendly design
- Fast loading time
- HTTPS secured site
- SEO-friendly URL structure
- Sitemap.xml and robots.txt configured properly

## Meta Tags

1.  **SEO-Related Meta Tags**
    These help search engines understand your page better.

    ```html
    <!-- Title and description -->
    <meta
      name="description"
      content="A complete guide to New York coffee shops."
    />
    <meta
      name="keywords"
      content="coffee, NYC cafes, best coffee in New York"
    />

    <!-- Control indexing -->
    <meta name="robots" content="index, follow" />
    <!-- index: allow listing, follow: allow crawling links -->
    <meta name="googlebot" content="noindex, nofollow" />
    <!-- Specific for Googlebot -->

    <!-- Canonical alternative (not a meta tag but SEO-related) -->
    <link rel="canonical" href="https://example.com/page-name" />
    ```

2.  **Language and Charset**
    Helps define the document's language and character encoding.

    ```html
    <meta charset="UTF-8" />
    <!-- Most common and preferred -->
    <meta http-equiv="content-language" content="en" />
    <!-- Optional, can specify language -->
    ```

3.  **Open Graph (OG) Tags for Social Sharing (Facebook, LinkedIn, etc.)**
    Control how your content appears when shared.

    ```html
    <meta property="og:title" content="Best Coffee in NYC" />
    <meta
      property="og:description"
      content="Explore top-rated coffee spots in New York."
    />
    <meta property="og:image" content="https://example.com/coffee-cover.jpg" />
    <meta property="og:url" content="https://example.com/best-coffee-nyc" />
    <meta property="og:type" content="article" />
    <meta property="og:site_name" content="Coffee Explorer" />
    ```

4.  **Twitter Cards**
    Controls appearance when shared on Twitter.

    ```html
    <meta name="twitter:card" content="summary_large_image" />
    <meta name="twitter:title" content="Best Coffee Shops in NYC" />
    <meta
      name="twitter:description"
      content="Your 2025 guide to NYC’s top cafes."
    />
    <meta
      name="twitter:image"
      content="https://example.com/coffee-twitter.jpg"
    />
    <meta name="twitter:site" content="@YourTwitterHandle" />
    ```

5.  **Mobile & Viewport Control**
    Helps your site be responsive and mobile-friendly.

    ```html
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    ```

6.  **Browser Behavior / Miscellaneous**
    These control how browsers behave or interpret content.

    ```html
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <!-- Ensure compatibility with modern IE -->
    <meta http-equiv="refresh" content="10; url=https://example.com/redirect" />
    <!-- Auto-redirect -->
    <meta name="theme-color" content="#ffffff" />
    <!-- Changes browser bar color on mobile -->
    ```

7.  **Security / Privacy**
    Used for things like preventing content sniffing or controlling referrer behavior.

    ```html
    <meta http-equiv="Content-Security-Policy" content="default-src 'self'" />
    <meta name="referrer" content="no-referrer" />
    <!-- Controls how much referrer info is passed -->
    ```

### Summary Table

| Purpose              | Attribute Example                    | Notes                               |
| -------------------- | ------------------------------------ | ----------------------------------- |
| SEO                  | name="description"                   | Helps search engines summarize page |
| Keywords (less used) | name="keywords"                      | Still used by some engines          |
| Robots               | name="robots"                        | Controls crawling & indexing        |
| Charset              | charset="UTF-8"                      | Always include this at top          |
| Viewport             | name="viewport"                      | Mobile responsiveness               |
| Open Graph (OG)      | property="og:title"                  | Facebook, LinkedIn, etc.            |
| Twitter Card         | name="twitter:card"                  | Social sharing on Twitter           |
| Refresh              | http-equiv="refresh"                 | Redirect or auto-refresh page       |
| CSP                  | http-equiv="Content-Security-Policy" | Sets rules for secure loading       |
| Referrer             | name="referrer"                      | Controls what URL info is shared    |
| X-UA-Compatible      | http-equiv="X-UA-Compatible"         | IE-specific compatibility           |
| Language             | http-equiv="content-language"        | Set document language               |
| Theme                | Color name="theme-color"             | Mobile browser toolbar color        |

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

## Resources

Here are some additional resources to help you on your HTML learning journey:

- [MDN Web Docs - HTML](https://developer.mozilla.org/en-US/docs/Web/HTML)
- [W3Schools - HTML](https://www.w3schools.com/html/)
- [freeCodeCamp - Responsive Web Design Certification](https://www.freecodecamp.org/learn/responsive-web-design/)
- [HTML.com](https://html.com/)
- [HTML5 Rocks](https://www.html5rocks.com/en/)

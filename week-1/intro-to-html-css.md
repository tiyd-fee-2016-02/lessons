## What is HTML?

* **HyperText** is the method by which you move around on the web by clicking on special text called hyperlinks. Hyper just means it's not linear - i.e. you can go to any place on the Internet whenever you want by clicking on links - there is no set order to do things in.

* **Markup** is what HTML tags do to the text inside them. They mark it as a certain type of text (italicised text, for example).

* HTML is a **Language**, as it has code-words and syntax like any other language.

---
Boring but Useful Definition of HTML (via [MDN](https://developer.mozilla.org/en-US/)):

<blockquote>
HTML adds "markup" to standard English text. "Hyper Text" refers to links that connect Web pages to one another, making the World Wide Web what it is today. By creating and uploading Web pages to the Internet, you become an active participant in the World Wide Web. HTML supports visual images and other media as well. HTML is the language that describes the structure and the semantic content of a web document. Content within a web page is tagged with HTML elements such as &lt;img&gt;, &lt;title&gt;, &lt;p&gt;, &lt;div&gt;, &lt;picture&gt;, and so forth.  These elements form the building blocks of a website.
</blockquote>

---
HTML provides a structure for your site - a skeleton of content.

![spooky](http://i.imgur.com/H6B0LWo.png)

---
## What does HTML look like?

```HTML
<tag-name="attribute value">
  <!--tag contents-->
</tag-name>
```
```HTML
  <a href="http://www.google.com">Google</a>
```

```HTML
  <p>Cats are cool!</p>
```

And sometimes there's self-closing tags...

```HTML
<img src="http://placebear.com/g/400/200" alt="bears!!">
```

Let's check out an [example](http://kellymurray.github.io/tiy-html-css-crash-course/).

---
Following is the basic structure, tagwise, for a basic html document

```html
<!-- This is a comment -->
<!DOCTYPE html>
<html>
  <head>
    <title>This is a title</title>
    <link rel="stylesheet" type="text/css" href="styles.css">
    <!-- The <head> tag usually contains any external CSS stylesheets or meta information about a particular page -->
  </head>
  <body>
  <!-- The <body> tag is where human-viewable content is stored -->
  </body>
</html>

```

---

## What is Semantic HTML?

* Semantic HTML tags provide information about the contents of those tags that goes beyond just how they look on a page.

* For example: you can now identify the navigation bar with the ``<nav>`` tag.

* Why use semantic HTML at all?

	* Works better for the visually impaired and SEO/Google Rankings.

	* Makes for better code in a team setting.


---

## HTML - Semantic Markup

These 'newer' tags are generally called 'sectioning' tags
sectioning tags: <code>&lt;section&gt;</code>, <code>&lt;nav&gt;</code>, <code>&lt;aside&gt;</code>, <code>&lt;article&gt;</code>

From the MDN:
<blockquote>
Elements belonging to the sectioning content model create a section in the current outline that defines the scope of  &lt;header&gt; elements, &lt;footer&gt; elements, and heading content.
</blockquote>

Sectioning Tags:

### section

From the MDN:
<blockquote>
The HTML Section Element ( &lt;section&gt; ) represents a generic section of a document, i.e., a thematic grouping of content, typically with a heading. Each &lt;section&gt; should be identified, typically by including a heading (h1-h6 element) as a child of the &lt;section&gt; element.
</blockquote>

### article

From the MDN:
<blockquote>
The HTML &lt;article&gt; Element represents a self-contained composition in a document, page, application, or site, which is intended to be independently distributable or reusable, e.g., in syndication. This could be a forum post, a magazine or newspaper article, a blog entry, a user-submitted comment, an interactive widget or gadget, or any other independent item of content. Each article should be identified, typically by including a heading (h1-h6 element) as a child of the &lt;article&gt; element.
</blockquote>

### aside

From the MDN:
<blockquote>
The HTML aside element represents a section of the page with content connected tangentially to the rest, which could be considered separate from that content. These sections are often represented as sidebars or inserts. They often contain the definitions on the sidebars, such as definitions from the glossary; there may also be other types of information, such as related advertisements; the biography of the author; web applications; profile information or related links on the blog.
</blockquote>

### nav

From the MDN:
<blockquote>
The HTML Navigation Element &lt;nav&gt; represents a section of a page that links to other pages or to parts within the page: a section with navigation links.
</blockquote>

Flow Content tags:

### header

From the MDN:
<blockquote>
The HTML header Element represents a group of introductory or navigational aids. It may contain some heading elements but also other elements like a logo, wrapped section's header, a search form, and so on. -MDN
</blockquote>

### footer

From the MDN:
<blockquote>
The HTML &lt;footer&gt; Element represents a footer for its nearest sectioning content or sectioning root element (i.e, its nearest parent &lt;article&gt;, &lt;aside&gt;, &lt;nav&gt;, &lt;section&gt;, &lt;blockquote&gt;, &lt;body&gt;, &lt;details&gt;, &lt;fieldset&gt;, &lt;figure&gt;, &lt;td&gt;). A footer typically contains information about the author of the section, copyright data or links to related documents. - MDN
</blockquote>
---

## Intro to CSS
* What is CSS and how does it differ from HTML?

	* Cascading Style Sheets.

	* CSS defines how HTML elements are displayed. It can't be used without HTML.

	* Primary purpose: separating content from design.

	* CSS should always be written after your basic HTML.

---

Boring but Useful Definition of CSS (via [MDN](https://developer.mozilla.org/en-US/)):
<blockquote>
Cascading Style Sheets, most of the time abbreviated as CSS, is a stylesheet language used to describe the presentation of a document written in HTML or XML (including various XML languages like SVG or XHTML). CSS describes how the structured element must be rendered on screen, on paper, in speech, or on other media.
</blockquote>

---
## How to get your CSS on the page
* Internal vs External

	* Internal styles are embedded in head section with the style tag.

		* One problem: browser continually has to re-download code every time a new HTML page loads.

	* External style sheets are the best option. They're the most efficient and we can change the look of an entire website with one file.

		* Just be careful how many stylesheets you link!

---
## CSS Selectors

* What is a selector and how does it look on the page?

* Basic CSS consists of three parts:

```css
selector {
property: value;
}
```

* The selector is the element that you want to style. The property is the actual property title, and the value is the style you apply to that property.


```css
body {
background: DodgerBlue;
font-family: "Trebuchet MS", Verdana, serif;
}
```

---

```css
/* This is a CSS comment */
body {
  background-color: red;
  font-size: 20px;
  font-weight: strong;
}

```

---

## ID selectors

* An ID selector lets us assign a unique ID to an element so we can manipulate it separately.

* Each element can have only one ID and each page can have only one element with that ID.

* ID names are up to you, but good practice is to give them meaningful names that explain what they do and their purpose, NOT how they look. Ex: "``#alert``" not "``#red``".

* How to remember #? Dogs at the **POUND** need an **ID**.

* IDs should be avoided in favor of...

---

## Class selectors

* Class selectors target elements based on their class attribute.

* IDs are unique and used to identify one element on the page, whereas a class can target more than one element and elements can have multiple classes.

* Classes provide more flexibility - you can use a class multiple times in a document but an ID only once.

* How to remember .? **CLASSES** at school are divided into **PERIODS**.

---

## Specificity

* If one selector is more specific than the others, the more specific rule will take precedence.

* ``h1`` is more specific than ``*``

* The different weight of selectors is usually the reason why your CSS-rules don't apply to some elements.

* Problems are caused when you define a more specific selector -- like an HTML selector and an ID selector.

---

## Resources

[HTML Element Reference Guide](https://developer.mozilla.org/en-US/docs/Web/HTML/Element)

[CSS Reference Guide](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference)

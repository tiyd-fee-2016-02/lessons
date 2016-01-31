class: center, middle, inverse

## What is HTML?

* **HyperText** is the method by which you move around on the web by clicking on special text called hyperlinks. Hyper just means it's not linear - i.e. you can go to any place on the Internet whenever you want by clicking on links - there is no set order to do things in.

* **Markup** is what HTML tags do to the text inside them. They mark it as a certain type of text (italicised text, for example).

* HTML is a **Language**, as it has code-words and syntax like any other language.

---

## What is Semantic HTML?

* Semantic HTML tags provide information about the contents of those tags that goes beyond just how they look on a page.

* For example: you can now identify the navigation bar with the < nav > tag.

* Why use semantic HTML at all?

	* Works better for the visually impaired and SEO/Google Rankings.

	* Makes for better code in a team setting.

---

## HTML Tags

* HTML's purpose is to provide a structure for your site - a skeleton.

* Mixing uppercase and lowercase names is bad.

* Close your HTML elements.

```html
<element="attribute"> </close tag>
```

---
## Common HTML Tags

* DOCTYPE

* html

* head

* title

* body

* a

* div

* p

* h1, h2, h3, h4, h5, h6

* header

* footer

* nav

---

## Intro to CSS
* What is CSS and how does it differ from HTML?

	* Cascading Style Sheets.

	* CSS defines how HTML elements are displayed. It can't be used without HTML.

	* Primary purpose: separating content from design.

	* CSS should always be written after your basic HTML.

---
## How to get your CSS on the page
* Internal vs External

	* Internal styles are embedded in head section with the style tag.

		* One problem: browser continually has to re-download code every time a new HTML page loads.

	* External style sheets are the best option. They're the most efficient and we can change the look of an entire website with one file.

		* Just be careful how many stylesheets you link!

## Resets
* Before CSS: Default styles applied by browser/normalizing

---

## How do I set up my files?
* Local structure

* Paths

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

## ID selectors

* An ID selector lets us assign a unique ID to an element so we can manipulate it separately.

* Each element can have only one ID and each page can have only one element with that ID.

* ID names are up to you, but good practice is to give them meaningful names that explain what they do and their purpose, NOT how they look. Ex: "``#alert``" not "``#red``".

* How to remember #? Dogs at the POUND need an ID.

* IDs should be avoided in favor of...

---
## Class selectors

* Class selectors target elements based on their class attribute.

* IDs are unique and used to identify one element on the page, whereas a class can target more than one element and elements can have multiple classes.

* Classes provide more flexibility - you can use a class multiple times in a document but an ID only once.

---

## Specificity

* If one selector is more specific than the others, the more specific rule will take precedence.

* ``h1`` is more specific than ``*``

* The different weight of selectors is usually the reason why your CSS-rules don't apply to some elements.

* Problems are caused when you define a more specific selector -- like an HTML selector and an ID selector.

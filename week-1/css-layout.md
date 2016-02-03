# CSS Layouts

## First, a digression about syntax

![Commas](http://ecx.images-amazon.com/images/I/414Alp8pEpL._SY355_.jpg)

## Syntax errors

- The most common reason something isn't working
- Look for missing semicolons, colons, braces, parenthesis, quotes, etc
- Escaping characters

```HTML
    <!-- Since greater than is a special character, how do you use it
    as a regular character? You use escape codes. -->
    <h1>This &gt; is a greater than</h1>

    <!-- Escape sequences start with an ampersand, followed by a set of
    characters, and ended by a semicolon. -->

    &quot; <!-- a quote -->
    &apos; <!-- a single quote / tick / apostrophe -->

    <!-- But since ampersand is a special character denoting an escape
    sequence, how do you insert an ampersand? -->
    <h2>Parker &amp; Otis</h2>
```
## Padding, margin, border

```css
.frame {
  border: 10px solid #333;
  margin: 1em;
  padding: 1em;
}
```

## Shorthand

Many CSS rules have a shorthand notation.

- short-hand notation for margin and padding
  - clockwise
  - top, right, bottom, left

```css
.frame {
  padding: 1em 0.5em 0.25em 0em;
}
```

## Border-Radius

```css
.frame {
  border-radius: 1em;
}
```

## Circles

```css
.frame {
  width: 3em;
  height: 3em;
  border-radius: 3em;
}
```

## Bevels

```css
.frame {
  border: 5px solid #0675f4;
  border-left-color: #88bdf5;
  border-right-color: #88bdf5;
}
```

## A note about units

- units
  - px - pixels
  - em - size relative to font of current element (1.5em is 1.5 times the font size)
  - rem - size relative to font of root element (e.g. the body or html)
  - % - size relative to parent (except in odd cases like padding)

## Position

- absolute - positioned relative to the closest `relative` parent
- fixed - positioned relative to the window/viewport
- static - positioned in normal, document flow
- relative - like static, except serving as a container for absolutely positioned elements

## Position fixed

[Here is an example](http://jsbin.com/vekuyunese/1/) of a fixed-position header.

- Usually, you set `top`, `right`, `bottom`, and or `left`
- Often, you specify a `z-index`

## Display

```css
.foo {
  /* The most common values are block, inline, inline-block */
  display: block;
}
```

<blockquote>`display` is CSS's most important property for controlling layout. Every element has a default `display` value depending on what type of element it is. The default for most elements is usually `block` or `inline`. A block element is often called a block-level element. An `inline element` is always just called an inline element.</blockquote> - Learn Layout

- inline elements
  - are treated like words in a sentence
  - allow other elements to sit on their right and left
  - examples: `<span>`, `<a>`
- inline-block elements
  - are like inline elements, except
  - can be vertically aligned
  - useful for turning `<li>`s into a vertical nav bar
- block elements
  - are like inline-block elements, except
  - they display on their own line
  - examples: `<div>`, `<h1>`, `<header>`, `<section>`

  [Learn Layout](http://learnlayout.com/display.html) has a great tutorial on this. Spend some time with it!

## Float

- left
- right
- none
- clear
- overflow
  - auto
  - hidden

[Example](http://jsbin.com/wazore/1/edit?html,output)

Floating an item (left or right) takes it out of the normal flow.

An item with `display: block; clear: both` will "clear" the float.

An alternative way to force a container to properly contain its floating children
is to use overflow auto or hidden.

## Tables

- table, thead, tr, th, td, tbody, tfoot
- Tables should not be used for layout
- Tables *should* be used to represent truly tabular data

## Centering things in CSS

Unfortunately, CSS centering is tough and there isn't just one right solution. But [CSS Tricks](https://css-tricks.com/centering-css-complete-guide/) has a great decision tree to help you find the right solution for your problem.

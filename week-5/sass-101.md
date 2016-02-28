# Sassy CSS with SCSS

_"We here in Sasslandia don't put up with repeating your code. Anyone who copies or pastes is an enemy of the state and shall be dealt with accordingly."_ - Hampton Catlin, the creator of Sass

We're sassy cats, but can we write Sassy CSS? What _is_ Sassy CSS, and why should we be interested in it? Glad you asked!

## Sass

[Sass](http://sass-lang.com/) stands for "Sytnastically Awesome StyleSheets" and was created specifically to address some of CSS's shortcomings. It allows you to use variables, nested rules, and more to take your CSS to the next level -- while providing DRY-er code overall.

There's two Sass Syntaxes out there: `.scss` and `.sass`. The latter is older and not as powerful as `.scss`, so you'll be learning `.scss`.

And finally -- don't _ever_ write it in all caps! It's "Sass."

## Install Time

Once again, let's thank our Apple overlords for shipping Ruby out of the box. Open up your terminal and type:

```
gem install sass
```

And...that's it. Now you've got Sass.

## Running Sass

```
$ sass test.scss
```

```
sass --watch .
```


## Importing

```css
@import 'reset';
```

Will import the content of `_reset.scss`

So, `main.scss` is generally what I use as the single place to import scss.

---

## Variables

```
$primary-color: #333;
```

---

## Nesting

```css
.modal {
  border: 1px solid

  .close {
    background: #AAA;
    color: white;
  }
}
```

Produces

```css
.modal {
  border: 1px solid
}

.modal .close {
  background: #AAA;
  color: white;
}
```

---

## Functions

Functions, but in CSS!!!

```css
@function shade($color, $percent) {
  @return mix(#000, $color, $percent);
}

@function tint($color, $percent) {
  @return mix(#fff, $color, $percent);
}

.modal-background {
  background-color: tint(#548dd8, 40%);
}
```

---

## Mixins

[Read about it here](http://davidwalsh.name/write-media-queries-sass)

```css
$medium-width: 768px;
$big-width: 1024px;

@mixin medium-screen {
  @media (min-width: #{$tablet-width}) and (max-width: #{$desktop-width - 1px}) {
    @content;
  }
}

@mixin big-screen {
  @media (min-width: #{$desktop-width}) {
    @content;
  }
}
```

---

### Use it like this:

```css
p {
  font-size: 16px;

  @include medium-screen {
    font-size: 18px;
  }

  @include big-screen {
    font-size: 20px;
  }
}
```

---

## More mixins

```css
@mixin stacked-item ($spacing: 1em) {
  padding: $spacing;

  // Use a slightly smaller margin than our padding
  margin-bottom: $spacing * 0.75;
}
```

Use it like this:

```scss

.user {
  // Include the stacked-item rules in .user, using the default $spacing value
  @include stacked-item;
}

.appointments {
  // Include the stacked-item rules in .user, using 1.2em as $spacing
  @include stacked-item(1.2em);
}
```

---

## What else?

SCSS supports loops, arrays (called lists), hashes (called maps), conditionals,
and more...

[More on that here](http://thesassway.com/intermediate/if-for-each-while)

---

## Example of lists and loops

[With credit from here](http://benfrain.com/working-with-lists-and-each-loops-in-sass-with-the-index-and-nth-function/)

```css
$colors: #00F #0F0 #F00;

@each $color in $colors {
  $i: index($colors, $color);

  .box-#{$i} {
    color: $color;
  }
}
```

Produces

```css
.box-1 {
  color: #00F;
}

.box-2 {
  color: #0F0;
}

.box-3 {
  color: #F00;
}
```

---

## Loops, conditionals, hashes, arrays, and more...

- My suggestion: don't use them.
- CSS is a simple language.
- Simplicity is a big part of it's strength.
- There's usually a CSS-y way to solve redundancy.
- Use complex logic only in very selective cases.
- Keep your SCSS as close to CSS as possible for the sake of others.
- But if you really need it...go for it. Just don't get carried away.

# Templates

Tired of manually building HTML in your JavaScript? Tired of writing code that
looks like this?

    var span = $('<span></span>');
    span.text(user.name);
    $('#some-place').html(span);

Me, too. Fortunately, there's a thing called templating that makes this
process much less painful.

## Definition

A template is a string that has some placeholder text in it. A really basic
example would look like this:

```javascript
    var template = 'Hey, NAME, how are you?';
    var hiChris = template.replace('NAME', 'Chris');
    var hiJane = template.replace('NAME', 'Jane');
```

- The process is:
  - Define a template with placeholders
  - Bind the template to data values
  - Get the final result with all placeholders replaced with real data

## Lodash

We're going to use [lodash](https://lodash.com/docs#template), but another popular option is [Underscore.js](http://underscorejs.org/).

- It's a library
- It's methods are always prefixed with `_.`
- It has *lots* of methods
- We're just going to talk about its templating abilities right now

## Templates with lodash

Here's an example of a real lodash template:

    <span><%- user.name %></span>

Wouldn't it be cool to be able to use that template to produce this HTML:

    <span>Jane Doe</span>

Guess what? We can!

## First, get lodash

You can use a [lodash CDN](https://cdnjs.com/libraries/lodash.js/) much like you do with jQuery. You can also install it locally, but we'll be talking more about that process next week.

## Next, create an HTML file

Create an HTML file that has a body like this:

    <body>
      <div id="main">
      </div>

      <!-- Include lodash, jquery, and your own app.js scripts here -->

    </body>

Be sure to include script tags whose src attributes point to lodash, jquery,
and your own JavaScript file. (I'll be referring to your own JS file as app.js
from now on.)

## Create a template

Now, in app.js, do something like this:

```javascript
var greeting = _.template('<h1>Hello, <%- m.name %>!</h1>', { variable: 'm' });
var renderedHtml = greeting({ name: 'Poe Dameron' });
$('#main').html(renderedHtml);
```

Now, refresh your HTMl file and see what happened. You should see a big h1
tag that reads: "Hello, Poe Dameron!".

## It's lodash magic!

First, let's talk about that `_.template` thing.

Just like jQuery defined a global variable `$`, so lodash defines a global
variable `_`.

- `_` is a variable that points to a big object
- `_.template` is a method that takes a string and optional parameters and
returns a function
- When you call the returned function,
  - Pass it the data (also called the model) you want to bind to the template
  - It returns a string with the data inserted into the template

---

## Example

So:

```javascript
var greeting = _.template('<h1>Hello, <%- m.name %>!</h1>', { variable: 'm' });
document.body.innerHTML = greeting({ name: 'Jane' });
```

- Lodash creates a function and returns it, and we are storing it in `greeting`
- When we call the `greeting` function, we pass it an object
- The `greeting` function uses the object to create the final HTML
- `<h1>Hello, Jane!</h1>`

### Escaped values

If `m.user` had a value of `'<script>alert("hi")</script>'`

This template: `<%- m.user %>` will automatically escape the value

So, when rendering data that you don't trust (e.g. user input), always use
`<%-`


### Unescaped

If you were to do this:

    'hello <%= m.user %>!'

And m.user was the alert script, then this would actually execute the script.

So, use `<%= %>` only when:

- You want to put raw HTML out
- You trust the source of your data!

### Loops

You can put JS code into your templates like this:

```html
  <% m.technologies.forEach(function (tech) { %>
    <div class="tech">
      <%- tech.name %>
    </div>
  <% }); %>
```

That is going to loop through all of the items in m.technologies (presumably
  an array), and write a div out for each one.

You could put if statements into your templates in much the same way.

## The script hack

It's a pain to write HTML templates in JS. It involves lots of string
 concatenation, etc.

It'd be much easier if we could write them in our HTML file itself.

We could do something like this:

```html
  <body>

    <div id="main">
    </div>

    <script type="text/html" id="myTemplate">
      Hello, <%- m.name %>!
    </script>

  </body>
```

If you tell the browser the script `type` is `"text/html"` then the browser will just ignore the script tag.

- text/html is not a valid script type
- The browser ignores the script (it's still there, just hidden)
- We can use JavaScript to grab our templates

```javascript
// Get the template from the hacky script tag:
var templateString = $('#myTemplate').html();

// Compile the template as per usual:
var compiledTemplate = _.template(templateString, { variable: 'm' });

// Render the template out to our main div tag:
$('#main').html(compiledTemplate({ name: 'John Smith' }));
```

## Lots of templates

We could write some code to load *all* templates from the DOM and store them
in a hash.

```javascript

var views = {};

$('script[type="text/html"]').each(function () {
  var script = $(this);
  views[script.attr('id')] = _.template(script.html(), { variable: 'm' });
  script.remove();
});

```

## Using it

Now, if we have an HTML file that looks like this:

```html
<body>

  <div id="main">
  </div>

  <script type="text/html" id="myTemplate">
    Hello, <%- m.name %>!
  </script>

</body>
```

We could render the myTemplate template out into the #main div tag like this:

```javascript
    $('#main').html(views.myTemplate({ name: 'Jane Doe' }));
```

## Partials

Even cooler, we can now include templates within other templates (a technique
  often called Partials).

```html
    <body>

     <div id="main">
     </div>

     <script type="text/html" id="header">
        <h1>Hi, <%- m.name %>!</h1>
     </script>

     <script type="text/html" id="myTemplate">
        <%= views.header(m) %>
        <p>You are <%- m.description %>!</p>
     </script>

     <!-- your JavaScript includes should go here -->
    </body>

```

Now, when we render myTemplate like this:

```javascript
$('#main').html(views.myTemplate({ name: 'Joe', description: 'awesome' }));
```

The #main div will have the following inner HTML:

```html
<h1>Hi, Joe!</h1>
<p>You are awesome!</p>
```

## Other ways

There are other ways to get templates, other than putting them in script tags.

- Loading them from a server using AJAX
- Using a build script to generate a big `views.js`

For now, we'll just use the script hack.

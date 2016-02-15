# jQuery 101 or:
# jQuery is really cool

## I know you love vanilla JavaScript but...

* Do you ever find yourself thinking vanilla JavaScript is weird, finicky, or frustrating?

* That's because it kind of is.

* You'll get used to the rules and quirks, and even learn to love them, but there **is** an easier way...sometimes.

## Sometimes working with vanilla JavaScript feels like...

![sometimes JavaScript kicks you out of a window](http://img.ccrd.clearchannel.com/media/mlib/2135/2015/05/default/bad_blood_1_0_1431953816.gif)


## What is jQuery?

* A JavaScript Library: pre-written JavaScript which allows for easier development of JS-based applications and sites.

* It's the most popular JavaScript library.

* Everything you can do in jQuery you can do in plain vanilla JavaScript -- because jQuery is written in JavaScript.

* Think of jQuery like a JavaScript toolkit: it simplifies tasks like DOM manipulation and Event Handling, but you still need to know and use JavaScript.

* It just makes some tasks a lot simpler.

## So how do I get jQuery on my page?

* Local Installation

* CDN (Content Delivery Network)

* jQuery-x.x.x.js vs jQuery.x.x.x-min.js
  - many devs will use minified for the live site and development for testing
  - that said, for now, you'll rarely pop the hood on jQuery

## jQuery Good Stuff

So you want to get an element by ID?

Vanilla JavaScript:

```javascript
var button = document.getElementByID("the-button")
```

jQuery:

```javascript
var button = $("#the-button");
```

## Or maybe you want to...

Vanilla JavaScript:
```javascript
var games = ["BioShock", "Assassin's Creed", "Mass Effect"];

for (var index = 0; index < games.length; index++) {
  var game = games[index];

  console.log("I played " + game)
};

```
jQuery:
```javascript
var games = ["BioShock", "Assassin's Creed", "Mass Effect"];

$.each(games, function(index, game) {
  console.log("I played " + game);
});
```

## Or maybe even...

Vanilla JavaScript:

```javascript
var bestAvenger = document.getElementById("best-avenger");
bestAvenger.innerText = "Black Widow";
bestAvenger.style.color = "black";
```

jQuery:

```javascript
var bestAvenger = $("#best-avenger").text("Black Widow").css("color", "black")
```

## jQuery is awesome!!!
![jQuery is awesome!!!](http://ak-hdl.buzzfed.com/static/2015-05/17/20/enhanced/webdr01/anigif_enhanced-21817-1431908634-17.gif)


## What's the $?

jQuery uses "$" as a shortcut for the function called "jQuery."


```javascript
var listItems = jQuery('li');

```

```javascript
var listItems = $('li');

```

## Chaining in jQuery

```javascript
$('#my-div').fadeIn('slow');
$('#my-div').addClass('active');
$('#my-div').css('background-color', '#6CA6CD');
```

```javascript
$('#my-div').fadeIn('slow').addClass('active').css('background-color', '#6CA6CD');
```

## jQuery Plugins

* jQuery is an extensible library

* [Flip](http://nnattawat.github.io/flip/)

* [Raptorize](http://zurb.com/playground/jquery-raptorize?timed_launch=true)

* Just remember: not all plugins are good code! Use with caution and don't bloat your page!

## So what's the downside?

* Bloated

* Sometimes CSS or vanilla JS are better choices and help avoid spaghetti code

* Not all plugins are built to a common standard

* Rapid development means updating your jQuery files...a lot

## Selecting elements

What do these do?

- `$('.menu-container')`
- `$(':input')`
- `$('li').first()`
- `$('li').last()`
- `$('ul').children()`
- `$('.menu-action').closest('.menu-container')`
- `$('textarea[maxlength]').next('.char-count')`
- `$('.selected-item').prev()`
- `$('.current-tab').siblings()`

To find out, go here:

- http://api.jquery.com/first/
- http://api.jquery.com/last/
- http://api.jquery.com/children/
- http://api.jquery.com/closest/
- http://api.jquery.com/next/
- http://api.jquery.com/prev/
- http://api.jquery.com/jquery/#jQuery-selector-context

## Manipulation

Basic content manipulation:

    `$('.user-list').html('<li>Joe Shmo</li>');`
    `$('.primary-action').text('Click me!');`

Class manipulation:

    `$('.tab').removeClass('selected-tab');`
    `$('.tab').addClass('selected-tab');`
    `$('.tab').hasClass('selected-tab');`
    `$('.menu').toggleClass('.menu-visible');`

Attribute manipulation:

    `$('button').attr('disabled');`
    `$('button').attr('disbled', 'disabled');`
    `$('button').removeAttr('disabled');`

Advanced content manipulation:

    `$('input[required]').after('<span class="required-label">*</span>');`
    `$('.user-list').append('<li>Jane Doe</li>');`
    `$('<li>Jane Doe</li>').appendTo('.user-list');`
    `$('.user-list').prepend('<li>Jane Doe</li>');`
    `$('<li>Jane Doe</li>').prependTo('.user-list');`
    `$('.user-list').before('<h2>User List:</h2>');`
    `$('<button>Are you sure?</button>').insertAfter('.delete-action');`
    `$('<button>Are you sure?</button>').insertBefore('.delete-action');`
    `$('.main-panel').replaceWith('<div>Main panel is gone!!</div>');`
    `$('.item').wrap('<div class="container"></div>');`
    `$('.item').unwrap();`
    `$('.user-list').clone();`
    `$('.current-item').remove();`

See here for more detail:

- http://api.jquery.com/category/manipulation/

## Interactive element shtuffs

    `$('input[name=firstName]').val();`
    `$('input').focus();`
    `$('input').select();`
    `$('form').submit();`

## Element positioning/sizing

    `$('button').height();`
    `$('button').outerHeight();`
    `$('div').width();`
    `$('div').outerWidth();`
    `$('.item').offset().top;`
    `$('.item').position().top;`
    `$('.item').offset().left;`
    `$('.item').position().left;`

## Events

- click
- dblclick
- focus
- blur
- change
- hover
- keydown
- keypress
- keyup
- mousedown
- mouseup
- mousemove
- mouseenter
- mouseleave
- select
- submit

What does this do?

```javascript
    $('button').click(function () {
      alert($(this).text());
    });```

//What does this do?

```javascript
    $('.container').on('click', 'button', function () {
      alert($(this).text()); // what is $(this) ?
    });```

//What does this do?

```javascript
    function myFunc() {
      alert($(this).text());
    }

    $('.container').off('click', 'button', myFunc);
```

## Style-related functions

Generally, this sort of thing should be done in CSS, and jQuery
should only be used to add/remove CSS classes. However, sometimes
it's just nice to do this quick-and-dirty stuff:

Note, that using these methods generally produces a slower site than
using CSS to do the same things. CSS takes advantage of hardware
acceleration.

    `$('.modal').fadeIn()`
    `$('.modal').fadeOut()`
    `$('.stuff').show();`
    `$('button').hide();`

## Useful jQuery Links
* [jQuery documentation](https://api.jquery.com/)

* [Unheap: jQuery Plugins Repo](http://www.unheap.com/)

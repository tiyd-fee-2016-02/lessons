# JavaScript Scope

To effectively use JavaScript, it's important to understand the concept of "scope". In JavaScript, scope refers to the context in which a piece of code is operating. Your scope determines which parts of your code are accessible at any given time.

## Scope: Local Scope

Variables defined in a function (including the function's arguments) are not
available outside of the function.

```javascript

function say(msg) {
  var x = msg.length;

  console.log(msg + ' is ' + x + ' chars long');
}

var aThingamabob = 'Hey, this is a string';
say(aThingamabob);

console.log(x); // illegal
console.log(msg); // illegal

```

## Scope: Global Scope

Variables defined outside of a function are available *everywhere* and are
called `globals`. This means it's accessible from anywhere in our code. New programmers generally start by placing everything in the global scope, but this is a bad practice that should be avoided whenever possible. Placing variables in the global scope can result in "[collisions](https://en.wikipedia.org/wiki/Collision_(computer_science))", where multiple variables react unexpectedly and break our code. We associate the global scope on webpages with the `window` object. Any functions, variables, or objects defined in the global scope are members of the `window` object.

```javascript

var foo = 'bar'; // This is available in all subsequent .js files on the page

function sayHi() {
  console.log('Hi, ' + foo); // works
}

```

## Immediately-Invoked Function Expressions (IIFEs)

We can utilize this concept of scoping to keep our code compartmentalized and reduce "collision", where multiple scripts interact unexpectedly and break our code. You'll often see entire scripts wrapped in a function expression to protect their contents. We refer to this as an [Immediately-Invoked Function Expression](http://benalman.com/news/2010/11/immediately-invoked-function-expression/), or IIFE ("iffy").

We'll talk more about these in a future lesson, but here's a simple example of what you might see in production:

```javascript
(function() {

    var name = "Alex";

    function sayMyName() {
      console.log(name);
    }

})();
```

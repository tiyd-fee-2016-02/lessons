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
called `globals`.

```javascript

var foo = 'bar'; // This is available in all subsequent .js files on the page

function sayHi() {
  console.log('Hi, ' + foo); // works
}

```

## Scope: Why?

Why is it illegal for an outer function to access the inner function's variables?

Because the inner function's variables have no values until the inner function
is called. And the inner function could be called any number of times. So,
how would the outer function know which call to the inner function it was
referring to when it accessed the inner function's variables?

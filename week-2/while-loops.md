
## while loop: break

This program will never stop!

``` js
while (true) {
    console.log('wow');
}
```

But inside the loop we can use `break` to quit the loop:

```
var x = 4;
while (true) {
    console.log(x);
    x --;
    if (x <= 0) break;
}
```

prints:

```
4
3
2
1
```
---
# for loop

For loops are like while loops but provide a place for
initialization and an expression to advance the loop.

```
for (var i = 0; i < 4; i++) {
    console.log(i);
}
```

prints:

```
0
1
2
3
```
---
Or you can jump by tens starting from 50:

``` js
for (var i = 50; i < 100; i += 10) {
    console.log(i);
}
```

prints:

```
50
60
70
80
90
```
---
# looping over an array

A very common use-case for `for` loops is to loop over each
element in an array:

``` js
var xs = [ 'a', 'b', 'c', 'd' ];
for (var i = 0; i < xs.length; i++) {
    console.log(xs[i]);
}
```

prints:

```
a
b
c
d
```
---
# functions

You can think of functions as little factories that take
input as arguments and return output.

``` js
function add (x, y) {
    return x + y;
}
console.log(add(3, 4));
```

prints:

```
7
```
---
# function hoisting

You can define a function lower down in a file than where
you use it too:

``` js
console.log(add(3, 4));

function add (x, y) {
    return x + y;
}
```
---
# function scope

Any variables declared inside a function are only accessible
inside of that function.

``` js
function fff (a, b) {
    var c = 500;
    return a + b + c;
}

console.log(fff(3,4));
console.log(c); // will raise an error
```
---
# functions as values

Functions can appear in any expression. You can assign them
to variables:

``` js
var add = function (a, b) {
    return a + b;
};
console.log(add(5, 2)); // 7
```

When you declare functions in expressions you don't need to
give them a name.

---
# higher-order functions

Because functions are ordinary values that can appear in
expressions, you can pass a function as an argument to
another function.

``` js
function binary (a, b, operator) {
    return operator(a, b);
}
function add (a, b) {
    return a + b;
}
console.log(binary(3, 4, add));
```
---
# higher-order functions: inline version

We could write the previous example with the `add` function
declared inline:

``` js
function binary (a, b, operator) {
    return operator(a, b);
}
console.log(binary(3, 4, function (a, b) {
    return a + b;
}));
```
---
# higher-order functions: everything inline why not

We could even define the binary function inline, although
this is not very readable:

``` js
console.log(
    function (a, b, operator) {
        return operator(a, b);
    }(3, 4, function (a, b) {
        return a + b;
    })
);
```
---
# higher-order functions: Array.prototype.map

There are some built-in functions that accept functions as
arguments. `.map()` takes a function that transforms the
contents of an array, creating a new array:

``` js
var first = [ 3, 4, 5 ];
var second = first.map(plusFifty);
console.log(second);

function plusFifty (x) { return x + 50 }
```

prints:

```
[ 53, 54, 55 ]
```
---
# higher-order functions: Array.prototype.forEach

You can also use `forEach` to loop over items in an array
without having to whip up a `for` loop:

``` js
[ 7, 8, 9 ].forEach(function (x) {
    console.log(x);
});
```
---
# returning a function

Functions can return any javascript value: numbers, strings,
arrays, objects, even other functions!

When you return a function from another function, the
variables you declare persist in the inner function.

``` js
function counter () {
    var times = 0;
    return function () {
        times ++;
        return times;
    };
}

var c = counter(); // c is a function
console.log(c()); // 1
console.log(c()); // 2
console.log(c()); // 3
```
---
# returning an object with functions

Another common pattern is to return an object with functions
as values:

```js
function Num (value) {
    return {
        add: function (x) {
            value += x;
            return value;
        },
        multiply: function (x) {
            value *= x;
            return value;
        };
    };
}

var n = Num(100);
console.log(n.add(5)); // 105
console.log(n.multiply(3)); // 315
```

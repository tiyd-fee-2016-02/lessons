## Intro to JavaScript

### Whitespace

In JavaScript, whitespace usually doesn't hold meaning. That means you _usually_ don't have to worry about whitespace _except for formatting for clarity_. However, whitespace is significant in situations such as:

```JavaScript
var instructor = "Kelly";
```

The whitespace between `var` and `instructor` must be present. However, all the other whitespaces were included for clarity.

### Comments

Like CSS and HTML, you can and _should_ use comments to clarify your code. The best way to comment in JavaScript is to use ``//``.

```JavaScript
// comment that code!
```

### Number

In JavaScript, there is only one type of number, which is double precision floating-point or binary floating point.

<blockquote>
According to the ECMAScript standard, there is only one number type: the double-precision 64-bit binary format IEEE 754 value (number between -(253 -1) and 253 -1). There is no specific type for integers. In addition to being able to represent floating-point numbers, the number type has three symbolic values: +Infinity, -Infinity, and NaN (not-a-number).
</blockquote> - [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures)

All you need to know for now is that a number is usually a number in JavaScript.

### String

Strings in JavaScript are used for textual information and cannot be altered (immutable).

You can add multiple strings together to make a new string, as well as alter a string using  `substr()` method, but these operations only create a new string, not altering the original.

```js

// original string
"Hello, I am a string".substr(0,5);
// "Hello" which is a new string

"I like ".concat("to code.");
// "I like to code."

```

### Boolean

<blockquote>
Boolean represents a logical entity and can have two values: true and false.
</blockquote> - [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures)

## Math

- Add `1 + 2`
- Subtract `1 - 2`
- Negate `-3`
- Divide `4 / 2`
- Multiply `4 * 2`
- Mod `4 % 2` yields the remainder (0, in this case)
- Get random number
  - Between 0 (inclusive) and 1 (exclusive) `Math.random()`
  - Between 1 and 10 (inclusive) `Math.floor(Math.random() * 10) + 1`
- [Math reference](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math)

## Variables

- Are named values
- You can change the value of a variable

```
    // Declare a variable x
    var x;


    // Assign a value to x
    x = 4;


    // Declare and assign variable y
    var y = 33;
```

### Array

[From the Cyberwizard Institute](https://github.com/cyberwizardinstitute/workshops/blob/master/javascript.markdown)

Arrays are ordered lists of values.
You can make an array with square brackets:

``` js
var arr = [ 3, 2, 5 ]
console.log(arr)
```
---
#### arrays: indexing

To get at individual elements, use square brackets and an
integer index starting from zero:

``` js
var arr = [ 1, 4, 9 ];
console.log('first:', arr[0]);
console.log('second:', arr[1]);
console.log('third:', arr[2]);
```

outputs:

```
first: 1
second: 4
third: 9
```
---
#### arrays: indexing with variables

You can use variables for indexing too, not just constant
integers:

``` js
var arr = [ 1, 4, 9 ];
var n = 2;
console.log(arr[n]);
```

prints:

```
9
```

Any expression inside the square brackets will work.

#### arrays: length

To get the length of an array, just use `.length`:

``` js
var arr = [ 1, 4, 9 ];
console.log(arr.length);
```

which is the same as:

``` js
console.log([ 1, 4, 9 ].length);
```
---
#### arrays: push

To add an item to the end of an array,
use `arr.push()`:

``` js
var arr = [ 8, 1 ];
arr.push(5);
console.log(arr);
```

prints:

```
[ 8, 1, 5 ]
```
---
`arr.push()` is an example of a builtin
method, a function you can call that has
been defined by the language itself.

Later we'll see how to inspect what
methods are available.

---
#### arrays: pop

You can also remove an element from the
end of an array with `arr.pop()`:

``` js
var xs = [ 10, 6, 3 ];
console.log('popped:', xs.pop());
console.log('now xs=', xs);
```

prints:

```
popped: 3
now xs= [ 10, 6 ]
```
---
#### arrays: shift

Remove an element from the beginning of an array with shift:

``` js
var xs = [ 1, 2, 3 ];
console.log('shifted:', xs.shift());
console.log('xs=', xs);
```
---
#### arrays: slice

Return a new array between a start index and an end index.
If you don't provide an end index, the array length is used.

``` js
var xs = [ 'a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i' ];
console.log(xs.slice(2, 3));
console.log(xs.slice(2));
```

prints:

```
[ 'c', 'd', 'e' ]
[ 'c', 'd', 'e', 'f', 'g', 'h', 'i' ]
```
---

## Functions

- A function is a named block of statements
- When you call the function, the statements run
- Can be passed inputs, can produce outputs

```
    // Define / declare function hello
    function hello(firstName, lastName) {
      var message = 'Hello, ' + firstName + ' ' + lastName;
      console.log(message);
      alert(message);
    }
```

- The code above
  - Declared a function named hello
  - Takes two arguments called `firstName` and `lastName`
  - Creates a local variable to store the hello message
  - Logs the message to the console
  - Alerts the message
  - But this code doesn't actually do anything until the function is called!

---

### Calling / invoking a function

```
    hello('Jasmine', 'Baik');
    hello('Kelly', 'Murray');
```

- Invoke a function by typing its name followed by parenthesis
- Arguments to a function go in the parenthesis
- If multiple arguments, separate them by commas
- Each time the function is called, the statements in the function block are executed


## Control Flow

### comparison operators

The comparison operators all return a boolean:

* `===` - strict equality
* `!==` - not strict equality
* `<` - less than
* `<=` - less than or equal to
* `>` - greater than
* `>=` - greater than or equal to

You might also see coercive equality operators:

* `==` - coercive equality
* `!=` - not coercive equality

but you should avoid these operators until
learning about type coercion.

### comparison operators: example

```
var x = 5;
console.log(x < 6);
console.log(x === 2);
console.log(x !== 5);
console.log(x >= 5);

// output:

// true
// false
// false
// true

```
### logical operators

* `&&` - AND
* `||` - OR
* `!` - NOT (the opposite truth value)

`!` is a "unary" operator like `++` and `--`
because it binds to a single value.

`&&` and `||` are "binary" operators
because they bind to two values:
one on the left and one on the right.
---
### logical operators: example

``` js
var x = true
var y = false
console.log(x && y) // false
console.log(x || y) // true
console.log(!(x || y)) // false
console.log(!y) // true

// outputs:

// false
// true
// false
// true
```

### if

You can make a block of code execute when
a conditional expression is true using an
`if` statement.

The conditional expression is the expression
surrounded by parenthesis following the word
`if`:

``` js
var x = 5;
if (x < 10) {
  console.log('wow');
}

// this program will print:

// wow
```
---
but if we change the program to be:

``` js
var x = 11;
if (x < 10) {
  console.log('wow');
}
```

then it won't print anything since the
conditional expression evaluated to false:

#### else

You can put an `else` statement after an
`if` statement to tell the computer what
to do if the `if` conditional expression
wasn't true:

``` js
var x = 11;
if (x < 10) {
  console.log('wow');
}
else {
  console.log('cool');
}

// will print:
// cool
```

# else if

Use `else if` to chain together fall-through cases:

``` js
var x = 22;
if (x < 10) {
  console.log('wow');
}
else if (x === 22) {
  console.log('twotwo');
}
else {
  console.log('cool');
}
```

#### nesting conditionals

``` js
var x = 5;
if (x < 5) {
  console.log('lt');
}
else {
  var y = x * 333 + 22;
  if (y > 1000) {
    console.log('y > 1000!!!');
  }
  else {
    console.log('y otherwise...');
  }
}
```

#### indentation

Now is a good time to talk about indentation.

First, you'll need to pick an amount of indentation to use
for each level.

4 spaces, 2 spaces, and tabs are all common amounts of
indentation.

#### 4 spaces

```
if (true) {
  if (true) {
    if (true) {
      // ...
    }
  }
}
```
#### 2 spaces

```
if (true) {
  if (true) {
    if (true) {
      // ...
    }
  }
}
```
#### first rule of indentation

However you choose to indent, be consistent!

Your code will be much easier for others and yourself to
read.

Remember to line up closing braces at the same level as
opening statements!


## Loops/Iteration

### for loop

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
#### looping over an array

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
## Resources

[MDN - Data Structures](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures)

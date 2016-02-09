# Objects

Objects map keys to values.

Like how a phone book maps names to telephone numbers:

```
key                     value
----------------------|---------
Benjamin Franklin     | 123-4142
Alexander Graham Bell | 214-6821
Marie Curie           | 615-2904
```

To create the same structure in javascript we could do:

``` js
var phonebook = {
    'Benjamin Franklin': '123-4142',
    'Alexander Graham Bell': '214-6821',
    'Marie Curie': '615-2904'
};
```

If a key is only letters, numbers, underscores, and dollar
signs (but doesn't start with a number), you can leave off
the quotes:

``` js
var obj = {
    abc: 555,
    def: 123,
    x1: 1000,
    y1: 5000,
    $x: 4444,
    "x y z": 12 // otherwise you'll need to use quotes
}
```

This way of building objects is sometimes called
"object literal" syntax.

## objects: pick out a single record

Once an object exists, you can reference an individual value
by its key using a `.` followed by the key name. Here we use
`obj.y` to get at the `y` key:

``` js
var obj = { x: 7, y: 8, z: 9 };
console.log(obj.y);
```

will print:

```
8
```

# objects: create a new record

Reference a key with a `.` followed by a key then use an
equal sign to create a new value under that key:

``` js
var obj = { a: 3, b: 4 };
obj.c = 5;
console.log(obj);
```

prints:

```
{ a: 3, b: 4, c: 5 }
```
---
## objects: update an existing record

The same `obj.c = 5` syntax works even if a key already
exists:

``` js
var obj = { x: 500, y: 200 };
obj.y = 300;
console.log(obj);
```

prints:

```
{ x: 500, y: 300 }
```
---
## objects: assignment operators

All of the assignment operators work for object keys just
like for variables!

``` js
var obj = { x: 500, y: 200 };
obj.y += 1000;
obj.x *= 3;
console.log(obj);
```

prints:

```
{ x: 1500, y: 1200 }
```
---
## objects: square brackets

Using the `.` operator to access keys is handy, but what
about special characters in keys?

We can use square brackets with a string to reference
keys with special characters:

```
var obj = { 'a b c': 123, 'x#y*z': 456 };
console.log(obj['a b c']);
```

prints:

```
123
```
---
## objects: square brackets

We can also use square brackets to reference dynamic keys.
For example, if we want to load a key from a variable:

``` js
var key = 'def';
var obj = {
    abc: 555,
    def: 333,
    xyz: 222
};
console.log(obj[key]);
```

prints:

```
333
```

Everything we can do with dot (updates, assignment
operators, etc) works with square bracket notation.

---
# objects: delete

To delete items from an object, use the `delete` keyword:

``` js
var obj = { a: 4, b: 5, d: 700, x: 6 };
delete obj.d;
console.log(obj);
```

prints:

```
{ a: 4, b: 5, x: 6 }
```

If you try to delete a key that doesn't exist, nothing
happens.

## Object.keys

Use `Object.keys()` to get an array of all the keys that an
object has:

``` js
var obj = { x: 5, y: 6, abc: 3 };
console.log(Object.keys(obj));
```

prints:

```
[ 'x', 'y', 'abc' ]
```

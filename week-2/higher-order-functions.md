# Higher-Order functions

A function which does one or both of the following:
* Takes another function as its input (argument)
* Returns a function as its output (return value)

```javascript
function forEach(arr, fn) {
  for (var counter = 0; counter < arr.length; ++counter) {
    fn(arr[counter]);
  }
}
forEach(['Hello', 'World'], alert);
```

## Higher-Order Functions and Arrays

Arrays have a set of really handy functions, each of which has a variant that takes a function as an argument.

`map`, `forEach`, `filter`, `reduce`, `some`, `every`, `sort`, `replace`
There are others, but these are your bread and butter. Look them up.

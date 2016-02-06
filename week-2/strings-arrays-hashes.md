# Strings, Arrays, and Hashes

---

## Programming is almost entirely about dealing with lists of things

- A `string` is a collection of characters
- An `array` is a collection of things (numbers, or strings, etc)
- A `hash` is a collection of values associated with keys

Some examples will help.

---

## Strings

```javascript
    var message = 'Hello, students!';
```

- Strings are a collection of characters
- It's how JS represents text
- Strings can be added, which concatenates them

```javascript

    var hi = 'Hello, ';
    var who = 'students';
    var message = hi + who + '!';

    // Now, message == 'Hello, students!'
```

---

## Strings (contd)

- Strings use a zero-based index
- This means,
  - you use `0` to get the first character of a string
  - you use `1` to get the second character of a string, etc
- Strings are read-only, meaning they cannot be modified

```javascript

    var message = 'Hello';
    var firstChar = message[0]; // firstChar === 'H'
    var altMessage = firstChar.toLowerCase() + message;

    // altMessage == 'hello'
```

---

## Strings have handy methods

- toUpperCase()
- toLowerCase()
- indexOf(subStr, fromIndex)
- lastIndexOf(subStr, fromIndex)
- replace(subStr, newSubstr)
- slice(beginSlice, endSlice)
- split(subStr)
- trim()

And many more:

[Deets](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)

---

## Examples

```javascript

    'hello'.replace('l', 'y'); // returns 'heyyo'
    'hello'.indexOf('l'); // returns 2
    'hello'.lastIndexOf('l'); // returns 3
    'hello'.slice(1, -1); // returns 'ell'
    'hi there'.split(' '); // returns ['hi', 'there']
    'hello'.length === 5; // is true

```

---

## Arrays

- Arrays are a collection of items
- They are zero-indexed, just like a string

```javascript

    // Here is an array containing 3 numbers
    var arr = [54, 23, 90];

    console.log(arr[0]); // logs 54
    console.log(arr[1]); // logs 23
    console.log(arr[2]); // logs 90
```

---

## Arrays (cont)

- Arrays can contain mixed types of data (numbers, strings, etc)
- You can update an array

```javascript
    var arr = [12, 'Marley Dr', 'Durham', 'NC', 27701];
    arr.length === 5; // this is true
    arr[2] = 'West Morgan St'; // update the value at position 2
```

---

## The handiest array methods

- push(item)
- pop()
- shift()
- unshift(item)
- reverse()
- sort()
- splice(start, deleteCount, itemToAdd, anotherItem, etc)
- concat(arr)
- join(subStr)
- slice(start, end)
- indexOf(item, fromIndex)
- lastIndexOf(item, fromIndex)
- forEach(fn)
- map(fn)
- filter(fn)
- every(fn)
- some(fn)
- reduce(fn, startingValue)

[And many more](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)

---

## Hashes

- Hashes are a kind of collection that is indexed by string

```javascript

    var myHash = {};

    myHash['jasmine'] = 'Jasmine Baik';
    myHash['kelly'] = 'Kelly Murray';

```

- 'jasmine' and 'kelly' are both keys
- 'Jasmine Baik' and 'Kelly Murray' are values
- You can get a value out of a hash like so:

```javascript

    console.log(myHash['jasmine']); // logs 'Jasmine Baik'

```

---

## Hashes (cont)

Hashes can be declared in a variety of ways:

```javascript
    var myHash = {
      'jasmine': 'Jasmine Baik',
      'kelly': 'Kelly Murray'
    };

    var myHash2 = {
      jasmine: 'Jasmine Baik',
      kelly: 'Kelly Murray'
    }
```

---

## Hashing rules...

- You have to put the key in quotes if it contains characters that are invalid
in a variable name

```javascript

    var myHash = {
      jasmine: 'Jasmine Baik', // This is cool
      '& the message': 'Something else' // This key needs quotes
    };

```

---

## Looping with arrays

It's pretty common to see a loop like this:

```javascript

    var arr = ['Hello', 'world', '!'];

    for (var i = 0; i < arr.length; ++i) {
      console.log(arr[i]);
    }

```

---

## Looping with hashes

To iterate through all of the keys in a hash:

```javascript

    var hashy = {
      hello: 'Hi',
      goodbye: 'Farewell'
    };

    for (var key in hashy) {
      // key === 'hello', then 'goodbye', but order is not guaranteed
      console.log(hashy[key]); // logs 'Hi', then 'Farewell'
    }

```

---

## Examples

```javascript
function sum(arr) {
  var total = 0;

  for (var i = 0; i < arr.length; ++i) {
    total += arr[i];
  }

  return total;
}
```

---

## Examples (contd)

```javascript
function distinct(arr) {
  var hash = {};
  var result = [];

  for (var i = 0; i < arr.length; ++i) {
    var item = arr[i];
    if (!hash[item]) {
      hash[item] = true;
      result.push(item);
    }
  }

  return result;
}
```

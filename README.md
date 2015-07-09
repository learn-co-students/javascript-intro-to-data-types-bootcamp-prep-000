# JavaScript Data Types

## Data Types

There are two types of data in JavaScript: 1) primatives and 2) objects.

All types except objects define immutable values (values, which are incapable of being changed). For example, Strings are immutable. We refer to values of these types as "primitive values".

#### Primative Data Types

JavaScript has a six primitive data types:

  1. Number
    - Examples include: `1`, `3.14`, `0.13`, `100`, ...
    - The largest number in JavaScript is `9007199254740992`. Similarly, the smallest number is -`9007199254740992` (see [here](http://stackoverflow.com/a/307200/2890716) for more info.

  2. String
    - Examples include:  `"a"`, `"World Wide Web"`

  3. Boolean
    - Only two examples: `true` and `false`
`
  4. Undefined
    - Only one example: `undefined`
    - Refers to an absent or unknown value

  5. Null
    - Only one example: `null`
    - This is a special keyword that means one of two things: no value or empty.  The difference from undefined is that when a variable is null, it is still defined.

  6. Symbol type
   - New (!) to JavaScript in ECMAScript Edition 6. Instead of creating new symbols with the `:` as we do in Ruby, you can make a new symbol by calling on the Symbol class and passing it a string:
   - `var greeting = Symbol("hello");`
   - `typeof sym;     // "symbol"`

#### Objects

In JavaScript, objects can be seen as a collection of properties. You can think of them as most similar to Ruby's hashes, but with superpowers of storing functions as values in addition to the standard strings, numbers, etc. We'll go over objects in more depth later, so for now just know that if you see something like this:

```javascript
var linkedInUser = {
  "name": "Adam Enbar",
  "position": "Co-Founder & CEO",
  "education": "Harvard Business School",
  "url": "http://www.adamenbar.com/",
  "connectionNum": 534
}
```

## Resources

* [MDN - JavaScript Data Structures](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures)

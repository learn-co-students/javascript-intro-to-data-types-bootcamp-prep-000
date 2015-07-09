# JavaScript Data Types

## About

There are two types of data in JavaScript: 1) primatives and 2) objects.

All types except objects define immutable values (values, which are incapable of being changed). For example, Strings are immutable. We refer to values of these types as "primitive values".

## Primative Data Types

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

```javascript
var greeting = Symbol("hello");
typeof sym; // Returns "symbol"
```

#### 1. Numbers

Unlike most programming languages JS uses floats by default. And creating literal numbers uses the Number Constructor. New numbers can optionally have decimal points with trailing zeros, but keep in mind they are floats either way.

Sometimes this can lead to unexpected consequences, which can generally be solved with `Math.floor`.  Note when comparing integers to unknown numbers it is best practice to floor the unknown because some floats are equal to the integer.

```javascript
4 === 4.0;                               // Returns true

Math.floor(4.00001);                     // Returns 4

4.0000000000000001 === 4;                // Returns true

Math.floor(4.0000000000000001); === true // safer!
```

#### 2. Strings

Strings are very straight forward in JS.  They are collections of characters.  Plus signs are used to concatenated strings.

JS does not support string interpolation like some other languages (i.e. Ruby). Concatenating strings coerces the types of the objects into strings if they are not already.

```javascript
'Hello ' + 'World';  // Returns 'Hello World'

'High ' + 5 + '!!!'; // Returns 'High 5!!!'
```

#### 3. Booleans

Booleans (**true** or **false** values) are fairly straight forward in JS; however, there are some quirks that you should be aware of.

Unlike in Ruby, booleans in JavaScript can be cast into numbers. The numbers 1 and 0 also follow boolean logic, so 1 is loosely equal to true and 0 is loosely equal to false. (1 and 0 can also be cast into true and false respectively). For example:

```javascript
!!0        // Returns false 

+ true     // Returns 1 

0 == false // Returns true 

!!1        // Returns true
```

#### 4. Undefined and 5. Null (and NaN)

`undefined` represents the absence of a primitve value while `null` represents the absence of an object.

NaN represents an error from the improper use of a math operator.  NaN is the only thing in JS that is not equal to itself. To check for NaN use the `isNaN()` function.

```javascript
1 - 'three' // Returns NaN
NaN === NaN // Returns false
isNaN(NaN)  // Returns true
```

#### 6. Symbols

Symbols are so new to JavaScript that you probably won't see or interact with them much unless you intentionally incoporate them into new code. To read more about symbols, see []()

## Objects

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

# JavaScript Data Types

In this lesson, we'll cover all the different data types in JavaScript.

## Objectives
- Define "data type"
- Explain different data types in JavaScript
- Use the `typeof` operator

## What is a data type?

At the machine level, all data on a computer is bits — 1s and 0s. Humans, it turns out, prefer not to work so close to the metal, so we have _data types_ for describing different bits of information. Data types give us a quick way of understanding how we can operate on a given bit of data.

## The `typeof` Operator

JavaScript provides an operator, [`typeof`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/typeof), which returns a string representing the type of an object.

``` javascript
typeof "foo" // 'string'
typeof true  // 'boolean'
```

Note that `typeof` is an _operator_, not a _function_. You'll come to appreciate this distinction more fully later on, but for now know that it means that `typeof("foo")` works because you're just wrapping `"foo"` in parentheses — `typeof "foo"` is just fine.

## The Types

In JavaScript, we have the following _primitive_ types:

+ Number
+ String
+ Boolean
+ Undefined
+ Null
+ Symbol (new in [ECMAScript 6](https://developer.mozilla.org/en-US/docs/Web/JavaScript/New_in_JavaScript/ECMAScript_6_support_in_Mozilla))

By "primitive type" we mean data that is not an object (more on that in a sec) and has no methods (more on that later).

In addition to the above primitive types, JavaScript also has a type called `Object`.

### Numbers

Unlike most programming languages, JS uses floats by default. New numbers can optionally have decimal points with trailing zeros, but keep in mind they are floats either way.

Sometimes this can lead to unexpected consequences:

```javascript
4 === 4.0;                               // Returns true

Math.floor(4.00001);                     // Returns 4

4.0000000000000001 === 4;                // Returns true(!)

Math.floor(4.0000000000000001) === 4     // Returns true
```

`Math.floor()` rounds a decimal _down_ to the nearest integer. Similarly, `Math.ceil()` rounds a decimal _up_ to the nearest integer. There's also `Math.round()`, which rounds a decimal according to traditional rounding rules (e.g., `Math.round(5.4)` is `5` and `Math.round(5.5)` is `6`).

Keep in mind that in JavaScript, `NaN` (which stands for "not a number") has the `Number` data type. (More on that below.)

#### `NaN`

`NaN`, standing for "Not A Number", represents the improper use of a math operator. It is a special value used to denote an unrepresentable value. `NaN` is the only thing in JS that is not equal to itself. To check for `NaN` use the `isNaN()` function. `isNan()` will return `false` if the argument can be operated on. For example, we saw earlier that `0 + true` returns `1`. Therefore, `isNan(true)` will return false, because `true` can be used in mathematical expressions.

```javascript
1 - 'three'    // Returns NaN
NaN === NaN    // Returns false
isNaN(NaN)     // Returns true
isNaN("Hello") // Returns true
isNaN(42)      // Returns false
isNaN(true)    // Returns false
```

To read more about `NaN`, see the *A Drip of Javascript*'s post titled [The Problem with Testing for NaN in JavaScript](http://adripofjavascript.com/blog/drips/the-problem-with-testing-for-nan-in-javascript.html).

### Strings

Strings are very straight forward in JavaScript. They are collections of characters. Plus signs are used to concatenate strings.

As of ECMAScript 6, JavaScript supports string interpolation in [template literals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals). Template literals (and ES6 generally) isn't quite fully implemented in all modern browsers, but you can try out many of these features in the latest builds of Chrome, FireFox, and Safari.

```javascript
'Hello ' + 'World';  // Returns 'Hello World'

'High ' + 5 + '!!!'; // Returns 'High 5!!!'

var person = "Pat"

// template literal
`Hey there, ${person}!` // 'Hey there, Pat!'
```

### Booleans

Booleans (`true` or `false` values) are fairly straight forward in JS; however, there are some quirks that you should be aware of.

Booleans in JavaScript can be _cast_ into numbers. We "cast" data when we change its type from one primitive to another. The numbers `1` and `0` also follow boolean logic, with `1` being "truthy" and `0` being "falsey". `1` and `0` can also be cast into `true` and `false` respectively. For example:

```javascript
!!0        // Returns false

+ true     // Returns 1

+ false    // Returns 0

!!1        // Returns true
```

### Undefined

In JavaScript, `undefined` is a property of the global object (`window` in the browser — go ahead, try exploring `window` in your browser's console). The primitive `undefined` is used in several cases:

1. If a variable has not been assigned a value, it is `undefined`.
2. If a function does not return a value, it returns `undefined`.

```javascript
var greeting;
greeting;         // Returns undefined
typeof greeting   // Returns undefined

function greet() {
  // don't return anything
}

greet() // Returns undefined
```

### Null

While `undefined` represents the absence of a primitive *value*, `null` represents the absence of an object. It can be assigned to a variable as a representation of no value:

```javascript
var example = null;
example;         // Returns null
typeof example;  // Returns object
```

From the preceding examples, it is clear that `undefined` and `null` are two distinct types: `undefined` is a type itself (`undefined`) while `null` is an object. To read more about the difference between `undefined` and `null`, see [this StackOverflow post](http://stackoverflow.com/q/5076944/2890716).

### Symbols

Symbols are so new to JavaScript that you probably won't see or interact with them much unless you intentionally incorporate them into new code. Symbols are a unique and immutable data type which straddle the two worlds of objects and strings.

Here's an excerpt from MDN's [blog post about symbols](https://hacks.mozilla.org/2015/06/es6-in-depth-symbols/):

> Symbols aren’t exactly like anything else. They’re immutable once created. You can’t set properties on them (and if you try that in strict mode, you’ll get a TypeError). They can be property names. These are all string-like qualities.

> On the other hand, each symbol is unique, distinct from all others (even others that have the same description) and you can easily create new ones. These are object-like qualities.

> ES6 symbols are similar to the more traditional symbols in languages like Lisp and Ruby.

To read more about symbols, see [the MDN docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol) or [this StackOverflow post](http://stackoverflow.com/q/21724326/2890716).

## Resources

* [MDN - JavaScript Data Structures](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures)
* [MDN - undefined](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined)

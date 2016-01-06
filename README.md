# JavaScript Data Types

JavaScript has many of the same data types as Ruby, and a few we've never seen before. In this lesson, we'll cover all the different data types in JavaScript.

## Objectives
+ List the JS datatypes

## Overview


* About
* Primitive Data Types
  1. Number
  2. String
  3. Boolean
  4. undefined
  5. Null
  6. Symbol
* Objects
* Errors in Brief

## The Types

JavaScript's data types are:

+ Number
+ String
+ Boolean
+ Undefined
+ Null
+ Symbol


### Numbers

Unlike most programming languages JS uses floats by default. And creating literal numbers uses the Number Constructor. New numbers can optionally have decimal points with trailing zeros, but keep in mind they are floats either way.

Sometimes this can lead to unexpected consequences, which can generally be solved with `Math.floor()`, which rounds the number down to the whole number.  Note when comparing integers to unknown numbers it is best practice to floor the unknown because some floats are equal to the integer.

```javascript
4 === 4.0;                               // Returns true

Math.floor(4.00001);                     // Returns 4

4.0000000000000001 === 4;                // Returns true

Math.floor(4.0000000000000001); === true // safer!
```

### Strings

Strings are very straight forward in JavaScript.  They are collections of characters.  Plus signs are used to concatenate strings.

JavaScript does not support string interpolation like some other languages (i.e. Ruby). Concatenating strings coerces the types of the objects into strings if they are not already.

```javascript
'Hello ' + 'World';  // Returns 'Hello World'

'High ' + 5 + '!!!'; // Returns 'High 5!!!'
```

### Booleans

Booleans (`true` or `false` values) are fairly straight forward in JS; however, there are some quirks that you should be aware of.

Unlike in Ruby, booleans in JavaScript can be cast into numbers. The numbers `1` and `0` also follow boolean logic, with `1` being "truthy" and `0` being "falsey". `1` and `0` can also be cast into `true` and `false` respectively. For example:

```javascript
!!0        // Returns false 

+ true     // Returns 1

+ false // Returns 0

!!1        // Returns true
```

### Undefined 

In JavaScript, `undefined` means a variable has been declared but has not yet been assigned a value, such as:

```javascript
var greeting;
greeting;         // Returns undefined
typeof(greeting); // Returns undefined
```

### Null

While `undefined` represents the absence of a primitive *value*, `null` represents the absence of an object. You can think of `null` as JavaScript's version of `nil` in Ruby. It can be assigned to a variable as a representation of no value:

```javascript
var example = null;
example;         // Returns null
typeof(example); // Returns object
```

From the preceding examples, it is clear that `undefined` and `null` are two distinct types: `undefined` is a type itself (`undefined`) while `null` is an object. To read more about the difference between `undefined` and `null`, see [this StackOverflow post](http://stackoverflow.com/q/5076944/2890716).

###. Symbols

Symbols are so new to JavaScript that you probably won't see or interact with them much unless you intentionally incorporate them into new code. As with Ruby, symbols are a unique and immutable data type which straddle the two worlds of objects and strings. 

Here's an excerpt from MDN's [blog post about symbols](https://hacks.mozilla.org/2015/06/es6-in-depth-symbols/):

> Symbols aren’t exactly like anything else. They’re immutable once created. You can’t set properties on them (and if you try that in strict mode, you’ll get a TypeError). They can be property names. These are all string-like qualities.

> On the other hand, each symbol is unique, distinct from all others (even others that have the same description) and you can easily create new ones. These are object-like qualities.

> ES6 symbols are similar to the more traditional symbols in languages like Lisp and Ruby.

To read more about symbols, see [the MDN docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol) or [this StackOverflow post](http://stackoverflow.com/q/21724326/2890716).


## Errors in Brief

Let's think back to Ruby. Ruby has standard errors ranging from type errors to syntax errors. Take a look at the example below:

```ruby
1 + "7"
TypeError: String can't be coerced into Fixnum
```

Just like Ruby, JavaScript also has errors. Here are some examples: EvalErrors, RangeErrors, SyntaxErrors, and TypeErrors. For instance, if you forget to pass the function `typeOf()` an argument, you'll get a syntax error:

```javascript
typeof(); // Returns Uncaught SyntaxError: Unexpected token )
```

#### NaN

`NaN`, standing for Not-A-Number, represents the improper use of a math operator. It is a special value used to denote an unrepresentable value. `NaN` is the only thing in JS that is not equal to itself. To check for `NaN` use the `isNaN()` function. `isNan()` will return `false` if the argument can be operated on. For example, we saw earlier that `0 + true` returns `1`. Therefore, `isNan(true)` will return false, because `true` can be used in mathematical expressions. 

```javascript
1 - 'three' // Returns NaN
NaN === NaN // Returns false
isNaN(NaN)  // Returns true
isNaN("Hello") // Returns true
isNaN(42) // Returns false
isNaN(true) // Returns false
```
To read more about `NaN`, see *A Drip of Javascript*'s post titled [The Problem with Testing for NaN in JavaScript](http://adripofjavascript.com/blog/drips/the-problem-with-testing-for-nan-in-javascript.html).

## Resources

* [MDN - JavaScript Data Structures](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures)

<a href='https://learn.co/lessons/intro-to-data-types.js' data-visibility='hidden'>View this lesson on Learn.co</a>

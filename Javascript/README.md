# Javascript Learning Guide: Beginner to Expert

Welcome to the Javascript Learning Guide! This document will help you navigate through the journey of mastering Javascript, from the basics to advanced concepts.

## Table of Contents

1. [Introduction to Javascript](#introduction-to-javascript)
2. [All About Variables](#all-about-variables)
3. [DataTypes](#datatypes)
4. [Type Casting](#type-casting)
5. [Data Structure](#data-structure)
6. [Equality Comparisons](#equality-comparisons)
7. [Loops and Iterations](#loops-and-iterations)
8. [Control Flow](#control-flow)
9. [Expressions & Operators](#expressions--operators)
10. [Functions](#functions)
11. [DOM APIs](#dom-apis)
12. [Strict Mode](#strict-mode)
13. [Using(this) keyword](#usingthis-keyword)
14. [Asynchronous Javascript](#asynchronous-javascript)
15. [Working with APIs](#working-with-apis)
16. [Classes](#classes)
17. [Iterators & Generators](#iterators--generators)
18. [Modules in javascript](#modules-in-javascript)
19. [Memory Management](#memory-management)
20. [Using browser DevTools](#using-browser-devtools)

---

## Introduction to Javascript

### Introduction to JavaScript

JavaScript is a versatile programming language primarily used to create interactive and dynamic experiences on web pages. This document covers the basics including what JavaScript is, its history, various versions, and how to run it.

### What is JavaScript?

JavaScript is a **lightweight, interpreted scripting language** widely used in web development. It enables dynamic content updates, interactive forms, animations, and much more — all running directly in the web browser.

**Key Features:**

- Interpreted and dynamically typed
- Runs in the browser (client-side) or on the server (via Node.js)
- Supports object-oriented, functional, and event-driven programming styles
- Prototype-based inheritance
- Asynchronous programming using callbacks, promises, and `async/await`

### History of JavaScript

JavaScript was created by **Brendan Eich** in **1995** during his time at **Netscape Communications**. Originally called **Mocha**, then **LiveScript**, it was finally renamed **JavaScript** — a marketing move to capitalize on Java's popularity.

It was standardized by **ECMA International** and became known as **ECMAScript**.

**Key Milestones:**

- **1995**: Created at Netscape
- **1997**: First standardized version (ECMAScript 1)
- **2009 (ES5)**: Brought strict mode and JSON support
- **2015 (ES6/ES2015)**: Major overhaul with modern syntax and features
- **Present**: Updated annually with new features and improvements

## JavaScript Versions

JavaScript evolves through versions defined by the **ECMAScript** specification.

| Version | Year  | Highlights                                                  |
| ------- | ----- | ----------------------------------------------------------- |
| ES1     | 1997  | Initial release                                             |
| ES3     | 1999  | Regular expressions, better error handling                  |
| ES5     | 2009  | Strict mode, JSON support, getters/setters                  |
| ES6     | 2015  | `let`, `const`, arrow functions, classes, promises, modules |
| ES7+    | 2016+ | Async/await, includes, optional chaining, etc.              |
| ES14    | 2023  | New array methods: `toSorted()`, `toReversed()` etc.        |

### How to Run JavaScript

JavaScript can be run in multiple environments:

1. **In the Browser**

- Most common usage.
- Every modern browser has a built-in JS engine (e.g., Chrome's V8).
- You can run JS:
  - In HTML via `<script>` tag
  - In the browser's DevTools Console

**Example:**

```html
<script>
  alert("Hello from JavaScript!");
</script>
```

2. **With Node.js (Server-side)**

- Use JavaScript outside the browser.
- Great for backend services, tools, and scripting.

  **Install Node.js**, then run:

  ```bash
  node script.js
  ```

  **Example:**

  ```javascript
  console.log("Running
  JavaScript with Node.js!");
  ```

3. **Online Editors**

- CodePen
- JSFiddle
- PlayCode
- Replit

### Task 1:

Create a webpage with a button that shows an alert that says:

“You clicked the button!”

## All About Variables

Variables in JavaScript are used to store data that can be used and manipulated later. Think of them as labeled boxes you can put stuff in.

### Variable Declaration

JavaScript allows declaring variables using three keywords:

1. **`var` (old way)**

- Introduced in ES1.
- Function-scoped (not block-scoped).
- Can be redeclared and reassigned.
- Subject to hoisting (more on this below).

```javascript
var name = "Alice";
var name = "Bob"; // Allowed
```

2. **`let` (modern, ES6+)**

- Block-scoped.
- Cannot be redeclared in the same scope.
- Can be reassigned.

```javascript
let age = 25;
// let age = 30; // ❌ SyntaxError
age = 30; // ✅ Works
```

3. **`const` (modern, ES6+)**

- Block-scoped.
- Cannot be redeclared or reassigned.
- Must be initialized at the time of declaration.
- Does not make the variable immutable — only the binding is constant.

```javascript
const PI = 3.14;
// PI = 3.14159; // ❌ Error
```

### Hoisting

Hoisting is JavaScript's behavior of moving declarations to the top of their scope during compilation phase — but only the declaration, not the assignment.

**Example with `var`:**

```javascript
console.log(greeting); // undefined (not error!)
var greeting = "Hello";
```

**With let/const:**

```javascript
console.log(greeting); // ❌ ReferenceError
let greeting = "Hello";
```

- let and const are hoisted too, but they're in a "temporal dead zone" — they can't be accessed before declaration.

### Variable Naming Rules

JavaScript variable names Can:

- Start with a letter, \_, or $
- Contain digits, letters, \_, $

Cannot:

- tart with a number
- Be a reserved keyword (e.g., if, for, let)

**Examples:**

```javascript
let \_name = "valid";
let $price = 20;
let user1 = "John";
let 1user = "invalid"; // ❌
let let = "bad"; // ❌
```

- Use camelCase for variable names by convention: firstName, totalPrice

### Variable Scopes

Scope defines where a variable is accessible. In JavaScript, we have:

1. **Block Scope**

- Variables declared with let and const are scoped to the nearest pair of {}.
- var is not block-scoped.

```javascript
{
  let x = 10;
  const y = 20;
  // var z = 30; // Accessible outside
}
// console.log(x); // ❌ ReferenceError
```

2. **Function Scope**

- Variables declared inside a function are only accessible inside that function.

```javascript
function testScope() {
  var a = 1;
  let b = 2;
  const c = 3;
}
// console.log(a); // ❌ Not accessible
```

3. **Global Scope**

- Declared outside any function/block.
- Accessible everywhere in the script.

```javascript
var globalVar = "I'm global";
function showVar() {
  console.log(globalVar); // ✅ Accessible
}
```

- Good practice: **Avoid polluting global scope** to reduce bugs.

### Task 2:

1. Declare a variable using `let` called `favoriteColor` and assign your favorite color to it. Then `console.log()` it.

2. Try declaring a constant using `const` for your birth year. Then try to change it and see what error shows up.

3. Create three variables:

- firstName → your name
- lastName → your surname
- fullName → combine the first and last name with a space between, and `console.log()` the result

## DataTypes

In JavaScript, data types represent different kinds of values. They are broadly categorized into:

1. Primitive Types – Simple, immutable values
2. Objects – Complex data structures

### Primitive Data Types

Primitive types are not objects and have no methods (though they behave like they do due to auto-boxing). There are 7 primitive data types in JavaScript:

1. **String**

- A sequence of characters (text).
- Can be enclosed in `single`, `double`, or `backticks` (template literals).

```javascript
let name = "Alice";
let greeting = `Hello, ${name}!`; // Template literal
```

2. **Undefined**

- A variable that has been declared but not assigned a value.

```javascript
let x;
console.log(x); // undefined
```

3. **Number**

- Represents both integers and floating-point numbers.
- Special values: `Infinity`, `-Infinity`, and `NaN`.

```javascript
let a = 42;
let b = 3.14;
let c = NaN; // Not a Number
```

4. **BigInt (ES11)**

- For integers larger than Number.MAX_SAFE_INTEGER.

```javascript
let big = 1234567890123456789012345678901234567890n;
```

5. **Boolean**

- Represents logical values: true or false.

```javascript
let isOnline = true;
```

6. **Null**

- Intentionally empty or "nothing" value.
- Type is object (legacy quirk).

```javascript
let data = null;
```

7. **Symbol (ES6)**

- Unique and immutable identifiers, often used as object keys.

```javascript
let id = Symbol("id");
```

### Object

Objects are collections of key-value pairs and can contain any type of value (including functions, arrays, and other objects).

1. **Basic Object:**

```javascript
let person = {
  name: "John",
  age: 30,
  greet() {
    console.log("Hi!");
  },
};
```

2. **Object Prototypes**

- All JavaScript objects inherit from a prototype object. This is how shared properties and methods are managed.

```javascript
let obj = {};
console.log(obj.toString()); // Inherited from Object.prototype
```

3. **Prototypal Inheritance**

- Objects can inherit from other objects. This is known as prototypal inheritance.

```javascript
let animal = {
  eats: true,
};
let rabbit = Object.create(animal);
console.log(rabbit.eats); // true
```

4. **Built-in Objects**

   JavaScript has many built-in objects, including:

   - `Object`
   - `Array`
   - `Function`
   - `Date`
   - `RegExp`
   - `Math`
   - `JSON`
   - `Map`, `Set`, `WeakMap`, `WeakSet`

```javascript
let today = new Date();
let numbers = [1, 2, 3];
```

### typeof Operator

The typeof operator is used to check the type of a value.

```javascript
console.log(typeof "hello"); // "string"
console.log(typeof 42); // "number"
console.log(typeof null); // "object" (bug in JS)
console.log(typeof undefined); // "undefined"
console.log(typeof {}); // "object"
console.log(typeof Symbol("id")); // "symbol"
```

### Task 3:

1. Identify the Data Types: Write a script that logs the `typeof` for the following values:

```javascript
"JavaScript";
42;
true;
undefined;
null;
1234567890123456789012345678901234567890n;
Symbol("sym");
{
}
```

2. Create and Access Object Properties: Create an object representing a car with the following properties:

- `make`
- `model`
- `year`
- A method `start()` that logs "Engine started" to the console

3. Explore Prototypal Inheritance: Create an object `animal` with a property `canEat: true`. Then create another object `dog` that inherits from `animal` and adds its own property `barks: true`. Log both properties from the `dog`.

4. Use typeof in a Function: Write a function `checkType(value)` that returns a string like:

```js
"The type of value is string";
```

## Type Casting

## Data Structure

## Equality Comparisons

## Loops and Iterations

## Control Flow

## Expressions & Operators

## Functions

## DOM APIs

## Strict Mode

## Using(this) keyword

## Asynchronous Javascript

## Working with APIs

## Classes

## Iterators & Generators

## Modules in javascript

## Memory Management

## Using browser DevTools

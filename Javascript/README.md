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

Type casting (or type conversion) refers to changing a value from one data type to another. In JavaScript, this happens in two ways:

### Type Conversion vs Type Coercion

| Aspect            | Type Conversion (Explicit) | Type Coercion (Implicit)        |
| ----------------- | -------------------------- | ------------------------------- |
| Who initiates it? | Developer (manual)         | JavaScript engine               |
| How is it done?   | Using functions/methods    | Automatically during operations |
| Example           | `Number("123")`            | `"5" \* 2 → 10`                 |

### Implicit Type Casting (Coercion)

JavaScript automatically converts values from one type to another when needed, especially in operations like addition or comparison.

**Examples:**

```javascript
console.log("5" + 1); // "51" → Number is coerced to String
console.log("5" - 1); // 4 → String is coerced to Number
console.log(true + 1); // 2 → true is coerced to 1
console.log(null + 1); // 1 → null is coerced to 0
console.log(undefined + 1); // NaN
```

#### Coercion Rules (Simplified):

- String + anything = string (except with `Symbol`)
- Boolean to number: `true → 1`, `false → 0`
- `null → 0`, `undefined → NaN`
- Objects → primitives via `.valueOf()` or `.toString()`

### Explicit Type Casting (Conversion)

You manually convert a value from one type to another using functions or constructors.

1. **To Number**

```javascript
Number("123"); // 123
parseInt("123px"); // 123
parseFloat("3.14"); // 3.14
+"42"; // 42 (unary plus)
```

2. **To String**

```javascript
String(123); // "123"
(123).toString(); // "123"
true.toString(); // "true"
```

3. **To Boolean**

```javascript
Boolean(0); // false
Boolean(""); // false
Boolean("hello"); // true
!!"JavaScript"; // true (double negation trick)
```

#### Common Pitfalls

| Code                | Output              | Why?                                 |
| ------------------- | ------------------- | ------------------------------------ |
| `"5" + 1`           | `"51"`              | String concatenation                 |
| `"5" - 1`           | `4`                 | Coerces "5" to number                |
| `null == undefined` | `true`              | Loose equality treats them the same  |
| `[] + {}`           | `"[object Object]"` | `[]` coerced to `""`, `{}` to string |
| `true + false`      | `1`                 | true → 1, false → 0                  |

### Task 4:

1. Predict Output: What will the following log?

```javascript
console.log("10" + 1);
console.log("10" - 1);
console.log(true + false);
console.log(null == undefined);
console.log(Number("abc"));
```

2. Convert Manually: Write code that

- Converts `"123"` to a number
- Converts `false` to a string
- Converts `0` to a boolean

3. Type Check Function: Create a function that takes any input and returns:

```javascript
"The input is of type: string and its value is: hello";
```

## Data Structure

Data structures help organize and store data efficiently. JavaScript offers built-in structures suited for different needs.

### Keyed Collections

Keyed collections store data in pairs (key → value). They allow fast access, insertion, and deletion.

1. **Map**

- Stores key-value pairs.
- Keys can be of any type (including objects).
- Maintains insertion order.

```javascript
const map = new Map();
map.set("name", "Alice");
map.set(42, "Answer");
map.set({ id: 1 }, "Object Key");

console.log(map.get("name")); // Alice
console.log(map.size); // 3
```

Use Map when:

- You need ordered entries.
- Keys are of various types.

2. **WeakMap**

- Similar to Map, but:
  - Only allows objects as keys.
  - Keys are weakly referenced (not prevented from garbage collection).
- Not iterable.

```javascript
let obj = {};
let weakMap = new WeakMap();
weakMap.set(obj, "Secret");

console.log(weakMap.get(obj)); // Secret
obj = null; // Entry is removed automatically
```

Use WeakMap for:

- Private data storage per object.
- Memory-efficient designs (like DOM node metadata).

3. **Set**

- Stores unique values.
- Can hold any type of value.
- Maintains insertion order.

```javascript
const set = new Set([1, 2, 2, 3]);
set.add(4);

console.log(set.has(2)); // true
console.log(set.size); // 4
```

Use Set when:

- You need unique elements.
- You want fast existence checking.

4. **WeakSet**

- Stores objects only.
- Each object appears only once.
- Weakly referenced (non-preventative for garbage collection).
- Not iterable.

```javascript
let person = { name: "Eve" };
const weakSet = new WeakSet();
weakSet.add(person);

console.log(weakSet.has(person)); // true
person = null; // Garbage collected
```

Use WeakSet for:

- Tracking object presence privately.
- Memory-sensitive lists.

### Structured Data

1. **JSON (JavaScript Object Notation)**

- Lightweight format for storing and exchanging data.
- Easy to convert to and from JavaScript objects.

```javascript
const obj = { name: "Alice", age: 30 };
const jsonStr = JSON.stringify(obj); // To JSON
console.log(jsonStr); // {"name":"Alice","age":30}

const parsedObj = JSON.parse(jsonStr); // From JSON
console.log(parsedObj.name); // Alice
```

Use JSON for:

- Sending/receiving data from a server.
- Saving structured data (e.g., in localStorage).

### Indexed Collections

Collections that use numerical indexes to access items.

1. **Arrays**

- Standard list-like objects.
- Can hold any type of element.

```javascript
const fruits = ["apple", "banana", "cherry"];
console.log(fruits[1]); // banana
fruits.push("date");
console.log(fruits.length); // 4
```

Use Arrays for:

- Lists, queues, stacks.
- General-purpose collection handling.

2. **Typed Arrays**

- Provide a way to work with binary data.
- Represented by views (e.g., `Int8Array`, `Float32Array`) over `ArrayBuffer`.

```javascript
let buffer = new ArrayBuffer(4); // 4 bytes
let intView = new Int32Array(buffer);
intView[0] = 42;

console.log(intView[0]); // 42
```

Use Typed Arrays when:

- Working with binary streams, files, or performance-critical tasks (e.g., WebGL, audio).

### Task 5:

1. Map Practice

- Create a Map to store the capital cities of countries
- Add at least 3 countries with their capitals
- Retrieve and print one capital
- Bonus: Try looping over the Map and printing all countries and capitals.

2. WeakMap Practice

- Create an object 'user'
- Add it as a key in a WeakMap with some secret info
- Retrieve the secret info
- Bonus: Set user = null and test what happens.

3. Set Practice

- Create a Set with some numbers, including duplicates
- Add a new number, remove one number, and check existence of a number
- Bonus: Convert a Set to an array.

4. WeakSet Practice

- Create two object variables
- Add them to a WeakSet
- Check if one of them exists in the WeakSet

5. JSON Practice

- Create a JavaScript object with your profile info (name, age, skills)
- Convert it to a JSON string
- Then parse it back to an object and log one property
- Bonus: Save the JSON string to localStorage (in browser).

6. Array Practice

- Create an array of your 5 favorite movies
- Add a new movie, remove one, and sort the array alphabetically
- Bonus: Use a loop to print all movies in uppercase.

7. Typed Array Practice

- Create a buffer and a typed array (Int16Array or Float32Array)
- Store a few values and print them
- Bonus: Try modifying values in the buffer directly.

8. Challenge Task

- Create an array of objects, each representing a student (name, score)
- Use a Map to store each student's name as key and their score as value
- Convert the array to JSON and back
- Find the average score

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

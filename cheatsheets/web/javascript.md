# JavaScript

## 📚 Table of Contents

- [JavaScript](#javascript)
  - [📚 Table of Contents](#-table-of-contents)
  - [📦 Variables](#-variables)
  - [🔀 Conditionals](#-conditionals)
  - [🔁 Loops](#-loops)
  - [🧩 Functions](#-functions)
  - [⚡ Arrow Functions vs Regular Functions](#-arrow-functions-vs-regular-functions)
  - [✂️ String \& Array Methods](#️-string--array-methods)
  - [🎯 Array \& Object Tricks](#-array--object-tricks)
  - [🧱 Classes](#-classes)
  - [📦 Modules](#-modules)
  - [✅ Unit Tests (with Jest)](#-unit-tests-with-jest)
  - [Semicolon ";"](#semicolon-)

## 📦 Variables

```js
let count = 0;        // mutable
const name = 'Melina'; // immutable
var oldWay = true;    // avoid using 'var' in modern JS
```

## 🔀 Conditionals

```js
if (score > 80) {
  console.log('Great!');
} else if (score > 50) {
  console.log('Okay');
} else {
  console.log('Try again');
}

// Ternary
const result = score >= 60 ? 'Pass' : 'Fail';
```

## 🔁 Loops

```js
// Classic for loop
for (let i = 0; i < 5; i++) {
  console.log(i);
}

// for...of (arrays)
for (const item of ['a', 'b', 'c']) {
  console.log(item);
}

// for...in (object keys)
const user = { name: 'Melina', age: 28 };
for (const key in user) {
  console.log(key, user[key]);
}

// Array methods
['a', 'b'].forEach(item => console.log(item));
```

## 🧩 Functions

```js
// Function declaration
function greet(name) {
  return `Hello, ${name}`;
}
```

## ⚡ Arrow Functions vs Regular Functions

```js
// Regular function
function greet(name) {
  return `Hello, ${name}`;
}

// Arrow function - equivalent
const greetArrow = name => `Hello, ${name}`;

// Regular function with multiple lines
function square(x) {
  return x * x;
}

// Arrow function with multiple lines (needs return)
const squareArrow = x => {
  return x * x;
};

// No parameters
function sayHi() {
  console.log('Hi!');
}

const sayHiArrow = () => {
  console.log('Hi!');
};
```

## ✂️ String & Array Methods

```js
// Slice
const text = 'JavaScript';
console.log(text.slice(0, 4)); // 'Java'

// Replace
const greeting = 'Hello world';
console.log(greeting.replace('world', 'Melina')); // 'Hello Melina'

// ReplaceAll
const messy = 'apple, apple, apple';
console.log(messy.replaceAll('apple', 'orange')); // 'orange, orange, orange'

// Array slicing
const arr = [10, 20, 30, 40, 50];
console.log(arr.slice(1, 4)); // [20, 30, 40]
```

## 🎯 Array & Object Tricks

```js
const nums = [1, 2, 3];
const doubled = nums.map(n => n * 2);

const user = { name: 'Melina', age: 28 };
const { name } = user;  // object destructuring

const copy = { ...user, age: 29 }; // object spread
```

## 🧱 Classes

```js
class Person {
  constructor(name) {
    this.name = name;
  }

  speak() {
    return `Hi, I'm ${this.name}`;
  }
}

const melina = new Person('Melina');
console.log(melina.speak());
```

## 📦 Modules

```js
// file: utils/math.js
export function multiply(a, b) {
  return a * b;
}

// file: app.js
import { multiply } from './utils/math.js';
```

## ✅ Unit Tests (with Jest)

```js
// example.js
export function add(a, b) {
  return a + b;
}

// example.test.js
import { add } from './example.js';

test('adds 1 + 2 = 3', () => {
  expect(add(1, 2)).toBe(3);
});
```

> To run: `npm run test` (assuming your `package.json` has `"test": "jest"`)

## Semicolon ";"

> If you're writing a **declaration or expression** that returns a value → **use a `;`**.
> If it's a **control structure** (condition, loop, class...) → **you don't need it**.

| Case                                    | ;   |
| --------------------------------------- | --- |
| Declaration `const`, `let`, `var`       | ✅  |
| Assignment / operation                  | ✅  |
| Function call                           | ✅  |
| Array / object declaration (assigned)   | ✅  |
| One-line expression                     | ✅  |
| `return` with an expression             | ✅  |
| `new` expression assigned to a variable | ✅  |
| Function declaration                    | ❌  |
| Class declaration                       | ❌  |
| Loops `for`, `while`, `do...while`      | ❌  |
| Conditions `if`, `else if`, `else`      | ❌  |
| Standalone or nested code blocks `{}`   | ❌  |
| Import / export                         | ❌  |
| Stored arrow function                   | ✅  |

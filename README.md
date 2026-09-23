# JavaScript for Beginners — Complete Learning Guide

> A structured, practical introduction to modern JavaScript.
>
> **Goal:** understand the language step by step, write small programs confidently, and build a solid foundation for browser development.

---

# 1. How to Use This Guide

Follow the chapters in order.

For each topic:

1. Read the explanation.
2. Type the example yourself.
3. Change the example and observe the result.
4. Solve the practice task without looking at the solution.
5. Move to the next chapter only when the idea feels familiar.

The examples use **modern JavaScript** and focus on clear, beginner-friendly code.

---

# 2. What Is JavaScript?

JavaScript is a programming language used to make web pages interactive and to build applications.

JavaScript can run:

- in web browsers
- on servers with Node.js
- in desktop applications
- in mobile applications
- in many development tools

A simple JavaScript program:

```js
console.log("Hello, JavaScript!");
```

`console.log()` prints a value to the console.

---

# 3. Running JavaScript

The easiest way to experiment in a browser is the Developer Console.

Open a web page, open Developer Tools, and select the **Console** tab.

You can also put JavaScript inside an HTML file:

```html
<script>
  console.log("Hello!");
</script>
```

Later, it is better to keep JavaScript in a separate file:

```html
<script src="app.js"></script>
```

---

# 4. Comments

Comments are ignored by JavaScript.

## Single-line comments

```js
// This is a comment
let age = 20;
```

## Multi-line comments

```js
/*
  This is a
  multi-line comment.
*/
```

Use comments to explain **why** something is done, not to describe every obvious line.

---

# 5. Variables

Variables store values.

The main keywords are:

- `let` — use when the variable may be reassigned
- `const` — use when the variable should not be reassigned
- `var` — older syntax; generally avoid it in modern JavaScript

```js
let age = 20;
const birthYear = 2006;

console.log(age);
console.log(birthYear);
```

A variable declared with `let` can be reassigned:

```js
let score = 10;
score = 20;

console.log(score);
```

A `const` variable cannot be reassigned:

```js
const country = "Poland";

// country = "Germany"; // Error
```

## Important

`const` prevents reassignment of the variable. It does **not** make objects or arrays immutable.

```js
const user = {
  name: "Alex"
};

user.name = "Sam"; // Allowed
```

---

# 6. Naming Variables

Use clear names.

Good:

```js
let userName = "Alex";
let totalPrice = 100;
let isLoggedIn = true;
```

Avoid:

```js
let x = "Alex";
let a = 100;
```

Common JavaScript style is **camelCase**:

```js
let firstName = "Alex";
let shoppingCartTotal = 50;
```

Variable names can contain letters, numbers, `_`, and `$`, but they cannot start with a number.

---

# 7. Data Types

JavaScript has several important data types.

## String

Text:

```js
let name = "Alex";
```

## Number

Integers and decimal numbers use the same `number` type:

```js
let age = 20;
let price = 19.99;
```

## Boolean

A logical value:

```js
let isStudent = true;
let isAdmin = false;
```

## Undefined

A variable can exist without having a value:

```js
let result;

console.log(result); // undefined
```

## Null

`null` represents an intentional absence of a value:

```js
let selectedUser = null;
```

## BigInt

Used for integers larger than the safe range of regular numbers:

```js
const hugeNumber = 12345678901234567890n;
```

Beginners usually do not need `BigInt` immediately.

## Symbol

Symbols create unique identifiers:

```js
const id = Symbol("id");
```

Symbols are an advanced topic and are rarely needed in beginner projects.

---

# 8. Checking Types

Use `typeof`:

```js
console.log(typeof "Hello"); // string
console.log(typeof 42);      // number
console.log(typeof true);    // boolean
```

For example:

```js
let age = 20;

console.log(typeof age);
```

---

# 9. Strings

Strings can use single quotes, double quotes, or backticks.

```js
let firstName = "Alex";
let lastName = 'Smith';
let country = `Poland`;
```

## String concatenation

```js
let name = "Alex";

console.log("Hello " + name);
```

## Template literals

Template literals are usually easier to read:

```js
let name = "Alex";
let age = 20;

console.log(`My name is ${name} and I am ${age} years old.`);
```

## Useful string properties and methods

```js
let message = "Hello World";

console.log(message.length);
console.log(message.toUpperCase());
console.log(message.toLowerCase());
console.log(message.includes("World"));
console.log(message.startsWith("Hello"));
console.log(message.endsWith("World"));
```

More useful methods:

```js
let text = "  JavaScript  ";

console.log(text.trim());
console.log(text.slice(2, 12));
console.log(text.replace("JavaScript", "JS"));
```

---

# 10. Numbers and Arithmetic

Basic operators:

```js
console.log(5 + 5);   // addition
console.log(10 - 3);  // subtraction
console.log(4 * 3);   // multiplication
console.log(10 / 2);  // division
console.log(10 % 3);  // remainder
console.log(2 ** 3);  // exponentiation
```

## Increment and decrement

```js
let count = 1;

count++;
count--;

console.log(count);
```

## Math

```js
console.log(Math.round(4.6));
console.log(Math.floor(4.9));
console.log(Math.ceil(4.1));
console.log(Math.max(10, 20, 30));
console.log(Math.min(10, 20, 30));
```

Random number:

```js
const randomNumber = Math.random();

console.log(randomNumber);
```

`Math.random()` returns a number from `0` up to, but not including, `1`.

---

# 11. Operators

## Assignment

```js
let score = 10;

score += 5;
score -= 2;
score *= 2;
score /= 2;
```

## Comparison

```js
console.log(5 > 3);
console.log(5 < 3);
console.log(5 >= 5);
console.log(4 <= 10);
console.log(10 === 10);
console.log(10 !== 5);
```

Prefer strict equality:

```js
10 === 10
10 !== 5
```

Avoid relying on loose equality:

```js
10 == "10";
```

Strict equality checks value and type.

---

# 12. Truthy and Falsy Values

JavaScript converts values to boolean in many situations.

Falsy values include:

```js
false
0
""
null
undefined
NaN
```

Most other values are truthy.

Example:

```js
let username = "";

if (username) {
  console.log("Username exists");
} else {
  console.log("Username is empty");
}
```

---

# 13. Type Conversion

Convert values explicitly when possible.

```js
const textNumber = "42";

const number = Number(textNumber);

console.log(number);
console.log(typeof number);
```

Other examples:

```js
String(42);
Number("10");
Boolean(1);
```

Be careful with invalid numeric input:

```js
const result = Number("hello");

console.log(result); // NaN
```

---

# 14. Conditional Statements

Use `if` when code should run only when a condition is true.

```js
let age = 20;

if (age >= 18) {
  console.log("You are an adult.");
} else {
  console.log("You are not an adult.");
}
```

## `else if`

```js
let score = 75;

if (score >= 90) {
  console.log("Excellent");
} else if (score >= 70) {
  console.log("Good");
} else {
  console.log("Keep practicing");
}
```

---

# 15. Logical Operators

## AND — `&&`

Both conditions must be true.

```js
const age = 20;
const hasTicket = true;

if (age >= 18 && hasTicket) {
  console.log("Access granted");
}
```

## OR — `||`

At least one condition must be true.

```js
const isAdmin = false;
const isModerator = true;

if (isAdmin || isModerator) {
  console.log("You can manage content.");
}
```

## NOT — `!`

Reverses a boolean value.

```js
const isLoggedIn = false;

if (!isLoggedIn) {
  console.log("Please log in.");
}
```

---

# 16. Ternary Operator

The ternary operator is useful for short conditional expressions.

```js
const age = 20;

const message = age >= 18
  ? "Adult"
  : "Minor";

console.log(message);
```

Do not use deeply nested ternaries. Use `if` when the logic becomes difficult to read.

---

# 17. Nullish Coalescing

The `??` operator uses the right-hand value only when the left-hand value is `null` or `undefined`.

```js
const username = null;

const displayName = username ?? "Guest";

console.log(displayName);
```

This is different from `||`:

```js
const count = 0;

console.log(count || 10);  // 10
console.log(count ?? 10);  // 0
```

---

# 18. `switch`

`switch` can be useful when comparing one value against several known cases.

```js
const day = "Monday";

switch (day) {
  case "Monday":
    console.log("Start of the week");
    break;

  case "Friday":
    console.log("Almost the weekend");
    break;

  default:
    console.log("Regular day");
}
```

---

# 19. Loops

Loops repeat code.

## `while`

```js
let count = 1;

while (count <= 5) {
  console.log(count);
  count++;
}
```

## `for`

```js
for (let count = 1; count <= 5; count++) {
  console.log(count);
}
```

## `do...while`

Runs the body at least once:

```js
let count = 1;

do {
  console.log(count);
  count++;
} while (count <= 5);
```

---

# 20. `break` and `continue`

`break` stops a loop:

```js
for (let i = 1; i <= 10; i++) {
  if (i === 5) {
    break;
  }

  console.log(i);
}
```

`continue` skips the current iteration:

```js
for (let i = 1; i <= 5; i++) {
  if (i === 3) {
    continue;
  }

  console.log(i);
}
```

---

# 21. Functions

Functions group reusable logic.

```js
function greet() {
  console.log("Hello!");
}

greet();
```

## Parameters

```js
function greetUser(username) {
  console.log(`Hello, ${username}!`);
}

greetUser("Alex");
```

## Return values

```js
function addNumbers(num1, num2) {
  return num1 + num2;
}

const result = addNumbers(6, 7);

console.log(result);
```

A `return` value can be stored, passed to another function, or used in an expression.

---

# 22. Default Parameters

```js
function greet(name = "Guest") {
  console.log(`Hello, ${name}!`);
}

greet();
greet("Alex");
```

---

# 23. Function Expressions

Functions can be stored in variables.

```js
const greet = function () {
  console.log("Hello!");
};

greet();
```

---

# 24. Arrow Functions

Modern JavaScript often uses arrow functions.

```js
const greet = () => {
  console.log("Hello!");
};
```

With one parameter:

```js
const greetUser = name => {
  console.log(`Hello, ${name}!`);
};
```

Short return:

```js
const add = (a, b) => a + b;

console.log(add(2, 3));
```

Arrow functions are especially common with array methods and callbacks.

---

# 25. Scope

Scope determines where a variable can be accessed.

```js
const globalName = "Alex";

function example() {
  const localName = "Sam";

  console.log(globalName);
  console.log(localName);
}

example();
```

`localName` cannot be accessed outside the function.

## Block scope

`let` and `const` are block-scoped:

```js
if (true) {
  const message = "Hello";
  console.log(message);
}

// console.log(message); // Error
```

---

# 26. Arrays

Arrays store ordered collections of values.

```js
const technologies = ["HTML", "CSS", "JavaScript"];

console.log(technologies);
```

Access an item by index:

```js
console.log(technologies[0]);
console.log(technologies[1]);
```

Indexes start at `0`.

---

# 27. Array Properties and Methods

```js
const technologies = ["HTML", "CSS", "JavaScript"];

console.log(technologies.length);
```

Add to the end:

```js
technologies.push("TypeScript");
```

Remove from the end:

```js
technologies.pop();
```

Add to the beginning:

```js
technologies.unshift("Git");
```

Remove from the beginning:

```js
technologies.shift();
```

---

# 28. Searching Arrays

```js
const numbers = [10, 20, 30, 40];

console.log(numbers.includes(20));
console.log(numbers.indexOf(30));
```

`find()` returns the first matching item:

```js
const users = [
  { name: "Alex", age: 20 },
  { name: "Sam", age: 25 }
];

const user = users.find(user => user.age > 21);

console.log(user);
```

---

# 29. `for...of`

Use `for...of` to iterate over values.

```js
const technologies = ["HTML", "CSS", "JavaScript"];

for (const technology of technologies) {
  console.log(technology);
}
```

---

# 30. `forEach`

`forEach()` executes a function for each array item.

```js
const technologies = ["HTML", "CSS", "JavaScript"];

technologies.forEach(technology => {
  console.log(technology);
});
```

It is useful when you want to perform an action for every item.

---

# 31. `map`

`map()` creates a new array by transforming every item.

```js
const numbers = [1, 2, 3, 4];

const doubled = numbers.map(number => number * 2);

console.log(doubled);
```

Original array:

```js
console.log(numbers);
```

New array:

```js
console.log(doubled);
```

---

# 32. `filter`

`filter()` creates a new array containing items that pass a condition.

```js
const numbers = [1, 2, 3, 4, 5, 6];

const evenNumbers = numbers.filter(number => number % 2 === 0);

console.log(evenNumbers);
```

---

# 33. `reduce`

`reduce()` combines array values into one result.

```js
const prices = [10, 20, 30];

const total = prices.reduce((sum, price) => {
  return sum + price;
}, 0);

console.log(total);
```

Do not use `reduce()` simply because it is shorter. Prefer readable code.

---

# 34. `some` and `every`

`some()` checks whether at least one item matches.

```js
const numbers = [1, 3, 5, 8];

console.log(numbers.some(number => number % 2 === 0));
```

`every()` checks whether all items match.

```js
console.log(numbers.every(number => number > 0));
```

---

# 35. Sorting Arrays

```js
const names = ["Charlie", "Alice", "Bob"];

names.sort();

console.log(names);
```

For numbers, provide a comparison function:

```js
const numbers = [10, 2, 30, 5];

numbers.sort((a, b) => a - b);

console.log(numbers);
```

For descending order:

```js
numbers.sort((a, b) => b - a);
```

Remember that `sort()` mutates the array.

---

# 36. Objects

Objects store related data using key-value pairs.

```js
const user = {
  name: "Alex",
  age: 20,
  isStudent: true
};

console.log(user);
```

Access properties:

```js
console.log(user.name);
console.log(user.age);
```

You can also use bracket notation:

```js
console.log(user["name"]);
```

---

# 37. Changing Objects

```js
const user = {
  name: "Alex",
  age: 20
};

user.age = 21;
user.city = "Warsaw";

console.log(user);
```

Delete a property:

```js
delete user.city;
```

---

# 38. Object Methods

Objects can contain functions.

```js
const user = {
  name: "Alex",

  greet() {
    console.log(`Hello, I am ${this.name}.`);
  }
};

user.greet();
```

`this` usually refers to the object that calls the method.

---

# 39. Nested Objects

Objects can contain other objects.

```js
const user = {
  name: "Alex",
  address: {
    city: "Warsaw",
    country: "Poland"
  }
};

console.log(user.address.city);
```

---

# 40. Optional Chaining

Optional chaining `?.` safely accesses nested properties.

```js
const user = {};

console.log(user.address?.city);
```

Without optional chaining, accessing `user.address.city` would throw an error because `address` is undefined.

---

# 41. Destructuring

Destructuring extracts values from arrays or objects.

## Object destructuring

```js
const user = {
  name: "Alex",
  age: 20
};

const { name, age } = user;

console.log(name);
console.log(age);
```

## Array destructuring

```js
const colors = ["red", "green", "blue"];

const [first, second] = colors;

console.log(first);
console.log(second);
```

---

# 42. Spread Syntax

Spread `...` expands values.

## Arrays

```js
const first = [1, 2];
const second = [3, 4];

const combined = [...first, ...second];

console.log(combined);
```

## Objects

```js
const user = {
  name: "Alex",
  age: 20
};

const updatedUser = {
  ...user,
  age: 21
};

console.log(updatedUser);
```

---

# 43. Rest Parameters

Rest parameters collect multiple arguments.

```js
function sum(...numbers) {
  return numbers.reduce((total, number) => total + number, 0);
}

console.log(sum(1, 2, 3, 4));
```

Spread and rest use the same `...` syntax but have different purposes.

---

# 44. Shallow Copies

Spread creates a shallow copy.

```js
const original = {
  name: "Alex",
  age: 20
};

const copy = { ...original };

copy.age = 21;

console.log(original.age);
console.log(copy.age);
```

Nested objects require extra care because nested references are still shared.

---

# 45. Callbacks

A callback is a function passed to another function.

```js
function processUser(name, callback) {
  console.log(`Processing ${name}`);
  callback();
}

processUser("Alex", () => {
  console.log("Finished");
});
```

Callbacks are fundamental to modern JavaScript.

---

# 46. Higher-Order Functions

A higher-order function takes a function as an argument or returns a function.

Array methods such as these are common examples:

```js
map()
filter()
forEach()
find()
reduce()
```

Example:

```js
const numbers = [1, 2, 3];

const result = numbers.map(number => number * 10);

console.log(result);
```

---

# 47. Closures

A closure happens when a function remembers variables from its surrounding scope.

```js
function createCounter() {
  let count = 0;

  return function () {
    count++;
    return count;
  };
}

const counter = createCounter();

console.log(counter());
console.log(counter());
console.log(counter());
```

Closures are important for understanding callbacks, private state, and many JavaScript patterns.

---

# 48. Dates

JavaScript provides the `Date` object.

```js
const now = new Date();

console.log(now);
```

Examples:

```js
console.log(now.getFullYear());
console.log(now.getMonth());
console.log(now.getDate());
```

Important: `getMonth()` is zero-based, so January is `0`.

For serious date/time work, learn the modern JavaScript date/time ecosystem and understand time zones before building complex date logic.

---

# 49. Regular Expressions

Regular expressions can search for text patterns.

```js
const pattern = /javascript/i;

console.log(pattern.test("I am learning JavaScript."));
```

A simple email-like check:

```js
const emailPattern = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;

console.log(emailPattern.test("alex@example.com"));
```

Regular expressions are useful, but complex patterns can become difficult to maintain. Prefer simple validation when possible.

---

# 50. Error Handling

Errors can be handled with `try...catch`.

```js
try {
  const result = JSON.parse("invalid JSON");
  console.log(result);
} catch (error) {
  console.log("Something went wrong.");
}
```

You can inspect the error:

```js
try {
  throw new Error("Something went wrong");
} catch (error) {
  console.log(error.message);
}
```

Use errors intentionally and handle cases that can realistically fail.

---

# 51. `throw`

You can create your own errors.

```js
function divide(a, b) {
  if (b === 0) {
    throw new Error("Cannot divide by zero.");
  }

  return a / b;
}
```

---

# 52. JSON

JSON is a common format for exchanging data.

Example JSON:

```json
{
  "name": "Alex",
  "age": 20
}
```

Convert an object to JSON:

```js
const user = {
  name: "Alex",
  age: 20
};

const json = JSON.stringify(user);

console.log(json);
```

Convert JSON to an object:

```js
const json = '{"name":"Alex","age":20}';

const user = JSON.parse(json);

console.log(user.name);
```

---

# 53. Asynchronous JavaScript

JavaScript often performs tasks that take time, such as:

- network requests
- timers
- reading files
- database operations

JavaScript can continue executing other work instead of blocking while waiting.

---

# 54. Timers

```js
console.log("Start");

setTimeout(() => {
  console.log("Finished later");
}, 1000);

console.log("End");
```

The output order is:

```text
Start
End
Finished later
```

---

# 55. Promises

A Promise represents the eventual result of an asynchronous operation.

A Promise can be:

- pending
- fulfilled
- rejected

Example:

```js
const promise = new Promise((resolve, reject) => {
  const success = true;

  if (success) {
    resolve("Operation completed");
  } else {
    reject(new Error("Operation failed"));
  }
});
```

---

# 56. `.then()` and `.catch()`

```js
promise
  .then(result => {
    console.log(result);
  })
  .catch(error => {
    console.log(error.message);
  });
```

---

# 57. `async` and `await`

Modern asynchronous JavaScript commonly uses `async` and `await`.

```js
function wait() {
  return new Promise(resolve => {
    setTimeout(() => {
      resolve("Done");
    }, 1000);
  });
}

async function run() {
  const result = await wait();

  console.log(result);
}

run();
```

`await` makes asynchronous code easier to read, but it does not make the operation synchronous.

---

# 58. Fetching Data

The Fetch API is used for HTTP requests.

```js
async function loadUsers() {
  const response = await fetch("https://example.com/users");

  const data = await response.json();

  console.log(data);
}
```

Always consider HTTP errors:

```js
async function loadUsers() {
  const response = await fetch("https://example.com/users");

  if (!response.ok) {
    throw new Error(`HTTP error: ${response.status}`);
  }

  const data = await response.json();

  return data;
}
```

Handle failures:

```js
loadUsers()
  .then(users => {
    console.log(users);
  })
  .catch(error => {
    console.error(error);
  });
```

---

# 59. Parallel Asynchronous Operations

When independent tasks can run at the same time, `Promise.all()` is useful.

```js
const [users, products] = await Promise.all([
  fetchUsers(),
  fetchProducts()
]);
```

Other Promise utilities worth learning later:

```js
Promise.all()
Promise.allSettled()
Promise.race()
Promise.any()
```

---

# 60. The DOM

The DOM (Document Object Model) represents an HTML document as objects that JavaScript can interact with.

Example HTML:

```html
<h1 id="title">Hello</h1>
```

JavaScript:

```js
const title = document.querySelector("#title");

console.log(title);
```

---

# 61. Changing HTML

```js
const title = document.querySelector("#title");

title.textContent = "Hello, JavaScript!";
```

Use `textContent` for plain text.

Be careful with `innerHTML` because inserting untrusted HTML can create security problems.

---

# 62. Changing Styles and Classes

```js
const title = document.querySelector("#title");

title.style.fontSize = "40px";
```

For larger applications, CSS classes are usually cleaner:

```js
title.classList.add("active");
title.classList.remove("active");
title.classList.toggle("active");
```

---

# 63. Selecting Elements

Common methods:

```js
document.querySelector(".card");
document.querySelectorAll(".card");
document.getElementById("title");
```

`querySelector()` returns the first matching element.

`querySelectorAll()` returns a collection of matching elements.

---

# 64. Creating Elements

```js
const button = document.createElement("button");

button.textContent = "Click me";

document.body.append(button);
```

---

# 65. Events

Events allow JavaScript to react to user actions.

```js
const button = document.querySelector("#button");

button.addEventListener("click", () => {
  console.log("Button clicked");
});
```

Common events include:

```text
click
input
change
submit
keydown
keyup
mouseover
focus
blur
```

---

# 66. Event Objects

Event handlers receive an event object.

```js
button.addEventListener("click", event => {
  console.log(event);
});
```

For keyboard events:

```js
document.addEventListener("keydown", event => {
  console.log(event.key);
});
```

---

# 67. Forms

Listen for the `submit` event:

```js
const form = document.querySelector("#loginForm");

form.addEventListener("submit", event => {
  event.preventDefault();

  console.log("Form submitted");
});
```

`preventDefault()` stops the browser's default form submission behavior.

---

# 68. Event Delegation

Instead of adding listeners to many child elements, listen on a parent.

```js
const list = document.querySelector("#list");

list.addEventListener("click", event => {
  if (event.target.matches(".delete-button")) {
    console.log("Delete clicked");
  }
});
```

Event delegation is useful for dynamic lists and large collections of elements.

---

# 69. Browser Storage

`localStorage` stores strings in the browser.

```js
localStorage.setItem("theme", "dark");

const theme = localStorage.getItem("theme");

console.log(theme);
```

Remove an item:

```js
localStorage.removeItem("theme");
```

Store an object with JSON:

```js
const user = {
  name: "Alex",
  age: 20
};

localStorage.setItem("user", JSON.stringify(user));

const savedUser = JSON.parse(
  localStorage.getItem("user")
);

console.log(savedUser);
```

Do not store sensitive secrets in `localStorage`.

---

# 70. Modules

Modules let you split code into separate files.

## Export

`math.js`:

```js
export function add(a, b) {
  return a + b;
}
```

## Import

`app.js`:

```js
import { add } from "./math.js";

console.log(add(2, 3));
```

In HTML:

```html
<script type="module" src="app.js"></script>
```

Modules make larger projects easier to organize.

---

# 71. Default Exports

A module can have a default export:

```js
export default function greet(name) {
  return `Hello, ${name}!`;
}
```

Import it:

```js
import greet from "./greet.js";

console.log(greet("Alex"));
```

---

# 72. Classes

Classes provide syntax for creating objects with shared behavior.

```js
class User {
  constructor(name) {
    this.name = name;
  }

  greet() {
    console.log(`Hello, ${this.name}!`);
  }
}

const user = new User("Alex");

user.greet();
```

Classes are built on JavaScript's prototype system.

---

# 73. Inheritance

A class can extend another class.

```js
class Animal {
  speak() {
    console.log("Animal sound");
  }
}

class Dog extends Animal {
  speak() {
    console.log("Woof!");
  }
}

const dog = new Dog();

dog.speak();
```

Do not use classes simply because they look familiar from other languages. JavaScript also supports functional and prototype-based patterns.

---

# 74. Prototypes

Every JavaScript object has a prototype relationship used for property and method lookup.

For beginners, understand this conceptually:

```text
object
  ↓
prototype
  ↓
another prototype
  ↓
null
```

Classes provide a convenient syntax over JavaScript's prototype-based object model.

Prototype details become important when learning advanced JavaScript, performance, and library internals.

---

# 75. `this`

`this` depends on how a function is called.

Example:

```js
const user = {
  name: "Alex",

  greet() {
    console.log(this.name);
  }
};

user.greet();
```

Arrow functions do not create their own `this`.

```js
const user = {
  name: "Alex",

  greet: () => {
    console.log(this.name);
  }
};
```

Do not automatically replace regular methods with arrow functions when `this` is required.

---

# 76. Strict Mode

Strict mode enables stricter JavaScript behavior.

```js
"use strict";
```

ES modules are automatically strict mode.

Modern projects generally use modules or tooling that already provide strict semantics, so manually adding `"use strict"` is less common in modern code.

---

# 77. Immutability

Avoid changing data unnecessarily.

Instead of:

```js
const user = {
  name: "Alex",
  age: 20
};

user.age = 21;
```

you can create a new object:

```js
const user = {
  name: "Alex",
  age: 20
};

const updatedUser = {
  ...user,
  age: 21
};
```

This style is especially common in modern application development.

---

# 78. Equality and Object References

Primitive values are compared by value:

```js
console.log(5 === 5);
console.log("hello" === "hello");
```

Objects are compared by reference:

```js
const first = { name: "Alex" };
const second = { name: "Alex" };

console.log(first === second); // false
```

They contain similar data, but they are different objects.

---

# 79. `NaN`

`NaN` means "Not a Number".

```js
const result = Number("hello");

console.log(result);
```

Check it with:

```js
console.log(Number.isNaN(result));
```

---

# 80. Big Picture: How JavaScript Executes

A useful beginner mental model:

```text
Source code
    ↓
JavaScript engine
    ↓
Call stack
    ↓
Web APIs / runtime
    ↓
Task queues
    ↓
Event loop
```

The exact implementation differs between environments, but the event loop model is important for understanding asynchronous JavaScript.

---

# 81. The Event Loop

Consider:

```js
console.log("A");

setTimeout(() => {
  console.log("B");
}, 0);

console.log("C");
```

The result is:

```text
A
C
B
```

A zero-millisecond timer does not mean "run immediately". The callback is scheduled to run later.

---

# 82. Debugging

Use `console.log()` while learning:

```js
const total = 100;

console.log("total:", total);
```

Also learn:

```js
console.error();
console.warn();
console.table();
```

Browser DevTools provide:

- breakpoints
- step over
- step into
- step out
- watch expressions
- call stack inspection
- network inspection

Debugging is a core programming skill, not a last resort.

---

# 83. Common Beginner Mistakes

## Mistake 1: Using `=` instead of comparison

```js
let age = 20;
```

Assignment.

```js
age === 20
```

Comparison.

## Mistake 2: Forgetting `return`

```js
function add(a, b) {
  a + b;
}
```

Correct:

```js
function add(a, b) {
  return a + b;
}
```

## Mistake 3: Forgetting that array indexes start at zero

```js
const items = ["A", "B", "C"];

console.log(items[0]); // A
```

## Mistake 4: Using `==` without understanding coercion

Prefer:

```js
value === expectedValue
```

## Mistake 5: Mutating data unexpectedly

Understand which array and object methods mutate their input.

---

# 84. Modern JavaScript Features to Know

A beginner should become comfortable with:

- `let` and `const`
- template literals
- strict equality
- destructuring
- spread/rest syntax
- arrow functions
- default parameters
- optional chaining
- nullish coalescing
- modules
- `for...of`
- array methods
- Promises
- `async` / `await`
- Fetch API
- modern browser APIs

---

# 85. Browser APIs Worth Learning

After the fundamentals, explore:

- DOM API
- Fetch API
- Web Storage API
- URL API
- History API
- Clipboard API
- Intersection Observer
- WebSocket API
- Web Workers

Do not try to memorize every API. Learn how to read documentation and find the right API for a problem.

---

# 86. npm and Node.js

After learning the language basics, learn the JavaScript ecosystem.

Important concepts:

- Node.js
- npm
- `package.json`
- dependencies
- development dependencies
- npm scripts
- semantic versioning
- environment variables
- package managers

A typical project may contain:

```text
my-project/
├── package.json
├── src/
│   └── app.js
└── README.md
```

---

# 87. Modern Development Tools

You should eventually understand the purpose of:

- code editors
- browser DevTools
- Git
- GitHub or another Git hosting service
- linters
- formatters
- test runners
- bundlers/build tools
- package managers

You do not need to master every tool before building projects.

---

# 88. Testing Basics

Tests check whether code behaves as expected.

Example idea:

```js
function add(a, b) {
  return a + b;
}

console.assert(add(2, 3) === 5);
```

Later, learn a test framework and concepts such as:

- unit tests
- integration tests
- end-to-end tests
- assertions
- mocks
- test coverage

---

# 89. Security Basics

Every JavaScript developer should understand basic web security.

Important topics:

- XSS
- CSRF
- input validation
- output escaping
- safe DOM manipulation
- authentication vs authorization
- secure cookies
- CORS
- avoiding secret keys in frontend code

Never put private API keys or passwords in browser JavaScript.

---

# 90. Performance Basics

Do not optimize before you understand the code.

Learn to recognize:

- unnecessary DOM updates
- expensive loops
- excessive network requests
- large JavaScript bundles
- unnecessary object creation
- inefficient event handling

Measure performance before making optimization decisions.

---

# 91. Clean Code Principles

Prefer:

```js
const totalPrice = calculateTotal(items);
```

over:

```js
const x = calc(items);
```

Good code is:

- readable
- predictable
- simple
- consistently formatted
- divided into small responsibilities
- easy to test

Do not make code complicated just to demonstrate advanced syntax.

---

# 92. Practical Project Structure

A small browser project might look like:

```text
todo-app/
├── index.html
├── styles.css
├── src/
│   ├── app.js
│   ├── storage.js
│   └── ui.js
└── README.md
```

Keep related responsibilities together.

For example:

```text
storage.js → localStorage operations
ui.js      → DOM rendering
app.js     → application logic
```

---

# 93. Mini Project 1 — Counter

HTML:

```html
<button id="decrease">-</button>
<span id="value">0</span>
<button id="increase">+</button>
```

JavaScript:

```js
const decreaseButton = document.querySelector("#decrease");
const increaseButton = document.querySelector("#increase");
const valueElement = document.querySelector("#value");

let value = 0;

increaseButton.addEventListener("click", () => {
  value++;
  valueElement.textContent = value;
});

decreaseButton.addEventListener("click", () => {
  value--;
  valueElement.textContent = value;
});
```

Skills practiced:

- variables
- DOM selection
- events
- functions
- state updates

---

# 94. Mini Project 2 — Simple Todo List

Core data:

```js
const todos = [
  {
    id: 1,
    text: "Learn JavaScript",
    completed: false
  }
];
```

Useful operations:

```js
const completedTodos = todos.filter(todo => todo.completed);

const todoTexts = todos.map(todo => todo.text);
```

This project can gradually add:

1. adding tasks
2. deleting tasks
3. completing tasks
4. filtering tasks
5. saving tasks to `localStorage`

---

# 95. Mini Project 3 — API Viewer

Build a page that:

1. has a button
2. sends a Fetch request
3. displays loading state
4. displays the result
5. handles errors
6. allows the user to retry

This project connects:

- DOM
- events
- functions
- Promises
- `async` / `await`
- Fetch
- JSON
- error handling

---

# 96. Recommended Learning Order

## Stage 1 — Core Syntax

Learn:

```text
variables
data types
operators
conditions
loops
functions
```

## Stage 2 — Data

Learn:

```text
arrays
objects
array methods
destructuring
spread/rest
```

## Stage 3 — Modern JavaScript

Learn:

```text
arrow functions
optional chaining
nullish coalescing
modules
callbacks
closures
```

## Stage 4 — Browser Development

Learn:

```text
DOM
events
forms
localStorage
Fetch
JSON
```

## Stage 5 — Asynchronous JavaScript

Learn:

```text
callbacks
Promises
async/await
Promise.all
event loop
```

## Stage 6 — Deeper JavaScript

Learn:

```text
this
prototypes
classes
closures
execution context
scope
hoisting
```

## Stage 7 — Ecosystem

Learn:

```text
Node.js
npm
Git
testing
linting
formatting
build tools
```

---

# 97. Practice Tasks

After the fundamentals, solve these without copying the examples.

## Beginner

1. Create a variable containing your name and print it.
2. Create two numbers and print their sum.
3. Check whether a number is positive, negative, or zero.
4. Print numbers from 1 to 20.
5. Write a function that returns the square of a number.
6. Find the largest number in an array.
7. Count how many numbers are even.
8. Create an object representing a book.

## Intermediate

9. Use `map()` to convert prices into prices with tax.
10. Use `filter()` to find users over 18.
11. Use `reduce()` to calculate a shopping cart total.
12. Create a function that returns another function.
13. Build a counter with `setInterval()` or recursive timers.
14. Fetch data from a public API and display it.
15. Create a form with validation.
16. Save a todo list in `localStorage`.

## Project Level

17. Build a Todo application.
18. Build a weather application.
19. Build a quiz application.
20. Build a notes application.
21. Build a small product search interface.
22. Build an API dashboard.

---

# 98. Questions You Should Be Able to Answer

Before moving beyond beginner JavaScript, make sure you can explain:

### Variables

- What is the difference between `let` and `const`?
- What is reassignment?
- What is scope?

### Types

- What is a primitive?
- What is the difference between `null` and `undefined`?
- What does `typeof` do?
- What is `NaN`?

### Operators

- What is the difference between `===` and `==`?
- What do `&&`, `||`, and `!` do?
- What is `??`?

### Functions

- What is a parameter?
- What is an argument?
- What does `return` do?
- What is an arrow function?
- What is a callback?

### Arrays and objects

- What is an array index?
- What is the difference between `map()` and `forEach()`?
- What does `filter()` return?
- What does `reduce()` do?
- How do you access an object property?
- What is destructuring?

### Asynchronous JavaScript

- What is a Promise?
- What does `await` do?
- What is `Promise.all()`?
- Why can a `setTimeout(..., 0)` callback run later?

### Browser

- What is the DOM?
- What is an event?
- What does `preventDefault()` do?
- What is `localStorage`?
- How does `fetch()` work?

---

# 99. Final Mental Model

Think about JavaScript as several connected layers:

```text
1. Values
   ↓
2. Variables
   ↓
3. Operators and expressions
   ↓
4. Conditions and loops
   ↓
5. Functions
   ↓
6. Arrays and objects
   ↓
7. Callbacks and higher-order functions
   ↓
8. Scope, closures, and this
   ↓
9. DOM and browser APIs
   ↓
10. Promises and async/await
   ↓
11. Modules
   ↓
12. Tools and application architecture
```

The goal is not to memorize syntax.

The goal is to understand:

```text
Input
  ↓
Data
  ↓
Logic
  ↓
Functions
  ↓
State
  ↓
Output
```

Once these concepts are clear, frameworks such as React, Vue, Angular, or other JavaScript tools become much easier to learn.

---

# 100. Beginner Checklist

Use this checklist as a progress tracker.

## Core

- [ ] Variables
- [ ] `let`
- [ ] `const`
- [ ] Data types
- [ ] Strings
- [ ] Numbers
- [ ] Booleans
- [ ] `null`
- [ ] `undefined`
- [ ] Operators
- [ ] Strict equality
- [ ] Type conversion
- [ ] Truthy and falsy values

## Control Flow

- [ ] `if`
- [ ] `else`
- [ ] `else if`
- [ ] Ternary operator
- [ ] `switch`
- [ ] `while`
- [ ] `do...while`
- [ ] `for`
- [ ] `for...of`
- [ ] `break`
- [ ] `continue`

## Functions

- [ ] Function declarations
- [ ] Parameters
- [ ] Arguments
- [ ] Return values
- [ ] Default parameters
- [ ] Function expressions
- [ ] Arrow functions
- [ ] Scope
- [ ] Callbacks
- [ ] Closures

## Data Structures

- [ ] Arrays
- [ ] Objects
- [ ] Nested objects
- [ ] Array methods
- [ ] `map`
- [ ] `filter`
- [ ] `reduce`
- [ ] `find`
- [ ] `some`
- [ ] `every`
- [ ] `sort`
- [ ] Destructuring
- [ ] Spread syntax
- [ ] Rest parameters

## Modern JavaScript

- [ ] Optional chaining
- [ ] Nullish coalescing
- [ ] Template literals
- [ ] Modules
- [ ] Classes
- [ ] `this`
- [ ] Prototypes
- [ ] Error handling
- [ ] JSON
- [ ] Dates
- [ ] Regular expressions

## Asynchronous JavaScript

- [ ] Timers
- [ ] Callbacks
- [ ] Promises
- [ ] `.then()`
- [ ] `.catch()`
- [ ] `async`
- [ ] `await`
- [ ] Fetch
- [ ] `Promise.all`
- [ ] Event loop

## Browser

- [ ] DOM
- [ ] `querySelector`
- [ ] `querySelectorAll`
- [ ] DOM manipulation
- [ ] Events
- [ ] Forms
- [ ] Event delegation
- [ ] `localStorage`

## Ecosystem

- [ ] Node.js basics
- [ ] npm
- [ ] `package.json`
- [ ] Git
- [ ] Debugging
- [ ] Testing
- [ ] Linting
- [ ] Formatting
- [ ] Build tools

---

# 101. Next Step

Do not try to learn the entire guide in one pass.

A practical sequence is:

```text
Learn a concept
    ↓
Write 3–5 small examples
    ↓
Solve a small exercise
    ↓
Build a mini feature
    ↓
Debug it
    ↓
Explain the concept in your own words
    ↓
Move forward
```

The most important milestone is not finishing the notes.

It is being able to open an empty JavaScript file and build something without following a tutorial line by line.

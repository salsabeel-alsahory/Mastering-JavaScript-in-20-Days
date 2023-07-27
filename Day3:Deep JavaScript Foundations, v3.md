# Day 3: Function Expressions and Advanced Scope

## Lesson Summary:

### Function Expressions:
Function expressions are a way to define functions in JavaScript. Unlike function declarations, function expressions do not have a function name and are often assigned to a variable. This provides flexibility in how functions are created and used.

- **Naming Function Expressions:** Named function expressions have advantages over anonymous ones, such as providing better stack traces and improving debugging by having meaningful function names.

- **Arrow Functions:** Arrow functions offer a concise syntax and lexically bind the value of `this`. While they are useful in certain situations, they also have drawbacks, such as the lack of a `this` context and not being suitable for methods.

- **Function Types Hierarchy:** JavaScript functions can be categorized into different types based on their behavior and characteristics. Understanding this hierarchy helps in working with various types of functions effectively.

### Advanced Scope:
Advanced Scope explores different aspects of scope and scoping rules in JavaScript.

- **Lexical & Dynamic Scope:** JavaScript uses lexical scoping, where scope is determined by the placement of functions and blocks in the code, unlike dynamic scoping, which depends on the call stack at runtime.

- **Function Scoping:** Function scoping allows strategically hiding information in different levels of scope, providing better control over variable access and reducing the risk of unintended side effects.

- **IIFE Pattern:** The Immediately Invoked Function Expression (IIFE) pattern creates a new scope and helps avoid variable collisions in the global scope. IIFEs are commonly used to create private variables and modules in JavaScript.

- **Block Scoping:** Block scoping with `let` and `const` is useful in certain situations to avoid issues with variable hoisting and make the code more predictable and maintainable.

- **Choosing `let` or `var`:** The choice between `let` and `var` depends on the scenario, with `let` preferred for block-scoped variables due to its better predictability and readability.

- **Hoisting:** Hoisting is a mechanism where variable declarations are moved to the top of their scope. Understanding hoisting is essential for correctly interpreting the behavior of variables in different scopes.

- **`this` & Prototypes Q&A:** This section answers questions related to the `this` keyword, its binding in various scenarios, the behavior of arrow functions regarding `this`, and how prototypes work in JavaScript.
## Coding Exercises
### []()
#### My solution
- **Question 1:**

```javascript
  const exampleNormalFunc1 = (a, b, c) => {
  return a * (b + c);
};

const exampleNormalFunc2 = (x, y) => {
  return x * y;
};

const exampleNormalFunc3 = (string) => {
  return string + " " + string + " " + string + "!";
};

const arrowHOF = (normalFunc) => {
  return (...args) => {
    return (times) => normalFunc(...args) * times;
  };
};

const hofNormalFunc1 = arrowHOF(exampleNormalFunc1);
const hofNormalFunc2 = arrowHOF(exampleNormalFunc2);
const hofNormalFunc3 = arrowHOF(exampleNormalFunc3);

console.log(hofNormalFunc1(3, 4, 5)(2)); // logs 60 twice
console.log(hofNormalFunc2(20, 35)(4)); // logs 700 four times
console.log(hofNormalFunc3("Meow")(1)); // logs "Meow Meow Meow!"

```
- **Question 2:**
```javascript
const obj = {
  name: 'John',
  greet: function (greeting) {
    console.log(`${greeting}, ${this.name}!`);
  }
};

const preserveThis = (func) => func.bind(obj);

const preservedGreet = preserveThis(obj.greet);

preservedGreet('Hello'); // Output: "Hello, John!"

```
- **Question 1:**
  The reasoning for both Example 1 and Example 2 remains the same as provided in the previous explanations.

These solutions are more concise and achieve the same functionality as the initial solutions.
The arrowHOF function uses concise arrow function syntax, and the preserveThis function uses Function.prototype.bind() to preserve the this context of the original function.

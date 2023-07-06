# Day 3:Functions, Arrow Function, and Scope

This README file provides a summary of the JavaScript lessons on Functions, Arrow Functions, and Scope. In these lessons, we explore the fundamental concepts of functions, including their declaration, invocation, and the usage of parameters and arguments. We also cover the concise syntax of arrow functions and how they can be assigned to variables for reusability. Additionally, we delve into the topic of scope, understanding how variables are scoped within functions and the global scope, and how scope affects variable visibility and accessibility throughout the code.

### Lesson 1: Functions
Functions are a way to organize and reuse blocks of code. We can declare a function with a name and define its behavior inside curly braces. Functions can take inputs called parameters, which act as placeholders for values we provide when calling the function. The actual values we pass to the function are called arguments. Functions can also produce an output value using the return statement.

```javascript
// x, y and z  parameters
function add3(x, y, z) { 
  console.log("My parameters are named x, y, z");
  console.log("I received the arguments", x, y, z);
  return x + y + z;
}
//put when we pass numbers like 1,2,3,4 this is an argument  
```
### Lesson 2: Arrow Function
Arrow functions provide a concise syntax for creating unnamed functions. Instead of using the function keyword, we use the arrow (=>) to define the function. They are useful when we want to write shorter, more readable code. Arrow functions can be assigned to variables, making them handy for callbacks and function expressions.

```javascript
const add = (x, y) => x + y; // arrow function
```
### Lesson 3: Scope
Scope refers to the visibility and accessibility of variables in our code. The global scope is the outermost scope and can be accessed from anywhere in the program. Each function has its own scope, created when the function is defined. Variables declared within a function are only accessible within that function's scope, not outside of it. The var keyword, when used to declare variables, does not have block scope, meaning they are not limited to the block of code in which they are defined.
```javascript
let planet = "Jupiter";
function scope() {
  let planet = "Mars";
  console.log("Inner scope planet:", planet);
}
scope(); // output: Mars
console.log("Outer scope planet:", planet);// output: Jupiter
```
## Difference Between var and let

- `var` variables are function-scoped and hoisted, while `let` variables are block-scoped and not hoisted.
- `var` variables can be redeclared and updated within their scope, whereas `let` variables cannot be redeclared within the same block.
- `let` variables provide more predictable scoping and help avoid common issues related to hoisting and redeclaration.
### Coding Exercises
#### [Return a Value from a Function with Return](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/return-a-value-from-a-function-with-return)
```javascript
function timesFive(num) {
  return num *5;
}

const answer = timesFive(5);
```
#### [Global Scope and Functions](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/local-scope-and-functions)
```javascript
// Declare the myGlobal variable below this line
let myGlobal=10;

function fun1() {
  // Assign 5 to oopsGlobal here
 oopsGlobal=5;
}

// Only change code above this line

function fun2() {
  let output = "";
  if (typeof myGlobal != "undefined") {
    output += "myGlobal: " + myGlobal;
  }
  if (typeof oopsGlobal != "undefined") {
    output += " oopsGlobal: " + oopsGlobal;
  }
  console.log(output);
}
```
#### [Local Scope and Functions](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/local-scope-and-functions)
```javascript
function myLocalScope() {
  // Only change code below this line
let myVar=5;
  console.log('inside myLocalScope', myVar);
}
myLocalScope();

// Run and check the console
// myVar is not defined outside of myLocalScope
console.log('outside myLocalScope', myVar);
```
#### [Stand in Line](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/stand-in-line)
```javascript
function nextInLine(arr, item) {
  // Only change code below this line
  arr.push(item);
  let x = arr.shift();
  return x;
  
  // Only change code above this line
}

// Setup
let testArr = [1, 2, 3, 4, 5];

// Display code
console.log("Before: " + JSON.stringify(testArr));
console.log(nextInLine(testArr, 6));
console.log("After: " + JSON.stringify(testArr));
```

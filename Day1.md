# Day 1: Introduction to JavaScript, DOM, Values & Data Types, and Operators

This README file summarizes the key concepts covered on Day 1 of my JavaScript learning journey. On this day, I explored the fundamentals of JavaScript, including an introduction to the language, the Document Object Model (DOM), values and data types, and operators. I also solved three coding exercises to practice my skills.

## Lesson Summary

In this lesson, I covered the following topics:

- **Introduction to JavaScript:** I learned about the basics of JavaScript as a powerful programming language widely used in web development. JavaScript enables interactivity, dynamic content manipulation, and various web application functionalities.

- **Document Object Model (DOM):** I discovered the DOM, which represents the structure of HTML documents as a tree-like structure. It allows me to manipulate and interact with web pages using JavaScript. I learned how to access and modify HTML elements, change their attributes, add or remove elements dynamically, and respond to user interactions.

- **Values & Data Types:** I explored the different types of values and data types in JavaScript. This includes strings (textual data), numbers (numeric data), booleans (true or false), null (represents the absence of any object value), undefined (represents an uninitialized variable), and objects (complex data structures). I also learned how to declare variables and assign values to them, understanding the concept of variable scope.

- **Operators:** I gained an understanding of various operators in JavaScript. This includes arithmetic operators (+, -, *, /) for performing mathematical calculations, comparison operators (>, <, >=, <=, ===, !==) for comparing values, and logical operators (&&, ||, !) for combining conditions and creating logical expressions.

## Coding Exercises

1. Math Operation:
   - Perform a math operation: 4 + 2 = 6

2. String Operation:
   - Concatenate two strings: "Hello" + " World" = "Hello World"

3. Number Operation:
   - Compare two numbers: 10 > 5 (Output true)

## Coding Examples

```javascript
// Example 1: Using console commands to find elements and text
console.log(document.querySelectorAll("p")); // Find all p elements
console.log(document.querySelector("#p1-symbol").textContent); // Find the text in element with id selector #
console.log(document.querySelectorAll(".square").length); // Find the number of squares on the board
console.log(document.querySelector("h2").textContent); // Find the text in the h2 element

// Example 3: Determining value types using typeof
let value1 = 42;
let value2 = "42";
let value3 = null;
console.log(typeof value1); // number
console.log(typeof value2); // string
console.log(typeof value3); // object (null is a special case its a primitive data type)

// Example 4: String manipulation exercises
let myString = "Hello , world!";
console.log(myString.length); // Length of the string Output: 14
console.log(myString.indexOf("world")); // Index of "world" Output: 8
console.log(myString.includes("Hello")); // Check if the string includes "Hello" Output: true 
console.log(myString.toUpperCase()); // Convert the string to uppercase

// Example 5: Arithmetic operators
let x = 6;
let y = 3;
let s = "3";
let addition = x + y; // Addition
let subtraction = x - y; // Subtraction
let multiplication = x * y; // Multiplication
let division = x / y; // Division
console.log(addition); // Output: 9
console.log(subtraction); // Output: 3
console.log(multiplication); // Output: 18
console.log(division); // Output: 2
console.log(y == s); // true because it just compares the value, not the type 
console.log(y === s); // false because it compares the value and the type of the argument 

---

### Coding Examples

### [Compound Assignment With Augmented Multiplication](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/compound-assignment-with-augmented-multiplication)
**My Solution**

```javascript
let a = 5;
let b = 12;
let c = 4.6;

// Only change code below this line
a *= 5;
b *= 3;
c *= 10;

### [Concatenating Strings with the Plus Equals Operator](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/concatenating-strings-with-the-plus-equals-operator)
**My Solution**

```javascript
let myStr = "This is the first sentence. ";
myStr += "This is the second sentence.";

### [Use Bracket Notation to Find the Nth-to-Last Character in a String](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/use-bracket-notation-to-find-the-nth-to-last-character-in-a-string)
**My Solution**

```javascript
// Setup
const lastName = "Lovelace";

// Only change code below this line
const secondToLastLetterOfLastName = lastName[lastName.length-2]; // Change this line

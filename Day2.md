# Day 2: Expressions, Arrays, and Objects

This README file provides a summary of the JavaScript lessons on expressions, arrays, and objects. In these lessons, we delve into the concepts of working with expressions to obtain values, manipulating arrays, and creating and manipulating objects.

## Lesson 1: Expressions

Expressions are fundamental to JavaScript, and understanding them is crucial. Here are the key points covered in this lesson:

- **What are expressions?** Expressions are valid combinations of literals, variables, and operators that resolve to a single value.
- **Working with variables:** JavaScript allows us to store and retrieve values by declaring and assigning them to variables. We use the `let` and `const` keywords for variable declaration, each having different behaviors.
- **Evaluation and resolution:** JavaScript evaluates expressions based on the order of operations and resolves them to a final value.
- **Difference from statements:** Expressions are distinct from statements, which instruct JavaScript to perform actions.

## Lesson 2: Arrays

Arrays play a crucial role in JavaScript as they enable us to store multiple values within a single variable. Here are the key points covered in this lesson:

- **Understanding arrays:** Arrays are collections of items, with each item stored at a specific index.
- **Accessing array items:** We can retrieve array items using their corresponding index and determine the length of an array using the `.length` property.
- **Manipulating arrays:** JavaScript provides various array methods, such as `sort`, `join`, and `concat`, which allow us to manipulate arrays by sorting, joining, and combining them.
- **Mutability of arrays:** Some array methods modify the original array, while others create a new copy without altering the original. It is important to understand these differences to avoid unintended data mutations.
- **Immutable data:** In JavaScript, it is generally preferred to use immutable data and variables to maintain data integrity and avoid unexpected side effects.

## Lesson 3: Objects

Objects serve as a cornerstone for representing complex data structures in JavaScript. Here are the key points covered in this lesson:

- **Understanding objects:** Objects store data in key-value pairs, where the key is a string or symbol, and the value can be of any data type.
- **Accessing object properties:** We can access object properties using dot notation (`object.property`) or bracket notation (`object['property']`).
- **Methods in objects:** Objects can have properties that point to functions, which we call methods. These methods allow us to perform actions or computations related to the object.
- **Nested objects and arrays:** It is common to have nested objects and objects within arrays in JavaScript, allowing for complex data structures and hierarchical representations.
- **Built-in objects:** JavaScript provides predefined objects like `document`, `console`, `Math`, and `String`, which come with built-in methods for performing various operations.

By understanding expressions, arrays, and objects in JavaScript, you'll gain the foundational knowledge to work with data, manipulate arrays, and create complex data structures for your applications.

## Learning Method

The learning method for this lesson includes three key aspects:

1. **Spread**: The spread method allows you to unpack elements from arrays and objects, enabling you to use them as separate entities in various operations.

2. **Freeze**: The freeze method is used to make objects and arrays immutable, preventing any further modifications to their properties or elements.

3. **Function**: Functions in JavaScript are reusable blocks of code that can perform specific tasks. They can take in parameters, execute a set of instructions, and return a value.

### Day 2 Agenda

On the second day of the course, we will cover the following topics:

- Introduction to expressions and their usage to obtain values.
- Manipulating arrays using various built-in methods and techniques.
- Creating objects and performing operations to modify their properties and behavior.
  
## Coding Examples

Here are some coding examples to illustrate concepts covered in the lessons.

 // Example 1: Declaring and Assigning Variables

```javascript

// Example 1: Manipulating Arrays
const numbers = [1, 2, 3, 4, 5];

// Accessing array items
console.log(numbers[0]); // Output: 1

// Adding items to the array 
numbers[2] = 8;
console.log(numbers); // Output: [1, 2, 8, 4, 5]

// Array methods (the sort method is tricky in some places as it arranges the array in lexicographic(alphabetical) order)

const sortedNumbers = numbers.sort();
console.log(sortedNumbers); // Output: [1, 8, 2, 4, 5]

const joinedNumbers = numbers.join("|");
console.log(joinedNumbers); // Output: "1|8|2|4|5"

const concatenatedNumbers = numbers.concat([6, 7, 8,9]);
console.log(concatenatedNumbers); // Output: [1, 10, 2, 4, 5, 6, 7, 8,9]

// Example 2: Creating and Accessing Objects
const person = {
  name: "Salsabeel Alsahoury",
  age: 20,
  address: Zatr'a
};

console.log(person.name); // Output: "Salsabeel Alsahoury"
console.log(person["age"]); // Output: 20
```
## Coding Exercises
## [Profile Lookup](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/profile-lookup)
### My Solution
```javascript
// Setup
const contacts = [
  {
    firstName: "Akira",
    lastName: "Laine",
    number: "0543236543",
    likes: ["Pizza", "Coding", "Brownie Points"],
  },
  {
    firstName: "Harry",
    lastName: "Potter",
    number: "0994372684",
    likes: ["Hogwarts", "Magic", "Hagrid"],
  },
  {
    firstName: "Sherlock",
    lastName: "Holmes",
    number: "0487345643",
    likes: ["Intriguing Cases", "Violin"],
  },
  {
    firstName: "Kristian",
    lastName: "Vos",
    number: "unknown",
    likes: ["JavaScript", "Gaming", "Foxes"],
  },
];

function lookUpProfile(name, prop) {
  const contact = contacts.find((contact) => contact.firstName === name);

  if (contact) {
    return contact[prop] || "No such property";
  }

  return "No such contact";
}

lookUpProfile("Akira", "likes");

```
### [Copy Array Items Using slice()](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-data-structures/copy-array-items-using-slice)
### My Solution
```javascript
function forecast(arr) {
  // Only change code below this line

  return arr.slice(2, 4);
}

// Only change code above this line
console.log(forecast(['cold', 'rainy', 'warm', 'sunny', 'cool', 'thunderstorms']));
```
### [Combine Arrays with the Spread Operator](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-data-structures/combine-arrays-with-the-spread-operator)

```javascript
function spreadOut() {
  let fragment = ['is', 'a'];
  let sentence =['salsabeel',...fragment,'student'];
  return sentence;
}

console.log(spreadOut());


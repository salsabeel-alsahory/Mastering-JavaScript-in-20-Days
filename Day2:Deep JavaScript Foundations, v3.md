# Day 2: Static Typing and Scope

Welcome to Day 2 of the "Deep JavaScript Foundations, v3" course. In this session, we'll dive into two important concepts in JavaScript: Static Typing and Scope. Understanding these concepts is crucial for writing robust and maintainable code.

## Lesson Summary:

### Static Typing:

Static typing is a powerful technique that involves specifying the data types of variables and function parameters during the development phase.
This helps catch type-related errors early in the development process, making the code more reliable and less prone to bugs.

#### TypeScript & Flow:

We'll explore two popular static type checkers for JavaScript: TypeScript and Flow.
These tools allow developers to define and enforce types,
leading to better code quality and maintainability.
TypeScript is a superset of JavaScript, while Flow is a static type checker. We'll discuss the benefits and drawbacks of using each of them and how they can enhance the development workflow.

#### Inferencing:

Inferencing is a fascinating feature in static typing where the type checker automatically deduces the data type of a variable based on its assigned value. This means developers can write code without always specifying explicit type annotations, as the type checker infers the types. This results in more concise and readable code.

#### Custom Types:

We'll explore the concept of custom types, where developers can create their own user-defined data structures using TypeScript or Flow. Custom types provide flexibility in modeling complex data and enable better control over type safety, reducing the likelihood of type misassignments.

#### Validating Operand Types:

One of the key advantages of static typing is validating operand types. By ensuring that the types of operands are correct, we can prevent errors caused by incompatible data types during operations.

### Scope:

Scope is another critical concept in JavaScript that deals with the visibility and accessibility of variables within different parts of the code.

#### Compilation & Scope:

During the compilation phase, variable declarations are hoisted, and scope determines where variables can be accessed. We'll delve into the compilation process and understand its relation to scope in JavaScript.

#### Executing Code:

We'll walk through the execution of code and differentiate between two types of lookups: lexical scope and dynamic scope. Understanding these scopes is essential for identifying where variables and functions are accessible within the code.

#### Dynamic Global Variables:

We'll demonstrate the concept of dynamic global variables and how they are created in different situations. This understanding is crucial for managing global variables effectively.

#### Strict Mode:

JavaScript's strict mode is an opt-in feature that enables a stricter set of rules for writing JavaScript code. We'll discuss the arguments for using strict mode, how it helps in writing safer code, and the common pitfalls it can prevent.

#### Nested Scope:

We'll explore examples of nested scope, where inner functions have access to variables in their containing (outer) functions. Understanding nested scope is essential for managing variable access and avoiding unintended side effects.

#### Undefined vs Undeclared:
-**Undefined:** In JavaScript, "undefined" is a special value that represents the absence of a value. It is assigned to a variable that has been declared but not explicitly given a value or when a function does not return any value. For example, let x; will initialize the variable x with the value "undefined" by default.

-**Undeclared:** "Undeclared" refers to a variable that has not been declared or defined in the current scope. Trying to access an undeclared variable will result in a ReferenceError. For instance, console.log(z); will throw a ReferenceError if the variable z has not been declared before this line of code.
## Coding Exercises
### [Learning sprint (1), week (3), day (2) delieverables](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week3-day2-tasks/tasks.md)
- **Question 1:**
  ### solution:
  B) 1, undefined, ReferenceError
 Variables declared with var have function scope and are hoisted, while let and const are block-scoped and not hoisted.
- **Question 2:**
- ### solution:
  B) 1, undefined, ReferenceError
  var variables are hoisted and initialized with undefined, while let and const are not hoisted and remain uninitialized until their declaration.
- **Question 3:**
  #### solution:
  A) because is declared using var, making it function-scoped and accessible throughout the function.
   Its value changes to 1 inside the if block




# Day 2: Closure

This README file summarizes the concept of closure, nested functions, memory management, and closure function scope.

## Lesson Summary

- **Closure:** Closure is a powerful concept in programming where a function retains access to variables from its outer scope even after the outer function has finished executing. This allows the inner function to "remember" and use those variables.

- **Nested functions:** Nested functions, also known as inner functions, are functions defined within the scope of another function. They have access to variables from their outer function's scope and can be invoked inside or returned as values.

- **Memory management:** Proper memory management is essential when working with closure. Variables and functions stored in memory through closure will persist until they are no longer referenced. Understanding memory allocation, deallocation, and garbage collection is crucial in managing memory effectively.

- **Closure function scope:** Closure functions have access to variables from their outer function's scope due to lexical scoping. Lexical scoping means that variables are resolved based on their position in the source code. This enables closure to maintain access to the variables it needs.

## Coding Exercises
### [Learning sprint (1), week (2), day (2) delieverables](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week2-day2-tasks/tasks.md)
#### Question 1:
```javascript
function createCounter(initialValue) {
  let counter = initialValue;

  function incrementCounter() {
    counter++;
    return counter;
  }

  return incrementCounter;
}

console.log(createCounter(2)()); // Output: 3

```
#### Question 2:
```javascript
function calculateAverage(numbers) {
  return function() {
    const sum = numbers.reduce((acc, num) => acc + num, 0);
    const count = numbers.length;
    const result = sum / count;
    return result;
  };
}

console.log(calculateAverage([1, 2, 3])); // Output: 2

```
#### Question 3:
```javascript
function powerOf(baseNum) {
  function power(exp) {
    return Math.pow(baseNum, exp);
  }
  return power;
}

console.log(powerOf(2)(3)); // Output: 8

```
#### Question 4: 
[example of this quastion ](https://medium.com/javascript-scene/curry-and-function-composition-2c208d774983)
```javascript
function compose(...functions) {
  function functionsCompose(argument) {
    return functions.reduceRight((output, func) => func(output), argument);
  }
  return functionsCompose;
}

function divide(x, y) {
  return x / y;
}

function multiply(x, y) {
  return x * y;
}

console.log(compose(divide, multiply)(6, 2));

```

# Day1:Introduction and types
This README file summarizes the key concepts covered on Day 1 of "Deep JavaScript Foundations, v3" course.
## Lesson Summary:
### Introduction:
Kyle introduces the course and emphasizes the importance of thinking deeply about JavaScript.
Types:

 ### Primitive Types: 
 Kyle explains JavaScript's type system and debunks the misconception that everything in JavaScript is an object.
- **typeof Operator:** Discussion on the behavior of the typeof operator and cases that may cause confusion.
- **BigInt:** Explanation of how BigInt differs from other numbers in JavaScript.
Kinds of Emptiness: Understanding various ways something can be empty in JavaScript, such as undefined, undeclared, and uninitialized.
- **NaN & isNaN:** Discussion about NaN (Not-a-Number), how to use isNaN, and common sources of error in using both.
Negative Zero: Context of -0 in JavaScript and how operations on it can lead to unexpected results.
## Coding Exercises
### [Learning sprint (1), week (3), day (1) delieverables](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week3-day1-tasks/tasks.md)
#### My solution

- **Question 1:**
```javascript
  function convertStringToNumber(input) {
  if (typeof input === 'string') {
    return +input;
  }
  return { value: input, type: typeof input };
}
```
**Question 2:**
```javascript
const checkNaN = (value) => {
  return Number.isNaN(value);
}

```
**Question 3:**
```javascript
function isEmptyValue(value) {
  return value === undefined || value === null || value === '';
}

```
**Question 4:**
```javascript
function compareObjects(input1, input2) {
  if (typeof input1 === 'object' && typeof input2 === 'object') {
    return JSON.stringify(input1) === JSON.stringify(input2);
  } else {
    return [input1, input2];
  }
}

```
**Question 5:**
```javascript
const complexCoercion = (input) => {
  if (typeof input !== 'object') {
    if (typeof input === 'number') {
      return !!String(input);
    } else if (typeof input === 'string') {
      return !!input;
    } else {
      return false;
    }
  } else {
    return input;
  }
}

```

# Day4:Advanced Scope and Closure
This README file summarizes the key concepts covered on Day 4 of "Deep JavaScript Foundations, v3" course.
## Coding Exercises
### [Learning sprint (1), week (3), day (4) delieverables](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week3-day4-tasks/tasks.md)
#### My solution
**Question 1:**
```javascript
for (let i = 0; i < 5; i++) {
  setTimeout(function () {
    console.log("value of [i] is: ", i);
  }, 100);
}
```
**Question 2:**
```javascript
let array = [];

for (let i = 0; i < 5; i++) {
  array.push(i);
  console.log("Current array is: ", array);
}
```
**Question 3:**
```javascript
let functions = [];

for (let i = 0; i < 5; i++) {
  functions.push(() => {
    console.log("Current value of i is:", i);
  });
}

functions.forEach((func) => func());
```
**Question 4:**
```javascript
function privateCounter() {
  let count = 0;

  return {
    increment: function () {
      count++;
    },
    getCount: function () {
      return count;
    }
  };
}

const counter = privateCounter();
counter.increment();
counter.increment();
console.log(counter.getCount()); // Output: 2

```
**Question 5:**
```javascript
function generateFibonacci(count) {
  let currentCount = 0;

  function fibonacci() {
    if (currentCount === 0 || currentCount === 1) {
      currentCount++;
      return currentCount - 1;
    } else {
      let result = currentCount;
      currentCount = currentCount + (currentCount - 1);
      return result;
    }
  }

  return function () {
    if (currentCount < count) {
      return fibonacci();
    } else {
      return undefined;
    }
  };
}

const nextFibonacci = generateFibonacci(5);
console.log(nextFibonacci()); // Output: 0
console.log(nextFibonacci()); // Output: 1
console.log(nextFibonacci()); // Output: 2
console.log(nextFibonacci()); // Output: 3
console.log(nextFibonacci()); // Output: 5
console.log(nextFibonacci()); // Output: undefined

```

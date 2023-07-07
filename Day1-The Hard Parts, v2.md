# Day 1: Introduction, javascript principles, Functions & Callbacks 
This README file summarizes the key concepts covered on Day 1 of my The Hard Parts, v2 course.
On this day, I explored the fundamentals of JavaScript, including an introduction to the language threads and how it runs the code, the javascript principles, and Functions & Callbacks 
I also solved three coding exercises to practice my skills.

## Lesson Summary
- **Introduction:** Introduction to the course.
- 
- **javascript principles** In JavaScript, a thread represents the basic unit of execution and JavaScript is single-threaded, meaning it executes code sequentially.
- The call stack is a data structure that keeps track of function calls in the program.
-  Functions are added to the stack when called and removed when they are complete.
-  This ensures proper execution order and follows the Last-In-First-Out principle.

  ## Coding Exercises
  - ### [Use Higher-Order Functions map, filter, or reduce to Solve a Complex Problem](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/functional-programming/use-higher-order-functions-map-filter-or-reduce-to-solve-a-complex-problem)
#### My solution
```javascript
const squareList = arr => {
  // Only change code below this line
  let i=0;
  let squer=[];
while(arr.length>i){
 let num =arr[i];
 if(num>0&&Number.isInteger(num)){
  squer.push(num*num)

 }
 i++;
}
 return squer;
  // Only change code above this line
};

const squaredIntegers = squareList([-3, 4.8, 5, 3, -3.2]);
console.log(squaredIntegers);
```
- ### [Apply Functional Programming to Convert Strings to URL Slugs](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/functional-programming/apply-functional-programming-to-convert-strings-to-url-slugs)
- #### My solution
  
  ```javascript
  // Only change code below this line
function urlSlug(title) {

    const url = title.split(" ").map(word=>word.toLowerCase()).join("-");
return url;

}
// Only change code above this line
console.log(urlSlug("A Mind Needs Books Like A Sword Needs A Whetstone"));
console.log(urlSlug("Winter Is Coming") );


### [Exircise for Functions and Callbacks](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week2-day1-tasks/tasks.md)
#### My solution 
```javascript
```



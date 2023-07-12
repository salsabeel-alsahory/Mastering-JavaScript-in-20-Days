# Day 1: Introduction, JavaScript Principles, Functions & Callbacks

This README file summarizes the key concepts covered on Day 1 of "The Hard Parts, v2" course.

## Lesson Summary

- **Introduction:** An introduction to the course.
- **JavaScript Principles:** JavaScript is a single-threaded language where code executes sequentially. The call stack keeps track of function calls, following the Last-In-First-Out principle.
- **Functions & Callbacks:** Functions are the building blocks of JavaScript. Callbacks are functions that are passed as arguments to other functions and are invoked later.

## Coding Exercises

### [Use Higher-Order Functions map, filter, or reduce to Solve a Complex Problem](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/functional-programming/use-higher-order-functions-map-filter-or-reduce-to-solve-a-complex-problem)

#### My solution

```javascript
const squareList = arr => {
  let squaredIntegers = arr.filter(num => num > 0 && Number.isInteger(num)).map(num => num * num);
  return squaredIntegers;
};

const squaredIntegers = squareList([-3, 4.8, 5, 3, -3.2]);
console.log(squaredIntegers);
```
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
### [Apply Functional Programming to Convert Strings to URL Slugs](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/functional-programming/apply-functional-programming-to-convert-strings-to-url-slugs)
 #### My solution
  ```javascript
  // Only change code below this line
    function urlSlug(title) {

    const url = title.split(" ").map(word=>word.toLowerCase()).join("-");
   return url;

}
// Only change code above this line
console.log(urlSlug("A Mind Needs Books Like A Sword Needs A Whetstone"));
console.log(urlSlug("Winter Is Coming") );
```

### [Exircise for Functions and Callbacks](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week2-day1-tasks/tasks.md)
#### My solution 
```javascript
function mapAsync(array, mapInstruction) {
    return new Promise(async (resolve, reject) => {
      try {
        const result = [];
        for (let i = 0; i < array.length; i++) {
            // pauses the execution of the loop until the promise returned by mapInstruction is resolved
          const mappedValue = await mapInstruction(array[i]);
          result.push(mappedValue);
        }
        resolve(result);
      } catch (error) {
        reject(error);
      }
    });
  }
  function multiplyByTwo(number) {
    return new Promise((resolve) => {
      setTimeout(() => {
        resolve(number * 2); // Multiply the number by 2
      }, 1000); // Simulating an asynchronous operation
    });
  }
  
  mapAsync([1, 2, 3, 4], multiplyByTwo)
    .then((result) => {
      console.log(result); // [2, 4, 6, 8]
    })
    .catch((error) => {
      console.error(error);
    });


//Write a JavaScript function called sumRange that calculates the sum of all integers in
//  a given range. The function should use recursion to handle the calculation and demonstrate 
// understanding of the call stack.
function sumRange (from,to){
    
        if (from > to) {
          return 0; 
        } else {
          return from + sumRange(from + 1, to); 
        }
  
}
console.log(sumRange(1, 10)); // Output: 55

```



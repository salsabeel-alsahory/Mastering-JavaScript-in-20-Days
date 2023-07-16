# Day 3: Async javaScript & Promises 

## Asynchronous in JavaScript :
Asynchronous programming in JavaScript allows for non-blocking execution of tasks, improving performance and responsiveness by a range of asynchronous browser features :
- **Timers:** such as setTimeout and setInterval, enable executing code after a specified delay or at regular intervals.
  
- **AJAX:** (Asynchronous JavaScript and XML) enables making HTTP requests to servers asynchronously, without blocking the main thread.
  
- **fetch:** The browser's fetch API simplifies making HTTP requests and handling responses asynchronously using Promises.

   ## Promises:
 - Promises are a programming pattern in JavaScript used for handling asynchronous operations.
- They represent the eventual completion (or failure) of an asynchronous task and allow writing asynchronous code in a more synchronous style.
- Promises have three states: pending, fulfilled, or rejected, which reflect the state of the asynchronous operation.
- Promises provide a cleaner and more readable way to handle asynchronous code compared to traditional callback-based approaches.
  ## Coding Exercises:
### [Learning sprint (1), week (2), day (3) delieverables](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week2-day3-tasks/tasks.md)
#### Question 1:
```javascript

const task1 = (cb) => setTimeout(() => {
  const message = "Task 1 has executed successfully!";
  cb(message);
}, 3000);

const task2 = (cb) => setTimeout(() => {
  const message = "Task 2 has executed successfully!";
  cb(message);
}, 0);

const task3 = (cb) => setTimeout(() => {
  const message = "Task 3 has executed successfully!";
  cb(message);
}, 1000);

const task4 = (cb) => setTimeout(() => {
  const message = "Task 4 has executed successfully!";
  cb(message);
}, 2000);

const task5 = (cb) => setTimeout(() => {
  const message = "Task 5 has executed successfully!";
  cb(message);
}, 4000);

const asyncTasks = [task1, task2, task3, task4, task5];

const executeInSequenceWithCBs = (tasks, callback) => {
  const messages = [];
  let index = 0;

  const executeTask = () => {
    if (index < tasks.length) {
      tasks[index]((message) => {
        messages.push(message);
        index++;
        executeTask();
      });
    } else {
      callback(messages);
    }
  };

  return executeTask();
};

const callback = (messages) => {
  console.log("Messages:", messages);
};

executeInSequenceWithCBs(asyncTasks, callback);

```
#### Question 2:
```javascript
const executeInParallelWithPromises = (apis) => {
  const promises = apis.map(api => fetch(api.apiUrl)
    .then(response => response.json())
    .then(data => ({
      apiName: api.apiName,
      apiUrl: api.apiUrl,
      apiData: data
    }))
  );

  return Promise.all(promises);
};
```

#### Question 3:
```javascript
const executeInSequenceWithPromises = (apis) => {
  let promiseChain = Promise.resolve();
  const results = [];

  apis.forEach(api => {
    promiseChain = promiseChain
      .then(() => fetch(api.apiUrl))
      .then(response => response.json())
      .then(data => {
        results.push({
          apiName: api.apiName,
          apiUrl: api.apiUrl,
          apiData: data
        });
      });
  });

  return promiseChain.then(() => results);
};

```

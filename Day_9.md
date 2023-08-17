
# Day 9: JavaScript: The Hard Parts, v2

## Asynchronous JavaScript

### JavaScript is:
- Single threaded (one command runs at a time)
- Synchronously executed (each line is run in order the code appears)

### Synchronous Programming
Synchronous programming is where the computer will complete one task before moving on to the next. This makes it easy to understand and predict what the computer will do at any given time.

### Asynchronous programming
Asynchronous programming in JavaScript allows you to perform non-blocking operations and handle tasks that may take some time to complete, such as fetching data from a server or reading a file. It ensures that your program doesn't get blocked while waiting for these operations to finish. There are several ways to achieve asynchronous programming in JavaScript, including callback functions, promises, and the newer async/await syntax.

### setTimeout is a built in function - its first argument is the function to delay followed by ms to delay by

core JavaScript engine has 3 main parts:
- Thread of execution
- Memory/variable environment
- Call stack
We need to add some new components:
- Web Browser APIs/Node background APIs->This is where the actual functionality for built-in functions like setTimeout() and fetch() are located.
- Promises
- Event loop, Callback/Task queue and micro task queue 

 ![image](https://github.com/AnwarMelhem/Mastering_JavaScript_in_20_Days/assets/97465642/9562a561-83bc-4a98-bd34-1af674ba8273)

We have rules for the execution of our asynchronously delayed code
Hold promise-deferred functions in a microtask queue and 
callback function in a task queue (Callback queue) 
when the Web Browser Feature (API) finishes add the function to the Call stack (i.e. run the function) when:
- Call stack is empty & all global code run (Have the Event Loop check this condition)
### Prioritize functions in the microtask queue over the Callback queue

### Call stack
A call stack is a mechanism for an interpreter (like the JavaScript interpreter in a web browser) to keep track of its place in a script that calls multiple functions — what function is currently being run and what functions are called from within that function, etc.

When a script calls a function, the interpreter adds it to the call stack and then starts carrying out the function.
Any functions that are called by that function are added to the call stack further up, and run where their calls are reached.
When the current function is finished, the interpreter takes it off the stack and resumes execution where it left off in the last code listing.
If the stack takes up more space than it was assigned, a "stack overflow" error is thrown.

### Promise 
The Promise object represents the eventual completion (or failure) of an asynchronous operation and its resulting value.

A Promise is a proxy for a value not necessarily known when the promise is created. It allows you to associate handlers with an asynchronous action's eventual success value or failure reason. This lets asynchronous methods return values like synchronous methods: instead of immediately returning the final value, the asynchronous method returns a promise to supply the value at some point in the future.

A Promise is in one of these states:
- pending: initial state, neither fulfilled nor rejected.
- fulfilled: meaning that the operation was completed successfully.
- rejected: meaning that the operation failed.
*********************************************************************************************************************
## Coding Exercises
### 1) [Question 1:](https://github.com/orjwan-alrajaby/gsg-QA-Nablus-training-2023/blob/main/learning-sprint-1/week2%20-%20javaScript-the-hard-parts-v2/day%203/tasks.md)
You are given a function executeInSequenceWithCBs and some code. The task is to modify the executeInSequenceWithCBs function so that it runs and executes all the tasks inside the asyncTasks array.

The function should return an array of messages obtained from each task's execution.

You are only allowed to change the executeInSequenceWithCBs function or add new functions/code. You cannot modify the tasks' functions.
```javascript

const task1 = (cb) => setTimeout(() => {
  const message = "Task 1 has executed successfully!";
  cb(message);
}, 3000)

const task2 = (cb) => setTimeout(() => {
  const message = "Task 2 has executed successfully!";
  cb(message);
}, 0)

const task3 = (cb) => setTimeout(() => {
  const message = "Task 3 has executed successfully!";
  cb(message);
}, 1000)

const task4 = (cb) => setTimeout(() => {
  const message = "Task 4 has executed successfully!";
  cb(message);
}, 2000)

const task5 = (cb) => setTimeout(() => {
  const message = "Task 5 has executed successfully!";
  cb(message);
}, 4000)

const asyncTasks = [task1, task2, task3, task4, task5];

const executeInSequenceWithCBs = async(tasks, callback) => {
  const results = [];

  await Promise.all(tasks.map((task) => new Promise(resolve => {
    task(message => {
      results.push(message);
      resolve();
    });
  })));

  callback(results);
}

console.log(executeInSequenceWithCBs(asyncTasks,(result)=>{console.log(result,"ans from callback")}));
```
***********************************************************************************************
### 2) [Question 2:](https://github.com/orjwan-alrajaby/gsg-QA-Nablus-training-2023/blob/main/learning-sprint-1/week2%20-%20javaScript-the-hard-parts-v2/day%202/tasks.md)


```javascript

```
************************************************************************************************
### 3) [Question 3:](https://github.com/orjwan-alrajaby/gsg-QA-Nablus-training-2023/blob/main/learning-sprint-1/week2%20-%20javaScript-the-hard-parts-v2/day%203/tasks.md)


```javascript

```



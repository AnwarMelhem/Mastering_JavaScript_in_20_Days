
# Day 9: JavaScript: The Hard Parts, v2

## Asynchronous JavaScript

## JavaScript is:
- Single threaded (one command runs at a time)
- Synchronously executed (each line is run in order the code appears)

## Synchronous Programming
Synchronous programming is where the computer will complete one task before moving on to the next. This makes it easy to understand and predict what the computer will do at any given time.

## Asynchronous programming
Asynchronous programming in JavaScript allows you to perform non-blocking operations and handle tasks that may take some time to complete, such as fetching data from a server or reading a file. It ensures that your program doesn't get blocked while waiting for these operations to finish. There are several ways to achieve asynchronous programming in JavaScript, including callback functions, promises, and the newer async/await syntax.

## setTimeout is a built in function - its first argument is the function to delay followed by ms to delay by

core JavaScript engine has 3 main parts:
- Thread of execution
- Memory/variable environment
- Call stack
We need to add some new components:
- Web Browser APIs/Node background APIs
- Promises
- Event loop, Callback/Task queue and micro task queue 


## Promise 
The Promise object represents the eventual completion (or failure) of an asynchronous operation and its resulting value.

A Promise is a proxy for a value not necessarily known when the promise is created. It allows you to associate handlers with an asynchronous action's eventual success value or failure reason. This lets asynchronous methods return values like synchronous methods: instead of immediately returning the final value, the asynchronous method returns a promise to supply the value at some point in the future.

A Promise is in one of these states:
- pending: initial state, neither fulfilled nor rejected.
- fulfilled: meaning that the operation was completed successfully.
- rejected: meaning that the operation failed.

  ![image](https://github.com/AnwarMelhem/Mastering_JavaScript_in_20_Days/assets/97465642/9562a561-83bc-4a98-bd34-1af674ba8273)


## Call stack
A call stack is a mechanism for an interpreter (like the JavaScript interpreter in a web browser) to keep track of its place in a script that calls multiple functions — what function is currently being run and what functions are called from within that function, etc.

When a script calls a function, the interpreter adds it to the call stack and then starts carrying out the function.
Any functions that are called by that function are added to the call stack further up, and run where their calls are reached.
When the current function is finished, the interpreter takes it off the stack and resumes execution where it left off in the last code listing.
If the stack takes up more space than it was assigned, a "stack overflow" error is thrown.
*********************************************************************************************************************
## Coding Exercises
### 1) [Question 1:](https://github.com/orjwan-alrajaby/gsg-QA-Nablus-training-2023/blob/main/learning-sprint-1/week2%20-%20javaScript-the-hard-parts-v2/day%202/tasks.md)
Write a closure named createCounter that takes an initial value start and returns a function. The returned function, when invoked, should increment the counter by 1 and return the updated value.

```javascript
const squareList = arr => {
  const arr1= arr.filter(num => num > 0 && num % parseInt(num) === 0)
          .map(num => Math.pow(num, 2));
  return arr1

};

const squaredIntegers = squareList([-3, 4.8, 5, 3, -3.2]);
console.log(squaredIntegers);
```
***********************************************************************************************
### 2) [Question 2:](https://github.com/orjwan-alrajaby/gsg-QA-Nablus-training-2023/blob/main/learning-sprint-1/week2%20-%20javaScript-the-hard-parts-v2/day%202/tasks.md)
Write a closure named calculateAverage that takes an array of numbers, nums, and returns a function. The returned function, when invoked, should calculate and return the average of the numbers in the array.

```javascript
function calculateAverage(ArrayOfNumber){
   
  function innerAverage (){ 
    let sum =0
    for(let i=0;i<ArrayOfNumber.length;i++){
      sum=sum+ArrayOfNumber[i];
    }
    let result=sum/ArrayOfNumber.length;
    return result;
   }
  return innerAverage;
 }
 const myNewFunction = calculateAverage([1,2,3,4,5,6,7,8,9,10]);
 const result=myNewFunction();
 console.log(result);
```
************************************************************************************************
### 3) [Question 3:](https://github.com/orjwan-alrajaby/gsg-QA-Nablus-training-2023/blob/main/learning-sprint-1/week2%20-%20javaScript-the-hard-parts-v2/day%202/tasks.md)
Write a closure named powerOf that takes a base number base and returns a function. The returned function, when invoked with an exponent exp, should calculate and return the result of base raised to the power of exp.

```javascript
function powerOf(baseNumber){
   
  function exponent (exp){ 
    return Math.pow(baseNumber,exp)
   }
  return exponent;
 }
 const myNewFunction = powerOf(2);
 const result=myNewFunction(5);
 console.log(result);
```
***********************************************************************************************
### 4) [Question 4:](https://github.com/orjwan-alrajaby/gsg-QA-Nablus-training-2023/blob/main/learning-sprint-1/week2%20-%20javaScript-the-hard-parts-v2/day%202/tasks.md)
Write a closure named compose that takes multiple functions as arguments and returns a new function. The returned function should apply the provided functions in reverse order, passing the result of each function as an argument to the next function.
```javascript
function add10(x) {
  return x + 10;
}

function multiply2(x) {
  return x * 2;
}

function subtract3(x) {
  return x - 3;
}

function compose(...functions) {
  return function(arg) {
    for (let i = functions.length - 1; i >= 0; i--) {
      arg = functions[i](arg);
    }
    return arg;
  };
}

const composedFunction = compose(subtract3, multiply2, add10);
console.log(composedFunction(10));
```
***********************************************************************************************


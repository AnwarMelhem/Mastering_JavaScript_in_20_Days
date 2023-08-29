
# Day 8: JavaScript: The Hard Parts, v2

## Clousers 
In JavaScript, closures are an important concept that allows functions to access variables from their outer lexical environment even after the outer function has finished executing. 

A closure is created when an inner function is returned from an outer function and still has access to its lexical scope, including the variables and parameters of the outer function.

A closure is a function that preserves the outer scope in its inner scope.

Closures are powerful because they allow functions to retain access to the variables they need, even when they are invoked outside their original lexical scope. This behavior enables advanced patterns and techniques in JavaScript programming.

- Lexical scoping describes how the JavaScript engine uses the location of the variable in the code to determine where that variable is available.
- A closure is a combination of a function and its ability to remember variables in the outer scope.

## Functions with memories
-the Functions get a new memory every run/invocation
- When our functions get called, we create a live store of data (local
memory/variable environment/state) for that function’s execution context.
- When the function finishes executing, its local memory is deleted (except the
returned value)

## Calling a function in the same function call as it was defined
```javascript
function outer (){
 let counter = 0;
 function incrementCounter (){
 counter ++;
 }
 incrementCounter();
}
outer();
```
## Calling a function outside of the function call in which it was defined
```javascript
function outer (){
 let counter = 0;
 function incrementCounter (){ counter ++; }
 return incrementCounter;
}
const myNewFunction = outer();
myNewFunction();
myNewFunction();
```

*********************************************************************************************************************
## Coding Exercises
### 1) [Question 1:](https://github.com/orjwan-alrajaby/gsg-QA-Nablus-training-2023/blob/main/learning-sprint-1/week2%20-%20javaScript-the-hard-parts-v2/day%202/tasks.md)
Write a closure named createCounter that takes an initial value start and returns a function. The returned function, when invoked, should increment the counter by 1 and return the updated value.

```javascript
function createCounter(start) {
  let counter = start;

  function increment() {
    counter++;
    return counter;
  }

  return increment;
}

const counter1 = createCounter(0);
console.log(counter1()); // Output: 1
console.log(counter1()); // Output: 2

const counter2 = createCounter(5);
console.log(counter2()); // Output: 6
console.log(counter2()); // Output: 7
```
***********************************************************************************************
### 2) [Question 2:](https://github.com/orjwan-alrajaby/gsg-QA-Nablus-training-2023/blob/main/learning-sprint-1/week2%20-%20javaScript-the-hard-parts-v2/day%202/tasks.md)
Write a closure named calculateAverage that takes an array of numbers, nums, and returns a function. The returned function, when invoked, should calculate and return the average of the numbers in the array.

```javascript
function calculateAverage(nums) {
   function avg() {
    let sum = 0;
    let avg1=0;
    for (let i = 0; i < nums.length; i++) {
      sum += nums[i];
    }
    avg1= sum / nums.length;
    console.log(avg1)
  };
  return avg;
}


// Example usage:
const numbers = [2, 4, 6, 8, 10];
const averageCalculator = calculateAverage(numbers);
console.log(averageCalculator());


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


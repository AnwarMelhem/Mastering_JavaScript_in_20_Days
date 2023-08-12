
# Day 7: JavaScript: The Hard Parts, v2

## JavaScript principles:
When JavaScript code runs, it:
Goes through the code line-by-line and runs/ ’executes’ each line - known as the thread of execution
Saves ‘data’ like strings and arrays so we can use that data later - in its memory
We can even save code (‘functions’)

Functions Created to run the code of a function - has 2 parts
- Thread of execution
- Memory
  
Execution context
Code we save (‘define’) functions &
can use (call/invoke/execute/run)
later with the function’s name & ( )

###  Call Stack
call stack-> JavaScript keeps track of what function is currently running (where’s the thread of execution)
- Run a function - add to call stack
- Finish running the function - JS removes it from call stack
- Whatever is top of the call stack that’s the function we’re currently running

### DRY-> Don't Repeat your self ->fundamental principle programming

### We can generalize the function to make it reusable

### Generalizing functions
‘Parameters’ (placeholders) mean we don’t need to decide what data to run our
functionality on until we run the function->Then provide an actual value (‘argument’) when we run the function

### Callback function
A callback function is a function passed into another function as an argument, which is then invoked inside the outer function to complete some kind of routine or action.

There are two ways in which the callback may be called: synchronous and asynchronous. Synchronous callbacks are called immediately after the invocation of the outer function, with no intervening asynchronous tasks, while asynchronous callbacks are called at some point later, after an asynchronous operation has completed.

# Which is our Higher Order Function?
The outer function that takes in a function is our higher-order function

# Which is our Callback Function
The function we insert is our callback function


## Functions in javascript = first class objects
They can co-exist with and can be treated like any other javascript object
1. Assigned to variables and properties of other objects
2. Passed as arguments into functions
3. Returned as values from functions

## Arrow function expressions
An arrow function expression is a compact alternative to a traditional function expression, with some semantic differences and deliberate limitations in usage

*********************************************************************************************************************
## Coding Exercises
### 1) [rick&Morty Character List](https://github.com/orjwan-alrajaby/gsg-QA-Nablus-training-2023/blob/main/learning-sprint-1/week1%20-%20javascript-from-first-steps-to-professional/day%206/task.md)

#### My Solution
https://github.com/AnwarMelhem/Rick_Morty_Character_List
#### My Vedio 
https://drive.google.com/file/d/1whKhujzWYzV8qhF5ndCJ5SBjLWzFc0Bn/view?usp=sharing

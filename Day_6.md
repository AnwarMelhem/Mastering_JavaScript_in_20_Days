
# Day 6: JavaScript: From First Steps to Professional Course By FrontEnd Master

## Lesson Summary
### API & Fetch

URLs point to resources on the web
APIs provide URLs that point at data we care about
fetch() lets us use JS to load data from APIs

### Promises
->Promises provide a more structured approach to handling asynchronous operations. A promise represents the eventual completion or failure of an asynchronous operation and allows you to attach callbacks to handle the resul

->JS writes us an "IOU" for the data value it doesn't have yet
aka a Promise of a value

Promises can be in 3 possible states:
pending: still waiting for the value, hang tight
fulfilled (aka "resolved"): finally got the value, all done
rejected: sorry couldn't get the value, all done
It takes time for Promises to resolve, so they are "asynchronous"

### await
- await lets us tell JS to stop and wait for an asynchronous operation to finish

- The await operator is used to wait for a Promise and get its fulfillment value. It can only be used inside an async function or at the top level of a module

### Destructuring
- Destructuring assignment provides a way to extract values from arrays or objects and assign them to variables
- Destructuring is a fancy way of declaring multiple variables at once
- We can also destructure Arrays, assigning variables for their items
- We can ignore the values in the array we don't need
- We can use commas to "skip" values
- We can use ... to collect remaining values

### async function
The async function declaration creates a binding of a new async function to a given name. The await keyword is permitted within the function body, enabling asynchronous, promise-based behavior to be written in a cleaner style and avoiding the need to explicitly configure promise chains

### Modules
Modules provide a way to organize code into reusable, independent pieces in JavaScript. They can be thought of as a file that exports certain values (variables, functions, classes, etc.) and can be imported into other files

- Modules let us split big codebases across multiple files
- JS modules work differently from JS scripts
- One difference is that we can't use await outside of a function in a script
- Another difference is that modules create their own scope

### import && export
- export lets us expose variables from our module's scope to the outside world
- import lets us use an exposed variable from another module

  ### Debugging
  console.log() (or .warn() or .error()) is one way to understand what's happening when your program runs
  can also use the browser's debugger to pause JS and inspect what's happening
  The debugger statement creates a breakpoint where JS will pause and let you look around
  Different browsers' debuggers work differently
- Firefox
- Chrome
- Safari

  ### try & catch Error Handling
  # Error Handling
Error handling is an important aspect of JavaScript programming as it allows you to gracefully handle and respond to unexpected errors and exceptions that may occur during the execution of your code. Here are some examples of error handling techniques in JavaScript

# Try...Catch Statement
The try...catch statement is used to catch and handle exceptions that may occur within a block of code.
*********************************************************************************************************************
## Coding Exercises
### 1) [rick&Morty Character List](https://github.com/orjwan-alrajaby/gsg-QA-Nablus-training-2023/blob/main/learning-sprint-1/week1%20-%20javascript-from-first-steps-to-professional/day%206/task.md)

#### My Solution
https://github.com/AnwarMelhem/Rick_Morty_Character_List
#### My Vedio 
https://drive.google.com/file/d/1whKhujzWYzV8qhF5ndCJ5SBjLWzFc0Bn/view?usp=sharing





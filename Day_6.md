
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
*********************************************************************************************************************
## Coding Exercises
### 1) [Global Scope and Functionsr](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/global-scope-and-functions)

#### My Solution

```javascript

let myGlobal=10;

function fun1() {
  oopsGlobal=5

}

function fun2() {
  let output = "";
  if (typeof myGlobal != "undefined") {
    output += "myGlobal: " + myGlobal;
  }
  if (typeof oopsGlobal != "undefined") {
    output += " oopsGlobal: " + oopsGlobal;
  }
  console.log(output);
}
console.log(spreadOut());
```
*************************************************************************************************************

## Coding Exercises

### 2) [Local Scope and Functions](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/local-scope-and-functions)

#### My Solution

```javascript
function myLocalScope() {
  let myVar;
  console.log('inside myLocalScope', myVar);
}
myLocalScope();

console.log('outside myLocalScope', myVar);

```
*************************************************************************************************************
## Coding Exercises

### 3) [Global vs. Local Scope in Functions](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/global-vs--local-scope-in-functions)

#### My Solution
```javascript
const outerWear = "T-Shirt";

function myOutfit() {
  const outerWear = "sweater";
  return outerWear;
}

myOutfit();
```
*************************************************************************************************************
## Coding Exercises
### 4) [Stand in Line](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/stand-in-line)
#### My Solution
```javascript
function nextInLine(arr, item) {
  arr.push(item);
  item=arr.shift()
  
  return item;
  
}

// Setup
let testArr = [1, 2, 3, 4, 5];

// Display code
console.log("Before: " + JSON.stringify(testArr));
console.log(nextInLine(testArr, 6));
console.log("After: " + JSON.stringify(testArr));

```
*************************************************************************************************************



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
await lets us tell JS to stop and wait for an asynchronous operation to finish

The await operator is used to wait for a Promise and get its fulfillment value. It can only be used inside an async function or at the top level of a module

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


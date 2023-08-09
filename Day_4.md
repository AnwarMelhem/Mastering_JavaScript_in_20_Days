
# Day 4: JavaScript: From First Steps to Professional Course By FrontEnd Master

## Lesson Summary
### Function 

A JavaScript function is a block of code designed to perform a particular task.
A JavaScript function is executed when "something" invokes it (calls it).


values are things
variables point to things
functions do things

parameters are the inputs a function expects
arguments are the actual values the function is called with

Parameters should be named like variables, and behave like variables within the function body

Return values-> A return statement specifies the function's output value

Arrow function-> The => "fat arrow" lets us create an unnamed function without much code
Arrow functions are great when we just want to return a value
For one-parameter functions, parentheses are optional
For multiple parameters, parentheses are required

If we need to do more than just return a value,
we can use curly braces for a "normal" function body
************************************************************************************
### Scope 
The scope is the current context of execution in which values and expressions are "visible" or can be referenced. If a variable or expression is not in the current scope, it will not be available for use. Scopes can also be layered in a hierarchy, so that child scopes have access to parent scopes, but not vice versa.

JavaScript has the following kinds of scopes:

Global scope: The default scope for all code running in script mode.
Module scope: The scope for code running in module mode.
Function scope: The scope created with a function.

In addition, variables declared with let or const can belong to an additional scope:
Block scope: The scope created with a pair of curly braces (a block).

Within each scope, you can access variables declared in a wider scope (e.g. global scope)
But not those declared in a narrower scope (e.g. function scope)

Variables declared with let can be modified from within a narrower scope

var->Variables declared with var are in the function scope
let->Variables declared as let are in the block scope.
const->Variables declared as const are in the block scope.

Reassign the value:
var-> allowed, let-> allowed, cost-> not allowed 

*************************************************************************************
### Events & Handler 
Events make our web page interactive!
The web browser fires events when certain things happen on the page
For example, when the user clicks somewhere on the page, a click event is fired

We can detect events with JS using an event listener
The .addEventListener() method lets us listen for events on a DOM element
ex:
document.addEventListener("click", () => {
    console.log("clicked")
});

.addEventListener() takes 2 parameters:
The name of the event to listen to (e.g. "click")
A handler function that JS calls when that event is fired on this element

JS passes an event object to the handler function with information about the event
"click", "dblclick","mouseover,"mouseout"-> type of event we can handle
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

***********************************************************************************************************************
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


## Coding Exercises

### 3) [Profile Lookup](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/profile-lookup)

#### My Solution
```javascript
function lookUpProfile(name, prop){
  for (var i = 0; i < contacts.length; i++) {
    if(contacts[i].firstName === name) {
      return contacts[i][prop] || "No such property";
    }
  }
  return "No such contact";
}

lookUpProfile("Akira", "likes");
```
*************************************************************************************************************
### 4) [Write Reusable JavaScript with Functions](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/write-reusable-javascript-with-functions)

#### My Solution
```javascript
function reusableFunction() {
  console.log("Hi World");
}
reusableFunction();

```
*************************************************************************************************************
## Coding Exercises

### 5) [Understanding Undefined Value returned from a Function](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/understanding-undefined-value-returned-from-a-functionr)

#### My Solution


```javascript

let sum = 0;

function addThree() {
  sum = sum + 3;
}
function addFive() {
  sum = sum + 5;
}

addThree();
addFive();
```
*************************************************************************************************************
## Coding Exercises

### 6) [Return a Value from a Function with Return](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/return-a-value-from-a-function-with-return)

#### My Solution


```javascript
function timesFive(num) {
  return num * 5;
}

const answer = timesFive(5);
```

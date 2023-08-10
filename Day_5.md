
# Day 5: JavaScript: From First Steps to Professional Course By FrontEnd Master

## Lesson Summary
### Conditionals 

if statements let us execute code under a certain condition
code in the if block only runs if the (condition) is true
we can use else to run other code if (condition) is false
We can chain else and if blocks to account for multiple conditions
The (condition) is usually an expression that evaluates to a boolean
If it's given some other value, JS will convert it to a boolean and decide based on its "truthiness"

0 inside condition is falsy
empty string inside condition is falsy
opject like array inside condition is truthy
null & undefined inside condition is fals

### Boolean (logical) operators
->The ! operator negates a boolean (gives its opposite)
->Logical operators let us make two boolean values become one
->Logical "and" (&&) requires both values to be truthy
->Logical "or" (||) requires only one value to be truthy

->Conditional ternary operator
->JS also has a "shortcut" operator for writing quick conditionals it needs 3 values to work:
->condition ? valueIfTrue : valueIfFalse;

### Loops
->Loops let us run the same chunk of code multiple times->this is called iteration

->for loops require us to:
->declare & initialize a loop counter
->give a condition for the loop to keep running
->describe how to change (usually increment) the counter each time

->for ... of loops let us more easily iterate over items in a collection

->We can use for...of to iterate over characters in a string or items in an array-> because strings & arrays are "iterables"

The While Loop
The while loop loops through a block of code as long as a specified condition is true.

The Do While Loop
The do while loop is a variant of the while loop. This loop will execute the code block once, before checking if the condition is true, then it will repeat the loop as long as the condition is true.

### map & filter
-> The map & filter methods also let us process all the items in an array
-> map calls a function on each item in an array to create a new array
-> filter calls a true/false function on each item and creates a new array with only the items where the function returns true

### Spread (...)
Spread (...) ->It lets us take all the items in an array and spread 'em around
We can use it to put all the items from one array inside another array
We can also use it to pass all the items from an array as arguments to a function or method

### (A)synchronous code

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



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



*************************************************************************************
## Coding Exercises

### 1) [Copy Array Items Using slice()](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-data-structures/copy-array-items-using-slice)

#### My Solution

```javascript
function forecast(arr) {
  let Array1=arr.slice(2,4)
  
  return Array1;
}

console.log(forecast(['cold', 'rainy', 'warm', 'sunny', 'cool', 'thunderstorms']));

```
*************************************************************************************************************
## Coding Exercises

### 2) [Concatenating Strings with the Plus Equals Operator](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/concatenating-strings-with-the-plus-equals-operator)

#### My Solution

```javascript
function spreadOut() {
  let fragment = ['to', 'code'];
  let sentence=['learning', ...fragment, 'is', 'fun']
  return sentence;
}

console.log(spreadOut());
```
*************************************************************************************************************
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

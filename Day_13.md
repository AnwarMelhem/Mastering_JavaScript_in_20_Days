# Day 13: JavaScript: Deep Javascript foundations, V3
## Scope
###  Scope:where to look for thing
for things
• Nested Scope
• Hoisting
• Closure
• Modules
JavaScript organizes scopes with functions and blocks

> ### Note:
>  Having two varibles with same name in different scopes called shadowing

### **Befor executing the code :**

1. scope maneger detrmine the scope
2. then bring data or store it in the variable

###  Auto Globale: 

If I try to use varible in cuurent scope without declaring it, it will be delared in the globale scope

```javaScript
function h (){
    x = "Hello"
    console.log(x)
}
h() // Hello
```

### Disable it 

```javaScript
"use strict" 
function h (){
    x = "Hello"
    console.log(x)
}
h() // erorr
```
******************************************************************************************************************************
## Scope & Function Expressions


### Function expression 
![image](https://github.com/AnwarMelhem/Mastering_JavaScript_in_20_Days/assets/97465642/0bacb49c-37b8-4dc5-964e-bb978b778042)
![image](https://github.com/AnwarMelhem/Mastering_JavaScript_in_20_Days/assets/97465642/11fd47ef-4e20-4bcb-b7cd-bdda445e5867)

```javaScript
let fun1 = function fun2(){
    console.log("Hello")
}

fun1() //Hello
fun2() //ReferenceError
```

### Named Function Expressions: Benefits

1. Reliable function self-reference (recursion, etc)
2. More debuggable stack traces
3. More self-documenting code

   
**************************************************************************************
**************************************************************************************

## Coding Exercises
### QUESTION #1

Create a function called `arrowHOF` that takes an arrow function as input and
returns a new arrow function that enhances the behavior of the input function. 

The enhanced function should accept additional arguments and execute the input
function multiple times based on these arguments.


```javascript

const exampleNormalFunc1 = (a, b, c) => {
  return a * (b + c);
}

const exampleNormalFunc2 = (x, y) => {
  return x * y;
}

const exampleNormalFunc3 = (string) => {
  return string + " " + string + " " + string + "!";
}


const arrowHOF = (normalFunc) => {
  // write your code here;
}

const hofNormalFunc1 = arrowHOF(exampleNormalFunc1);
const hofNormalFunc2 = arrowHOF(exampleNormalFunc2);
const hofNormalFunc3 = arrowHOF(exampleNormalFunc3);

console.log(hofNormalFunc1(3, 4, 5)(2)); // logs 60 twice
console.log(hofNormalFunc2(20, 35))(4); // logs 700 four times
console.log(hofNormalFunc3("Meow")()); // logs "Meow Meow Meow!" once

```

## My Solution:
```javascript
const arrowHOF = (normalFunc) => {
  return (...args) => {
    return (times) => {
      for (let i = 0; i < times; i++) {
        console.log(normalFunc(...args));
      }
    };
  };
};

```
-------------------------------------------------------------------

### QUESTION #2

Build a function called `preserveThis` that takes a function as input and
returns a new arrow function that behaves the same way as the input function but
preserves the original this context when used as a method of an object.

```javascript

// Example object
const obj = {
  name: 'John',
  greet: function (greeting) {
    console.log(`${greeting}, ${this.name}!`);
  }
};

const preserveThis = (func) => {
  // write your code here;
  return func;
}

// Wrap the greet function using preserveThis
const preservedGreet = preserveThis(obj.greet);

// Call the wrapped function as a method of the object
preservedGreet('Hello'); // Output: "Hello, John!"

```
## My Solution:
```javascript
const preserveThis = (func) => {
  return function (...args) {
    return func.apply(this, args);
  };
};
```
-------------------------------------------------------------------

### QUESTION #3

Consider the 2 following examples and distinguish the different output in each
one with them with a reasoning.

**Example 1:**

```javascript
function outer1() {
  var x = 10;

  var inner1 = function() {
    console.log(x);
  };

  inner1();
}

outer1(); // Output: 10
```

> **Reasoning for example 1's output:**  
> when the outer1 function is called, it defines a variable x with a value of 10. Then, it defines an inner1 function that tries to log the value of x. Since the inner1 function is defined within the same scope as the x variable, it has access to the x variable and logs its value, which is 10. When inner1() is invoked, it outputs 10 to the console.



**Example 2:**

```javascript
function outer2() {
  var x = 10;

  var inner2 = function() {
    var x = 20;
    console.log(x);
  };

  inner2();
}

outer2(); // Output: 20
```

> **Reasoning for example 2's output:**  
> when the outer2 function is called, it defines a variable x with a value of 10. Then, it defines an inner2 function that defines a new variable x with a value of 20 within its own scope. When the inner2 function is invoked, it logs the value of the inner x variable, which is 20, because it's the one that's accessible within the function's scope. Therefore, when inner2() is invoked, it outputs 20 to the console.

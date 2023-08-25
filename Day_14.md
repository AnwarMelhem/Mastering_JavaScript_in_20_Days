# Day 14: JavaScript: Deep Javascript foundations, V3

## Advanced Scope 

### lexical scope 

The idea that a compiler is figuring out all the scopes ahead of time befor being executed 
lex → the first stage of parsing

Lexical scoping in JavaScript
JavaScript uses lexical scoping to resolve the variable names when a function is created inside another function. It determines the function's parent scope by looking at where the function was created instead of where it was invoked.

Dynamic scoping
Dynamic scoping is considered the opposite approach of lexical scoping. It creates variables that can be called from outside the block of code in which they are defined. A variable declared in this fashion is sometimes called a public variable.
![image](https://github.com/AnwarMelhem/Mastering_JavaScript_in_20_Days/assets/97465642/d2fd2c0a-d56a-4f6f-b3b0-98078a51884b)

### lexical scope VS. dynamic scope 

The scope of **dynamic scope** is determined based upon a conditions at runtime (where this function has been called).

while **lexical scope** is determined at auther time.

```javaScript
const n = "Hello"

function f(){
    console.log(n)
}

function ff(){
    const n = " Hello1"
    f()
}

ff()
// Hello1 => lexical
// Hello => dynamic
```

<br>

## Function Scoping 

> ### Principle of privilage:
> You  should default to keep evreything private and only exposing the minimal necessary


```javaScript
let x
try {
    x = funMayReturnError(1)
}
catch (error) {
    x = 5
}

// using anaymaous function 
let x = (function bringX() {
    try {
        return funMayReturnError(1)
    }
    catch (error) {
        return 5
    }
})
```

<br>

### IIFE (Immediately Invoked Function Expression) 

```javaScript
function f (){
    console.log("hello")
}
f()

// we can do
// also it may do not have name
(function  ff (){    // not a functon declertion
    console.log("hello")
})()
```

<br>

### Block Scoping 


> ### Note:
> Block(curly braces) are not scopecauntil they have let or const inside them

<br>

### Hoisting 
- **Hoisting** is the process of moving variable and function declarations to the top of their scope.
- Variable declarations are hoisted but not their assignments. They are accessible but have an initial value of `undefined`.
- Function declarations are also hoisted, allowing them to be called before they are defined.
- Hoisting does not apply to function expressions, arrow functions, or variables declared with `let` or `const`.

<br>


```javaScript
var t = "1"
o()

function o(){
    console.log(t)
    var t = "2"
}
o() //undefined
```

   <br>
   <br>
   
### let & hoisting 
Wa can’t say that let dosn’t have hoisting, insted it’s kind of uninitioalized state

```javaScript
var t = "1"

{
    console.log(t)
    let t = "2"
}

// error
// but should print 1, beacuse it's in the outer scope, 
```


### QUESTION #1

Given the following code snippet and **explain what's happening**.

```javascript
for (var i = 0; i < 5; i++) {
    setTimeout(function() {
      console.log("value of [i] is: ", i);
    }, 100);
}
```

The current output is: "value of [i] is: 5" five times.

The output should be: 

"value of [i] is: ", 0 "value of [i] is: ", 1 "value of [i] is: ", 2 "value of
[i] is: ", 3 "value of [i] is: ", 4

Without changing anything in the for loop's code itself, provide a solution to
fix it.
## soluation:

The setTimeout function is asynchronous, and by the time the callbacks inside setTimeout are executed, the loop has already finished executing, and the variable i has reached its final value of 5. This is why you're seeing "value of [i] is: 5" five times.
To fix this issue without changing the for loop's code itself, you can create a new scope for each iteration of the loop using an immediately-invoked function expression (IIFE) or by using let instead of var to declare the loop variable. Here's the solution using let:
```javascript
for (let i = 0; i < 5; i++) {
    setTimeout(function() {
        console.log("value of [i] is: ", i);
    }, 100);
}

```
```javascript
for (var i = 0; i < 5; i++) {
    (function(index) {
        setTimeout(function() {
            console.log("value of [i] is: ", index);
        }, 100);
    })(i);
}


```
-------------------------------------------------------------------

### QUESTION #2

Given the following code snippet and **explain what's happening**. 

```javascript

for (let i = 0; i < 5; i++) {
   let array = [];
   array.push(i);
   console.log("Current array is: ", array)
}

```

The current output is: 

"Current array is: [ 0 ]" "Current array is: [ 1 ]" "Current array is: [ 2 ]"
"Current array is: [ 3 ]" "Current array is: [ 4 ]".

The output should be: "Current array is: [0, 1, 2, 3, 4]".

Provide a solution to fix it. 

### Soluation:
 because you're reinitializing the array variable inside each iteration of the loop, causing it to have only one element corresponding to the current value of i. To achieve the desired output of having all values [0, 1, 2, 3, 4] in the array, you need to declare the array variable outside the loop scope
``` javascript
let array = [];

for (let i = 0; i < 5; i++) {
   array.push(i);
}

console.log("Current array is: ", array);

```
-------------------------------------------------------------------

### QUESTION #3

Given the following code snippet and **explain what's happening**. 

```javascript

let functions = [];

for (var i = 0; i < 5; i++) {
  functions.push(() => {
    console.log("Current value of i is:", i);
  });
}

functions.forEach((func) => func());

```

The current output is: 

"Current value of i is: 5" "Current value of i is: 5" "Current value of i is: 5"
"Current value of i is: 5" "Current value of i is: 5"

The output should be: 

"Current value of i is: 0" "Current value of i is: 1" "Current value of i is: 2"
"Current value of i is: 3" "Current value of i is: 4"

Provide a solution to fix it. 
### soluation
The arrow function inside the loop captures the reference to the variable i, and by the time the functions inside the functions array are executed, the loop has finished, and the value of i is 5.

To fix this issue, you need to capture the current value of i during each iteration of the loop. You can achieve this by using an IIFE to create a new scope for each iteration.
``` javascript
let functions = [];

for (var i = 0; i < 5; i++) {
  functions.push((function(index) {
    return function() {
      console.log("Current value of i is:", index);
    };
  })(i));
}

functions.forEach((func) => func());

```

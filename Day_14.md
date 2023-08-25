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

<br>

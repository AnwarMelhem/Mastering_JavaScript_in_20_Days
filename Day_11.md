
# Day 11: JavaScript: Deep Javascript foundations, V3

### Introduction
Whenever there's a divergence
between what your brain thinks
is happening, and what the
computer does, that's where
bugs enter the code.

```javascript
// ex
let x = 2;
++x;  // 3
// this means 
x = x +1

let x = "2"
++x; // shoudl be 21
// but it's 3 beacuse JS is written like this
```
### "In JavaScript, everything is an object."->[False] this The sentence is wrong
### Evereh thing can bevhave as an object


## Types

![image](https://github.com/AnwarMelhem/Mastering_JavaScript_in_20_Days/assets/97465642/77290de9-8c29-4653-92de-1a9d168ebbeb)

### Primitive Types 
undefined
string
number
boolean
object
symbol: in ES6 used for suto private keys
bigInt (future): let x = 34n
function & arrays are a subtype of a object type

### In JavaScript, variables don't have types, values do.

Notes:
typeof : always return string
function & arrays not types of the top level they are sub types of object, but when using 
typeof array ⇒ object while function ⇒ function
type of null = object it is a bug in JS, ih they want to correct it a lot of things will fail in the JS

### Undefined: It occurs when a variable has been declared but has not been assigned any value. Undefined is not a keyword. 
### Undeclared: It occurs when we try to access any variable that is not initialized or declared earlier using the var or const keyword.

Undefined:
```javascript 
let geek;
undefined
console.log(geek) 
```
Undeclared: 
```javascript
// ReferenceError: myVariable is not defined
console.log(myVariable)
```
### Nan -> not a number 
(Special Values)is the only value that is not equall to it self
Typy of Nan->NaN type is number (invalid number), becuase it cmoes from numeric operations
![image](https://github.com/AnwarMelhem/Mastering_JavaScript_in_20_Days/assets/97465642/a28f496a-bafa-403f-901b-79a24c43f7fa)

```javascript
isNan()
// evaluate any argument to number then cheak weather it's a Nan or not

Number.isNan()
// better than the prevous

isNaN("String")          //  true
Number.isNaN("String")   //  false
```


### Negative Zero
![image](https://github.com/AnwarMelhem/Mastering_JavaScript_in_20_Days/assets/97465642/60b3fd5e-66bd-40a7-8c5e-49fd3c8abfd5)

Object.is( , )
it’s built in cheaker
better way for cheaking equality (better than ===)
```javascript
 // we might use -0 for directons in some applecaions which the sign means direc.
 
-0 === 0                // true
Object.is(-0 ,0 )       // false
```
### Note:=== failed in Nan & -0





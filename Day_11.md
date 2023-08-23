
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

undefined vs. undeclared vs. uninitialized (aka TDZ error):
undefined: We can have a variable that's been initialized that is undefined.
undeclared: We can have a variable that was never even created.
uninitialized: We can have a variable that's never been initialized.

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
Excersie
```javaScript
// TODO: define polyfill for `Object.is(..)`

if (!Object.is || true){   // to disaple the built in method & build my own
    Object.is = function ObjectIs(x,y){
        const xNegZero = isItNegZero(x)
        const yNegZero = isItNegZero(y)

        if (yNegZero || xNegZero ){
            return yNegZero && xNegZero
        }else if (isItNane(x) && isItNane(y)){
            return true
        }else {
            return x===y
        }

        function isItNegZero(v){
            return v===0 && (1/v)=== -Infinity
        }

        function isItNane(v){
            return v !==v
        }
    }
} 

// tests:
console.log(Object.is(42,42) === true);
console.log(Object.is("foo","foo") === true);
console.log(Object.is(false,false) === true);
console.log(Object.is(null,null) === true);
console.log(Object.is(undefined,undefined) === true);
console.log(Object.is(NaN,NaN) === true);
console.log(Object.is(-0,-0) === true);
console.log(Object.is(0,0) === true);

console.log(Object.is(-0,0) === false);
console.log(Object.is(0,-0) === false);
console.log(Object.is(0,NaN) === false);
console.log(Object.is(NaN,0) === false);
console.log(Object.is(42,"42") === false);
console.log(Object.is("42",42) === false);
console.log(Object.is("foo","bar") === false);
console.log(Object.is(false,true) === false);
console.log(Object.is(null,undefined) === false);
console.log(Object.is(undefined,null) === false);
```

![image](https://github.com/AnwarMelhem/Mastering_JavaScript_in_20_Days/assets/97465642/5e76773f-86d8-4b40-80de-4fae61d5135d)

![image](https://github.com/AnwarMelhem/Mastering_JavaScript_in_20_Days/assets/97465642/88bf8257-2844-46ac-b4e7-a304ede48c0a)
***********************************************************************
***********************************************************************
## Coercion 
![image](https://github.com/AnwarMelhem/Mastering_JavaScript_in_20_Days/assets/97465642/b71bb835-02ac-45e7-bbc3-573bdc49c261)

### Abstract Operations
#### .toString ()
![image](https://github.com/AnwarMelhem/Mastering_JavaScript_in_20_Days/assets/97465642/2eda23f7-014f-4c03-946e-746ebc56dab5)
![image](https://github.com/AnwarMelhem/Mastering_JavaScript_in_20_Days/assets/97465642/e5376440-03e5-4867-b1dc-881cecf72e7a)
![image](https://github.com/AnwarMelhem/Mastering_JavaScript_in_20_Days/assets/97465642/44b72544-86c6-4e51-b57e-cc32ecc64369)
![image](https://github.com/AnwarMelhem/Mastering_JavaScript_in_20_Days/assets/97465642/3216f65d-c9f2-495d-a07e-3daf613ab559)

```javaScript
(null).toString()                  // "null"
undefined.toString()               // "undefined"
true.toString()                    // "true"
false.toString()                   // "false"
3.14159.toString()                 // "3.14159"
(0).toString()                     // "0"
(-0).toString()                    // "0"

([]).toString()                    // ""
[1, 2, 3].toString()               // "1,2,3"
[null, undefined].toString()       // ","
[[[], [], []], []].toString()      // ",,,"
([,,,,]).toString()                // ",,,"

{}      "[object Object]"
{a:2}   "[object Object]"
```

#### .toNumber ()
![image](https://github.com/AnwarMelhem/Mastering_JavaScript_in_20_Days/assets/97465642/2ff2dbfa-8f41-4f16-a0b3-25e5d76696bf)
![image](https://github.com/AnwarMelhem/Mastering_JavaScript_in_20_Days/assets/97465642/a490962f-ad17-493e-9def-a1cd11fa45e5)
![image](https://github.com/AnwarMelhem/Mastering_JavaScript_in_20_Days/assets/97465642/7bea6bf7-af46-4c50-9f77-921fb3e3d851)
![image](https://github.com/AnwarMelhem/Mastering_JavaScript_in_20_Days/assets/97465642/c0e0150e-0484-4418-803f-5a2bc9c4f371)
![image](https://github.com/AnwarMelhem/Mastering_JavaScript_in_20_Days/assets/97465642/156a0ab4-19a3-457f-888a-4ea5dade4b4f)
![image](https://github.com/AnwarMelhem/Mastering_JavaScript_in_20_Days/assets/97465642/883f2dfb-c810-4c9a-bbaf-9fea32d8ca47)

```javaScript
// using Number(x)

""        // 0
"0"       // 0
"-0"      // -0
" 009 "   // 9
"3.14159" // 3.14159
"0."      // 0
".0"      // 0
"."       // NaN
"0xaf"    // 175 // consvert hexacecimal to decimal

false      // 0
true       // 1
null       // 0
undefined  // Nan

[""]        // 0
["0"]       // 0
["-0"]      // 0-
[null]      // 0
[undefined] // 0
[1,2,3]     // NaN
[[[[]]]]    // 0
{ .. }      // NaN
```

### ToBoolean()
![image](https://github.com/AnwarMelhem/Mastering_JavaScript_in_20_Days/assets/97465642/ff1f8a54-72e0-4800-86b9-b42033315fb5)
**************************************************************************

![image](https://github.com/AnwarMelhem/Mastering_JavaScript_in_20_Days/assets/97465642/1774f4f4-0e8f-4102-8342-6c26774a895f)

## All programming languages have type conversions, because it's absolutely necessary

## type conversion corner cases
![image](https://github.com/AnwarMelhem/Mastering_JavaScript_in_20_Days/assets/97465642/877b7482-a233-46be-a801-367ea150587c)
![image](https://github.com/AnwarMelhem/Mastering_JavaScript_in_20_Days/assets/97465642/5222b4c2-071a-4ec7-8646-37c7f321dc62)
![image](https://github.com/AnwarMelhem/Mastering_JavaScript_in_20_Days/assets/97465642/924f2d1f-0897-4feb-b53e-4ebd46248c49)



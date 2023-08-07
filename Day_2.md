
# Day 2: JavaScript: From First Steps to Professional Course By FrontEnd Master

## Lesson Summary
### 1) Values & Data Types 
Values-> chunks of information we want to work with
that information (data) can be of different types

typeof-> tells you the type of a value

JS has two kinds of data:
1. Primitive types (e.g. strings, numbers)
2. Objects (e.g. document )

Primitive data types [string , number, boolean, undefined, null ]
typeOf null -> object
typeof undefined -> undefined


### 2) Strings
strings made of characters

you can create strings by wrapping the text inside single quotes ('), double quotes ("), or backticks (`)

Characters are in a specific order Each gets a number, starting at 0 aka an "index"

String Length->To find the length of a string, use the built-in length property

you can create strings by wrapping the text inside single quotes ('), double quotes ("), or backticks (`)

indexOf() ->index of a specific character
includes() ->Does this string contain some other string
startsWith() ->Does this string start with some other string
+ -> Connecting strings together
toLowerCase()-> converet char to small char

### 2) Operator
Arithmetic operators
+ add
- subtract
* multiply
/ divide

Comparison operators
> greater than
< less than
>= greater than or equal to
<= less than or equal to

Equality operators
=== strict equal 
== loosey-goosey equal
!== strict does not equal
!= loosey-goosey does not equal

## Coding Exercises
### QUESTION #1
Consider the following JavaScript code:
```javascript
let a = 0;
let b = "0";
let c = false;
let d = "false";

console.log(a == b);
console.log(b === c);
console.log(!!d);
```

What will be the output of each console.log statement? **_You MUST explain WHY_**.
console.log(a == b); -> true becaause == checks whether its two operands are equal
console.log(b === c); -> false because === checks equality without type coersion
console.log(!!d); -> true because the d consider true value then !true =false then !false=true
EX:
!""; // !f returns true
!"Cat"; // !t returns false
*************************************************************************************************************
### QUESTION #2:
Consider the following JavaScript expression:

```javascript
console.log(4 + 5 * "7");
```
What will be the output of this expression? **_You MUST explain the steps of evaluation taken by JS_**.
1. "7" is a string, but JavaScript performs automatic type coercion when attempting to perform arithmetic operations. In this case, the string is coerced into a number because of the multiplication operation.
2. Multiplying 5 by the number 7 results in 35.
3. Adding 4 to 35 gives us 39.
*************************************************************************************************************
### QUESTION #3:
Evaluate the following expression:
```javascript
let result = 5 + 2 * 3 - 1;
```
What will be the output of this expression? **_You MUST explain the steps of evaluation taken by JS_**.
- Multiplication: First, the multiplication operation 2 * 3 is performed.
2 * 3 equals 6.
-Addition and Subtraction: Then, the addition and subtraction operations are performed in left-to-right order.
5 + 6 equals 11.
11 - 1 equals 10.
Assignment: Finally, the result of the entire expression (10) is assigned to the variable result.
*************************************************************************************************************
### QUESTION #4:
Consider the following code:
```javascript
let x = 10;
let y = '10';
console.log(x == y);
console.log(x === y);
```
What will be the output of each `console.log` statement? **_You MUST explain WHY_**.
x == y evaluates to true because JavaScript performs type coercion to compare the values.
x === y evaluates to false because it checks both value and type, and the types are different.
*************************************************************************************************************
### QUESTION #5:
Given the code below:
```javascript
let num = "15";
let isPositive = true;
let result = (num > 10 && isPositive) || num < 0;
console.log(result);
```
What is the value of result? **_You MUST explain the steps of evaluation taken by JS_**

num is a string ("15"), and 10 is a number.
JavaScript attempts to compare them by performing type coercion.
The string "15" is coerced into a number 15.
15 > 10 is true.
Since isPositive is also true, the && (logical AND) operation results in true.
15 < 0 is false.
The result of (num > 10 && isPositive) is true 
The result of num < 0 is false.
true || false -> true
The value true is assigned to the variable result.

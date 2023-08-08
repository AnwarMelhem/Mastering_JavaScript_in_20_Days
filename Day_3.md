
# Day 3: JavaScript: From First Steps to Professional Course By FrontEnd Master

## Lesson Summary

## Array 
Array - a special type of object used to represent an ordered list of values, with each value accessible by an index
->Arrays let us keep multiple values together in a single collection
->Arrays have a length ->length
->Each value inside array has an index
->Arrays can hold any type of items, or mix and match! ->let mixedArray = ["pop", 6, "squish", false, document];

->To add elements to an array, you can use the push() method

->To remove elements from array, you can use the pop() method

->The sort() method sorts the elements of an array in ascending or descending order, the default sort order is ascending, built upon converting the elements into strings, then comparing their sequences of UTF-16 code units values.

->The join() method creates and returns a new string by concatenating all of the elements in this array, separated by commas or a specified separator string.

->The concat() method is used to merge two or more arrays. This method does not change the existing arrays, but instead returns a new array.

->The indexOf() method returns the first index at which a given element can be found in the array, or -1 if it is not present.

->The includes() method determines whether an array includes a certain value among its entries, returning true or false as appropriate.
************************************************************************************
## Mutability 
mutable vs. immutable
"Mutable" data can be edited (e.g. Arrays)
"Immutable" data always stays the same (e.g. strings & other primitives)


## Coding Exercises

### 1) [Compound Assignment With Augmented Multiplication](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/compound-assignment-with-augmented-multiplication)

#### My Solution


```javascript
let a = 5;
let b = 12;
let c = 4.6;
a *= 5;
b *= 3 ;
c *=10;

```
*************************************************************************************************************
## Coding Exercises

### 2) [Concatenating Strings with the Plus Equals Operator](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/concatenating-strings-with-the-plus-equals-operator)

#### My Solution


```javascript
let myStr="This is the first sentence. ";
myStr+= "This is the second sentence.";
```
*************************************************************************************************************
## Coding Exercises

### 3) [Use Dot Notation to Access the Properties of an Object](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/object-oriented-programming/use-dot-notation-to-access-the-properties-of-an-object)

#### My Solution


```javascript
let dog = {
  name: "Spot",
  numLegs: 4
};
console.log(dog.name);
console.log(dog.numLegs);
```
it is a programming language of the web , created in 1995 , we can run javascript in prowser we can also run javascript on server using project called node.js
### Where Js write?
1. The browser's JS console
2. Local text file in editor, e.g. TextEdit, VS Code
3. Online playground e.g. CodePen, CodeSandbox

### The DOM is -> Document Object Model
1.Finding HTML Elements:
- document.getElementById(id)->Find an element by element id
- document.getElementsByTagName(name)->Find elements by tag name
- document.getElementsByClassName(name)->Find elements by class name
- document.querySelectorAll->find all HTML elements that match a specified CSS selector


## Coding Exercises

### 1) [Compound Assignment With Augmented Multiplication](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/compound-assignment-with-augmented-multiplication)

#### My Solution


```javascript
let a = 5;
let b = 12;
let c = 4.6;
a *= 5;
b *= 3 ;
c *=10;

```
*************************************************************************************************************
## Coding Exercises

### 2) [Concatenating Strings with the Plus Equals Operator](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/concatenating-strings-with-the-plus-equals-operator)

#### My Solution


```javascript
let myStr="This is the first sentence. ";
myStr+= "This is the second sentence.";
```
*************************************************************************************************************
## Coding Exercises

### 3) [Use Dot Notation to Access the Properties of an Object](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/object-oriented-programming/use-dot-notation-to-access-the-properties-of-an-object)

#### My Solution


```javascript
let dog = {
  name: "Spot",
  numLegs: 4
};
console.log(dog.name);
console.log(dog.numLegs);
```

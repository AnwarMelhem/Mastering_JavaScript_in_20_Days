
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
->"Mutable" data can be edited (e.g. Arrays)
->"Immutable" data always stays the same (e.g. strings & other primitives)

Some actions "mutate" an array (e.g. oldArray.push(newValue))->aka change the array in-place

Other actions do not mutate the original array, but instead create a new copy (e.g. oldArray.concat(otherArray))
************************************************************************************
## Object
The Object type represents one of JavaScript's data types. It is used to store various keyed collections and more complex entities.

In JavaScript objects we can access, add, change, and remove members by using either dot or bracket notation.
dot like js.name->Getting property values

JavaScript Objects are Mutable
Objects are mutable: They are addressed by reference, not by value.
We call function-properties "methods" on objects


this-> in a method lets us reference other properties on the object

-> A method is a function associated with an object, or, put differently, a method is a property of an object that is a function. Methods are defined the way normal functions are defined, except that they have to be assigned as the property of an object. 

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

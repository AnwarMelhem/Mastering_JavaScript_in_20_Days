
# Day 8: JavaScript: The Hard Parts, v2

## Clousers 
In JavaScript, closures are an important concept that allows functions to access variables from their outer lexical environment even after the outer function has finished executing. 

A closure is created when an inner function is returned from an outer function and still has access to its lexical scope, including the variables and parameters of the outer function.

A closure is a function that preserves the outer scope in its inner scope.

Closures are powerful because they allow functions to retain access to the variables they need, even when they are invoked outside their original lexical scope. This behavior enables advanced patterns and techniques in JavaScript programming.

- Lexical scoping describes how the JavaScript engine uses the location of the variable in the code to determine where that variable is available.
- A closure is a combination of a function and its ability to remember variables in the outer scope.

*********************************************************************************************************************
## Coding Exercises
### 1) [Use Higher-Order Functions map, filter, or reduce to Solve a Complex Problem](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/functional-programming/use-higher-order-functions-map-filter-or-reduce-to-solve-a-complex-problem)
```javascript
const squareList = arr => {
  const arr1= arr.filter(num => num > 0 && num % parseInt(num) === 0)
          .map(num => Math.pow(num, 2));
  return arr1

};

const squaredIntegers = squareList([-3, 4.8, 5, 3, -3.2]);
console.log(squaredIntegers);
```

*********************************************************************************************************************
## Coding Exercises
### 2) [Apply Functional Programming to Convert Strings to URL Slugs](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/functional-programming/apply-functional-programming-to-convert-strings-to-url-slugs)
```javascript
function urlSlug(title) {
return title
    .split(" ")
    .filter(substr => substr !== "")
    .join("-")
    .toLowerCase();
}
urlSlug("A Mind Needs Books Like A Sword Needs A Whetstone");
```
*********************************************************************************************************************
### 3) [Question 1: Functions and Callbacks](https://github.com/orjwan-alrajaby/gsg-QA-Nablus-training-2023/blob/main/learning-sprint-1/week2%20-%20javaScript-the-hard-parts-v2/day%201/tasks.md)
``` javascript
async function mapAsync(array, instructions) {
    const output = [];
    for (let i = 0; i < array.length; i++) {
    output.push(await instructions(array[i]));
    }
    return output;
   }
   async function multiplyBy2(input) { return input * 2; }
   const result = mapAsync([1, 2, 3, 4, 5],  multiplyBy2)
   .then((result) => {
    console.log(result);
  })
  .catch((error) => {
    console.error(error);
  });
```




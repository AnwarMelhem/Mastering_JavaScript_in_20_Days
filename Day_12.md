
# Day 12: JavaScript: Deep Javascript foundations, V3

## Equality  == vs. ===

== checks value (loose)
=== checks value and type (strict)
![image](https://github.com/AnwarMelhem/Mastering_JavaScript_in_20_Days/assets/97465642/6c2202e5-e251-48e7-9b21-261149bf6d37)

== allows coercion (types different)
=== disallows coercion (types same)

== Summary:
If the types are the same: ===
If null or undefined: equal
If non-primitives: ToPrimitive
Prefer: ToNumber


Avoid:
1. == with 0 or "" (or even " ")
2. == with non-primitives
3. == true or == false : allow
ToBoolean or use ===

Knowing types is always
better than not knowing them
Static Types is not the only (or
even necessarily best) way to
know your types


== is not about comparisons
with unknown types
== is about comparisons
with known type(s), optionally
where conversions are helpful

Summary: making types
known and obvious leads to
better code. If types are
known, == is best.
Otherwise, fall back to ===


## Static Typing
Benefits: 
Catch type-related mistakes
Communicate type intent
Provide IDE feedback
validating operand types to avoid errors

### TypeScript vs Flow 
### **[TypeScript vs Flow](https://github.com/niieani/typescript-vs-flowtype)**


Pros and Cons:
Familiarity: they look like other language's type systems
Extremely popular these days
They're very sophisticated and good at what they do
They use "non-JS-standard" syntax (or code comments)
They require* a build process, which raises the barrier to entry
Their sophistication can be intimidating to those without prior formal types experience
They focus more on "static types" (variables, parameters, returns, properties, etc) than value types
The only way to have confidence over the runtime behavior is to limit/eliminate dynamic typing
*************************************************************************

## Coding Exercises 
## Question 1:

Given the following promisesArray, convert the array into an object using the convertToObj function.

You should apply typescript types to every promise, the input of convertToObj, and the output of convertToObj.

Build interfaces and types as needed

```javascript

const sayHelloWorld = new Promise(resolve, reject => {
  resolve("Hello world!");
});

const checkBoolean = (boolean) => new Promise(resolve, reject => {
  if (boolean) {
    resolve(boolean);
  } else {
    reject(`Input is false :(`)
  }
})

const returnObj = new Promise(resolve, reject => {
  resolve({
    x: "meow",
    y: 45,
  })
})

const promisesArray = [sayHeloWorld, checkBoolean, returnObj];

const convertToObj = (array) => {
  //write your code here;
  return obj;
}

```
 
 **My Solution:**

```javascript
interface HelloWorldPromise {
  (): Promise<string>;
}

interface CheckBooleanPromise {
  (boolean: boolean): Promise<boolean>;
}

interface ReturnObjPromise {
  (): Promise<{ x: string; y: number }>;
}

type PromisesArray = Array<HelloWorldPromise | CheckBooleanPromise | ReturnObjPromise>;

const sayHelloWorld: HelloWorldPromise = () => {
  return new Promise((resolve, reject) => {
    resolve("Hello world!");
  });
};

const checkBoolean: CheckBooleanPromise = (boolean) => {
  return new Promise((resolve, reject) => {
    if (boolean) {
      resolve(boolean);
    } else {
      reject(`Input is false :(`);
    }
  });
};

const returnObj: ReturnObjPromise = () => {
  return new Promise((resolve, reject) => {
    resolve({
      x: "meow",
      y: 45,
    });
  });
};

const promisesArray: PromisesArray = [sayHelloWorld, checkBoolean, returnObj];

const convertToObj = async (array: PromisesArray) => {
  const obj: Record<string, any> = {};

  for (const promise of array) {
    if (promise === sayHelloWorld) {
      obj["sayHelloWorld"] = await promise();
    } else if (promise === checkBoolean) {
      obj["checkBoolean"] = await promise(true);
    } else if (promise === returnObj) {
      obj["returnObj"] = await promise();
    }
  }

  return obj;
};

convertToObj(promisesArray)
  .then((result) => {
    console.log(result);
  })
  .catch((error) => {
    console.error(error);
  });

```
-------------------------------------------------------------------
### QUESTION #2:

What will be the output of the following code snippet? Pick the right choice
then **justify your answer with an explanation**.

```javascript
function testScope1() {
  if (true) {
    var a = 1;
    let b = 2;
    const c = 3;
  }
  console.log(a);
  console.log(b);
  console.log(c);
}

testScope1();

```
**Choices:**

A) `undefined`, `undefined`, `undefined`   
B) `1`, `undefined`, `ReferenceError`  
C) `1`, `ReferenceError`, `ReferenceError`   
D) `1`, `ReferenceError`

 **My Solution:**
 The answer is-> C) `1`, `ReferenceError`, `ReferenceError` 
Variable a is declared using the var keyword. In JavaScript, var has a function-level scope, which means it's hoisted to the top of the function. So, a will be accessible and retain its value of 1 throughout the function, including after the if block.

Variable b is declared using the let keyword. let has block-level scope, which means it's only accessible within the block where it's defined. In this case, it's defined within the if block, so it won't be accessible outside of it. Therefore, trying to log b outside the if block will result in a ReferenceError.

Variable c is declared using the const keyword. Like let, const also has block-level scope. It's also not accessible outside the if block, so trying to log c outside the if block will result in a ReferenceError.

 -------------------------------------------------------------------
### QUESTION #3:

What will be the output of the following code snippet? Pick the right choice
then **justify your answer with an explanation**.

```javascript
function testScope2() {
  console.log(a);
  console.log(b);
  console.log(c);
  if (true) {
    var a = 1;
    let b = 2;
    const c = 3;
  }
}

testScope2();

```
Choices:
A) undefined, ReferenceError
B) 1, undefined, ReferenceError
C)undefined, undefined, ReferenceError
D) 1, ReferenceError

**My Solution:**
Variable a is declared using the var keyword. As mentioned before, var declarations are hoisted to the top of their scope but are initialized with undefined. Therefore, a will be accessible within the function but will have an initial value of undefined until it's assigned a value. So, the first console.log(a) will output undefined.

Variable b is declared using the let keyword. Similar to the previous scenario, let declarations are hoisted to the top of their scope, but they are in the "temporal dead zone" until the point of declaration. Since b is defined within the if block, trying to access it before the declaration point will result in a ReferenceError.

Variable c is declared using the const keyword. Like let, const declarations are also hoisted to the top of their scope but are in the temporal dead zone until the point of declaration. Trying to access c before the declaration point will result in a ReferenceError.
-------------------------------------------------------------------
### QUESTION #4:

What will be the output of the following code snippet? Pick the right choice
then **justify your answer with an explanation**.

```javascript

function testScope3() {
  var a = 36;
  let b = 100;
  const c = 45;

  console.log([a, b, c]);

  if (true) {
    var a = 1;
    let b = 2;
    const c = 3;

    console.log([a, b, c]);
  }

  console.log([a, b, c]);
}

testScope3();

```
A) [ 36, 100, 45 ] | [ 1, 2, 3 ] | [ 36, 2, 3 ]
B) [ 36, 100, 45 ] | [1, 2, 3 ] | [ 36, 100, 45 ]
C) [ 36, 100, 45 ] | [ 1, 2, 3 ] | [ 1,100, 45 ]
D) [ 36, 100, 45 ] | [ 1, 2, 3 ] | [ 1, 2, 3 ]
**My Solution:**

B) [36, 100, 45], [1, 2, 3], [1, 100, 45]

Here's the justification for each part of the code:

At the beginning of the function, variables a, b, and c are declared using var, let, and const respectively. They are assigned values of 36, 100, and 45. The first console.log statement outputs [36, 100, 45].

Inside the if block, new values are assigned to a, b, and c. The var declaration of a inside the if block modifies the existing a variable declared earlier in the function's scope. The let and const declarations of b and c inside the if block are block-scoped and do not affect the outer variables with the same names. The second console.log statement within the if block outputs [1, 2, 3].

After the if block, the values of a and c declared earlier are changed by the assignments within the if block. The value of b remains the same, as it was block-scoped within the if block. The third console.log statement after the if block outputs [1, 100, 45].

So, the overall output will be:
-------------------------------------------------------------------

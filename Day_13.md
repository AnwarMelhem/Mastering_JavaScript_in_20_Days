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

   

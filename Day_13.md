##  Scope 

JavaScript organizes scopes with functions and blocks

> ### Note:
>  Having two varibles with same name in different scopes called shadowing

### **Befor executing the code :**

1. scope maneger detrmine the scope
2. then bring data or store it in the variable
###  
###  Auto Globale: 👩🏻‍💻🌍

If I try to use varible in cuurent scope without declaring it, it will be delared in the globale scope

```javaScript
function h (){
    x = "sarah"
    console.log(x)
}
h() // sarah
```

### Disable it 

```javaScript
"use strict" 
function h (){
    x = "sarah"
    console.log(x)
}
h() // erorr
```


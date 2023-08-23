
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

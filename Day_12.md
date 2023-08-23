
# Day 11: JavaScript: Deep Javascript foundations, V3

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



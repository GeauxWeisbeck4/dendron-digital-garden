---
id: 0w5kpcnl07ggpqnxycvw9hj
title: 01 Values
desc: 'Eloquent JavaScript Chapter 1'
updated: 1664496294254
created: 1664493446263
---
# Values
Many different types

# Numbers
1 integer
1.3 floating type

# Special Numbers
Infinity -Infinity NaN

# Strings
"I'm a STring"
'Me too'
`Me three`
"This is the first line\nAnd this is the second"
-Can't multiply or divide or subtract
-But can "con" + "cat" + "e" + "nate"

# Unary Operators
console.log(typeof 4.5)
// -> number
console.log(typeof "x")
// -> string

# Boolean Values
True
False

## Comparison
-One way to produce Boolean values
console.log(3 > 2)
// -> true
console.log( 3 < 2)
// -> false

console.log("Aardvark" < "Zoroaster")
// -> true
-when comparing strings ,JS goe3s over the characters from left to right comparing the unicodes one by one

other similar operators are >=, <=, ==, !=
console.log("Itchy" != "Scratchy")
// -> true
console.log("Apple" == "Orange")
// -> false

- Only value in JavaScript that is not equal to itslef is NaN

# Logical Operators
&& logical and
-True only if both values are true
console.log(true && false)
// -> false
|| logical or
-True if either value is true
console.log(false || true)
// -> true
console.log(false || false)
// -> false

# Ternary
console.log(true 1 : 2);
// -> 1
CONSOLE.LOG(false ? 1 : 2);
// -> 2
- This is a conditional operator

# Empty Values
null and undefined
- can be treated almost interchangeably

# Automatic type conversion
console.log(8 * null)
// -> 0 # null becomes 0
console.log("5" - 1)
// -> 4  # "5" becomes number
console.log("5" + 1)
// -> 51 # 1 is converted to string "1"
console.log("five" * 2)
// -> NaN # Doesn't map well so NaN
console.log(false == 0)
// -> true
- Coercion: JavaScript will automatically try to convert value to set of rules it needs
- Null and undefined:
console.log(null == undefined);
// -> true
console.log(null == 0);
// -> false

When you want to tes aif a value has a real value instead of null or undefined, compare it to null with the == or != operator

If you don't want type cnversion to happen then use === and !== for precisely equal values

# Short-Circuiting of logical operators
Logical operators handle values of different types in a peculiar order. Converts value on theri left side to boolean type in order to decide what to do. They will return either original left-hand value or right hand value

|| returns value to its leftt
console.log(null || "user")
// -> user
console.log("Agnes" || "user")
// -> Agnes

&& is same but the other way around if left is something false, it returns that value

Next Chapter
[[02-Program Structure]]

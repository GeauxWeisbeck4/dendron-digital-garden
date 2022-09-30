---
id: bt2wqi7iu4y8g7122vglga1
title: 02-Program Structure
desc: 'Chapter 2 of Eloquent JavaScript'
updated: 1664503802135
created: 1664496295997
---
# Program Structure
Need to have structure

# Expressions and Statements
A fragment of code that produces a value is an expression.
22 or "psychoanalysis"

- Statements are like sentences of expressions
  Simplest statement - >  1;
  !fales;
Changes statements create are called side effects

# Bindings
How JavaScript keeps an internal state

```
let caught = 5 * 5;
```
(keyword = `let`)  defines a binding

After a binding is defined, it can be used as an expression.
```
let ten = 10;
console.log(ten * ten);
// -> 100
```
We can change the value to change no existing values
```
let mood = "light"
console.log(mood)
// -> light
mood = "dark";
console.log(mood)
// -> dark
```
Imagine binding as tentacles - they don't contain values, they grasp them
```
let luigisDebt = 140;
luigisDebt = luigiDebt - 35;
console.log(luigisDebt)
// -> 105
```
Single let statement may define multiple bindings
```
let one = 1, two = 2;
console.log(one + two)
// -> 3
```
var and const also create bindings
```
var name = "Ayda";
const greeting = "Hello";
console.log(greeting + name);
// -> Hello Ayda
```

# Binding names
Can inclue _  or $ but no other symbols
-Words reserved for binding
 ```
 break case catch class const continue debugger default delete do else enum export extends false finally for function if implements import interface in instanceof let new package private protected public return static super switch this throw true try typeof var void while with yield
 ```

 # The Environment
-Collections of bindings

## Functions
Funtionis a piece of program wrapped in a value. can be applied to run the wrapped program
- prompt holds a function that shows a little dialog box assking for user input
![](/assets/images/2022-09-29-20-28-52.png)

-Executing a function is invoking, calling or applying it
You can call a function by putting parentheses after an exopression that produces a function value
-Values given to functions are arguments
```
let x = 30
console.log("the value of x is", x);
// -> the value of x is 30
```
## Return values
Showing a dialog box or writing text to the screen is a side effect
console.log(Math.max(2, 4))
// -> 4

- Anything that returens a value is an expression
console.log(Math.min(2, 4) + 100);
// -> 102

# Control Flow
When program has more than one statement, the statments are executed from top to bottom like a story
```
let theNumber = Number(prompt("Pick a number"));
console.log("Your number is the square root of " + theNumber * theNumber);
```
![](/assets/images/2022-09-29-20-35-07.png)

# Conditional execution
![](/assets/images/2022-09-29-20-35-31.png)
based on situatoin adn createdwith if
```
let theNumber = Number(prompt("Pick a number"));
if (!Number.isNaN(theNumber)) {
    console.log("Your number is the square root of " + theNumber * theNumber);
}
```
{} statements group number of statemnts into a single group called a block
```
if (1 + 1 == 2) console.log("It's true");
// → It's true
```
You can use the else keyword with if to create two separate alternative execution paths
```
let theNumber = Number(prompt("Pick a number"));
if (!Number.isNaN(theNumber)) {
  console.log("Your number is the square root of " +
              theNumber * theNumber);
} else {
  console.log("Hey. Why didn't you give me a number?");
}
```
You can chain multiple if/else pairs together:
```
let num = Number(prompt("Pick a number"));

if (num < 10) {
    console.log("small")
} else if (num < 100) {
    console.log("medium")
} else {
    console.log("large")
}
```
![](/assets/images/2022-09-29-20-47-15.png)

# While and Do Loops
![](/assets/images/2022-09-29-20-48-07.png)
```
let number = 0;
while (number <= 12) {
    console.log(number);
    number = number + 2;
}
// -> 0
// -> 2
// ... etcetera
```
-Statements starting with while creates a loop.
-Lets calculate 2 ^ 10
```
let result = 1;
let counter = 0;
while (counter < 10) {
    result = result * 2;
    counter = counter + 1;
}
console.log(result);
// -> 1024
```
do loop control structure is similar to a while loop - the test appears after body of loop
```
let yourName;
do {
    yourName = prompt("Who are you?");
} while (!yourName);
console.log(yourName);
```

# Indenting Code
- Each new block adds the same amouunt of space

# For Loops
many loops follow patter on of whle. Because it is so common, JavaScript and similar languages provide a slightly shorter and more comprehensive form, the for loop
```
for (let number = 0; number <= 12; number = number +2) {
    console.log(number);
}
// -> 0
// -> 2
// ... etcetera
```
This program is exactly equivalent to earlier even-number-printing example. Only change is that all the statements that are related to the "state" of the loop grouped together after for

The parenthesesafter a for keyword must contain two semicolons. The part before the first semicolon initializes the loop by defining a binding. The second part is expression that checks whether the loop must continue. The final part updates the state of the loop after every iteration. Most cases, this is shorter and clearer than a while construct
```
let result = 1;
for (let counter = 0; counter < 10; counter + 1) {
    result = result + 2;
}
console.log(result);
// -> 1024
```

# Breaking out of a loop
-Oter than false, ya break can jump out of a loop
```
for (let current = 20; ; current = current + 1) {
    if (current % 7 == 0) {
    console.log(current);
    break;
    }
}
// -> 21
```
- removing break statement or accidentally writing an end condition that is true will create an infinite loop
- `continue` jumps out of body and continues with the loop's next iteration

# Updating Bindings Succintly
counter = counter + 1;
-short cut
```
counter += 1;
```
can now shorten 🌩️example
```
for (let number = 0; number <- 12; number += 2) {
    console.log(number);
}
```

for += 1 and -=1 you can even go counter++ and counter--

# Dispatching on a value with switch
```
switch (prompt("What is the weather like?")) {
    case "rainy":
        console.log("remember to bring an umbrella.");
        break;
    case "sunny":
        console.log("Remember to bring an umbrella.");
    case "cloudy":
        console.log("Go outside.");
        break;
    default:
        console.log("Unknown weather type!");
        break;
}
```
# Capitalization
`fuzzyLittleTurtle`

# comments
```
let accountBalance = calculateBalance(account);
// It's a green hollow where a river sings
accountBalance.adjust();
// Madly catching white tatters in the grass.
let report = new Report();
// Where the sun on the proud mountain rings:
addToReport(accountBalance, report);
// It's a little valley, foaming like light in a glass.
```
// goes to end of line
/* */ goes forever


# Exercises
```
for  (let line = "#"; line.length < 8; line += "#")
console.log(line);
```
Exercise 2
```
for (let i = 0; i <= 100; counter += 1) {
    let output = "";
    if (n % 3 == 0) output += "Fizz";
    if (n % 5 == 0) output += "Buzz";
    console.log(output || n);
}
```
Exercise 3
```
let size = 8;

let board = "";

for (let y = 0; y < size; y++) {
    for (let x = 0; x < size; x++) {
        if ((x -+ y) % 2 == 0) {
            board += "";
        } else {
            board += "#";
    }
  }
  board += "\n";
}

console.log(board);
```

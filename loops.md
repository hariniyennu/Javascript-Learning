# JavaScript Loops
Loops are handy, if you want to run the same code over and over again, each time with a different value.

JavaScript supports different kinds of loops:

- for - loops through a block of code a number of times
- for/in - loops through the properties of an object
- for/of - loops through the values of an iterable object
- while - loops through a block of code while a specified condition is true
- do/while - also loops through a block of code while a specified condition is true

## The For Loop

```js
for (expression 1; expression 2; expression 3) {
  // code block to be executed
}
```
- Expression 1 is executed (one time) before the execution of the code block.
- Expression 2 defines the condition for executing the code block.
- Expression 3 is executed (every time) after the code block has been executed.

Example
```js
for (let i = 0; i < 5; i++) {
  text += "The number is " + i + "<br>";
}
```

```js
The number is 0
The number is 1
The number is 2
The number is 3
The number is 4
```

You can omit expression 1 when your values are set before the loop starts:

Example
```js
let i = 2;
let len = cars.length;
let text = "";
for (; i < len; i++) {
  text += cars[i] + "<br>";
}
```
```js
Saab
Ford
```

You can intiate many values in expression 1 (separated by comma):

Example
```js
for (i = 0, len = cars.length, text = ""; i < len; i++) {
  text += cars[i] + "<br>";
}
```
```js
BMW
Volvo
Saab
Ford
```

Expression 2 is used to evaluate the condition of the initial variable (i < len).
**Note
If you omit expression 2, you must provide a break inside the loop. Otherwise the loop will never end.**

Expression 3 increments the value of the initial variable (i++).
**Expression 3 can do anything like negative increment (i--), positive increment (i = i + 15), or anything else.**
Expression 3 can also be omitted (like when you increment your values inside the loop):

Example
```js
let i = 0;
let len = cars.length;
let text = "";
for (; i < len; ) {
  text += cars[i] + "<br>";
  i++;
}
```

## Loop Scope
### Using var in a loop:

Example
```js
var i = 5;
for (var i = 0; i < 10; i++) {
  // some code
}
// Here i is 10
```
### Using let in a loop:

Example
```js
let i = 5;
for (let i = 0; i < 10; i++) {
  // some code
}
// Here i is 5
```

- In the first example, using var, the variable declared in the loop redeclares the variable outside the loop.
- In the second example, using let, the variable declared in the loop does not redeclare the variable outside the loop.
- When let is used to declare the i variable in a loop, the i variable will only be visible within the loop.

## The For In Loop
The JavaScript for in statement loops through the properties of an Object:

Syntax
```js
for (key in object) {
  // code block to be executed
}
```

```js
const person = {fname:"John", lname:"Doe", age:25};
let text = "";
for (let x in person) {
  text += person[x];
}
```
text is John Doe 25

## For In Over Arrays
The JavaScript for in statement can also loop over the properties of an Array:

Syntax
```js
for (variable in array) {
  code
}
```

Example
```js
const numbers = [45, 4, 9, 16, 25];
let txt = "";
for (let x in numbers) {
  txt += numbers[x];
}
```

```js
45
4
9
16
25
```

## The For Of Loop
The JavaScript for of statement loops through the values of an iterable object.
It lets you loop over iterable data structures such as Arrays, Strings, Maps, NodeLists, and more:

Syntax
```js
for (variable of iterable) {
  // code block to be executed
}
```
### Looping over an Array
Example
```js
const cars = ["BMW", "Volvo", "Mini"];
let text = "";
for (let x of cars) {
  text += x;
}
```
BMW
Volvo
Mini

### Looping over a String
Example
```js
let language = "JavaScript";
let text = "";
for (let x of language) {
text += x;
}
```

## The While Loop
The while loop loops through a block of code as long as a specified condition is true.

Syntax
```js
while (condition) {
  // code block to be executed
}
```
Example
```js
while (i < 10) {
  text += "The number is " + i;
  i++;
}
```

The number is 0.
The number is 1.
The number is 2.
The number is 3.
The number is 4.
The number is 5.
The number is 6.
The number is 7.
The number is 8.
The number is 9.

## The Do While Loop
The do while loop is a variant of the while loop. This loop will execute the code block once, before checking if the condition is true, then it will repeat the loop as long as the condition is true.

Syntax
```js
do {
  // code block to be executed
}
while (condition);
```
```js
do {
  text += "The number is " + i;
  i++;
}
while (i < 10);
```
The number is 0.
The number is 1.
The number is 2.
The number is 3.
The number is 4.
The number is 5.
The number is 6.
The number is 7.
The number is 8.
The number is 9.

## JavaScript Break and Continue

The break statement "jumps out" of a loop.
The continue statement "jumps over" one iteration in the loop.


Example
```js
for (let i = 0; i < 10; i++) {
  if (i === 3) { break; }
  text += "The number is " + i + "<br>";
}
```
The number is 0.
The number is 1.
The number is 2.

---

The continue statement breaks one iteration (in the loop), if a specified condition occurs, and continues with the next iteration in the loop.
This example skips the value of 3:
Example
```js
for (let i = 0; i < 10; i++) {
  if (i === 3) { continue; }
  text += "The number is " + i + "<br>";
}
```
The number is 0.
The number is 1.
The number is 2.
The number is 4.
The number is 5.
The number is 6.
The number is 7.
The number is 8.
The number is 9.


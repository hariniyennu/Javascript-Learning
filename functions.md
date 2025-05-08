# JavaScript Functions
JavaScript functions are defined with the **function** keyword.

```js
function functionName(parameters) {
  // code to be executed
}
```
Example
```js
function myFunction(a, b) {
  return a * b;
}
```

## Function Expressions
A JavaScript function can also be defined using an **expression.**

A function expression can be stored in a variable:
```js
const x = function (a, b) {return a * b};
let z = x(4, 3);
```
The function above is actually an **anonymous function** (a function without a name).

## The Function() Constructor
Functions can also be defined with a built-in JavaScript function constructor called Function().
```js
const myFunction = new Function("a", "b", "return a * b");
let x = myFunction(4, 3);
```
## Self-Invoking Functions
Function expressions will execute automatically if the expression is followed by ().

You cannot self-invoke a function declaration.

```js
(function () {
  let x = "Hello!!";  // I will invoke myself
})();
```
The function above is actually an **anonymous self-invoking function** (function without name).

### Functions are Objects
The typeof operator in JavaScript returns *"function"* for functions.
JavaScript functions have both properties and methods.
```js
function myFunction(a, b) {
  return arguments.length; //2
}
```
```js
function myFunction(a, b) {
  return a * b;
}
let text = myFunction.toString(); // function myFunction(a, b) { return a * b; }
```
## Arrow Functions
You don't need the function keyword, the return keyword, and the curly brackets.

```js
// ES5
var x = function(x, y) {
  return x * y;
}

// ES6
const x = (x, y) => x * y;
```
- Using const is safer than using var, because a function expression is always constant value.

## Function Parameters and Arguments
Function parameters are the names listed in the function definition.

Function arguments are the real values passed to (and received by) the function.

### Default Parameters
If a function is called with missing arguments (less than declared), the missing values are set to undefined.
```js
function myFunction(x, y) {
  if (y === undefined) {
    y = 2;
  }
}
```

If y is not passed or undefined, then y = 10.
```js
function myFunction(x, y = 10) {
  return x + y;
}
myFunction(5);
```

- The rest parameter (...) allows a function to treat an indefinite number of arguments as an array:
```js
function sum(...args) {
  let sum = 0;
  for (let arg of args) sum += arg;
  return sum;
}
let x = sum(4, 9, 16, 25, 29, 100, 66, 77);
```
**Arguments are Passed by Value**
Changes to arguments are not visible (reflected) outside the function.

**Objects are Passed by Reference**
Changes to object properties are visible (reflected) outside the function.

What is **this?**
this is not a variable. It is a keyword. You cannot change the value of this.

- In an object method, this refers to the object.
- Alone, this refers to the global object.
- In a function, this refers to the global object.
- In a function, in strict mode, this is undefined.
- In an event, this refers to the element that received the event.
- Methods like call(), apply(), and bind() can refer this to any object.

```js
const myObject = {
  firstName:"John",
  lastName: "Doe",
  fullName: function () {
    return this.firstName + " " + this.lastName;
  }
}
myObject.fullName();         // Will return "John Doe"
```
## The JavaScript call() Method
It can be used to invoke (call) a method with an object as an argument (parameter).

**Note**
With call(), an object can use a method belonging to another object.
```js
const person = {
  fullName: function() {
    return this.firstName + " " + this.lastName;
  }
}
const person1 = {
  firstName:"John",
  lastName: "Doe"
}
const person2 = {
  firstName:"Mary",
  lastName: "Doe"
}

// This will return "John Doe":
person.fullName.call(person1);
```
## The JavaScript apply() Method
The apply() method is similar to the call() method
```js
const person = {
  fullName: function() {
    return this.firstName + " " + this.lastName;
  }
}

const person1 = {
  firstName: "Mary",
  lastName: "Doe"
}

// This will return "Mary Doe":
person.fullName.apply(person1);
```
The call() method takes arguments **separately.**
The apply() method takes arguments as an **array.**

## Function Borrowing
With the bind() method, an object can borrow a method from another object.
```js
const person = {
  firstName:"John",
  lastName: "Doe",
  fullName: function () {
    return this.firstName + " " + this.lastName;
  }
}
const member = {
  firstName:"Hege",
  lastName: "Nilsen",
}
let fullName = person.fullName.bind(member);
```

## JavaScript Closures
### Local Variables
A local variable is a "private" variable defined inside a function.

A function can access all variables in the local scope.
```js
function myFunction() {
  let a = 4;        //a is a local variable defined inside the function
  return a * a;
}
```

### Global Variables
A global variable is a "public" variable defined outside a function.

A function can access all variables in the global scope:
```js
let a = 4; //a is global variable defined outside the function
function myFunction() {
  return a * a;
}
```
**Note**
Undeclared variables (created without a keyword var, let, const), are always global, even if they are created inside a function.

### Variable Lifetime
Global variables live until the page is discarded, like when you navigate to another page or close the window.
Local variables have short lives. They are created when the function is invoked, and deleted when the function is finished.

## JavaScript Nested Functions
```js
function add() {
  let counter = 0;
  function plus() {counter += 1;}
  plus();   
  return counter;
}
```

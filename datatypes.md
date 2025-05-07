# JavaScript Data Types

### JavaScript has 8 Datatypes
- String
- Number
- Bigint
- Boolean
- Undefined
- Null
- Symbol
- Object

## The Object Datatype
The object data type can contain both built-in objects, and user defined objects. Built-in object types can be:
objects, arrays, dates, maps, sets, intarrays, floatarrays, promises, and more.

**Note
A JavaScript variable can hold any type of data.**

**JavaScript has dynamic types. This means that the same variable can be used to hold different data types:**

Example
```js
let x;       // Now x is undefined
x = 5;       // Now x is a Number
x = "John";  // Now x is a String
```

## JavaScript Strings

A string (or a text string) is a series of characters like "John Doe".
Strings are written with quotes. You can use single or double quotes

Example
```js
// Single quote inside double quotes:
let answer1 = "It's alright";
// Single quotes inside double quotes:
let answer2 = "He is called 'Johnny'";
// Double quotes inside single quotes:
let answer3 = 'He is called "Johnny"';
```

## JavaScript Numbers
All JavaScript numbers are stored as decimal numbers (floating point).
Numbers can be written with, or without decimals:

Example
```js
// With decimals:
let x1 = 34.00;
// Without decimals:
let x2 = 34;
```

**Exponential Notation**
```js
let y = 123e5;    // 12300000
let z = 123e-5;   // 0.00123
```

**Javascript numbers are always one type:
double (64-bit floating point).**

**JavaScript BigInt**
```js
let x = BigInt("123456789012345678901234567890");
```

## JavaScript Booleans
Booleans can only have two values: true or false.

Example
```js
let x = 5;
let y = 5;
let z = 6;
(x == y)       // Returns true
(x == z)       // Returns false
```

## JavaScript Arrays

Example
```js
const cars = ["Saab", "Volvo", "BMW"];
```

## JavaScript Objects
Object properties are written as name:value pairs, separated by commas.

Example
```js
const person = {firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"};
```

**The typeof Operator**
The typeof operator returns the type of a variable or an expression:

Example
```js
typeof ""             // Returns "string"
typeof "John"         // Returns "string"
typeof "John Doe"     // Returns "string"
```

## Undefined
In JavaScript, a variable without a value, has the value undefined. The type is also undefined.

Example
```js
let car;    // Value is undefined, type is undefined
```

## Empty Values
An empty value has nothing to do with undefined.
An empty string has both a legal value and a type.

Example
```js
let car = "";    // The value is "", the typeof is "string"
```





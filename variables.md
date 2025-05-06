# 📘 JavaScript Variables

Variables are **containers for storing data**. In JavaScript, variables can be declared in the following ways:

1.  Automatically
2.  Using `var`
3.  Using `let`
4.  Using `const`

---

## 📌 Declaring Variables

## 1️⃣ Automatically Declaring Variables

```js
x = 5;
y = 6;
z = x + y;
console.log(z);
```
---

## 2️⃣ Using var

```js
var x = 5;
var y = 6;
var z = x + y;
console.log(z);
```
> ⚠️ The var keyword should only be used in code written for older browsers.

---

## 3️⃣ Using let

```js
let x = 5;
let y = 6;
let z = x + y;
console.log(z);
```

---

## 4️⃣ Using const

```js
const x = 5;
const y = 6;
const z = x + y;
console.log(z);
```
---

# 📌 When to Use var, let, or const

- Always declare variables.
- Always use `const` if the value should not be changed.
- Always use `const` if the type should not be changed (Arrays and Objects).
- Only use `let` if you can't use `const`.
- Only use `var` if you must support old browsers.

 ---

 # 📌 Variable Naming Rules
 
 ## The general rules for constructing names for variables (unique identifiers) are:
 - Names can contain letters, digits, underscores, and dollar signs.
 - Names must begin with a letter.
 - Names can also begin with $ and _ (but we will not use these in this tutorial).
 - Names are case sensitive (e.g., y and Y are different variables).
 - Reserved words (like JavaScript keywords) cannot be used as names.

 ---

 ## 📌 Undefined Variable
 ### A variable declared without a value will have the value undefined.

 ---
 ## 📌 Re-declaring Variables
 ### You cannot re-declare a variable declared with let or const.
 ```js
let carName = "Volvo";
let carName; // This will throw an error
 ```
 ---
 
 ## 📌 Type Coercion in JavaScript
 ```js
let x = 5 + 2 + 3; // 10
let x = "John" + " " + "Doe"; // "John Doe"
let x = "5" + 2 + 3; // "523" (string concatenation)
let x = 2 + 3 + "5"; // "55" (string concatenation)
```
### If you put a number in quotes, the rest of the numbers will be treated as strings and concatenated.

---

 ## 📌 let Keyword (ES6)
 ## The let keyword was introduced in ES6 (2015).
 - Variables declared with let have block scope.
 - Variables declared with let must be declared before use.
 - Variables declared with let cannot be redeclared in the same scope.

 ## Block Scope Example:
 ```js
{
  let x = 2;
} // x cannot be used here

 ```
 ## Global Scope Example:
 ```js
{
  var x = 2;
} // x can be used here
 
 ```
 ## With let, you cannot do this:
 ```js
let x = "John Doe";
let x = 0; // Error: Cannot redeclare variable
```
 ## With var, you can do this:
 ```js
var x = "John Doe";
var x = 0; // No error
```
 ---

 # 📌 Difference Between var, let, and const

|          | Scope    | Redeclare | Reassign | Hoisted | Binds this |
|----------|----------|-----------|----------|---------|------------|
| **var**  | Function | Yes       | Yes      | Yes     | Yes        |
| **let**  | Block    | No        | No       | Yes     | No         |
| **const**| Block    | No        | No       | No      | No         |

---

# 📌 Pros and Cons of let and const
✅ **What is Good?**
- `let` and `const` have block scope.
- `let` and `const` cannot be redeclared.
- `let` and `const` must be declared before use.
- `let` and `const` do not bind to `this`.
- `let` and `const` are not hoisted.

❌ **What is Not Good?**
- `var` does not have to be declared.
- `var` is hoisted.
- `var` binds to `this`.
- The `let` and `const` keywords are not supported in Internet Explorer 11 or earlier.

📌 **const Keyword**
- Variables defined with `const` cannot be redeclared or reassigned.

### Example (Invalid):
```js
const PI = 3.141592653589793;
PI = 3.14; // Error: Assignment to constant variable
PI = PI + 10; // Error: Assignment to constant variable
```
**Correct Usage:**
```js
const PI = 3.14159265359;
```
### JavaScript const variables must be assigned a value when they are declared.

## When to use const?
### Always declare a variable with const when you know that the value should not be changed. Use const for:
 - A new Array
 - A new Object
 - A new Function
 - A new RegExp

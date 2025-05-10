# JavaScript Objects

Objects are collections of key-value pairs where values can be of any data type. 

In JavaScript, objects are one of the most important concepts, used to store various data and more complex entities

# Methods for Defining JavaScript Objects

1. **Using an Object Literal**
2. **Using the `new` Keyword**
3. **Using an Object Constructor**
4. **Using `Object.assign()`**
5. **Using `Object.create()`**
6. **Using `Object.fromEntries()`**

# JavaScript Object Literal

An **object literal** is a list of property names and values inside curly braces `{}`.

```js
{ firstName: "John", lastName: "Doe", age: 50, eyeColor: "blue" };
```
**An object literal is also called an object initializer.**

## Creating a JavaScript Object
1. Using Object Literals
```js
// Create an Object
const person = {};
// Add Properties
person.firstName = "John";
person.lastName = "Doe";
person.age = 50;
person.eyeColor = "blue";
```
2. Using new Object()
```js
const person = new Object();
person.firstName = "John";
person.lastName = "Doe";
person.age = 50;
person.eyeColor = "blue";
```
3. Using Constructor Functions
```js
// Create an Object
const person = new Object();
// Add Properties
person.firstName = "John";
person.lastName = "Doe";
person.age = 50;
person.eyeColor = "blue";
```
```js
const myFather = new Person("John", "Doe", 50, "blue");
const myMother = new Person("Sally", "Rally", 48, "green");
const mySister = new Person("Anna", "Rally", 18, "green");
const mySelf = new Person("Johnny", "Rally", 22, "green");
```
## Object Iteration 

- for...in loop:
```js
const person = { name: "John", age: 25 };
for (let key in person) {
  console.log(key, person[key]);
}
```
- Object.keys(), Object.values(), Object.entries():
```js
console.log(Object.keys(person));   // ["name", "age"]
console.log(Object.values(person)); // ["John", 25]
console.log(Object.entries(person)); // [["name", "John"], ["age", 25]]
```
```js
const person = { name: 'John', age: 30 };
const keys = Object.keys(person);
const values = Object.values(person);
const entries = Object.entries(person);

console.log(keys); // ['name', 'age']
console.log(values); // ['John', 30]
console.log(entries); // [['name', 'John'], ['age', 30]]

const person = { name: 'John', age: 30 };
Object.entries(person).forEach(([key, value]) => {
  console.log(key + ": " + value);
});
// Output:
// name: John
// age: 30

```

## JavaScript Object Methods
JavaScript Object Methods can be grouped into:

- General Methods
- Property Management Methods
- Object Protection Methods

### General Methods

| Method                       | Description                                     | Example                                                                 |
|-----------------------------|-------------------------------------------------|------------------------------------------------------------------------|
| `Object.assign(target, source)` | Copies properties from a source object to a target object | `const obj1 = { a: 1 }; const obj2 = { b: 2 }; Object.assign(obj1, obj2);` |
| `Object.create(proto)`         | Creates a new object with the specified prototype object | `const parent = { greet() { console.log('Hello!'); } }; const child = Object.create(parent);` |
| `Object.entries(object)`       | Returns an array of the key/value pairs of an object      | `Object.entries({ a: 1, b: 2 }); // [['a', 1], ['b', 2]]`               |
| `Object.fromEntries(iterable)` | Creates an object from a list of key-value pairs          | `Object.fromEntries([['a', 1], ['b', 2]]); // { a: 1, b: 2 }`           |
| `Object.keys(object)`          | Returns an array of the keys of an object                 | `Object.keys({ a: 1, b: 2 }); // ['a', 'b']`                            |
| `Object.values(object)`        | Returns an array of the values of an object              | `Object.values({ a: 1, b: 2 }); // [1, 2]`                              |

### Property Management Methods

| Method                             | Description                                      | Example                                                                 |
|-----------------------------------|--------------------------------------------------|------------------------------------------------------------------------|
| `Object.defineProperty()`         | Adds or changes a property in an object          | `Object.defineProperty(obj, 'name', { value: 'John', writable: false });` |
| `Object.defineProperties()`       | Adds or changes multiple properties              | `Object.defineProperties(obj, { age: { value: 30 }, city: { value: 'NY' }});` |
| `Object.getOwnPropertyDescriptor()` | Returns property descriptor for a named property | `Object.getOwnPropertyDescriptor(obj, 'name');`                         |
| `Object.getOwnPropertyDescriptors()` | Returns all property descriptors of an object    | `Object.getOwnPropertyDescriptors(obj);`                                |
| `Object.getOwnPropertyNames()`    | Returns an array of all properties               | `Object.getOwnPropertyNames(obj);`                                      |
| `Object.getPrototypeOf()`         | Returns the prototype of an object               | `Object.getPrototypeOf(obj);`                                           |

### Object Protection Methods

| Method                       | Description                                        | Example                                                                 |
|-----------------------------|--------------------------------------------------|------------------------------------------------------------------------|
| `Object.preventExtensions()` | Prevents new properties from being added to an object | `const obj = { name: 'John' }; Object.preventExtensions(obj); obj.age = 30; // Not added`|
| `Object.isExtensible()`      | Checks if properties can be added to an object       | `Object.isExtensible(obj); // false`                                   |
| `Object.seal()`              | Prevents properties from being added or removed     | `Object.seal(obj); delete obj.name; // Cannot delete`                   |
| `Object.isSealed()`          | Checks if an object is sealed                        | `Object.isSealed(obj); // true`                                        |
| `Object.freeze()`            | Prevents any changes to an object                   | `Object.freeze(obj); obj.name = 'Doe'; // No change`                    |
| `Object.isFrozen()`          | Checks if an object is frozen                       | `Object.isFrozen(obj); // true`                                        |

- Differences Between Object.freeze() and Object.seal()
  
| Method            | Prevent Adding | Prevent Deleting | Prevent Modifying | Extensible |
| ----------------- | -------------- | ---------------- | ----------------- | ---------- |
| `Object.freeze()` | ✅              | ✅                | ✅                 | ❌          |
| `Object.seal()`   | ✅              | ✅                | ❌                 | ❌          |

#  Prototypes and Inheritance

- JavaScript Prototypes
Every JavaScript object has a built-in property called prototype, which allows you to add properties and methods to it.

Objects inherit properties and methods from their prototype.
```js
// Constructor function
function Person(firstName, lastName) {
  this.firstName = firstName;
  this.lastName = lastName;
}
// Adding a method to the prototype
Person.prototype.getFullName = function() {
  return this.firstName + " " + this.lastName;
};
const person1 = new Person("John", "Doe");
console.log(person1.getFullName()); // Output: John Doe
```
- Prototype Inheritance
JavaScript objects inherit features from their prototype.

Prototypal inheritance allows objects to inherit properties and methods from other objects.
```js
const car = {
  type: "Sedan",
  wheels: 4,
  start() {
    console.log("Car started");
  }
};
// Creating a new object with car as its prototype
const myCar = Object.create(car);
console.log(myCar.type); // Output: Sedan
myCar.start(); // Output: Car started
```
- Prototype Chain
When accessing a property, JavaScript looks for it in the object itself first.

If not found, it continues up the prototype chain until it finds the property or reaches the end of the chain (null).
```js
const animal = {
  eats: true
};

const rabbit = Object.create(animal);
rabbit.jumps = true;

console.log(rabbit.eats);  // Output: true  (inherited from animal)
console.log(rabbit.jumps); // Output: true
```

- Adding Properties and Methods to Prototypes
You can add new properties or methods to a constructor's prototype even after objects are created:
```js
function User(name) {
  this.name = name;
}

const user1 = new User("Alice");
const user2 = new User("Bob");

// Adding a method to the prototype
User.prototype.sayHello = function() {
  console.log(`Hello, my name is ${this.name}`);
};

user1.sayHello(); // Output: Hello, my name is Alice
user2.sayHello(); // Output: Hello, my name is Bob
```
- Modifying Built-in Prototypes (Not Recommended)
Although it's possible to modify built-in prototypes like Array, String, or Object, it's not recommended because it can lead to unexpected behavior.

Example (Not Recommended):
```js
Array.prototype.last = function() {
  return this[this.length - 1];
};

const arr = [1, 2, 3];
console.log(arr.last()); // Output: 3
```
- Using hasOwnProperty()
The hasOwnProperty() method checks if a property exists directly on the object (not in its prototype chain).

```js
const obj = { name: "John" };

console.log(obj.hasOwnProperty('name')); // true
console.log(obj.hasOwnProperty('toString')); // false, inherited from prototype
```
- Prototype vs. __proto__
prototype is a property of constructor functions.

__proto__ is an internal property that points to the prototype of the object.

```js
function Animal(name) {
  this.name = name;
}

const dog = new Animal("Buddy");

console.log(dog.__proto__ === Animal.prototype); // true
console.log(Animal.prototype.constructor === Animal); // true
```
# Object Cloning and Iteration
- Object Cloning
Cloning an object means creating a new object that has the same properties as the original object. In JavaScript, we can achieve this using various methods.

- Shallow Copy
A shallow copy only copies the top-level properties. Nested objects or arrays will still reference the original objects.

Methods for Cloning
1. Using Object.assign() : Creates a shallow copy of the object.
```js
   const person = { name: 'John', age: 30 };
  const clone = Object.assign({}, person);

  console.log(clone); // { name: 'John', age: 30 }
  console.log(clone === person); // false (new object)
```
2. Using Spread Syntax (...) : Another way to create a shallow copy of an object.
```js
const person = { name: 'John', age: 30 };
const clone = { ...person };

console.log(clone); // { name: 'John', age: 30 }
console.log(clone === person); // false (new object)
```
3. Using JSON.parse() and JSON.stringify() : This creates a deep copy, where both nested objects and arrays are cloned. However, it does not work with functions, undefined, or symbols.
```js
const person = { name: 'John', age: 30, address: { city: 'New York' } };
const deepClone = JSON.parse(JSON.stringify(person));

console.log(deepClone); // { name: 'John', age: 30, address: { city: 'New York' } }
console.log(deepClone.address === person.address); // false (new nested object)
```

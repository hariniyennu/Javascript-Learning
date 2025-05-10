# JavaScript Classes
JavaScript Classes are templates for creating objects. They are a syntactical sugar over JavaScript's existing prototype-based inheritance and make object-oriented programming more intuitive.

## 1️⃣ Defining a Class
A class is defined using the class keyword, followed by its name, and a curly-braced body containing methods.
```js
class Person {
  // Constructor Method
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }
  // Method
  sayHello() {
    console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
  }
}
// Creating an instance of the class
const john = new Person('John', 25);
john.sayHello(); // Output: Hello, my name is John and I am 25 years old.
```
## 2️⃣ Class Methods
Class methods are defined inside the class body. They do not require the function keyword.
```js
class Car {
  constructor(brand) {
    this.brand = brand;
  }
  displayBrand() {
    console.log(`This car is a ${this.brand}.`);
  }
}
const myCar = new Car('Toyota');
myCar.displayBrand(); // Output: This car is a Toyota.
```

## 3️⃣ Getter and Setter Methods
```js
class Book {
  constructor(title, author) {
    this._title = title;
    this._author = author;
  }
  // Getter
  get title() {
    return this._title;
  }
  // Setter
  set title(newTitle) {
    this._title = newTitle;
  }
}
const myBook = new Book('The Alchemist', 'Paulo Coelho');
console.log(myBook.title); // Output: The Alchemist
myBook.title = 'Brida';
console.log(myBook.title); // Output: Brida

```
## 4️⃣ Static Methods
Static methods are defined using the static keyword and are called on the class itself, not on instances.
```javascript
class MathUtils {
  static add(a, b) {
    return a + b;
  }
}

console.log(MathUtils.add(5, 3)); // Output: 8
```
## 5️⃣ Inheritance
```js
class Animal {
  constructor(name) {
    this.name = name;
  }

  speak() {
    console.log(`${this.name} makes a noise.`);
  }
}

class Dog extends Animal {
  speak() {
    console.log(`${this.name} barks.`);
  }
}

const myDog = new Dog('Buddy');
myDog.speak(); // Output: Buddy barks.
```
## 6️⃣ The super() Keyword
When inheriting from a parent class, you can use super() to call its constructor and methods.
```js
class Vehicle {
  constructor(brand) {
    this.brand = brand;
  }

  start() {
    console.log(`${this.brand} is starting.`);
  }
}

class Bike extends Vehicle {
  constructor(brand, type) {
    super(brand); // Call the parent constructor
    this.type = type;
  }

  display() {
    console.log(`${this.brand} is a ${this.type} bike.`);
  }
}

const myBike = new Bike('Yamaha', 'Sports');
myBike.start(); // Output: Yamaha is starting.
myBike.display(); // Output: Yamaha is a Sports bike.
```
## 7️⃣ Private Fields
Private fields are declared with a # and cannot be accessed outside the class.
```javascript
class Account {
  #balance;

  constructor(balance) {
    this.#balance = balance;
  }

  getBalance() {
    return this.#balance;
  }
}

const myAccount = new Account(1000);
console.log(myAccount.getBalance()); // Output: 1000
console.log(myAccount.#balance); // ❌ SyntaxError: Private field '#balance' must be declared in an enclosing class
```
## 8️⃣ Class Expressions
```js
const Person = class {
  constructor(name) {
    this.name = name;
  }

  sayHello() {
    console.log(`Hello, I am ${this.name}`);
  }
};

const john = new Person('John');
john.sayHello(); // Output: Hello, I am John
```

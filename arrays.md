# JavaScript Arrays

---

## 🔹 **1. What is an Array?**
- An **array** is a special variable that can hold multiple values at the same time.
- Arrays are defined using **square brackets `[]`**, and elements are separated by **commas**.

```javascript
let colors = ["Red", "Green", "Blue"];
console.log(colors[0]); // Output: Red
```
## 🔹 2. Creating Arrays
- Using an Array Literal (Preferred way):
```js
let fruits = ["Apple", "Banana", "Mango"];
```
- Using the new Array() Constructor:
```js
let cars = new Array("BMW", "Audi", "Mercedes");
```
## 🔹 3. Accessing Array Elements
- Use the index number to access an element.
- Indexes start from 0.
```js
let animals = ["Lion", "Tiger", "Elephant"];
console.log(animals[1]); // Output: Tiger
```
## 🔹 4. Array Properties and Methods

| **Property/Method**                               | **Description**                                          | **Example**                                                              |
|---------------------------------------------------|----------------------------------------------------------|--------------------------------------------------------------------------|
| `length`                                          | Returns the number of elements in the array              | `["a", "b", "c"].length; // 3`                                          |
| `push()`                                          | Adds new elements to the **end** of the array            | `arr.push("Orange");`                                                   |
| `pop()`                                           | Removes the **last** element from the array              | `arr.pop();`                                                             |
| `shift()`                                         | Removes the **first** element from the array             | `arr.shift();`                                                           |
| `unshift()`                                       | Adds new elements to the **beginning** of the array      | `arr.unshift("Lemon");`                                                 |
| `indexOf()`                                       | Searches for an element and returns its **first index**  | `["a", "b", "c"].indexOf("b"); // 1`                                    |
| `lastIndexOf()`                                   | Searches for an element and returns its **last index**   | `["a", "b", "c", "b"].lastIndexOf("b"); // 3`                           |
| `includes()`                                      | Checks if an array contains a specified element          | `["Apple", "Banana"].includes("Banana"); // true`                        |
| `concat()`                                        | Joins two or more arrays                                 | `arr1.concat(arr2);`                                                    |
| `join()`                                          | Joins all array elements into a string                   | `["Red", "Green"].join(" & "); // "Red & Green"`                         |
| `slice(start, end)`                               | Extracts a section of an array into a **new array**      | `["a", "b", "c"].slice(0, 2); // ["a", "b"]`                            |
| `splice(start, deleteCount, item1, item2, ...)`   | Adds/removes elements                                    | `arr.splice(1, 0, "Lemon");`                                            |
| `reverse()`                                       | Reverses the order of the elements in an array           | `["a", "b", "c"].reverse(); // ["c", "b", "a"]`                         |
| `sort()`                                          | Sorts the elements of an array                           | `["Banana", "Apple"].sort(); // ["Apple", "Banana"]`                     |
| `find()`                                          | Returns the **first element** that matches the condition | `[4, 9, 16].find(x => x > 10); // 16`                                   |
| `findIndex()`                                     | Returns the **index** of the first element that matches  | `[4, 9, 16].findIndex(x => x > 10); // 2`                                |
| `filter()`                                        | Creates a **new array** with elements that pass the test | `[4, 9, 16].filter(x => x > 10); // [16]`                               |
| `map()`                                           | Creates a **new array** with the results of a function   | `[2, 4, 6].map(x => x * 2); // [4, 8, 12]`                              |
| `forEach()`                                       | Calls a function **once for each element** in the array  | `[1, 2, 3].forEach(x => console.log(x)); // 1 2 3`                       |
| `reduce()`                                        | Reduces the array to a **single value**                  | `[1, 2, 3].reduce((a, b) => a + b); // 6`                               |

## 🔹 5. Iterating Through Arrays
1. for Loop:
```js
let fruits = ["Apple", "Banana", "Mango"];
for (let i = 0; i < fruits.length; i++) {
    console.log(fruits[i]);
}
```
2. for...of Loop:
```js
for (let fruit of fruits) {
    console.log(fruit);
}
```
3. forEach() Method:
```js
fruits.forEach(fruit => console.log(fruit));
```

## 🔹 6. Multidimensional Arrays
```js
let matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
];

console.log(matrix[1][2]); // Output: 6
```

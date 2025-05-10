# JavaScript Asynchronous Programming
JavaScript is single-threaded, meaning it executes code sequentially line by line. 

However, with asynchronous programming, it can handle long-running tasks (like API calls, file reading, timers, etc.) without blocking the main thread.

## 1️⃣ JavaScript Callbacks
A callback is a function passed as an argument to another function and is executed after the completion of that function.

```js
function fetchData(callback) {
  console.log("Fetching data...");
  setTimeout(() => {
    console.log("Data fetched!");
    callback(); // Calling the callback function
  }, 2000); // Simulate a network request delay
}

function displayData() {
  console.log("Displaying data...");
}

fetchData(displayData);
```
Output:

```js
Fetching data...
Data fetched!
Displaying data...
```
Here, displayData is a callback function that executes after fetchData finishes.

## 2️⃣ JavaScript Asynchronous Programming
Asynchronous programming allows JavaScript to perform long network requests or file reading without freezing the UI or blocking further execution.
```js
console.log("1: Start");

setTimeout(() => {
  console.log("2: Asynchronous Task Completed");
}, 2000);

console.log("3: End");
```
Output
```js
1: Start
3: End
2: Asynchronous Task Completed
```
The setTimeout() function runs after 2 seconds without blocking the execution of the next line.

## 3️⃣ JavaScript Promises
A Promise is an object representing the eventual completion or failure of an asynchronous operation.

Promise States:
- Pending: Initial state, neither fulfilled nor rejected.
- Fulfilled: Completed successfully.
- Rejected: Failed.

Creating a Promise:
```js
const promise = new Promise((resolve, reject) => {
  let success = true;

  if (success) {
    resolve("Operation Successful");
  } else {
    reject("Operation Failed");
  }
});

promise
  .then((message) => {
    console.log(message); // Output: Operation Successful
  })
  .catch((error) => {
    console.error(error); // If rejected
  });
```
## 4️⃣ Chaining Promises
You can chain .then() calls to handle multiple asynchronous operations sequentially.
```js
const getNumber = () => {
  return new Promise((resolve) => {
    setTimeout(() => resolve(10), 1000);
  });
};

getNumber()
  .then((num) => {
    console.log(num); // Output: 10
    return num * 2;
  })
  .then((num) => {
    console.log(num); // Output: 20
    return num * 2;
  })
  .then((num) => {
    console.log(num); // Output: 40
  });
```

## 5️⃣ Async/Await
Async/Await is syntactic sugar over Promises, making asynchronous code look synchronous and more readable.
```js
const fetchData = () => {
  return new Promise((resolve) => {
    setTimeout(() => {
      resolve("Data Fetched!");
    }, 2000);
  });
};

async function displayData() {
  console.log("Fetching...");
  const result = await fetchData(); // Waits for the Promise to resolve
  console.log(result);
}

displayData();
```
Output
```js
Fetching...
(Data Fetches after 2 seconds...)
Data Fetched!
```

## 6️⃣ Error Handling with Async/Await
You can use try...catch to handle errors gracefully.
```js
const fetchData = async () => {
  try {
    const response = await fetch("https://jsonplaceholder.typicode.com/posts/1");
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.error("Error fetching data:", error.message);
  }
};

fetchData();
```

## 7️⃣ Promise Methods

| Method               | Description                                                    | Example                                                                 |
|-----------------------|----------------------------------------------------------------|------------------------------------------------------------------------|
| `Promise.all()`      | Waits for all promises to resolve or any to reject.            | `Promise.all([p1, p2, p3]).then((values) => console.log(values));`      |
| `Promise.race()`     | Resolves or rejects as soon as one of the promises does.       | `Promise.race([p1, p2]).then((value) => console.log(value));`           |
| `Promise.allSettled()` | Waits for all promises to complete (either resolved or rejected). | `Promise.allSettled([p1, p2]).then((results) => console.log(results));` |
| `Promise.any()`      | Waits for the first promise that is fulfilled.                 | `Promise.any([p1, p2]).then((value) => console.log(value));`            |

## 8️⃣ Differences Between Callbacks, Promises, and Async/Await

| Concept        | Description                               | Readability | Error Handling    |
|----------------|-------------------------------------------|-------------|-------------------|
| **Callback**  | A function passed to another function      | Low         | Callback Hell     |
| **Promise**   | Object representing completion/failure     | Medium      | `.catch()` method |
| **Async/Await** | Cleaner syntax over Promises              | High        | `try...catch`     |


# JavaScript Web APIs (Application Programming Interfaces)
Web APIs are built into your web browser and allow you to manipulate the browser and its content. 

They provide a way to interact with the browser, retrieve data, manipulate the DOM, store information, and much more.

## 1️⃣ Web API Intro
- A Web API is an interface that allows you to interact with web browsers or services.

Examples of Web APIs include:
- DOM API - For manipulating HTML and CSS
- Fetch API - For making HTTP requests
- Geolocation API - For getting the geographical location of the user
- LocalStorage API - For storing data locally in the browser
- Web Worker API - For running JavaScript in the background

## 2️⃣ Web Validation API
- The Constraint Validation API allows you to validate form elements before submission.
- You can use properties like .validity, .validationMessage, and methods like .checkValidity().
```html
<!DOCTYPE html>
<html>
<body>

<form id="myForm">
  <input type="text" id="username" required minlength="3" maxlength="10">
  <button type="submit">Submit</button>
</form>

<script>
document.getElementById("myForm").addEventListener("submit", function(event) {
  const username = document.getElementById("username");
  if (!username.checkValidity()) {
    alert(username.validationMessage); // Shows validation error message
    event.preventDefault(); // Prevents form submission
  }
});
</script>

</body>
</html>
```

## 3️⃣ Web History API
- The History API allows you to interact with the browser's history stack.
- You can navigate back and forth, and manipulate history entries.

Methods include:
- history.back() - Goes back one page.
- history.forward() - Goes forward one page.
- history.go(n) - Goes to a specific page in history. (e.g., history.go(-1) goes back one step).
```js
// Go back one page
history.back();

// Go forward one page
history.forward();

// Go to a specific position
history.go(-2); // Goes back two steps
```

## 4️⃣ Web Storage API
- Provides a way to store key/value pairs locally.

Two types of storage:
- Local Storage - Data persists even when the browser is closed.
- Session Storage - Data is cleared when the browser session ends.
Example (Local Storage):
```js
// Store data
localStorage.setItem("username", "Harini");

// Retrieve data
const user = localStorage.getItem("username");
console.log(user); // Harini

// Remove data
localStorage.removeItem("username");
```
Example (Session Storage):
```js
// Store data
sessionStorage.setItem("sessionUser", "John Doe");

// Retrieve data
const sessionUser = sessionStorage.getItem("sessionUser");
console.log(sessionUser); // John Doe

// Remove data
sessionStorage.removeItem("sessionUser");
```

## 5️⃣ Web Worker API
- Web Workers allow you to run JavaScript in the background without affecting the user interface.
- Useful for tasks like calculations, API calls, or processing large data.
Example: main.js
```js
// Create a worker
const worker = new Worker('worker.js');

// Listen for messages from the worker
worker.onmessage = (event) => {
  console.log("Received from worker: ", event.data);
};

// Send a message to the worker
worker.postMessage("Hello, worker!");
```
worker.js
```js
// Listen for messages from the main thread
onmessage = (event) => {
  console.log("Message received from main script:", event.data);
  postMessage("Hello from the Worker!");
};
```

## 6️⃣ Web Fetch API
- The Fetch API provides a way to make HTTP requests to fetch resources asynchronously.
- It is more powerful and flexible than XMLHttpRequest.
```js
fetch('https://jsonplaceholder.typicode.com/todos/1')
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```
Output
```js
{
  userId: 1,
  id: 1,
  title: "delectus aut autem",
  completed: false
}
```

## 7️⃣ Web Geolocation API
- The Geolocation API allows you to get the geographical position of a user.
- It requires the user's permission.
```html
<!DOCTYPE html>
<html>
<body>

<button onclick="getLocation()">Get Location</button>
<p id="location"></p>

<script>
function getLocation() {
  if (navigator.geolocation) {
    navigator.geolocation.getCurrentPosition(showPosition);
  } else {
    document.getElementById("location").innerHTML = "Geolocation is not supported by this browser.";
  }
}

function showPosition(position) {
  document.getElementById("location").innerHTML = 
    "Latitude: " + position.coords.latitude + 
    "<br>Longitude: " + position.coords.longitude;
}
</script>

</body>
</html>
```

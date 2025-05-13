# 🌟 What is AJAX?
AJAX (Asynchronous JavaScript and XML) is a technique for creating fast and dynamic web pages. It allows web applications to send and receive data from a server asynchronously, without reloading the entire page.

## 🔹 How AJAX Works:
1. A client event occurs (like a button click).
2. JavaScript creates an XMLHttpRequest object.
3. The request is sent to the server.
4. The server processes the request and sends back a response.
5. JavaScript handles the response and updates the webpage dynamically.

## 📌 AJAX Workflow Diagram:

```js
   [Client Event]
         ↓
[XMLHttpRequest Created]
         ↓
  [Request Sent to Server]
         ↓
    [Server Processes]
         ↓
[Server Sends Back Response]
         ↓
[JavaScript Handles Response]
         ↓
   [Web Page Updated]
```
## 🔹 1️⃣ Create an XMLHttpRequest Object
To use AJAX, you first need to create an XMLHttpRequest object:
```js
const xhr = new XMLHttpRequest();
```
## 🔹 2️⃣ Open the Request
The open() method initializes a request.
```js
xhr.open("GET", "https://jsonplaceholder.typicode.com/todos/1", true);
```
Parameters:

- "GET": Type of request (GET or POST).
- URL: The API endpoint or URL to send the request to.
- true: Asynchronous (if false, it would be synchronous).

## 🔹 3️⃣ Send the Request
To actually send the request, use the send() method:
```js
xhr.send();
```
## 🔹 4️⃣ Handle the Response
You need to listen for the server's response using the onload event:

```js
xhr.onload = function () {
  if (xhr.status === 200) {
    console.log("Response received: ", xhr.responseText);
  } else {
    console.log("Error: ", xhr.status);
  }
};
```
Explanation:

- xhr.status: HTTP status code (200 means OK).
- xhr.responseText: The response data from the server.

## 📌 Complete Example:
```js
<!DOCTYPE html>
<html>
<head>
  <title>AJAX Example</title>
</head>
<body>
  <button onclick="loadData()">Fetch Data</button>
  <p id="output"></p>

  <script>
    function loadData() {
      const xhr = new XMLHttpRequest();
      xhr.open("GET", "https://jsonplaceholder.typicode.com/todos/1", true);

      xhr.onload = function () {
        if (xhr.status === 200) {
          const data = JSON.parse(xhr.responseText); // Parse JSON data
          document.getElementById("output").innerText = 
              `Title: ${data.title}\nCompleted: ${data.completed}`;
        } else {
          console.error("Error fetching data");
        }
      };

      xhr.send();
    }
  </script>
</body>
</html>
```
## 🔹 Different HTTP Methods:

| Method | Description                        |
| ------ | ---------------------------------- |
| GET    | Retrieve data from the server      |
| POST   | Send new data to the server        |
| PUT    | Update existing data on the server |
| DELETE | Remove data from the server        |

## 🔹 AJAX with POST Request:

When sending data to the server, you use a POST request:

```js
const xhr = new XMLHttpRequest();
xhr.open("POST", "https://example.com/api/users", true);
xhr.setRequestHeader("Content-type", "application/json");

xhr.onload = function () {
  if (xhr.status === 201) {
    console.log("Data sent successfully!");
  }
};

const data = JSON.stringify({ name: "Harini", age: 21 });
xhr.send(data);
```
Explanation:

- We set the header to application/json to send JSON data.
- The status 201 means the resource was successfully created.

## 🌟 AJAX with Fetch API (Modern Way)
```js
fetch("https://jsonplaceholder.typicode.com/todos/1")
  .then((response) => response.json()) // Convert to JSON
  .then((data) => {
    console.log(data);
  })
  .catch((error) => {
    console.error("Error fetching data: ", error);
  });
```
Advantages of fetch():

- Cleaner syntax (uses Promises).
- Easier to read and maintain.
- Built-in support for Promises, making it easier to handle asynchronous code.

## 🔹 AJAX Error Handling:

```js
fetch("https://jsonplaceholder.typicode.com/invalid-url")
  .then((response) => {
    if (!response.ok) {
      throw new Error("Network response was not OK");
    }
    return response.json();
  })
  .then((data) => {
    console.log(data);
  })
  .catch((error) => {
    console.error("Fetch Error:", error.message);
  });
```
## 🔹 AJAX and HTML Forms:
You can also submit forms using AJAX without refreshing the page.

```js
<form id="myForm">
  <input type="text" name="username" placeholder="Username">
  <button type="submit">Submit</button>
</form>

<script>
  document.getElementById("myForm").addEventListener("submit", function (e) {
    e.preventDefault();
    
    fetch("https://example.com/api/users", {
      method: "POST",
      headers: {
        "Content-Type": "application/json",
      },
      body: JSON.stringify({ username: e.target.username.value }),
    })
      .then((response) => response.json())
      .then((data) => console.log(data))
      .catch((error) => console.error(error));
  });
</script>
```

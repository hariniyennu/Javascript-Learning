# JavaScript JSON (JavaScript Object Notation)
## 1️⃣ JSON Intro
- JSON (JavaScript Object Notation) is a lightweight data interchange format.
- It is language-independent and is used to transmit data between a server and a web application.
- It is text-based, easy to read, and write.
```json
{
  "name": "John",
  "age": 30,
  "city": "New York"
}
```
## 2️⃣ JSON Syntax
- Data is in key/value pairs.
- Data is separated by commas.
- Curly braces {} hold objects.
- Square brackets [] hold arrays.
```json
{
  "employees": [
    { "firstName": "John", "lastName": "Doe" },
    { "firstName": "Anna", "lastName": "Smith" },
    { "firstName": "Peter", "lastName": "Jones" }
  ]
}
```
## 3️⃣ JSON vs XML

| **Feature** | **JSON**                          | **XML**                          |
| ----------- | --------------------------------- | -------------------------------- |
| Syntax      | Lighter and less verbose          | More verbose                     |
| Readability | Easier to read and write          | Harder to read                   |
| Data Type   | Supports arrays and objects       | Does not natively support arrays |
| Parsing     | Easily parsed with `JSON.parse()` | Needs XML parsers                |

## 4️⃣ JSON Data Types
- String
- Number
- Object
- Array
- Boolean
- Null
```json
{
  "name": "John",
  "age": 30,
  "isStudent": false,
  "marks": [85, 90, 78],
  "address": {
    "city": "New York",
    "zipcode": "10001"
  }
}
```
## 5️⃣ JSON Parse
Converts a JSON string into a JavaScript object.

Method: JSON.parse()
```json
const jsonString = '{"name": "John", "age": 30}';
const obj = JSON.parse(jsonString);

console.log(obj.name); // John
console.log(obj.age);  // 30
```
## 6️⃣ JSON Stringify
Converts a JavaScript object into a JSON string.

Method: JSON.stringify()
```json
const person = {
  name: "John",
  age: 30,
  city: "New York"
};

const jsonString = JSON.stringify(person);
console.log(jsonString); // {"name":"John","age":30,"city":"New York"}
```
## 7️⃣ JSON Objects
Objects in JSON are written inside curly braces.

Key-value pairs are separated by commas.
```json
{
  "employee": {
    "firstName": "John",
    "lastName": "Doe",
    "age": 30,
    "department": "Sales"
  }
}
```
## 8️⃣ JSON Arrays
Arrays in JSON are written inside square brackets.

Can hold multiple objects.
```json
{
  "employees": [
    { "firstName": "John", "lastName": "Doe" },
    { "firstName": "Anna", "lastName": "Smith" },
    { "firstName": "Peter", "lastName": "Jones" }
  ]
}
```
## 9️⃣ JSON Server
JSON Server is a tool that allows you to create a full REST API with zero coding.

Useful for testing and prototyping.

You can use it with fetch or axios to make API calls.

## 🔟 JSON PHP
- In PHP, you can encode and decode JSON using:

json_encode() - Converts PHP objects to JSON.

json_decode() - Converts JSON string to PHP objects or arrays.

```php
<?php
    $person = array("name" => "John", "age" => 30, "city" => "New York");
    echo json_encode($person);
?>
```
## 1️⃣1️⃣ JSON HTML
You can fetch JSON data and use it to manipulate HTML elements.

```html
<!DOCTYPE html>
<html>
<body>

<h2>Fetch JSON Data</h2>
<p id="demo"></p>

<script>
fetch('https://jsonplaceholder.typicode.com/users')
    .then(response => response.json())
    .then(data => {
        document.getElementById("demo").innerHTML = 
            `Name: ${data[0].name} <br> Email: ${data[0].email}`;
    });
</script>

</body>
</html>
```
## 1️⃣2️⃣ JSONP (JSON with Padding)
A technique to overcome CORS (Cross-Origin Resource Sharing) restrictions.

Allows you to request data from a server in a different domain.

```html
<script src="https://example.com/getData?callback=myFunction"></script>

<script>
function myFunction(data) {
  console.log(data);
}
</script>
```

# 📘 JavaScript Basics

JavaScript is the **programming language of the web**. It can dynamically update and change both HTML and CSS, and it enables the manipulation, calculation, and validation of data.

---

## 📌 Inserting JavaScript into HTML

### 1️⃣ The `<script>` Tag

JavaScript code is inserted between `<script>` and `</script>` tags.

```html
<script>
  document.getElementById("demo").innerHTML = "My First JavaScript";
</script>
```

---

### 2️⃣ Where to Place JavaScript

JavaScript can be placed in the `<head>`, `<body>`, or both.

#### 🧠 In the `<head>` Section

```html
<!DOCTYPE html>
<html>
<head>
  <script>
    function myFunction() {
      document.getElementById("demo").innerHTML = "Paragraph changed.";
    }
  </script>
</head>
<body>
  <h2>Demo JavaScript in Head</h2>
  <p id="demo">A Paragraph</p>
  <button type="button" onclick="myFunction()">Try it</button>
</body>
</html>
```

#### 💪 In the `<body>` Section

```html
<!DOCTYPE html>
<html>
<body>
  <h2>Demo JavaScript in Body</h2>
  <p id="demo">A Paragraph</p>
  <button type="button" onclick="myFunction()">Try it</button>

  <script>
    function myFunction() {
      document.getElementById("demo").innerHTML = "Paragraph changed.";
    }
  </script>
</body>
</html>
```

> ✅ Placing scripts **at the bottom of the `<body>` improves page load speed**, as scripts can block rendering.

---

### 3️⃣ External JavaScript

**`myScript.js`**

```js
function myFunction() {
  document.getElementById("demo").innerHTML = "Paragraph changed.";
}
```

**HTML File**

```html
<script src="myScript.js"></script>
```

> 🔸 External scripts **cannot contain `<script>` tags**.
> 🔸 Useful when the same JavaScript code is reused across multiple web pages.

#### ✅ Advantages of External Scripts:

* Separates HTML and logic
* Improves readability and maintainability
* Can be cached for faster page loads

---

## 🖥️ JavaScript Output Methods

### 1. `innerHTML` / `innerText`

Used to modify HTML content:

```js
document.getElementById("demo").innerHTML = "<h2>Hello World</h2>";
document.getElementById("demo").innerText = "Hello World";
```

* Use `innerHTML` to insert HTML tags or elements.
* Use `innerText` for plain text only.

---

### 2. `document.write()`

```js
document.write(5 + 6);
```

> ⚠️ Using `document.write()` after the page loads **will erase all content**. Best used for testing only.

---

### 3. `alert()` or `window.alert()`

```js
alert(5 + 6);
// or
window.alert(5 + 6);
```

> `window` is the global object, so it can be omitted.

---

### 4. `console.log()`

```js
console.log(5 + 6);
```

> Use this for **debugging** in the browser’s developer console.

---

## 🚫 Note on Printing

JavaScript does not have a `print()` method like in other languages. However, you can use:

```js
window.print();
```

To print the current browser window.

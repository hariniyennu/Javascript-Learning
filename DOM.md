# 🌟 JavaScript DOM (Document Object Model) 
The Document Object Model (DOM) is a programming interface that represents an HTML or XML document as a structured tree of objects. It allows JavaScript to manipulate, access, and modify both the structure and the content of a webpage.

## 1️⃣ Understanding the DOM Tree Structure
When the browser loads a webpage, it creates a DOM tree that represents the HTML document. The structure looks like this:

```js
<!DOCTYPE html>
<html>
  <head>
    <title>My Page</title>
  </head>
  <body>
    <h1 id="header">Hello, World!</h1>
    <p class="text">Welcome to the DOM tutorial.</p>
  </body>
</html>
```

The DOM tree representation:

```js
Document
│
├── html
│   ├── head
│   │   └── title → "My Page"
│   └── body
│       ├── h1 → "Hello, World!"
│       └── p → "Welcome to the DOM tutorial."
```

- Document Node: Represents the entire document.
- Element Nodes: Represents each HTML element (e.g., <h1>, <p>).
- Text Nodes: Represents the text inside HTML elements.
- Attribute Nodes: Represents the attributes of HTML elements (like id, class).

## 2️⃣ Accessing HTML Elements
### 📌 2.1 By ID
```js
<h1 id="header">Hello, DOM!</h1>
```
```js
const header = document.getElementById("header");
console.log(header.innerHTML); // Output: Hello, DOM!
```

### 📌 2.2 By Tag Name
```js
<p>This is paragraph 1.</p>
<p>This is paragraph 2.</p>
```
```js
const paragraphs = document.getElementsByTagName("p");
console.log(paragraphs[0].innerHTML); // Output: This is paragraph 1.
```

### 📌 2.3 By Class Name
```js
<div class="box">Box 1</div>
<div class="box">Box 2</div>
```
```js
const boxes = document.getElementsByClassName("box");
console.log(boxes[1].innerHTML); // Output: Box 2
```

### 📌 2.4 By CSS Selector
```js
<p class="text">Selector Example</p>
```
```js
const textElement = document.querySelector(".text");
console.log(textElement.innerHTML); // Output: Selector Example
```

**querySelector** selects the first match.

**querySelectorAll** selects all matches and returns a NodeList.

## 3️⃣ Modifying HTML Elements
### 📌 3.1 Change Content
```js
<p id="description">Old Content</p>
```
```js
document.getElementById("description").innerHTML = "New Content";
```
Before: Old Content
After: New Content

### 📌 3.2 Change Attribute
```js
<img id="logo" src="old_logo.png" alt="Logo">
```
```js
document.getElementById("logo").setAttribute("src", "new_logo.png");
```
The src attribute of the image is changed to "new_logo.png".

### 📌 3.3 Change CSS Style
```js
<p id="styledText">Styled Text</p>
```
```js
const text = document.getElementById("styledText");
text.style.color = "red";
text.style.fontSize = "20px";
```
Before: Default text
After: Text turns red with a font size of 20px.

## 4️⃣ Creating and Removing Elements
### 📌 4.1 Create a New Element
```js
const newParagraph = document.createElement("p");
newParagraph.innerHTML = "This is a new paragraph.";
document.body.appendChild(newParagraph);
```
👉 Result: A new paragraph with the text "This is a new paragraph." is added to the end of the <body>.

### 📌 4.2 Remove an Element
```js
<div id="toBeRemoved">Remove Me!</div>
```
```js
const element = document.getElementById("toBeRemoved");
element.remove();
```
👉 Result: The <div> with the text "Remove Me!" is deleted from the DOM.

## 5️⃣ Handling Events
Events are things that happen in the browser — clicking, scrolling, typing, etc. You can use JavaScript to listen and respond to these events.
### 📌 5.1 Event Listener Example
```js
<button id="btn">Click Me!</button>
```
```js
const button = document.getElementById("btn");
button.addEventListener("click", () => {
  alert("Button was clicked!");
});
```
👉 Result: When you click the button, an alert with the message "Button was clicked!" pops up.

### 📌 5.2 Common Event Types
| Event Type | Description                         |
|-------------|-------------------------------------|
| **click**   | When the user clicks an element     |
| **mouseover** | When the user hovers over an element |
| **mouseout** | When the user moves the mouse away |
| **keydown**  | When a key is pressed               |
| **submit**   | When a form is submitted            |

## 6️⃣ Traversing the DOM
You can navigate the DOM tree using properties:

- .parentElement → Get the parent element.
- .children → Get all child elements.
- .firstElementChild → Get the first child element.
- .lastElementChild → Get the last child element.
- .nextElementSibling → Get the next sibling element.
- .previousElementSibling → Get the previous sibling element.
Example:
```js
<ul id="list">
  <li>Item 1</li>
  <li id="middle-item">Item 2</li>
  <li>Item 3</li>
</ul>
```
```js
const middleItem = document.getElementById("middle-item");
console.log(middleItem.nextElementSibling.innerHTML); // Output: Item 3
```


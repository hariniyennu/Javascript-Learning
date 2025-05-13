# 🌟 JavaScript DOM (Document Object Model) 
The Document Object Model (DOM) is a programming interface that represents an HTML or XML document as a structured tree of objects. It allows JavaScript to manipulate, access, and modify both the structure and the content of a webpage.

## Understanding the DOM Tree Structure
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

## Accessing HTML Elements
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

## DOM Document
The document object is the root of the DOM and gives you access to the whole page.

It represents your HTML document and provides methods to interact with the content.
### 📌 Common Properties:

| Property        | Description                          |
|------------------|-------------------------------------|
| **document.title** | Gets or sets the title of the page. |
| **document.body**  | Accesses the `<body>` element.     |
| **document.URL**   | Gets the current URL of the page.  |
| **document.head**  | Accesses the `<head>` section.     |

```js
console.log(document.title);       // Logs the title of the document
console.log(document.URL);         // Logs the URL of the page
console.log(document.body.innerHTML); // Logs the inner HTML of the body
```

## DOM CSS
The DOM CSS allows you to manipulate the styling of HTML elements using JavaScript.
You can use the .style property to change CSS properties directly.

### 📝 Common CSS Properties in DOM:

| **Property**             | **Description**                              |
|---------------------------|---------------------------------------------|
| `style.backgroundColor`  | Changes the background color.               |
| `style.color`            | Changes the text color.                     |
| `style.fontSize`         | Changes the font size.                      |
| `style.margin`           | Changes the margin space.                   |
| `style.display`          | Toggles visibility (e.g., `none`, `block`). |

```js
<p id="text">Hello, DOM CSS!</p>
<button onclick="changeStyle()">Change Style</button>
```
```js
function changeStyle() {
  const text = document.getElementById("text");
  text.style.color = "white";
  text.style.backgroundColor = "black";
  text.style.fontSize = "24px";
  text.style.padding = "10px";
}
```
Explanation:
When the button is clicked, the paragraph's style is modified:

Text color becomes white

Background color becomes black

Font size increases

Padding is added

## Modifying HTML Elements
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

## Creating and Removing Elements
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

## Handling Events
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

## Traversing the DOM
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

## DOM Animations
📝 Common Techniques:
Using setInterval() to update position or style.

Using requestAnimationFrame() for smoother animations.

```js
<div id="box" style="width:50px; height:50px; background:red; position:absolute;"></div>
<button onclick="startAnimation()">Move Right</button>
```
```js
function startAnimation() {
  const box = document.getElementById("box");
  let position = 0;
  const id = setInterval(frame, 5);

  function frame() {
    if (position == 350) {
      clearInterval(id);
    } else {
      position++;
      box.style.left = position + 'px';
    }
  }
}
```
Explanation:

A red box moves from left to right when the button is clicked.

setInterval() is used to update its position every 5ms.

## DOM Nodes
In the DOM, everything is a node:
- The entire document is a document node.
- Each HTML element is an element node.
- Text inside elements is a text node.

```js
<p id="demo">Hello, Node!</p>
```
```js
const node = document.getElementById("demo");
console.log(node.nodeType); // Output: 1 (Element Node)
```
Explanation:

Node Type 1 represents an Element Node.

Node Type 3 represents a Text Node.

## DOM Collections
Collections are array-like objects that hold a list of elements.

They are live, meaning they automatically update when the DOM changes.

```js
<div class="item">Item 1</div>
<div class="item">Item 2</div>
<div class="item">Item 3</div>
```
```js
const items = document.getElementsByClassName("item");
console.log(items.length); // Output: 3
```
Explanation:

getElementsByClassName() fetches all elements with the class .item.

It's not an array, but it can be looped through.

##  DOM Node Lists
Node Lists are collections of document nodes.

They can be static or live based on how they're fetched.

### 📝 Difference Between NodeList and HTMLCollection:

| **Feature**         | **NodeList**         | **HTMLCollection**          |
|----------------------|-----------------------|-----------------------------|
| **Live Update**     | ❌ (Static)           | ✅ (Live)                   |
| **Access Method**   | `querySelectorAll`   | `getElementsByTagName`      |

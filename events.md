# 🌟 JavaScript Events
JavaScript events are actions or occurrences that happen in the browser window. When an event occurs, you can execute a JavaScript function to respond to it.
For example, clicking a button, pressing a key, or loading a page.

## 🔹 Types of Events
| Event Type          | Description                              | Example                                      |
| ------------------- | ---------------------------------------- | -------------------------------------------- |
| **Mouse Events**    | Triggered by mouse actions               | `click`, `dblclick`, `mouseover`, `mouseout` |
| **Keyboard Events** | Triggered by keyboard actions            | `keydown`, `keypress`, `keyup`               |
| **Form Events**     | Triggered by form interactions           | `submit`, `change`, `focus`, `blur`          |
| **Window Events**   | Triggered by window/browser interactions | `load`, `resize`, `scroll`, `unload`         |

## 🔹 1️⃣ Mouse Events
```js
<button onclick="onClick()">Click Me</button>
<button ondblclick="onDoubleClick()">Double Click Me</button>
<div onmouseover="onMouseOver()" onmouseout="onMouseOut()">Hover Me</div>
```
```js
function onClick() {
  alert("Button clicked!");
}

function onDoubleClick() {
  alert("Button double-clicked!");
}

function onMouseOver() {
  alert("Mouse is over the element!");
}

function onMouseOut() {
  alert("Mouse left the element!");
}
```

Explanation:

- onclick: Executes when the button is clicked.
- ondblclick: Executes on double-click.
- onmouseover: Executes when the mouse enters the element.
- onmouseout: Executes when the mouse leaves the element.

## 🔹 2️⃣ Keyboard Events
```js
<input type="text" onkeydown="keyDown()" onkeyup="keyUp()" />
```
```js
function keyDown() {
  console.log("Key is pressed down.");
}

function keyUp() {
  console.log("Key is released.");
}
```
Explanation:

- onkeydown: Executes when a key is pressed down.
- onkeyup: Executes when the key is released.

## 🔹 3️⃣ Form Events
```js
<form onsubmit="formSubmit(event)">
  <input type="text" id="name" placeholder="Enter Name" required />
  <button type="submit">Submit</button>
</form>
```
```js
function formSubmit(event) {
  event.preventDefault();  // Prevents the form from refreshing the page
  const name = document.getElementById("name").value;
  alert(`Hello, ${name}`);
}
```
Explanation:

- onsubmit: Executes when the form is submitted.
- event.preventDefault(): Prevents the default behavior (form refresh).

## 🔹 4️⃣ Window Events
```js
<button onclick="windowResize()">Resize Window</button>
```
```js
function windowResize() {
  window.addEventListener("resize", () => {
    console.log("Window resized!");
  });
}
```
Explanation:

window.addEventListener("resize"): Listens for window size changes.

# 🌟 JavaScript Event Listeners
Instead of using HTML attributes like onclick, you can attach event listeners to elements directly in JavaScript.
This keeps JavaScript separate from HTML, which is a good practice.

```js
<button id="btn">Click Me</button>
```
```js
const button = document.getElementById("btn");

button.addEventListener("click", () => {
  alert("Button was clicked through Event Listener!");
});
```
Explanation:

- addEventListener attaches an event handler to the element.
- The event handler is triggered when the event occurs.

## 🔹 Removing Event Listeners
You can also remove event listeners using removeEventListener.

```js
<button id="stopButton">Stop Click Event</button>
```
```js
function handleClick() {
  alert("Button Clicked!");
}

const button = document.getElementById("stopButton");
button.addEventListener("click", handleClick);

// To remove the listener:
button.removeEventListener("click", handleClick);
```
Explanation:

- The handleClick function is called when the button is clicked.
- When removeEventListener is called, it stops listening for the click event.

# ✨ Event Bubbling and Event Capturing
When an event happens in the DOM, it does two things:

- Capturing Phase: Event moves from the root to the target element.
- Bubbling Phase: Event moves from the target element back to the root.

By default, events are handled during the bubbling phase.

```js
<div id="parent">
  <button id="child">Click Me</button>
</div>
```
```js
document.getElementById("parent").addEventListener(
  "click",
  () => {
    alert("Parent Div Clicked");
  },
  true // Setting to true makes it run in the Capturing Phase
);

document.getElementById("child").addEventListener("click", () => {
  alert("Child Button Clicked");
});
```
Explanation:

- When the button is clicked, by default, "Child Button Clicked" shows first (bubbling phase).
- If the third parameter of addEventListener is true, it triggers during the capturing phase.

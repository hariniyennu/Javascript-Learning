## 1️⃣ What is a String?
A string is a sequence of characters used to represent text.

Strings are written inside single (' '), double (" "), or backticks ( ).
```js
let singleQuote = 'Hello, World!';
let doubleQuote = "Hello, World!";
let backtick = `Hello, World!`;
```
## 2️⃣ String Length
Use the .length property to find the length of a string.

```js
let text = "JavaScript";
console.log(text.length); // Output: 10
```
## 3️⃣ Escape Characters
Use a backslash \ to escape special characters inside strings.

| Character | Description     |
|------------|-----------------|
| `\'`      | Single quote    |
| `\"`      | Double quote    |
| `\\`      | Backslash       |
| `\n`      | New line        |
| `\t`      | Tab             |

```js
let text = "He said, \"JavaScript is awesome!\"";
console.log(text);
```

## 4️⃣ JavaScript String Methods

| Method                   | Description                                      | Example                                                      |
|---------------------------|--------------------------------------------------|-------------------------------------------------------------|
| `toUpperCase()`          | Converts string to uppercase                     | `"hello".toUpperCase(); // "HELLO"`                         |
| `toLowerCase()`          | Converts string to lowercase                     | `"WORLD".toLowerCase(); // "world"`                         |
| `trim()`                 | Removes whitespace from both ends               | `" hello ".trim(); // "hello"`                              |
| `charAt(index)`          | Returns the character at the specified index     | `"JavaScript".charAt(4); // "S"`                            |
| `indexOf(substring)`     | Returns the index of the first occurrence        | `"Hello World".indexOf("World"); // 6`                      |
| `lastIndexOf()`          | Returns the last occurrence of a substring       | `"Hello World".lastIndexOf("o"); // 7`                      |
| `includes(substring)`    | Checks if string contains the specified substring | `"Hello".includes("ell"); // true`                          |
| `startsWith()`           | Checks if string starts with the specified text  | `"JavaScript".startsWith("Java"); // true`                  |
| `endsWith()`             | Checks if string ends with the specified text    | `"JavaScript".endsWith("Script"); // true`                  |
| `slice(start, end)`      | Extracts part of a string                        | `"Hello World".slice(0, 5); // "Hello"`                     |
| `substring(start, end)`  | Extracts characters between two indices          | `"Hello World".substring(0, 5); // "Hello"`                 |
| `replace(search, replace)` | Replaces the first occurrence of text          | `"Hello World".replace("World", "JS"); // "Hello JS"`       |
| `split(separator)`       | Splits the string into an array                  | `"Hello World".split(" "); // ["Hello", "World"]`           |
| `concat()`               | Joins two or more strings                        | `"Hello".concat(" ", "World"); // "Hello World"`            |

## 5️⃣ Template Literals (Template Strings)
Template literals allow embedded expressions and multi-line strings.

Use backticks (`) instead of quotes.

Interpolation with ${expression}.

```js
let name = "Harini";
let greeting = `Hello, ${name}!`;
console.log(greeting); // Output: Hello, Harini!
```

Multi-line strings:

```js
let message = `This is line 1.
This is line 2.`;
console.log(message);
```

## **String Searching Methods**
JavaScript provides powerful methods to **search for substrings** inside strings.

| Method                    | Description                                    | Example                                                      |
|---------------------------|------------------------------------------------|-------------------------------------------------------------|
| `indexOf()`              | Returns the **first occurrence** of a substring | `"Hello World".indexOf("World"); // 6`                      |
| `lastIndexOf()`          | Returns the **last occurrence** of a substring  | `"Hello World".lastIndexOf("o"); // 7`                      |
| `includes()`             | Checks if a string contains a specified substring | `"Hello".includes("ell"); // true`                          |
| `startsWith()`           | Checks if a string **starts** with the specified text | `"JavaScript".startsWith("Java"); // true`             |
| `endsWith()`             | Checks if a string **ends** with the specified text | `"JavaScript".endsWith("Script"); // true`              |

---

## 🔎 **2. Pattern Matching with Regular Expressions (RegEx)**
- **RegEx** (Regular Expressions) are patterns used to match character combinations in strings.
- Defined with **slashes (`/pattern/`)** or using `RegExp` constructor.

```javascript
// Example: Check if a string contains digits
let text = "My age is 21";
let pattern = /\d+/;  // \d matches any digit
console.log(pattern.test(text)); // Output: true
```

## Common RegEx Patterns

| Pattern   | Description                                  |
|------------|--------------------------------------------|
| `.`        | Any character except newline               |
| `\d`       | Any digit (0-9)                            |
| `\D`       | Any non-digit                              |
| `\w`       | Any alphanumeric character (a-z, 0-9)      |
| `\W`       | Any non-alphanumeric character             |
| `\s`       | Any whitespace character                   |
| `\S`       | Any non-whitespace character               |
| `^`        | Start of a string                          |
| `$`        | End of a string                            |
| `+`        | One or more occurrences                    |
| `*`        | Zero or more occurrences                   |
| `?`        | Zero or one occurrence (optional)          |

---

## Useful String Methods with RegEx

| Method                | Description                                          | Example                                                                 |
|------------------------|------------------------------------------------------|-------------------------------------------------------------------------|
| `match()`             | Matches a string against a RegEx                    | `"Hello 123".match(/\d+/); // ["123"]`                                  |
| `search()`            | Searches for a RegEx match and returns the index    | `"Hello 123".search(/\d+/); // 6`                                       |
| `replace()`           | Replaces matched substring with new text            | `"Hello World".replace(/World/, "JavaScript"); // "Hello JavaScript"`    |
| `split()`             | Splits the string into an array based on the pattern | `"Hello-World".split(/-/); // ["Hello", "World"]`                        |

## 🔒 3. String Immutability
Strings are immutable in JavaScript.

This means you cannot change individual characters directly.

Any modification creates a new string instead.

```js
let greeting = "Hello";
greeting[0] = "J"; // This won't change the string
console.log(greeting); // Output: "Hello"

greeting = "Jello"; // This creates a new string
console.log(greeting); // Output: "Jello"
```

## 💡 4. Template Literals for Easier String Manipulation
Template literals allow multi-line strings and interpolation.

Use backticks (`) for template strings.

```js
let name = "Harini";
let age = 21;
let introduction = `My name is ${name} and I am ${age} years old.`;
console.log(introduction); // Output: My name is Harini and I am 21 years old.
```



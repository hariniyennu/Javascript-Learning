# Types of JavaScript Operators

There are different types of JavaScript operators:

- Arithmetic Operators
- Assignment Operators
- Comparison Operators
- String Operators
- Logical Operators
- Bitwise Operators
- Ternary Operators
- Type Operators

---

## 1. JavaScript Arithmetic Operators

Arithmetic Operators are used to perform arithmetic on numbers:

```js
let a = 3;
let x = (100 + 50) * a;
```

| Operator | Description               |
|----------|---------------------------|
| `+`      | Addition                  |
| `-`      | Subtraction               |
| `*`      | Multiplication            |
| `**`     | Exponentiation (ES2016)   |
| `/`      | Division                  |
| `%`      | Modulus (Division Remainder) |
| `++`     | Increment                 |
| `--`     | Decrement                 |

## 2. JavaScript Assignment Operators

Assignment operators assign values to JavaScript variables:

```js
let x = 10;
x += 5;
```

| Operator | Example   | Same As     |
|----------|-----------|-------------|
| `=`      | `x = y`   | `x = y`     |
| `+=`     | `x += y`  | `x = x + y` |
| `-=`     | `x -= y`  | `x = x - y` |
| `*=`     | `x *= y`  | `x = x * y` |
| `/=`     | `x /= y`  | `x = x / y` |
| `%=`     | `x %= y`  | `x = x % y` |
| `**=`    | `x **= y` | `x = x ** y`|

## 3.JavaScript Comparison Operators

| Operator | Description                          |
|----------|--------------------------------------|
| `==`     | equal to                             |
| `===`    | equal value and equal type          |
| `!=`     | not equal                            |
| `!==`    | not equal value or not equal type   |
| `>`      | greater than                         |
| `<`      | less than                            |
| `>=`     | greater than or equal to             |
| `<=`     | less than or equal to                |
| `?`      | ternary operator                     |

## 4. JavaScript String Comparison

All the comparison operators above can also be used on strings:

```js
let text1 = "A";
let text2 = "B";
let result = text1 < text2;
```
***Note that strings are compared alphabetically***

### JavaScript String Addition

The + can also be used to add (concatenate) strings:

```js
let text1 = "John";
let text2 = "Doe";
let text3 = text1 + " " + text2;
```

The += assignment operator can also be used to add (concatenate) strings:

```js
let text1 = "What a very ";
text1 += "nice day";
```
The result of `text1` will be:  
**What a very nice day**

***Note
When used on strings, the + operator is called the concatenation operator.***

### Adding Strings and Numbers

Adding two numbers, will return the sum as a number like 5 + 5 = 10.
Adding a number and a string, will return the sum as a concatenated string like 5 + "5" = "55".

```js
let x = 5 + 5;
let y = "5" + 5;
let z = "Hello" + 5;
```
The result of x, y, and z will be:
- 10
- 55
- Hello5

***Note
If you add a number and a string, the result will be a string!***

## 5.JavaScript Logical Operators

| Operator | Description   |
|----------|---------------|
| &&       | logical and   |
| ||       | logical or    |
| !        | logical not   |

## 6.JavaScript Type Operators

| Operator    | Description                                         |
|-------------|-----------------------------------------------------|
| typeof      | Returns the type of a variable                      |
| instanceof  | Returns true if an object is an instance of an object type |

## 7. JavaScript Bitwise Operators

Bit operators work on 32 bits numbers.
Any numeric operand in the operation is converted into a 32 bit number. The result is converted back to a JavaScript number.

| Operator | Description           | Example    | Same as   | Result | Decimal |
|----------|-----------------------|------------|-----------|--------|---------|
| &        | AND                   | 5 & 1      | 0101 & 0001 | 0001   | 1       |
| \|       | OR                    | 5 \| 1     | 0101 \| 0001 | 0101   | 5       |
| ~        | NOT                   | ~5         | ~0101     | 1010   | 10      |
| ^        | XOR                   | 5 ^ 1      | 0101 ^ 0001 | 0100   | 4       |
| <<       | Left Shift            | 5 << 1     | 0101 << 1 | 1010   | 10      |
| >>       | Right Shift           | 5 >> 1     | 0101 >> 1 | 0010   | 2       |
| >>>      | Unsigned Right Shift  | 5 >>> 1    | 0101 >>> 1| 0010   | 2       |


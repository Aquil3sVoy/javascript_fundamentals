# 1. **JavaScript Fundamentals:**

Before diving into Node.js, ensure you have a strong grasp of core JavaScript concepts such as variables, data types, loops, conditional statements, functions, and objects. These fundamentals are essential for writing effective Node.js code.

## 1.1 **Variables and Data Types:**

- Declaring variables using **`var`**, **`let`**, and **`const`**.

`var`, `let`, and `const` are all used for variable declaration in JavaScript, but they have different **scoping rules** and **behaviors**. Here's a breakdown of their differences:

### **1.1.2 var:**

- `var` is the oldest way to declare variables in JavaScript.
- Variables declared with `var` are **function-scoped or globally-scoped**, but they are not **block-scoped**.
- This means that `var` variables are accessible within the entire function they are declared in, regardless of blocks.
- If `var` is declared in a block (such as an if statement), it is still accessible outside that block.
- **Variables declared with `var` are also hoisted, which means they are moved to the top of their function or global scope during the compilation phase.**

Example:

```jsx
function example() {
  if (true) {
    var x = 10
  }
  console.log(x) // Outputs 10, even though x was declared inside the if block
}
```

### 1.1.**2. let:**

- `let` was introduced in ES6 (ECMAScript 2015) and provides block-scoping.
- Variables declared with `let` are block-scoped, **which means they are only accessible within the block they are declared in.**
- Unlike `var`, `let` variables are not hoisted to the top of their scope, so they are not accessible before their declaration.
- You can re-declare a value using the "let" keyword.
- You can't re-declare a variable with `let` in the same scope.

Example:

```jsx
function example() {
  if (true) {
    let y = 20
  }
  console.log(y) // Throws an error, y is not defined in this scope
}
```

### 1.1.**3. const:**

- `const` is also introduced in ES6.
- Like `let`, `const` variables are block-scoped and not hoisted.
- However, `const` variables cannot be reassigned once they are assigned a value. The value they hold is constant.
- When used with objects or arrays, `const` means the reference to the object or array is constant, but the internal properties can still be modified.

Example:

```jsx
const PI = 3.14159
PI = 3.14 // Throws an error, reassignment is not allowed

const person = { name: 'John' }
person.name = 'Alice' // This is allowed and changes the value of the property
```

**General Rule:**

- **Use `const` when you want a value to remain constant throughout its scope.**
- **Use `let` when you need to reassign the variable's value.**
- **Avoid using `var` in modern JavaScript as it has scoping issues that can lead to unexpected behavior. Instead, prefer `let` and `const`.**

**In modern JavaScript development, it's recommended to use `const` by default and only use `let` when you need to reassign a variable's value. This helps prevent accidental variable reassignments and results in more predictable code behavior.**

- Primitive data types: number, string, boolean, null, undefined.
- Complex data types: object, array, function.

## **2. Operators and Expressions:**

### 2.1.1 **Arithmetic Operators:**

- **`+`** (addition)
- - (subtraction)
- - (multiplication)
- **`/`** (division)
- **`%`** (modulus, remainder)

```jsx
let result = 5 + 3 * 2 // result will be 11
```

### 2.1.2 **Assignment Operators:**

Assigns a value to a variable **`=`**(assignment)

```jsx
let x = 10
```

**`+=`**, -=, \*=, **`/=`**, **`%=`** (compound assignment)

```jsx
let x = 10
let y = x + 5 // y will be 15
```

#### 2.1.2.1 Addition Assignment (`+=`)

```jsx
let x = 5
x += 3 // Equivalent to: x = x + 3;
console.log(x) // Outputs 8
```

#### 2.1.2.2 **Subtraction Assignment(`-=`)**

```jsx
let y = 10
y -= 4 // Equivalent to: y = y - 4;
console.log(y) // Outputs 6
```

#### 2.1.2.3 **Multiplication Assignment(`*=`)**

```jsx
let z = 7
z *= 2 // Equivalent to: z = z * 2;
console.log(z) // Outputs 14
```

#### 2.1.2.4 **Division Assignment (`/=`)**

```jsx
let w = 20
w /= 5 // Equivalent to: w = w / 5;
console.log(w) // Outputs 4
```

#### 2.1.2.5 **Modulus Assignment(`%=`)**

```jsx
let num = 17
num %= 5 // Equivalent to: num = num % 5;
console.log(num) // Outputs 2
```

#### 2.1.2.6 **Exponentiation Assignment(`**=`)\*\*

```jsx
let base = 2
base **= 3 // Equivalent to: base = base ** 3;
console.log(base) // Outputs 8
```

### 2.2.7 **Bitwise Operators Assignment(`&=`, `|=`, `^=`, `<<=`, `>>=`, `>>>=`)**

```jsx
let bitmask = 5
bitmask &= 3 // Equivalent to: bitmask = bitmask & 3;
console.log(bitmask) // Outputs 1
```

## 2.3 **Comparison Operators:**

- **`==`** (loose equality)
- **`===`** (strict equality)
- **`!=`** (loose inequality)
- **`!==`** (strict inequality)
- **`>`**, **`<`**, **`>=`**, **`<=`** (greater than, less than, greater than or equal to, less than or equal to)

```jsx
let a = 10
let b = 15
let isGreaterThan = a > b // isGreaterThan will be false
```

## 2.4 **Logical Operators:**

- **`&&`** (logical AND)
- **`||`** (logical OR)
- **`!`** (logical NOT)

```jsx
let isTrue = true
let isFalse = false
let isBothTrue = isTrue && isFalse // isBothTrue will be false
```

**Unary Operators:**

- **`+`** (unary plus, converts to a number)
- `-` (unary minus, negates a number)
- **`++`** (increment)
- **`-`** (decrement)
- **`typeof`** (returns the type of an operand)
- **`!`** (logical NOT, converts to a boolean value)

## 2.5 **Ternary Operator:**

- **`condition ? expr1 : expr2`** (conditional operator, returns **`expr1`** if **`condition`** is true, otherwise **`expr2`**)

```jsx
let age = 20
let isAdult = age >= 18 ? 'Yes' : 'No' // isAdult will be "Yes"
```

```jsx
function multiply(a, b) {
  return a * b
}
let product = multiply(3, 4) // product will be 12
```

## **3. Control Flow:**

### 3.1 **Conditional Statements**

Conditional statements allow you to execute different blocks of code based on a condition. The most common conditional statements are **`if`**, **`else if`**, and **`else`**.

```jsx
if (condition1) {
  // Code to execute if condition1 is true
} else if (condition2) {
  // Code to execute if condition2 is true
} else {
  // Code to execute if no conditions are true
}
```

### 3.2 **Switch Statement**

The. `switch` statement provides a way to perform different actions based on different conditions. It's especially useful when you have a single value and multiple possible execution paths.

```jsx
switch (value) {
  case condition1:
    // Code to execute if value matches condition1
    break
  case condition2:
    // Code to execute if value matches condition2
    break
  default:
  // Code to execute if no cases match
}
```

### 3.3 **Loops:**

Loops allow you to repeat a block of code multiple times. There are several types of loops in JavaScript:

- for loop for iterating over a range of values.

```jsx
for (initialization; condition; increment) {
  // Code to repeat
}
```

- while loop for repeated execution based on a condition.

```jsx
while (condition) {
  // Code to repeat
}
```

- do-while loop for ensuring the loop executes at least once.

```jsx
do {
  // Code to repeat
} while (condition)
```

- for...of loop (ES6+)

```jsx
for (let element of iterable) {
  // Code to execute for each element in the iterable
}
```

- for...in loop for iterating over the properties of an object.

```jsx
for (let property in object) {
  // Code to execute for each property in the object
}
```

- Break and Continue
  The `break` statement is used to exit a loop prematurely, while the continue statement is used to skip the rest of the current iteration and move to the next iteration.

```jsx
for (let i = 0; i < 10; i++) {
  if (i === 5) {
    continue // Skip the rest of the code in this iteration
  }
  if (i === 8) {
    break // Exit the loop entirely
  }
  console.log(i) // 0 1 2 3 4 6 7
}
```

## **5. Functions:**

Functions are reusable blocks of code that perform a specific task. They allow you to break your code into smaller, more manageable chunks.

### 5.1 **Function Declaration:**

You can declare a function using the `function` keyword followed by the function name, a list of parameters enclosed in parantheses, and the function body enclosed in curly braces.

```jsx
function functionName(param1, param2) {
  // Code to execute
}
```

### 5.2 **Function Expression:**

You can also create functions as expressions by assigning them to variables. These are known as anonymous functions.

```jsx
const functionName = function (param1, param2) {
  // Code to execute
}
```

### 5.3 **Arrow Function:**

Arrow functions are a more concise syntax for writing function expressions. They use the `=>` syntax, which is where the name "arrow function" comes from.

```jsx
const functionName = (param1, param2) => {
  // Code to execute
}
```

### 5.4 **Function Invocation:**

To execute a function, you need to invoke it. You can invoke a function by using the function name followed by a list of arguments enclosed in parantheses.

```jsx
functionName(arg1, arg2)
```

### 5.5 **Function Parameters and Arguments:**

Function parameters are the names listed in the function definition. Function arguments are the real values passed to the function.

```jsx
function functionName(param1, param2) {
  // Code to execute
}
functionName(arg1, arg2)
```

### 5.6 **Return Values:**

Functions can optionally return a value using the `return` keyword. If no return value is specified, the function will return `undefined`.

```jsx
function functionName() {
  return value
}
```

### 5.7 **Immediately Invoked Function Expression (IIFE):**

An IIFE is a function that is executed immediately after it is created. It is wrapped inside a grouping operator `()` and followed by a set of parantheses `()` which indicates that the function should be invoked immediately.

```jsx
;(function () {
  // Code to execute
})()
```

### 5.8 **Callback Functions:**

A callback function is a function that is passed to another function as an argument and is executed after some operation has been completed.

```jsx
function greeting(name) {
  alert('Hello ' + name)
}
function processUserInput(callback) {
  var name = prompt('Please enter your name.')
  callback(name)
}
processUserInput(greeting)
```

### 5.9 **Higher-Order Functions:**

Higher-order functions are functions that take other functions as arguments or return functions as their results.

```jsx
function add(x, y) {
  return x + y
}
function subtract(x, y) {
  return x - y
}
function multiply(x, y) {
  return x * y
}
function divide(x, y) {
  return x / y
}
function doMath(operation, x, y) {
  return operation(x, y)
}
var x = 2
var y = 4

doMath(add, x, y) // 6
doMath(subtract, x, y) // -2
doMath(multiply, x, y) // 8
doMath(divide, x, y) // 0.5
```

### 5.10 ** Default Parameters:**

You can provide default values for parameters, wich will be used if the corresponding argument is not provided when the function is called.

```jsx
function power(base, exponent = 2) {
  return Math.pow(base, exponent)
}
let squared = power(5) // squared will be 25
let cubed = power(3, 3) // cubed will be 27
```

### 5.11 **Rest Parameters:**

Rest parameters allow you to pass an indefinite number of arguments to a function as an array.

```jsx
function sum(...numbers) {
  let total = 0
  for (let number of numbers) {
    total += number
  }
  return total
}
let sum1 = sum(1, 2, 3) // sum1 will be 6

let sum2 = sum(1, 2, 3, 4, 5) // sum2 will be 15
```

### 5.12 **Spread Operator:**

The spread operator allows you to expand an array into individual elements. It can be used to expand the elements of an array in places where zero or more arguments are expected.

```jsx
let numbers = [1, 2, 3, 4, 5]
let sum = add(...numbers) // sum will be 15
```

### 5.13 **Function Scope:**

Variables declared inside a function are only accessible inside that function. This is known as function scope.

```jsx
function example() {
  let x = 10
  console.log(x) // Outputs 10
}
console.log(x) // Throws an error, x is not defined outside the function
```

### 5.14 **Block Scope:**

Variables declared inside a block are only accessible inside that block. This is known as block scope.

```jsx
if (true) {
  let x = 10
  console.log(x) // Outputs 10
}
console.log(x) // Throws an error, x is not defined outside the block
```

### 5.15 **Lexical Scope:**

Lexical scope means that a variable defined outside a function can be accessible inside another function defined after the variable declaration. However, the reverse is not true.

```jsx
let x = 10
function example() {
  console.log(x) // Outputs 10
}
example()
```

### 5.16 **Hoisting:**

Hoisting is a JavaScript mechanism where variables and function declarations are moved to the top of their scope before code execution.

```jsx
console.log(x) // Outputs undefined
var x = 10
```

### 5.17 **Closures:**

A closure is the combination of a function and the lexical environment within which that function was declared. This environment consists of any local variables that were in-scope at the time the closure was created.

```jsx
function outer() {
  let x = 10
  function inner() {
    console.log(x) // inner can access x because it's in the parent scope
  }
  return inner
}
let foo = outer()
foo() // Outputs 10
```

## **6. Objects and Classes:**

### 6.1 **Creating Objects:**

Objects are one of the most important data types in JavaScript. They allow you to store keyed collections of values.

```jsx
let person = {
  name: 'John',
  age: 20,
  hobbies: ['reading', 'games', 'coding'],
}
```

### 6.2 **Accessing Object Properties:**

You can access object properties using dot notation or bracket notation.

```jsx
let person = {
  name: 'John',
  age: 20,
  hobbies: ['reading', 'games', 'coding'],
}
console.log(person.name) // Outputs "John"
console.log(person['age']) // Outputs 20
```

### 6.3 **Adding and Modifying Properties:**

You can add new properties to an object by simply assigning a value to a new key.

```jsx
let person = {
  name: 'John',
  age: 20,
  hobbies: ['reading', 'games', 'coding'],
}
person.height = 180
person['weight'] = 70
console.log(person.height) // Outputs 180
console.log(person['weight']) // Outputs 70
```

### 6.4 **Deleting Properties:**

You can delete a property from an object using the `delete` keyword.

```jsx
let person = {
  name: 'John',
  age: 20,
  hobbies: ['reading', 'games', 'coding'],
}
delete person.age
console.log(person.age) // Outputs undefined
```

### 6.5 **Object Methods:**

Objects can also have methods. Methods are actions that can be performed on objects.

```jsx
let person = {
  name: 'John',
  age: 20,
  hobbies: ['reading', 'games', 'coding'],
  greet: function () {
    console.log('Hello!')
  },
}
person.greet() // Outputs "Hello!"
```

### 6.6 **Constructor Functions:**

Constructor functions are used to create objects in JavaScript. They are similar to classes in other programming languages.

```jsx
function Person(name, age, hobbies) {
  this.name = name
  this.age = age
  this.hobbies = hobbies
}
let person1 = new Person('John', 20, ['reading', 'games', 'coding'])
let person2 = new Person('Mary', 25, ['sports', 'music', 'movies'])
```

### 6.7 **The new Keyword:**

The `new` keyword is used to create an instance of an object that was created using a constructor function.

```jsx
function Person(name, age, hobbies) {
  this.name = name
  this.age = age
  this.hobbies = hobbies
}
let person = new Person('John', 20, ['reading', 'games', 'coding'])
```

### 6.8 **ES6 Classes:**

ES6 introduced a new syntax for creating objects using the `class` keyword.

- The `constructor` method is a special method that runs when an object is instantiated from a class. It's used to initialize object properties.
- Methods are functions defined within the class. They can be called on instances of the class and can access properties and other methods using the this keyword.
- Static methods are methods that are called on the class itself, not on instances of the class. They are typically utility functions.
- Instantiating a class without the `new` keyword will throw an error.
- Classes are not hoisted, so they must be defined before they are used.

```jsx
class Person {
  constructor(name, age, hobbies) {
    this.name = name
    this.age = age
    this.hobbies = hobbies
  }
  greet() {
    console.log(`Hello, my name is ${this.name}.`)
  }
}
let person = new Person('John', 20, ['reading', 'games', 'coding'])
```

### 6.9 **Inheritance and extends:**

Inheritance is a way to create a class as a child of another class. It allows you to reuse code from existing classes without having to duplicate it.
The `extends` keyword is used to create a subclass.
The super keyword is used to call the constructor of the parent class.

```jsx
class Person {
  constructor(name, age, hobbies) {
    this.name = name
    this.age = age
    this.hobbies = hobbies
  }
  greet() {
    console.log(`Hello, my name is ${this.name}.`)
  }
}
class Student extends Person {
  constructor(name, age, hobbies, major) {
    super(name, age, hobbies)
    this.major = major
  }
  study() {
    console.log(`${this.name} is studying ${this.major}.`)
  }
}
let student = new Student(
  'John',
  20,
  ['Reading', 'Games', 'Coding'],
  'Computer Science'
)
student.greet() // Outputs "Hello, my name is John."
student.study() // Outputs "John is studying Computer Science."
```

### 6.10 **Getters and Setters:**

Getters and setters are special methods that allow you to define how properties are accessed and set on an object.

```jsx
class Person {
  constructor(name, age) {
    this.name = name
    this.age = age
  }
  get info() {
    return `${this.name} is ${this.age} years old.`
  }
  set info(value) {
    let parts = value.split(' ')
    this.name = parts[0]
    this.age = parts[1]
  }
}
let person = new Person('John', 20)
console.log(person.info) // Outputs "John is 20 years old."
person.info = 'Mary 25'
console.log(person.info) // Outputs "Mary is 25 years old."
```

## ** 6.11 **Static Methods and Properties:\*\*

Static methods and properties are methods and properties that belong to the class itself, not to instances of the class.

```jsx
class Person {
  constructor(name, age) {
    this.name = name
    this.age = age
  }
  static adultAge = 18
  static adult(person) {
    return person.age >= Person.adultAge
  }
}
let person1 = new Person('John', 20)
console.log(Person.adult(person1)) // Outputs true
let person2 = new Person('Mary', 16)
console.log(Person.adult(person2)) // Outputs false
```

## **7. Arrays:**

Arrays are used to store multiple values in a single variable. They are created using square brackets.

```jsx
let numbers = [1, 2, 3, 4, 5]
let colors = ['red', 'green', 'blue']
```

### 7.1 **Accessing Array Elements:**

You can access array elements using bracket notation. The index starts at 0.

```jsx
let numbers = [1, 2, 3, 4, 5]
console.log(numbers[0]) // Outputs 1
console.log(numbers[1]) // Outputs 2
console.log(numbers[2]) // Outputs 3
```

### 7.2 **Modifying Array Elements:**

You can modify array elements by assigning new values to them.

```jsx
let numbers = [1, 2, 3, 4, 5]
numbers[0] = 10
numbers[1] = 20
numbers[2] = 30
console.log(numbers) // Outputs [10, 20, 30, 4, 5]
```

### 7.3 **Array Methods:**

Arrays have many useful methods that make it easy to work with arrays.

#### 7.3.1 **push()**

The `push()` method adds one or more elements to the end of an array and returns the new length of the array.

```jsx
let numbers = [1, 2, 3, 4, 5]
numbers.push(6)
console.log(numbers) // Outputs [1, 2, 3, 4, 5, 6]
```

#### 7.3.2 **pop()**

The `pop()` method removes the last element from an array and returns that element.

```jsx
let numbers = [1, 2, 3, 4, 5]
let last = numbers.pop()
console.log(numbers) // Outputs [1, 2, 3, 4]
console.log(last) // Outputs 5
```

#### 7.3.3 **shift()**

The `shift()` method removes the first element from an array and returns that element.

```jsx
let numbers = [1, 2, 3, 4, 5]
let first = numbers.shift()
console.log(numbers) // Outputs [2, 3, 4, 5]
console.log(first) // Outputs 1
```

#### 7.3.4 **unshift()**

The `unshift()` method adds one or more elements to the beginning of an array and returns the new length of the array.

```jsx
let numbers = [1, 2, 3, 4, 5]
numbers.unshift(0)
console.log(numbers) // Outputs [0, 1, 2, 3, 4, 5]
```

#### 7.3.5 **slice()**

The `slice()` method returns a shallow copy of a portion of an array into a new array object selected from begin to end (end not included). The original array will not be modified.

```jsx
let numbers = [1, 2, 3, 4, 5]
let copy = numbers.slice(1, 3)
console.log(copy) // Outputs [2, 3]
console.log(numbers) // Outputs [1, 2, 3, 4, 5]
```

#### 7.3.6 **splice()**

The `splice()` method changes the contents of an array by removing or replacing existing elements and/or adding new elements in place.

```jsx
let numbers = [1, 2, 3, 4, 5]
numbers.splice(2, 1) // Removes one element at index 2
console.log(numbers) // Outputs [1, 2, 4, 5]
numbers.splice(2, 0, 3) // Adds element 3 at index 2
console.log(numbers) // Outputs [1, 2, 3, 4, 5]
numbers.splice(2, 1, 3) // Replaces element at index 2 with 3
console.log(numbers) // Outputs [1, 2, 3, 4, 5]
```

#### 7.3.7 **concat()**

The `concat()` method is used to merge two or more arrays. This method does not change the existing arrays, but instead returns a new array.

```jsx
let numbers1 = [1, 2, 3]
let numbers2 = [4, 5, 6]
let numbers3 = numbers1.concat(numbers2)
console.log(numbers3) // Outputs [1, 2, 3, 4, 5, 6]
```

#### 7.3.8 **join()**

The `join()` method creates and returns a new string by concatenating all of the elements in an array, separated by commas or a specified separator string.

```jsx
let numbers = [1, 2, 3, 4, 5]
let string = numbers.join()
console.log(string) // Outputs "1,2,3,4,5"
```

#### 7.3.9 **indexOf()**

The `indexOf()` method returns the first index at which a given element can be found in the array, or -1 if it is not present.

```jsx
let numbers = [1, 2, 3, 4, 5]
let index = numbers.indexOf(3)
console.log(index) // Outputs 2
```

#### 7.3.10 **lastIndexOf()**

The `lastIndexOf()` method returns the last index at which a given element can be found in the array, or -1 if it is not present.

```jsx
let numbers = [1, 2, 3, 4, 5, 3]
let index = numbers.lastIndexOf(3)
console.log(index) // Outputs 5
```

#### 7.3.11 **includes()**

The `includes()` method determines whether an array includes a certain value among its entries, returning true or false as appropriate.

```jsx
let numbers = [1, 2, 3, 4, 5]
let hasThree = numbers.includes(3)
console.log(hasThree) // Outputs true
```

#### 7.3.12 **reverse()**

The `reverse()` method reverses an array in place. The first array element becomes the last, and the last array element becomes the first.

```jsx
let numbers = [1, 2, 3, 4, 5]
numbers.reverse()
console.log(numbers) // Outputs [5, 4, 3, 2, 1]
```

#### 7.3.13 **sort()**

The `sort()` method sorts the elements of an array in place and returns the sorted array. The default sort order is ascending, built upon converting the elements into strings, then comparing their sequences of UTF-16 code units values.

```jsx
let numbers = [5, 3, 2, 4, 1]
numbers.sort()
console.log(numbers) // Outputs [1, 2, 3, 4, 5]
```

#### 7.3.14 **forEach()**

The `forEach()` method executes a provided function once for each array element.

```jsx
let numbers = [1, 2, 3, 4, 5]
numbers.forEach(function (number) {
  console.log(number)
})
// Outputs 1 2 3 4 5
```

#### 7.3.15 **map()**

The `map()` method creates a new array populated with the results of calling a provided function on every element in the calling array.

```jsx
let numbers = [1, 2, 3, 4, 5]
let squares = numbers.map(function (number) {
  return number * number
})
console.log(squares) // Outputs [1, 4, 9, 16, 25]
```

#### 7.3.16 **filter()**

The `filter()` method creates a new array with all elements that pass the test implemented by the provided function.

```jsx
let numbers = [1, 2, 3, 4, 5]
let evens = numbers.filter(function (number) {
  return number % 2 === 0
})
console.log(evens) // Outputs [2, 4]
```

#### 7.3.17 **reduce()**

The `reduce()` method executes a reducer function (that you provide) on each element of the array, resulting in a single output value.

```jsx
let numbers = [1, 2, 3, 4, 5]
let sum = numbers.reduce(function (total, number) {
  return total + number
}, 0)
console.log(sum) // Outputs 15
```

#### 7.3.18 **every()**

The `every()` method tests whether all elements in the array pass the test implemented by the provided function. It returns a Boolean value.

```jsx
let numbers = [1, 2, 3, 4, 5]
let allPositive = numbers.every(function (number) {
  return number > 0
})
console.log(allPositive) // Outputs true
```

#### 7.3.19 **some()**

The `some()` method tests whether at least one element in the array passes the test implemented by the provided function. It returns a Boolean value.

```jsx
let numbers = [1, 2, 3, 4, 5]
let hasNegative = numbers.some(function (number) {
  return number < 0
})
console.log(hasNegative) // Outputs false
```

#### 7.3.20 **find()**

The `find()` method returns the value of the first element in the array that satisfies the provided testing function. Otherwise undefined is returned.

```jsx
let numbers = [1, 2, 3, 4, 5]
let even = numbers.find(function (number) {
  return number % 2 === 0
})
console.log(even) // Outputs 2
```

#### 7.3.21 **findIndex()**

The `findIndex()` method returns the index of the first element in the array that satisfies the provided testing function. Otherwise -1 is returned.

```jsx
let numbers = [1, 2, 3, 4, 5]
let evenIndex = numbers.findIndex(function (number) {
  return number % 2 === 0
})
console.log(evenIndex) // Outputs 1
```

#### 7.3.22 **flat()**

The `flat()` method creates a new array with all sub-array elements concatenated into it recursively up to the specified depth.

```jsx
let numbers = [1, [2, 3], [4, [5]]]
let flat = numbers.flat(2)
console.log(flat) // Outputs [1, 2, 3, 4, 5]
```

#### 7.3.23 **flatMap()**

The `flatMap()` method first maps each element using a mapping function, then flattens the result into a new array. It is identical to a map followed by a flat of depth 1, but slightly more efficient than calling those two methods separately.

```jsx
let numbers = [1, 2, 3, 4, 5]
let squares = numbers.flatMap(function (number) {
  return [number * number]
})
console.log(squares) // Outputs [1, 4, 9, 16, 25]
```

#### 7.3.24 **keys()**

The `keys()` method returns a new Array Iterator object that contains the keys for each index in the array.

```jsx
let numbers = [1, 2, 3, 4, 5]
let iterator = numbers.keys()
for (let key of iterator) {
  console.log(key) // Outputs 0 1 2 3 4
}
```

#### 7.3.25 **values()**

The `values()` method returns a new Array Iterator object that contains the values for each index in the array.

```jsx
let numbers = [1, 2, 3, 4, 5]
let iterator = numbers.values()
for (let value of iterator) {
  console.log(value) // Outputs 1 2 3 4 5
}
```

#### 7.3.26 **entries()**

The `entries()` method returns a new Array Iterator object that contains the key/value pairs for each index in the array.

```jsx
let numbers = [1, 2, 3, 4, 5]
let iterator = numbers.entries()
for (let entry of iterator) {
  console.log(entry) // Outputs [0, 1] [1, 2] [2, 3] [3, 4] [4, 5]
}
```

#### 7.3.27 **from()**

The `from()` method creates a new, shallow-copied Array instance from an array-like or iterable object.

```jsx
let numbers = [1, 2, 3, 4, 5]
let copy = Array.from(numbers)
console.log(copy) // Outputs [1, 2, 3, 4, 5]
```

#### 7.3.28 **isArray()**

The `isArray()` method determines whether the passed value is an Array.

```jsx
let numbers = [1, 2, 3, 4, 5]
let isNumbersArray = Array.isArray(numbers)
console.log(isNumbersArray) // Outputs true
```

#### 7.3.29 **of()**

The `of()` method creates a new Array instance with a variable number of arguments, regardless of number or type of the arguments.

```jsx
let numbers = Array.of(1, 2, 3, 4, 5)
console.log(numbers) // Outputs [1, 2, 3, 4, 5]
```

## **8. Scope and Closures:**

### 8.1 **Variable Scope:**

The scope of a variable determines where it can be accessed within your code. JavaScript has two types of scope: global scope and local scope.

- Global scope refers to variables that are accessible everywhere in your code.
- Local scope refers to variables that are only accessible in a particular block or function.

```jsx
let x = 10 // Global scope
function foo() {
  let y = 20 // Local scope
  console.log(x) // 10
  console.log(y) // 20
}
foo()
console.log(x) // 10
console.log(y) // Throws an error, y is not defined
```

### 8.2 **Variable Hoisting:**

Hoisting is a JavaScript mechanism where variables and function declarations are moved to the top of their scope before code execution.

```jsx
console.log(x) // Outputs undefined
var x = 10
```

### 8.3 **Function Scope:**

Variables declared inside a function are only accessible inside that function. This is known as function scope.

```jsx
function foo() {
  let x = 10
  console.log(x) // Outputs 10
}
console.log(x) // Throws an error, x is not defined outside the function
```

### 8.4 **Block Scope:**

Variables declared inside a block are only accessible inside that block. This is known as block scope.

```jsx
if (true) {
  let x = 10
  console.log(x) // Outputs 10
}
console.log(x) // Throws an error, x is not defined outside the block
```

### 8.5 **Lexical Scope:**

Lexical scope means that a variable defined outside a function can be accessible inside another function defined after the variable declaration. However, the reverse is not true.

```jsx
let x = 10
function foo() {
  console.log(x) // Outputs 10
}
foo()
```

### 8.6 **Closures:**

A closure is the combination of a function and the lexical environment within which that function was declared. This environment consists of any local variables that were in-scope at the time the closure was created.

```jsx
function outer() {
  let x = 10
  function inner() {
    console.log(x) // inner can access x because it's in the parent scope
  }
  return inner
}

let foo = outer()
foo() // Outputs 10
```

## **9. Asynchronous JavaScript:**

### 9.1 **The Event Loop:**

JavaScript is a single-threaded language, meaning only one task can be executed at a time. However, web browsers use multiple threads to enable asynchronous behavior.

The event loop is a mechanism that allows JavaScript to perform non-blocking operations. It consists of a call stack and a task queue.

- The call stack is a data structure that records the function calls, basically where in the program we are.
- The task queue is a list of messages to be processed. Each message has an associated function which gets called in order to handle the message.

```jsx
console.log('Hello')
setTimeout(function () {
  console.log('World')
}, 1000)
console.log('Goodbye')
// Outputs "Hello" "Goodbye" "World"
```

### 9.2 **Callback Functions:**

A callback function is a function that is passed to another function as an argument and is executed after some operation has been completed.

```jsx
function greeting(name) {
  alert('Hello ' + name)
}
function processUserInput(callback) {
  var name = prompt('Please enter your name.')
  callback(name)
}
processUserInput(greeting)
```

### 9.3 **Promises:**

A promise is an object that represents the eventual completion (or failure) of an asynchronous operation, and its resulting value. EMCA2015 introduced the Promise object natively into JavaScript. The meaning of EMCA is European Computer Manufacturers Association.

```jsx
let promise = new Promise(function (resolve, reject) {
  setTimeout(function () {
    resolve('Success!')
  }, 1000)
})
promise.then(function (value) {
  console.log(value) // Outputs "Success!"
})
```

### 9.4 **Async/Await:**

Async/await is a new way to write asynchronous code. It is built on top of promises, and is compatible with all existing promise-based APIs. EMCA2017 introduced the async and await keywords into JavaScript.

```jsx
async function foo() {
  let promise = new Promise(function (resolve, reject) {
    setTimeout(function () {
      resolve('Success!')
    }, 1000)
  })
  let result = await promise // Wait until the promise resolves
  console.log(result) // Outputs "Success!"
}
foo()
```

## **10. DOM Manipulation (in a browser environment):**

### 10.1 **Selecting Elements:**

You can select elements using the `document.querySelector()` and `document.querySelectorAll()` methods.

```jsx
let element = document.querySelector('p')
let elements = document.querySelectorAll('p')
```

### 10.2 **Modifying Elements:**

You can modify elements using the `innerHTML` and `textContent` properties.

```jsx
let element = document.querySelector('p')
element.innerHTML = 'Hello <strong>World</strong>'
element.textContent = 'Hello World'
```

### 10.3 **Modifying Attributes:**

You can modify attributes using the `setAttribute()` and `removeAttribute()` methods.

```jsx
let element = document.querySelector('img')
element.setAttribute('src', 'image.jpg')
element.removeAttribute('src')
```

### 10.4 **Modifying Styles:**

You can modify styles using the `style` property.

```jsx
let element = document.querySelector('p')
element.style.color = 'red'
element.style.backgroundColor = 'blue'
```

### 10.5 **Adding and Removing Classes:**

You can add and remove classes using the `classList` property.

```jsx
let element = document.querySelector('p')
element.classList.add('active')
element.classList.remove('active')
```

### 10.6 **Adding and Removing Elements:**

You can add and remove elements using the `appendChild()` and `removeChild()` methods.

```jsx
let element = document.querySelector('p')
let child = document.createElement('strong')
child.textContent = 'Hello World'
element.appendChild(child)
element.removeChild(child)
```

### 10.7 **Handling Events:**

You can handle events using the `addEventListener()` method.

```jsx
let button = document.querySelector('button')
button.addEventListener('click', function () {
  alert('Hello World')
})
```

## **11. Error Handling:**

### 11.1 **try-catch Blocks:**

You can use try-catch blocks to handle exceptions.

```jsx
try {
  let x = 10
  let y = x + z // z is not defined
} catch (error) {
  console.log(error) // Outputs "ReferenceError: z is not defined"
}
```

### 11.2 **Throwing Custom Errors:**

You can throw custom errors using the `throw` keyword.

```jsx
let x = 10
if (x > 5) {
  throw new Error('x should not exceed 5. The value of x was: ' + x)
}
```

## **12. Type Coercion and Equality:**

### 12.1 **Type Coercion:**

Type coercion is the automatic or implicit conversion of values from one data type to another.

```jsx
let x = 10
let y = '20'
let z = x + y // z will be '1020'
```

### 12.2 **Loose Equality:**

The loose equality operator (**`==`**) checks whether the operands are equal, performing type coercion if they are not of the same type.

```jsx
console.log(1 == '1') // Outputs true
console.log(true == '1') // Outputs true

console.log(0 == '') // Outputs true
console.log(0 == ' ') // Outputs true
console.log(0 == '\t') // Outputs true
```

### 12.3 **Strict Equality:**

The strict equality operator (**`===`**) checks whether the operands are equal, performing no type coercion.

```jsx
console.log(1 === '1') // Outputs false
console.log(true === '1') // Outputs false

console.log(0 === '') // Outputs false
console.log(0 === ' ') // Outputs false
console.log(0 === '\t') // Outputs false
```

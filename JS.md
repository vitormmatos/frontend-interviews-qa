# JavaScript

- [JavaScript](#JavaScript)
  - [What are Block Statements?](#what-are-block-statements)
  - [What is the Typeof operator?](#what-is-the-typeof-operator)
  - [What are Promises?](#what-are-promises)
  - [What are Arrow Functions? What are their advantages?](#what-are-arrow-functions-what-are-their-advantages)
  - [What is Hoisting in JS?](#what-is-hoisting-in-js)
  - [What is the usage of the Array method find?](#what-is-the-usage-of-the-array-method-find)
  - [What is the usage of the Array method map?](#what-is-the-usage-of-the-array-method-map)
  - [What is the usage of the Array method filter?](#what-is-the-usage-of-the-array-method-filter)
  - [What is a Closure?](#what-is-a-closure)
  - [What is a Higher Order Function?](#what-is-a-higher-order-function)
  - [What is the difference in usage between const and Object.freeze?](#what-is-the-difference-in-usage-between-const-and-objectfreeze)
  - [What are Webworkers?](#what-are-webworkers)

## What are **Block Statements**?

Block statements are commonly used with control flow statements i.e. while, for, if etc. The block is delimited by a pair of **curly brackets**.

**[⬆ Back to Top](##JavaScript)**

## What is the **Typeof** operator?

The typeof operator returns a string indicating the type of the unevaluated operand.

**[⬆ Back to Top](##JavaScript)**

## What are **Promises**?

Promises are a way of dealing with **asynchronous** code.

for sake of example, we're just using setTimeout. This could be any asynchronous action as well:

```JavaScript
function asyncA(callback) {
  setTimeout(callback, 100)
}
function asyncB(callback) {
  setTimeout(callback, 200)
}
function asyncC(callback) {
  setTimeout(callback, 300)
}

asyncA(function (resultA) {
  asyncB(function (resultB) {
    asyncC(function (resultC) {
      someFunction(resultA, resultB, resultC)
    })
  })
})
```

Code using promises can make asynchronous code easier to compose, and can also avoid the common issue of **“callback hell”**:

```JavaScript
function promiseA() {
  return new Promise((resolve, reject) => setTimeout(resolve, 100))
}
function promiseB() {
  return new Promise((resolve, reject) => setTimeout(resolve, 200))
}
function promiseC() {
  return new Promise((resolve, reject) => setTimeout(resolve, 300))
}

Promise.all([promiseA(), promiseB(), promiseC()]).then(([a, b, c]) => {
  someFunction(a, b, c)
})
```

**[⬆ Back to Top](##JavaScript)**

## What are **Arrow Functions**? What are their advantages?

Arrows is a new syntax for functions, which brings several benefits:

- Arrow syntax automatically binds this to the surrounding code’s context
- The syntax allows an implicit return when there is no body block, resulting in shorter and simpler code in some cases
- Last but not least, => is shorter and simpler than function, although stylistic issues are often subjective

**Implicit Return:**

**ES5** style:

```JavaScript
el.onclick = function (x, y, z) {
  return this.doSomething()
}.bind(this)
```

**ES6** style:

```JavaScript
el.onclick = (x, y, z) => this.doSomething()
```

**Map**

**ES5** style:

```JavaScript
var names = users.map(function (u) {
  return u.name
})
```

**ES6** style:

```JavaScript
var names = users.map(u => u.name)
```

**[⬆ Back to Top](##JavaScript)**

## What is **Hoisting** in JS?

Hoisting is JavaScript's default behaviour of moving all declarations to the **top of the current scope** (to the top of the current script or the current function).

Variables defined with **let** and **const** are hoisted to the top of the block, but **not initialized**.

Meaning: The block of code is aware of the variable, but it cannot be used until it has been declared.

Using a **let** variable before it is declared will result in a **ReferenceError**.

**[⬆ Back to Top](##JavaScript)**

## What is the usage of the Array method **find**?

The find() method returns the first element in the provided array that satisfies the provided testing function. If no values satisfy the testing function, undefined is returned.

```JavaScript
const array1 = [5, 12, 8, 130, 44]

const found = array1.find(element => element > 10)

console.log(found)
// expected output: 12
```

- If you need the index of the found element in the array, use findIndex().
- If you need to find the index of a value, use Array.prototype.indexOf(). (It's similar to findIndex(), but checks each element for equality with the value instead of using a testing function.)
- If you need to find if a value exists in an array, use Array.prototype.includes(). Again, it checks each element for equality with the value instead of using a testing function.
- If you need to find if any element satisfies the provided testing function, use Array.prototype.some().

**[⬆ Back to Top](##JavaScript)**

## What is the usage of the Array method **map**?

The map() method creates a new array populated with the results of calling a provided function on every element in the calling array.

```JavaScript
const array1 = [1, 4, 9, 16]

// pass a function to map
const map1 = array1.map(x => x * 2)

console.log(map1)
// expected output: Array [2, 8, 18, 32]
```

**[⬆ Back to Top](##JavaScript)**

## What is the usage of the Array method **filter**?

The filter() method creates a shallow copy of a portion of a given array, filtered down to just the elements from the given array that pass the test implemented by the provided function.

```JavaScript
const array = [-3, -2, -1, 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13]

const isPrime = num => {
  for (let i = 2; num > i; i++) {
    if (num % i == 0) {
      return false
    }
  }
  return num > 1
}

console.log(array.filter(isPrime)) // [2, 3, 5, 7, 11, 13]
```

**[⬆ Back to Top](##JavaScript)**

## What is a **Closure**?

A closure is the combination of a function bundled together with references to its surrounding state. A closure gives you access to an **outer function’s scope** from an **inner function**.

**[⬆ Back to Top](##JavaScript)**

## What is a **Higher Order Function**?

A higher order function is a function that takes a **function as an argument**, or **returns a function**

**[⬆ Back to Top](##JavaScript)**

## What is the difference in usage between **const** and **Object.freeze**?

const applies to bindings ("variables"). It creates an immutable binding, i.e. you cannot assign a new value to the binding.

Object.freeze works on values, and more specifically, object values. It makes an object immutable, i.e. you cannot change its properties.

**[⬆ Back to Top](##JavaScript)**

## What are **Webworkers**?

Web Workers are a simple means for web content to run scripts in background threads. The worker thread can perform tasks without interfering with the user interface.

Once created, a worker can send messages to the JavaScript code that created it by posting messages to an event handler specified by that code (and vice versa).

**[⬆ Back to Top](##JavaScript)**

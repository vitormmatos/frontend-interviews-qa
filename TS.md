# TypeScript

- [TypesScript](#typescript)
    - [What is Typescript?](#what-is-typescript)
    - [What is the any type?](#what-is-the-any-type)
    - [What is the unknown type?](#what-is-the-unknown-type)
    - [What is the void type?](#what-is-the-void-type)
    - [What are the null and undefined types?](#what-are-the-null-and-undefined-types)
    - [What is a non-null assertion operator?](#what-is-a-non-null-assertion-operator)
    - [What is a constructor?](#what-is-a-constructor)
    - [What is optional chaining?](#what-is-optional-chaining)
    - [What is a interface in Typescript?]()


## What is **Typescript**?

TypeScript is a strongly typed programming language created by Microsoft that builds on JavaScript.
It adds optional types, classes, async/await, and many other features, and compiles to plain JavaScript.
Angular built entirely in TypeScript and used as a primary language.

**[⬆ Back to Top](#typescript)**

## What is the **any** type?

TypeScript has a special type, any, that you can use whenever you don’t want a particular value to cause typechecking errors.

When a value is of type any, you can access any properties of it (which will in turn be of type any), call it like a function, assign it to (or from) a value of any type, or pretty much anything else that’s syntactically legal:

```typescript
let obj: any = { x: 0 }
// None of the following lines of code will throw compiler errors.
// Using `any` disables all further type checking, and it is assumed 
// you know the environment better than TypeScript.
obj.foo()
obj()
obj.bar = 100
obj = "hello"
const n: number = obj
```

**[⬆ Back to Top](#typescript)**

## What is the **unknown** type?

We may need to describe the type of variables that we do not know when we are writing an application. These values may come from dynamic content – e.g. from the user – or we may want to intentionally accept all values in our API. In these cases, we want to provide a type that tells the compiler and future readers that this variable could be anything, so we give it the **unknown** type.

```typescript
let notSure: unknown = 4
notSure = "maybe a string instead"
 
// OK, definitely a boolean
notSure = false
```

If you have a variable with an unknown type, you can narrow it to something more specific by doing **typeof** checks, comparison checks, or more advanced type guards:

```typescript
declare const maybe: unknown
// 'maybe' could be a string, object, boolean, undefined, or other types
const aNumber: number = maybe
// Type 'unknown' is not assignable to type 'number'.
 
if (maybe === true) {
  // TypeScript knows that maybe is a boolean now
  const aBoolean: boolean = maybe
  // So, it cannot be a string
  const aString: string = maybe
  // Type 'boolean' is not assignable to type 'string'.
}
 
if (typeof maybe === "string") {
  // TypeScript knows that maybe is a string
  const aString: string = maybe
  // So, it cannot be a boolean
  const aBoolean: boolean = maybe
  //  Type 'string' is not assignable to type 'boolean'.
}
```

**[⬆ Back to Top](#typescript)**

## What is the **void** type?

void is a little like the opposite of any: the absence of having any type at all. You may commonly see this as the return type of functions that do not return a value:

```typescript
function warnUser(): void {
  console.log("This is my warning message")
}
```

Declaring variables of type void is not useful because you can only assign null (only if strictNullChecks is not specified, see next section) or undefined to them:

```typescript
let unusable: void = undefined
// OK if `--strictNullChecks` is not given
unusable = null
```

**[⬆ Back to Top](#typescript)**

## What are the **null** and **undefined** types?

In TypeScript, both undefined and null actually have their types named undefined and null respectively. Much like void, they’re not extremely useful on their own:

```typescript
// Not much else we can assign to these variables!
let u: undefined = undefined
let n: null = null
```

By default null and undefined are subtypes of all other types. That means you can assign null and undefined to something like number.

However, when using the strictNullChecks flag, null and undefined are only assignable to unknown, any and their respective types (the one exception being that undefined is also assignable to void). This helps avoid many common errors. In cases where you want to pass in either a string or null or undefined, you can use the union type string | null | undefined.

**[⬆ Back to Top](#typescript)**

## What is a **non-null assertion operator**?

A new ! post-fix expression operator may be used to assert that its operand is non-null and non-undefined in contexts where the type checker is unable to conclude that fact. Specifically, the operation x! produces a value of the type of x with null and undefined excluded. Similar to type assertions of the forms <T>x and x as T, the ! non-null assertion operator is simply removed in the emitted JavaScript code

```typescript
// Compiled with --strictNullChecks
function validateEntity(e?: Entity) {
  // Throw exception if e is null or invalid entity
}
function processEntity(e?: Entity) {
  validateEntity(e)
  let s = e!.name // Assert that e is non-null and access name
}
```

**[⬆ Back to Top](#typescript)**

## What is a **constructor**?

A constructor is a special method which will be called whenever we create new objects. And generally used of initializing the class members. It is a feature of the class(typescript) itself, an object-oriented design concept not Angular.

A constructor example in Angular:

```typescript
class Square {
  constructor(private height: number, private width: number) {}

  calculateArea = () => this.height * this.width
}
```

The any type is useful when you don’t want to write out a long type just to convince TypeScript that a particular line of code is okay.

In the example from above, the constructor will be automatically invoked by JavaScript engine when we create a new object.

**[⬆ Back to Top](#typescript)**

## What is **optional chaining**?

Optional chaining allows you to access properties and call methods on them in a chain-like fashion.

TypeScript immediately stops running some expression if it runs into a ‘null’ or ‘undefined’ value and returns ‘undefined’ for the entire expression chain.

Without optional chaining:
```typescript
let x = foo === null || foo === undefined ? undefined : foo.bar.baz()
```

With optional chaining:
```typescript
let x = foo?.bar.baz()
```

**[⬆ Back to Top](#typescript)**

## What is a **interface** in Typescript?

Interface is a structure that defines the contract in your application. It defines the syntax for classes to follow. Classes that are derived from an interface must follow the structure provided by their interface.

The TypeScript compiler does not convert interface to JavaScript. It uses interface for type checking. This is also known as "duck typing" or "structural subtyping".

An interface is defined with the keyword interface and it can include properties and method declarations using a function or an arrow function.

```typescript
interface Employee {
    empCode: number
    empName: string
    getSalary: (number) => number // arrow function
    getManagerName(number): string 
}
```

Interfaces can extend one or more interfaces. This makes writing interfaces flexible and reusable.
```typescript
interface Person {
    name: string
    gender: string
}

interface Employee extends Person {
    empCode: number
}

let empObj: Employee = {
    empCode:1,
    name:"Bill",
    gender:"Male"
}
```

Interfaces can be implemented with a Class.
The Class implementing the interface needs to strictly conform to the structure of the interface.

```typescript
interface Employee {
    empCode: number
    name: string
    getSalary:(empCode: number) => number
}

class Employee implements Employee { 
    empCode: number
    name: string

    constructor(code: number, name: string) { 
        this.empCode = code
        this.name = name
    }

    getSalary(empCode: number): number { 
        return 20000
    }
}

let emp = new Employee(1, "Steve")
```

**[⬆ Back to Top](#typescript)**

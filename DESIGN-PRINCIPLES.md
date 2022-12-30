# Design Principles

- [Design Principles](#design-principles)
  - [What is Dependency Injection?](#what-is-dependency-injection)
  - [What are the 5 SOLID principles?](#what-are-the-5-solid-principles)
    - [**Single-Responsiblity Principle**](#single-responsiblity-principle)
    - [**Open-Closed Principle**](#open-closed-principle)
    - [**Liskov-Substitution Principle**](#liskov-substitution-principle)
    - [**Interface Segregation Principle**](#interface-segregation-principle)
    - [**Dependency Inversion Principle**](#dependency-inversion-principle)

## What is Dependency Injection?

Dependency injection is a programming technique that makes a class independent of its dependencies. It achieves that by decoupling the usage of an object from its creation.

**[⬆ Back to Top](#table-of-contents)**

## What are the 5 SOLID principles?

SOLID is an acronym for the first five object-oriented design (OOD) principles by Robert C. Martin (also known as Uncle Bob).

These principles establish practices that lend to developing software with considerations for maintaining and extending as the project grows. Adopting these practices can also contribute to avoiding code smells, refactoring code, and Agile or Adaptive software development.

**[⬆ Back to Top](#table-of-contents)**

## **Single-Responsiblity Principle**

```quote
A class should have one and only one reason to change.
```

Meaning that a class should have only one job.

**[⬆ Back to Top](#table-of-contents)**

## **Open-Closed Principle**

Intially written about by Bertrand Meyer in the 1980s, Uncle Bob calls this the "most important principle of object-oriented design".

Generally, this principle is all about writing your code in such a way so that when you need to add new functionality, it shouldn't require changing the existing code.

To do this, we write **interfaces** and **abstract classes** in order to dictate the higher-level policy that needs to be implemented, and then we implement that policy using concrete classes.

**[⬆ Back to Top](#table-of-contents)**

## **Liskov-Substitution Principle**

The Liskov Substitution principle was introduced by Barbara Liskov in her conference keynote “Data abstraction” in 1987.

The principle defines that objects of a superclass shall be replaceable with objects of its subclasses without breaking the application. That requires the objects of your subclasses to behave in the same way as the objects of your superclass.

In Uncle Bob's "Clean Architecture", he says:

```quote
"To build software systems from interchangeable parts, those parts must adhere to a contract that allows those parts to be substituted one for another."
```

**[⬆ Back to Top](#table-of-contents)**

## **Interface Segregation Principle**

```quote
Prevent classes from relying on things that they dont need
```

In order to prevent this, it is needed to really split up the unique functionality into interfaces.

**[⬆ Back to Top](#table-of-contents)**

## **Dependency Inversion Principle**

```quote
Abstractions should not depend on details. Details should depend on abstractions.
```

What's an abstraction again? An interface or abstract class.

What's a detail again? A concrete class.

Abstractions should never depend on details. Ok, so that means, try not to do this:

```typescript
interface IMailService {
  // refering to concrete "PrettyEmail" and "ShortEmailTransmissionResult" from an abstraction
  sendMail(email: PrettyEmail): Promise<ShortEmailTransmissionResult>
}
```

But instead, do this:

```typescript
class SendGridEmailService implements IMailService {
  // concrete class relies on abstractions
  sendMail(email: IMail): Promise<IEmailTransmissionResult> {}
}
```

**[⬆ Back to Top](#table-of-contents)**

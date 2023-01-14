# Angular

<link href="./ASSETS/STYLES.css" rel="stylesheet"></link>
<img src="./ASSETS/ANGULAR.svg" alt="Angular Logo" class="logo"></img>

- [What is Angular?](#what-is-angular)
- [What are Single Page Applications?](#what-are-single-page-applications)
- [What are Directives?](#what-are-directives)
- [What are Components?](#what-are-components)
- [What are Services in Angular?](#what-are-services-in-angular)
- [What are the differences between Component and Directive?](#what-are-the-differences-between-component-and-directive)
- [What are Decorators?](#what-are-decorators)
- [What is a Template?](#what-is-a-template)
- [What is a Module?](#what-is-a-module)
- [What are Lifecycle Hooks?](#what-are-lifecycle-hooks)
- [What is ngOnInit() in Angular?](#what-is-ngoninit-in-angular)
- [When is ngOnInit() Executed?](#when-is-ngoninit-executed)
- [What is a Data Binding?](#what-is-a-data-binding)
- [What are Pipes?](#what-are-pipes)
- [What is the difference between AOT and JIT?](#what-is-the-difference-between-aot-and-jit)
- [What are AOT advantages?](#what-are-aot-advantages)
- [What is Angular TestBed?](#what-is-angular-testbed)
- [What is RxJS?](#what-is-rxjs)
- [What are the differences between Reactive Forms vs Template Forms?](#what-are-the-differences-between-reactive-forms-vs-template-forms)
- [What is Eager and Lazy loading?](#what-is-eager-and-lazy-loading)
- [What is Sanitization? Does angular supports it?](#what-is-sanitization-does-angular-supports-it)

## What is Angular?

Angular is an application design framework and development platform for creating efficient and sophisticated single-page apps.

**[⬆ Back to Top](#angular)**

## What are Single Page Applications?

Single-page applications are web applications that load once with new features just being mere additions to the user interface. It does not load new HTML pages to display the new page's content, instead generated dynamically.

This is made possible through JavaScript's ability to manipulate the DOM elements on the existing page itself. A SPA approach is faster, thus providing a seamless user experience.

## What are Directives?

Directives add behaviour to an existing DOM element or an existing component instance.

```typescript
import { Directive, ElementRef, Input } from '@angular/core'

@Directive({ selector: '[myHighlight]' })
export class HighlightDirective {
  constructor(el: ElementRef) {
    el.nativeElement.style.backgroundColor = 'yellow'
  }
}
```

Now this directive extends HTML element behavior with a yellow background as below:

```html
<p myHighlight>Highlight me!</p>
```

Now this directive extends HTML element behavior with a yellow background as below

**[⬆ Back to Top](#angular)**

## What are Components?

Components are the most basic UI building block of an Angular app which formed a tree of Angular components. These components are subset of directives. Unlike directives, components always have a template and only one component can be instantiated per an element in a template.

**[⬆ Back to Top](#angular)**

## What are Services in Angular?

Angular Services perform tasks that are used by multiple components. These tasks could be data and image fetching, network connections, and database management among others.

They perform all the operational tasks for the components and avoid rewriting of code. A service can be written once and injected into all the components that use that service.

**[⬆ Back to Top](#angular)**

## What are the differences between Component and Directive?

In a short note, A component(@component) is a directive-with-a-template.

## What are Decorators?

Decorators are a design pattern or functions that define how Angular features work. They are used to make prior modifications to a class, service, or filter. Angular supports four types of decorators, they are:

- Class Decorators
- Property Decorators
- Method Decorators
- Parameter Decorators

**[⬆ Back to Top](#angular)**

## What is a Template?

A template is a **HTML** view where you can display data by binding controls to properties of an Angular component. You can store your component's template in one of **two places**. You can define it **inline** using the template property, or you can define the template in a **separate HTML file** and link to it in the component metadata using the @Component decorator's templateUrl property.

## What is a Module?

Angular applications are modular and Angular has its own modularity system called NgModules. NgModules are containers for a cohesive block of code dedicated to an application domain, a workflow, or a closely related set of capabilities.

They can contain components, service providers, and other code files whose scope is defined by the containing NgModule. They can import functionality that is exported from other NgModules, and export selected functionality for use by other NgModules.

Every Angular application has at least one NgModule class, the root module, which is conventionally named AppModule and resides in a file named _app.module.ts_.

**[⬆ Back to Top](#angular)**

## What are Lifecycle Hooks?

A component instance has a lifecycle that starts when Angular instantiates the component class and renders the component view along with its child views.

The lifecycle continues with change detection, as Angular checks to see when data-bound properties change, and updates both the view and the component instance as needed. The lifecycle ends when Angular destroys the component instance and removes its rendered template from the DOM.

Directives have a similar lifecycle, as Angular creates, updates, and destroys instances in the course of execution.

The description of each lifecycle method is as below:

- ngOnChanges: When the value of a data bound property changes, then this method is called.
- ngOnInit: This is called whenever the initialization of the directive/component after Angular first displays the data-bound properties happens.
- ngDoCheck: This is for the detection and to act on changes that Angular can't or won't detect on its own.
- ngAfterContentInit: This is called in response after Angular projects external content into the component's view.
- ngAfterContentChecked: This is called in response after Angular checks the content projected into the component.
- ngAfterViewInit: This is called in response after Angular initializes the component's views and child views.
- ngAfterViewChecked: This is called in response after Angular checks the component's views and child views.
- ngOnDestroy: This is the cleanup phase just before Angular destroys the directive/component.

**[⬆ Back to Top](#angular)**

## What is ngOnInit() in Angular?

- ngOnInit is a life cycle hook managed by Angular
- ngOnInit being added to prototype of the class created
- ngOnInit called by Angular when component is initialized
- Actual business logic performed ngOnInit method

Every component we create has a life cycle managed by Angular.

As part of the life cycle, angular creates it, renders it and checks when its bounded data properties changes, destroys the component before removing it from the DOM.

**[⬆ Back to Top](#angular)**

## When is ngOnInit() Executed?

- ngOnInit will be executed, When Angular done with the creating of component DOM.
- ngOnInit will be called after the constructor execution and after first ngOnChanges

**[⬆ Back to Top](#angular)**

## What is a Data Binding?

Data binding is a core concept in Angular and allows to define **communication between a component and the DOM**, making it very easy to define interactive applications without worrying about pushing and pulling data.

There are **four** forms of data binding(divided as 3 categories) which differ in the way the data is flowing.

- From the Component to the DOM:

**Interpolation**: {{ value }}: Adds the value of a property from the component

```html
<li>Name: {{ user.name }}</li>
<li>Address: {{ user.address }}</li>
```

**Property binding**: [property]=”value”: The value is passed from the component to the specified property or simple HTML attribute

```html
<input type="email" [value]="user.email" />
```

- **From the DOM to the Component**: Event binding: (event)=”function”: When a specific DOM event happens (eg.: click, change, keyup), call the specified method in the component

```html
<button (click)="logout()"></button>
```

- **Two-way binding**: Two-way data binding: [(ngModel)]=”value”: Two-way data binding allows to have the data flow both ways. For example, in the below code snippet, both the email DOM input and component email property are in sync

```html
<input type="email" [(ngModel)]="user.email" />
```

**[⬆ Back to Top](#angular)**

## What are Pipes?

Use pipes to transform strings, currency amounts, dates, and other data for display. Pipes are simple functions to use in template expressions to accept an input value and return a transformed value. Pipes are useful because you can use them throughout your application, while only declaring each pipe once.

```html
<p>The hero's birthday is {{ birthday | date }}</p>
```

**[⬆ Back to Top](#angular)**

## What is the difference between AOT and JIT?

Ahead of Time (AOT) compilation converts your code during the build time before the browser downloads and runs that code. This ensures faster rendering to the browser. To specify AOT compilation, include the --aot option with the ng build or ng serve command.

The Just-in-Time (JIT) compilation process is a way of compiling computer code to machine code during execution or run time. It is also known as dynamic compilation. JIT compilation is the default when you run the ng build or ng serve CLI commands.

**[⬆ Back to Top](#angular)**

## What are AOT advantages?

- Faster rendering
- Fewer asynchronous requests
- Smaller Angular framework download size
- Quick detection of template errors
- Better security

**[⬆ Back to Top](#angular)**

## What is Angular TestBed?

Configures and initializes environment for unit testing and provides methods for creating components and services in unit tests.

**[⬆ Back to Top](#angular)**

## What is RxJS?

RxJS is a library for reactive programming using Observables, to make it easier to compose asynchronous or callback-based code.

**[⬆ Back to Top](#angular)**

## What are the differences between Reactive Forms vs Template Forms?

Template-driven approach:

- In this method, the conventional form tag is used to create forms. Angular automatically interprets and creates a form object representation for the tag.
- Controls can be added to the form using the NGModel tag. Multiple controls can be grouped using the NGControlGroup module.
- A form value can be generated using the “form.value” object. Form data is exported as JSON values when the submit method is called.
- Basic HTML validations can be used to validate the form fields. In the case of custom validations, directives can be used.
- Arguably, this method is the simplest way to create an Angular App.

Reactive Form Approach:

- This approach is the programming paradigm oriented around data flows and propagation of change.
- With Reactive forms, the component directly manages the data flows between the form controls and the data models.
- Reactive forms are code-driven, unlike the template-driven approach.
- Reactive forms break from the traditional declarative approach.
- Reactive forms eliminate the anti-pattern of updating the data model via two-way data binding.
- Typically, Reactive form control creation is synchronous and can be unit tested with synchronous programming techniques.

**[⬆ Back to Top](#angular)**

## What is Eager and Lazy loading?

Eager loading is the default module-loading strategy. Feature modules under Eager loading are loaded before the application starts. This is typically used for small size applications.

Lazy loading dynamically loads the feature modules when there's a demand. This makes the application faster. It is used for bigger applications where all the modules are not required at the start of the application.

## What is Sanitization? Does angular supports it?

Sanitization is the inspection of an untrusted value, turning it into a value that's safe to insert into the DOM. Yes, Angular suppports sanitization. It sanitizes untrusted values for HTML, styles, and URLs but sanitizing resource URLs isn't possible because they contain arbitrary code.

**[⬆ Back to Top](#angular)**

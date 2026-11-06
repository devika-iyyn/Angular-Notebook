# Angular Basics

> **Version:** Angular v22  
> **Official Website:** Angular.dev

---

# What is Angular?

Angular is a **front-end framework** used to build **client-side web applications**.

It is mainly used for building **Single Page Applications (SPAs)**.

Angular is developed and maintained by **Google**.

Angular mainly uses **TypeScript**, which was developed by **Microsoft**.

## Single Page Application (SPA)

In a traditional website, when we click a link, the browser may load a completely new page.

In an Angular SPA, Angular can update the required part of the view **without reloading the entire page**.

```text
Traditional Website:
Click → Full page reload

Single Page Application:
Click → Required view/content updates
```

## Why do we use Angular?

- Structured / Modular Approach
- Reusable Code
- Unit Testable and Maintainable


# Angular History

## 2010 — AngularJS

AngularJS was introduced in **2010**.

It became very popular, and many organizations used AngularJS to build enterprise applications.

AngularJS is also known as:

```text
Angular 1.x
AngularJS
```

> AngularJS and modern Angular are different architectures.

---

## 2016 — Angular 2

In **2016**, Angular 2 was released.

This was a major redesign compared to AngularJS.

Modern Angular started with Angular 2.

---

## Angular Version 3 Was Skipped

Angular version 3 was skipped.

This was mainly done to avoid confusion because Angular packages had different version numbers, including the Router package version.

The Angular team moved directly from:

```text
Angular 2 → Angular 4
```

---

## Other Angular Versions

Angular continued releasing new major versions regularly:

```text
Angular 4 → 2017
Angular 5 → 2017
Angular 6 → 2018
Angular 7 → 2018
Angular 8 → 2019
Angular 9 → 2020
Angular 10 → 2020
Angular 11 → 2020
Angular 12 → 2021
Angular 13 → 2021
Angular 14 → 2022
Angular 15 → 2022
Angular 16 → 2023
Angular 17 → 2023
Angular 18 → 2024
Angular 19 → 2024
Angular 20 → 2025
Angular 21 → 2025
Angular 22 → 2026
```

> **Current learning version: Angular v22**

---


## Node.js

Node.js is required for Angular development.

Node.js allows JavaScript to run **outside the browser**.

We can check the Node.js version using:

```bash
node -v
```

---

## npm

npm stands for **Node Package Manager**.

npm is used to install and manage packages.

npm is installed along with Node.js.

Check the npm version:

```bash
npm --version
```

or:

```bash
npm -v
```

---

# How to Create a New Angular App

First, create or open a folder where you want to create your Angular project.

Open the terminal or Command Prompt in that folder.

For modern Angular, the recommended way is to use Angular CLI:

```bash
ng new my-app
```

Example:

```bash
ng new my-angular-app
```

---

# Running the Project

Move into the project folder:

```bash
cd my-angular-app
```

Run the application:

```bash
npm start
```

or:

```bash
ng serve
```

To automatically open the application in the browser:

```bash
ng serve -o
```

The application normally runs on:

```text
http://localhost:4200
```

---

# Angular CLI

CLI means:

> **Command Line Interface**

Angular CLI helps us create and manage Angular applications using commands instead of manually creating files and folders.

Install Angular CLI globally:

```bash
npm install -g @angular/cli
```

After installing Angular CLI, we can use the:

```text
ng
```

command.

Examples:

```bash
ng new my-app
ng serve
```

Check the Angular CLI version:

```bash
ng version
```

---

# Project Structure

A basic modern Angular project contains:

```text
my-angular-app/
│
├── src/
│   ├── app/
│   ├── index.html
│   ├── main.ts
│   └── styles.css
│
├── angular.json
├── package.json
└── tsconfig.json
```

---

# `src/`

The `src` folder contains the main source code of the Angular application.

---

## `index.html`

`index.html` is the main HTML page loaded by the browser.

Angular renders the application inside:

```html
<app-root></app-root>
```

The root Angular component is connected to this element.

---

## `styles.css`

`styles.css` contains **global styles** for the entire application.

Example:

```css
body {
  margin: 0;
}
```

---

## `main.ts`

`main.ts` is the main entry point of the Angular application.

In a modern Angular standalone application, it bootstraps the application.

Example:

```ts
import { bootstrapApplication } from '@angular/platform-browser';
import { appConfig } from './app/app.config';
import { App } from './app/app';

bootstrapApplication(App, appConfig)
  .catch((err) => console.error(err));
```

---

## `favicon.ico`

This is the icon displayed in the browser tab.

---

# `src/app/`

The `src/app/` folder contains the main Angular application code.

A modern Angular project may contain files such as:

```text
src/app/
│
├── app.ts
├── app.html
├── app.css
├── app.config.ts
└── app.routes.ts
```

---

## Root Component

The root component is the main starting component of the Angular application.

Modern Angular CLI projects use a standalone component.

Example:

### `app.ts`

```ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  standalone: true,
  imports: [],
  templateUrl: './app.html',
  styleUrl: './app.css',
})
export class App {
  title = 'my-angular-app';
}
```

The selector:

```text
app-root
```

connects to:

```html
<app-root></app-root>
```

in `index.html`.

---

## `app.html`

This file contains the HTML template of the root component.

Example:

```html
<h1>Hello Angular</h1>
```

---

## `app.config.ts`

This file contains application-level configuration and providers.

---

## `app.routes.ts`

This file contains application routes.

Routes decide which component should be displayed for a particular URL.

---

# Other Important Files

## `angular.json`

Contains Angular project configuration.

It is used for configuration related to:

- Build
- Serve
- Project settings

---

## `package.json`

Contains:

- Dependencies
- Packages
- npm commands/scripts

Example:

```json
{
  "scripts": {
    "start": "ng serve"
  }
}
```

When we run:

```bash
npm start
```

it runs the configured Angular start command.

---

## `tsconfig.json`

This file contains TypeScript configuration.

---



# Data Binding

Data binding creates a connection between the:

```text
Component Class ↔ Template/View
```

The component contains the application data and logic.

The template displays the data to the user.

If data changes, Angular can update the view.

---

# Types of Data Binding

The main types are:

1. One-way binding
2. Two-way binding

Common one-way binding techniques include:

- String interpolation
- Property binding
- Event binding

---

# 1. One-Way Binding

In one-way binding, data communication happens in one direction.

For example:

```text
Component → View
```

If the component data changes, the view can display the updated value.

---

## Example

### `app.ts`

```ts
export class App {
  title = 'Hello';
}
```

### `app.html`

```html
<h1>{{ title }}</h1>
```

Output:

```text
Hello
```

Here, we are displaying the value from the component in the view.

---

# 2. Two-Way Binding

In two-way binding, data can interact between both the:

```text
Component ↔ View
```

If the user changes the value in the view, the component value is updated.

This can be done using:

```text
ngModel
```

---

## Example

### `app.ts`

```ts
import { Component } from '@angular/core';
import { FormsModule } from '@angular/forms';

@Component({
  selector: 'app-root',
  imports: [FormsModule],
  templateUrl: './app.html',
})
export class App {
  fullName = 'Devika';
}
```

### `app.html`

```html
<h1>{{ fullName }}</h1>

<input type="text" [(ngModel)]="fullName">
```

If the user changes the input value, `fullName` is automatically updated.

The updated value is displayed in:

```html
<h1>{{ fullName }}</h1>
```

---

# `FormsModule` and `ngModel`

`ngModel` comes from Angular Forms.

Therefore, we need to import `FormsModule`.

In a modern standalone component:

```ts
import { FormsModule } from '@angular/forms';

@Component({
  imports: [FormsModule]
})
```

Now we can use:

```html
<input [(ngModel)]="fullName">
```

---

# String Interpolation

String interpolation allows us to display values from the component inside the HTML template.

Syntax:

```html
{{ expression }}
```

---

## Displaying a Variable

### `app.ts`

```ts
export class App {
  title = 'Angular';
}
```

### `app.html`

```html
<h1>{{ title }}</h1>
```

---

## Displaying a Function Result

### `app.ts`

```ts
export class App {
  getName() {
    return 'Devika';
  }
}
```

### `app.html`

```html
<h1>{{ getName() }}</h1>
```

---

# String Interpolation with Attribute Binding

We can use values from the component in HTML attributes.

### `app.ts`

```ts
export class App {
  imageUrl = 'assets/pic.jpg';
  imageAlt = 'Logo';
}
```

### `app.html`

Using property binding:

```html
<img [src]="imageUrl" [alt]="imageAlt">
```

We can also use interpolation inside an attribute:

```html
<img [src]="imageUrl" alt="This is the {{ imageAlt }}">
```

---


## Property Binding

We know that HTML/DOM elements have many **properties**.

**Property binding** is used to assign a value from the Angular component to an HTML element property.

The syntax is:

```html
[property]="value"
```

### Example: `innerText`

```html
<h1 [innerText]="title"></h1>
```

`innerText` is a property of the HTML element that controls its text content.

### Component

**app.ts**

```ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  standalone: true,
  templateUrl: './app.html',
})
export class AppComponent {
  title = 'Hello';
}
```

### Template

**app.html**

```html
<h1 [innerText]="title"></h1>
```

Angular takes the value of `title` from the component and assigns it to the `innerText` property of the `<h1>` element.

---

## Example: Disabling a Button

The `disabled` property determines whether a button can be clicked.

```html
<button [disabled]="isDisabled">Click me</button>
```

### Component

```ts
export class AppComponent {
  isDisabled = true;
}
```

When `isDisabled` is `true`, the button will be disabled.

When it is `false`, the button will be enabled.

So, using property binding, we can dynamically assign property values and change the **behavior or appearance of an HTML element**.

---

## Property Binding with Different Values

We can also directly assign a string:

```html
<p [textContent]="'TEST'"></p>
```

We can assign a value from an object:

### Component

```ts
export class AppComponent {
  user = {
    name: 'Devika',
    age: 23,
  };
}
```

### Template

```html
<p [textContent]="user.name"></p>
```

The value of `user.name` will be assigned to the `textContent` property.

---

# Property Binding with Safe Navigation Operator

Sometimes an object may be `null` or `undefined`.

For example:

### Component

```ts
export class AppComponent {
  user: any = null;
}
```

If we try to access:

```html
<p [textContent]="user.name"></p>
```

Angular tries to access `name` from `user`.

But `user` is currently `null`, so this can cause an error.

To avoid this, Angular provides the **safe navigation operator (`?.`)**.

```html
<p [textContent]="user?.name"></p>
```

### How it works

```text
user has a value?
        │
       Yes ───→ Get user.name
        │
       No
        ↓
Return undefined without causing an error
```

So:

```html
user?.name
```

means:

> If `user` exists, get the `name`. Otherwise, safely return no value.

---

## Example with Data Loaded Later

Sometimes data is not available immediately when the component is created.

For example:

```ts
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-root',
  standalone: true,
  templateUrl: './app.html',
})
export class AppComponent implements OnInit {
  user: { name: string } | null = null;

  ngOnInit(): void {
    this.user = {
      name: 'Devi',
    };
  }
}
```

### Template

```html
<p [textContent]="user?.name"></p>
```

Initially:

```text
user = null
```

The page can render safely.

After `ngOnInit()`:

```text
user = {
  name: 'Devi'
}
```

The value will be displayed.

> The safe navigation operator is useful when data may be `null` or not yet available.

---

# Event Binding

User actions are called **events**.

Examples of events:

- Mouse click
- Key down
- Key up
- Mouse enter
- Input changes

Angular uses **event binding** to listen for these events.

The syntax is:

```html
(event)="method()"
```

---

## Click Event Example

### Component

```ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  standalone: true,
  templateUrl: './app.html',
})
export class AppComponent {
  clickCount = 0;

  clickMe(): void {
    this.clickCount++;
  }
}
```

### Template

```html
<h1>Clicked {{ clickCount }} times</h1>

<button (click)="clickMe()">Click me</button>
```

### How it works

```text
User clicks the button
        ↓
(click) event occurs
        ↓
clickMe() method is called
        ↓
clickCount increases
        ↓
Angular updates the UI
```

For example:

```text
Clicked 0 times
```

After clicking once:

```text
Clicked 1 time
```

After clicking again:

```text
Clicked 2 times
```

---

## Key Events Example

Angular can also listen to keyboard events.

### Template

```html
<input (keydown)="onKeyDown()" />
```

### Component

```ts
onKeyDown(): void {
  console.log('A key was pressed');
}
```

Other common keyboard events include:

```html
<input (keyup)="onKeyUp()" />
```

---

# Property Binding vs Event Binding

| Property Binding | Event Binding |
|---|---|
| Sends data from Component → HTML | Sends user actions from HTML → Component |
| Uses `[ ]` | Uses `( )` |
| Example: `[disabled]` | Example: `(click)` |

---
# Day 1 Summary

Today I learned:

- What Angular is
- Why Angular is used
- Single Page Applications (SPA)
- Angular history
- Angular versions
- Angular CLI
- Creating an Angular application
- Running an Angular application
- Angular project structure
- Standalone components
- Data binding
- One-way binding
- Two-way binding
- `ngModel`
- `FormsModule`
- String interpolation
- Property binding
- Event binding
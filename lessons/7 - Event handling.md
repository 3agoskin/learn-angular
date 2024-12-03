Event handling enables interactive features on web apps. It gives you the ability as a developer to respond to user actions like button presses, form submissions and more.

In this activity, you'll learn how to add an event handler.

---
In Angular you bind to events with the parentheses syntax `()`. On a given element, wrap the event you want to bind to with parentheses and set an event handler. Consider the `button` example:

```ts
@Component({
  ...
  template: `<button (click)="greet()">`
})
class AppComponent {
  greet() {
    console.log('Hello, there 👋');
  }
}
```

In this example, the `greet()` function will run every time the button is clicked. Take note that `greet()` syntax includes the trailing parenthesis.

Alright, your turn to give this a try:
### 1. Add an event handler
Add the `onMouseOver` event handler function in the `AppComponent` class. Use the following code as the implementation:

```ts
onMouseOver() {
  this.message = 'Way to go 🚀';
}
```

### 2. Bind to the template event
Update the template code in `app.component.ts` to bind the `mouseover` event of the `section` element.
```ts
<section (mouseover)="onMouseOver()">
```

---
And with a few steps in the code you've created your first event handler in Angular.

```ts
// app/app.component.ts

import {Component} from '@angular/core';

@Component({
  selector: 'app-root',
  template: `
    <section (mouseover)="onMouseOver()">
      There's a secret message for you, hover to reveal 👀
      {{ message }}
    </section>
  `,
})
export class AppComponent {
  message = '';

  onMouseOver() {
    this.message = 'Way to go 🚀';
  }
}

```
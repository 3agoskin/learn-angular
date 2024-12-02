Deciding what to display on the screen for a user in a common task in application development. Many times, the decision is made programmatically using conditions.

To express conditional displays in templates, Angular uses the `@if` template syntax.

In this activity, you'll learn how to use conditionals in templates.

---
The syntax that enables the conditional display of elements in a template is `@if`.

Here's an example of how to use the `@if` syntax in a component: 

```ts
@Component({
  ...
  template: `
    @if (isLoggedIn) {
      <p>Welcome back, Friend!</p>
    }
  `,
})
class AppComponent {
  isLoggedIn = true;
}
```

Two things to take note of:
- There is an `@` prefix for the `if` because it is a special type of syntax called [Angular template syntax](https://angular.dev/guide/templates)

---
### 1. Create a property called `isServerRunning`
In the `AppComponent` class, add a `boolean` property called `isServerRunning`, set the initial value to `true`.

### 2. Use `@if` in the template
Update the template to display the message `Yes, the server is running` if the value of `isServerRunning` is `true`.

### 3. Use `@else` in the template
Now Angular supports native template syntax for defining the else case with the `@else` syntax. Update the template to display the message `No, the server is not running` as the else case.

Here's an example:

```ts
template: `
  @if (isServerRunning) { ... }
  @else { ... }
`;
```

Add your code to fill in the missing markup.

---
This type of functionality is called conditional control flow.

```ts
// app/app.component.ts

import {Component} from '@angular/core';

@Component({
  selector: 'app-root',
  template: `
    @if (isServerRunning) {
    <span>Yes, the server is running</span>
    } @else {
    <span>No, the server is not running</span>
    }
  `,
})
export class AppComponent {
  isServerRunning = false;
}
```
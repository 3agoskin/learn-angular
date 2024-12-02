You've learned to update the component template, component logic, and component styles, but how do you use a component in your application?

The `selector` property of the component configuration gives you a name to use when referencing the component in another template. You use the `selector` like an HTML tag, for example `app-user` would be `<app-user />` in the template.

In the activity, you'll learn how to compose components.

---
In this example, there are two components `UserComponent` and `AppComponent`.

### 1. Add a reference to `UserComponent`
Update the `AppComponent` template to include a reference to the `UserComponent` which uses the selector `app-user`. Be sure to add `UserComponent` to the imports of `AppComponent`, this makes it available for use in the `AppComponent` template.

```ts
template: `<app-user />`
imports: [UserComponent]
```

The component now displays the message `Username: youngTech`. You can update the template code to include more markup.

### 2. Add more markup
Because you can use any HTML markup that you want in a template, try updating the template for `AppComponent` to also include more HTML elements. This example will add a `<selection>` element as the parent of the `<app-user>` element.

```ts
template: `<selection><app-user /></selection>`
```

---
You can use as much HTML markup and as many components as you need to bring your app idea to reality. You can even have multiple copies of your component on the same page.

```ts
// app/app.component.ts

import {Component} from '@angular/core';

@Component({
  selector: 'app-username',
  template: `
    Username: {{ username }}
  `,
})
export class UserComponent {
  username = 'youngTech';
}

@Component({
  selector: 'app-root',
  template: `<section><app-username /></section>`,
  imports: [UserComponent],
})
export class AppComponent {}

```
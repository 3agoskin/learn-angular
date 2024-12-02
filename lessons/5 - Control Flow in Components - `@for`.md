Often when building web applications, you need to repeat some code a specific number of times - for example, given an array of names, you may want to display each name in a `<p>` tag.

In this activity, you'll learn how to use `@for` to repeat elements in a template.

---
The syntax that enables repeating elements in a template is `@for`.

Here's an example of how to use the `@for` syntax in a component.

```ts
@Component({
  ...
  template: `
    @for (os of operatingSystems; track os.id) {
      {{ os.name }}
    }
  `,
})
export class AppComponent {
  operatingSystems = [{id: 'win', name: 'Windows}, {id: 'osx', name: 'MacOS'}, {id: 'linux', name: 'Linux'}];
}
```

Two things to take note of:
- There is an `@` prefix for the `for` because it is a special syntax called [Angular template syntax](https://angular.dev/guide/templates)
- For applications using v16 and older please refer to the [Angular documentation for NgFor](https://angular.dev/guide/directives/structural-directives)

---
### 1. Add the `users` property
In the `AppComponent` class, add a property called `users` that contains users and their names.

```ts
[{id: 0, name: 'Sarah'}, {id: 1, name: 'Amy'}, {id: 2, name: 'Rachel'}, {id: 3, name: 'Jessica'}, {id: 4, name: 'Poornima'}]
```

### 2. Update the template
Update the template to display each user name in a `p` element using the `@for` template syntax.

```ts
@for (user of users; track user.id) {
  <p>{{ user.name }}</p>
}
```

Note: the use of `track` is required, you may use the `id` or some other unique identifier.

---
This type of functionality is called control flow.

```ts
// app/app.component.ts

import {Component} from '@angular/core';

@Component({
  selector: 'app-root',
  template: `
    @for (user of users; track user.id) {
      <p>{{ user.name }}</p>
    }
  `,
})
export class AppComponent {
  users = [{id: 0, name: 'Sarah'}, {id: 1, name: 'Amy'}, {id: 2, name: 'Rachel'}, {id: 3, name: 'Jessica'}, {id: 4, name: 'Poornima'}]
}
```

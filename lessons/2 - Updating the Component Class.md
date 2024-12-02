In Angular, the component's logic and behavior are defined in the component's TypeScript class.

In this activity, you'll learn how to update the component class and how to use interpolation.

---
```ts
// app/app.component.ts

import {Component} from '@angular/core';

@Component({
  selector: 'app-root',
  template: `
    Hello
  `,
})
export class AppComponent {}
```
---
### 1. Add a property called `city`
Update the component class by adding a property called `city` to the `AppComponent` class.

```ts
export class AppComponent {
  city = 'San Francisco';
}
```

The `city` property is of type `string` but you can omit the type because of type inference in TypeScript. The `city` property can be used in the `AppComponent` class and can be referenced in the component template.

To use a class property in a template, you have to use the `{{ }}` syntax.

### 2. Update the component template
Update the `template` property to match the following HTML:

```ts
template: `Hello {{ city }}`
```

This is an example of interpolation and is a part of Angular template syntax. it enables you to do much more than put dynamic text in a template. You can also use this syntax to call functions, write expressions and more.

### 3. More practice with interpolation
Try this - add another set of `{{ }}` with the contents being `1 + 1`:

```ts
template: `Hello {{ city }}, {{ 1 + 1 }}`
```

Angular evaluates the contents of the `{{ }}` and renders the output in the template

---
This is just beginning of what's possible with Angular templates, keep on learning to find out more.


```ts
// app/app.component.ts
import {Component} from '@angular/core';

@Component({
  selector: 'app-root',
  template: `
  I have been living in {{myCity}} city for about {{ 2024 - 2014 }} years.
  `,
})
export class AppComponent {
  myCity = 'St. Petersburg';
}

```

```preview
I have been living in St. Petersburg city for about 10 years.
```

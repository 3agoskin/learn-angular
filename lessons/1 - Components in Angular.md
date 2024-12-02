Components are the foundational building blocks for any Angular application. Each components has three parts:
- TypeScript class
- HTML template
- CSS styles
---
```ts
// app/app.component.ts

import {Component} from '@angular/core';

@Component({
  selector: 'app-root',
  template: `
    Hello
  `,
  styles: `
    :host {
      color: blue;
    }
  `,
})
export class AppComponent {}

```
### 1. Update the component template
Update the `template` property to read `Hello Universe`

```ts
template: `
  Hello Universe 
`
```

When HTML template is changed, the preview is updated with new message.

### 2. Update the component styles
Update the styles value and change the `color` property from `blue` to `#a144eb`

```ts
styles: `
  :host {
    color: #a144eb;
  }
`
```

The text color should change the color

---
In Angular, you can use all the browser supported CSS and HTML that's available. If you'd like, you can store your templates and styles in separate files.

```ts
// app/app.component.ts

import {Component} from '@angular/core';

@Component({
  selector: 'app-root',
  template: `
    Hello Universe
  `,
  styles: `
    :host {
      color: #a144eb;
    }
  `,
})
export class AppComponent {}

```
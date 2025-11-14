* Built with TypeScript
* Components and templates
* Routes, forms, HTTP and dependency injection
* Standalone APIs
* SPAs (single-page applications)
### How Angular Works
Compiles your templates into JS and updates the DOM when a component state changes.

**Create a project**
`ng new my-angular-app`
**Start dev**
`ng serve`
#### Components, Templates and Selectors
* A component is a class that controls a view (its template)
* Each component has a selector (e.g, app-root) that you place in HTML
* The root component renders inside index.html's

**Initial render** Angular creates the component and processes the template.
**Change detection** On user events, timers, or async workm Angular re-evaluates template expressions and updates only what changes.
**Directives** Create/destroy embedded views (DOM fragments) beased on state.
**Binding flow** Interpolation/Property binding push data to the view. Event binding captures broswer events back to the component.

==Interpolation escapes HTML Use ?. to avoid null errors==


> [!NOTE] Template expressions run in the component context
> Work in the class, not inline in the template to keep it fast and side-effect free/

#### Template Essentials
Key concepts :
* **Templates** are the HTML that Angular renders for a component.
- **Bindings**: interpolation `{{ ... }}`, property `[prop]`, and event `(event)`.
- **Template refs**: local names like `#box` to reference elements or directives.
- **Structural directives** (`*ngIf`, `*ngFor`) change the DOM layout.



#### Template Reference Variables
```ts
import { bootstrapApplication } from '@angular/platform-browser';
import { Component } from '@angular/core';
import { CommonModule } from '@angular/common';

@Component({
  selector: 'app-root',
  standalone: true,
  imports: [CommonModule],
  styles: [`
    .toolbar { display: flex; gap: 8px; align-items: center; flex-wrap: wrap; }
    input { padding: 6px 8px; }
  `],
  template: `
    <h3>Template Reference Variables (#var)</h3>
    <div class="toolbar">
      <input #box type="text" placeholder="Type something" (input)="current = box.value" />
      <button (click)="read(box.value)">Read value</button>
      <button (click)="box.focus()">Focus input</button>
      <span style="margin-left:8px;color:#666">length={{ box.value?.length || 0 }}</span>
    </div>
    <p>Current: {{ current || '(empty)' }}</p>
  `
})
export class App {
  current = '';
  read(val: string) { this.current = val ?? ''; }
}

bootstrapApplication(App);
```
- `#box`: A template reference variable bound to the input element instance.
- **Read a value**: `box.value` reads the input's current text.
- **Call a method**: `box.focus()` calls the input's focus method.
- **Update state**: `(input)="current = box.value"` copies the current input text into the component's `current` field.
- **Scope**: The variable exists only in the template where it is declared.
![[Pasted image 20251113155109.png]]

#### Null-Sage Navigation (?.)
- **Optional chaining (?.)**: `user?.profile?.email` reads **email** only if **user** and **profile** are defined; otherwise the whole expression is `undefined` (no error).
#### Structural Directives
- `*` is shorthand that expands to an underlying `<ng-template>`.
- Provides context variables (e.g., `index as i`, `else`).
- Angular rewrites `*ngIf`, `*ngFor`, etc., using this syntax.
> Important in Angular 17+, prefer the new control flow syntax (@if, @for, @switch) The micro-syntax for \*ngIf / ngFor remains supported.


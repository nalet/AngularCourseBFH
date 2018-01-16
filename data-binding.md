## Data Binding

- Data binding allows to bind controls in an HTML template to properties of an Angular component
- There are different types of data bindings:
  - interpolation binding
  - two-way binding
  - event binding
  - property binding

![](img/databinding.png)

----

## Interpolation Binding

- An interpolation binding allows to display a component property (one-way binding)

Syntax
```
{{property}}
```

Example
```html
<td>{{book.isbn}}</td>
```

(details see [Displaying Data](https://angular.io/docs/ts/latest/guide/displaying-data.html#interpolation))

----

## Event Binding

- An event binding binds an event to a template statement, e.g. a component method
- The event information is accessible through the object `$event`

Syntax
```
(event)="statement"
```

Examples
```html
<button (click)="searchBooks()">Search</button>
<button (click)="selectedBook=null">Back</button>
```

(details see [Template Syntax](https://angular.io/docs/ts/latest/guide/template-syntax.html#event-binding))

----

## Property Binding

- A property binding sets the property of a DOM element to the value of a template expression (one-way data binding)

Syntax
```
[property]="expression"
```

Examples
```html
<button (click)="searchBooks()" [disabled]="!keywords">
<img [src]="book.imageUrl">
```

(details see [Template Syntax](https://angular.io/docs/ts/latest/guide/template-syntax.html#property-binding))

----

## Two-way Data Binding

- The `ngModel` directive binds the value of an input element to a component property such that both are kept up to date
- In order to use `ngModel` directive, the `FormsModule` is required

Syntax
```
[(ngModel)]="property"
```

Example
```html
<input [(ngModel)]="keywords">
```

(details see [Template Syntax](https://angular.io/guide/template-syntax#two-way-binding))

<br>
A two-way data binding could also be achieved by combining a property and an event binding
```html
<input [value]="keywords" (input)="keywords=$event.target.value">
```

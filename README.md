# The Basic

## Creating a new Component

A component is a typescript class were we use component decorator from angular core for convert it angular component from a simple typescript class.

### Example of a basic angular component

```typescript
import { Component } from "@angular/core";
@Component({
  selector: "app-server",
  templateUrl: "server.component.html"
})
export class Server {}
```

## Creating a new Component By Angular CLI

By Angular CLI we can create new component, service and directive also.
Here is the commend by this we can create new component:

```
ng g c component-name

```

## Working with angular component template

In any angular template we can use external html template by using tamplateUrl in @Component({}) decorator but can use inline template also by using template:

#### Example 1 of inline template

```typescript
import { Component, OnInit } from "@angular/core";

@Component({
  selector: "app-servers",
  template: "<app-server></app-server>",
  styleUrls: ["./servers.component.css"]
})
export class ServersComponent implements OnInit {
  constructor() {}

  ngOnInit() {}
}
```

#### Example 2 of inline template

```typescript
import { Component, OnInit } from "@angular/core";

@Component({
  selector: "app-servers",
  template: `
    <h1>This is component Heading</h1>
    <p>This is component content</p>
  `,
  styleUrls: ["./servers.component.css"]
})
export class ServersComponent implements OnInit {
  constructor() {}

  ngOnInit() {}
}
```

### Working with style

In angular component we can use our style in different ways:

#### Example 1 – Use external stylesheet by using styleUrls

```typescript
@Component({
  styleUrls: ['./servers.component.css']
})
```

We can use multiple stylesheet also

```typescript
@Component({
  styleUrls: ['./servers.component.css',’otherstyle.css’]
})
```

## Example 2– Use inline style by using style

```typescript
@Component({
  style: `
h3{
color:blue
}
`
})
```

## Data Binding in angular

In angular we have different type of data binding

1. String Interpolation(Output Data)
2. Property Binding(Output Data)
3. Event Binding(react to user Event)
4. Two way data binding([(ngModel)]=’data’)

### String Interpolation

By using curly bracts we can use string Interpolation in our template.

#### Example of string Interpolation

In the example serverId and serverStatus is defined in typescript file

```typescript
Your server ID is {{ serverId }} and this is {{ serverStatus }} server
```

### Property Binding

Property binding is a one-way mechanism that lets you set the property of a view element. It involves updating the value of a property in the component and binding it to an element in the view template. Property binding uses the [] syntax for data binding.

#### An example is setting the disabled state of a button

```typescript
// component.html

    <button [disabled]="buttonDisabled"></button>

```

```typescript
// component.ts
@Component({
  templateUrl: "component.html",
  selector: "app-component"
})
export class Component {
  buttonDisabled = true;
}
```

### Event binding

This data binding type is when information flows from the view to the component when an event is triggered. The view sends the data from an event like the click of a button to be used to update the component. It is the exact opposite of property binding, where the data goes from the component to the view. An example of this type of data binding can be described using the example below:

```typescript
// component.html

    <p>My name is {{name}}</p>
    <button (click)="updateName()">Update button</button>

```

```typescript
// component.ts

@Component({
  templateUrl: "component.html",
  selector: "app-component"
})
export class Component {
  name = "Peter";

  updateName() {
    this.name = "John";
  }
}
```

### Passing and using data

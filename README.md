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

### Example 1 of inline template

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

### Example 2 of inline template

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

## Working with style

In angular component we can use our style in different ways:

## Example 1 – Use external stylesheet by using styleUrls

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

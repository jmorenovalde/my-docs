# Objects name in an Angular Project

In this document, I would want to put the bases to a standard to name objects:

* [Variables](#variables).
* [Constants](#constants).
* [Functions](#functions).
* [Classes and Interfaces](#classes-and-intefaces).

> _**IMPORTANT:**_ All the names should be in English.

## Variables

The names of the variables must be self-explanatory (_CleanCode_), and we will use the _lower camelCase_ notification.

```typescript
let numberObjectsPerPage = 10;
```

> **Note:** In the past, private variables were put a `_` in front of them. This practice is now deprecated, and the _linter_ will mark it as an error.

Depending on the functionality of the variable we will use some additions to the variables.

### Boolean

In _CleanCode_ it is recommended to use the word `is` in front of what we want to mark as` boolean`. Also, it is implied that `true` is active and` false` is not active.

```typescript
public isVisible: boolean;
// isVisible = false => It is not visible.
// isVisible = true => It is visible.
```

If `is` does not fit, we will have to put another verb that implies a yes or no answer, for example, `can` (`canSave`).

### Events

To indicate that the content of the variable is an element, it is suggested to put the symbol `$` at the beginning of the variable.

```typescript
let $openWindow: Event;
```

In this way we save putting the variable as:

```typescript
let openWindowEvent: Event;
```

Another example of use:

```html
<button (click) = "method($mouseEvent)"> Acction </button>
```

### Observables

To indicate that a variable is an Observable, it is suggested to put the symbol `` $ '' at the end of the variable.

```typescript
let openWindow$: Observable;
```

In this way we save putting the variable as:

```typescript
let openWindowObservable: Observable;
```

### Services

For the variables that are created in the `constructor` of the class, it is proposed to use the name of the service, in _lower camelCase_

```typescript
constructor (private userService: UserService) {}
```

## Constants

For constants it is suggested to use the naming convention *SCREAMING_SNAKE_CASE*.

```typescript
CONSTANT const = 1;
const NEW_CONSTANT = 2;
```

## Functions

For functions we are going to use the naming convention _lower camelCase_.

```typescript
public getUsers (): void {}

private updateUser (user: User): void {}
```

## Classes and Interfaces

For _classes_ and _interfaces_ we are going to use the _Upper CamelCase_ naming convention.

```typescript
export class MyClae {};
export interface MyInterface {};
```

> Note: Avoid using `INname` to name the interface _Name_.

Back to [Readme](./README.md).

___
Author:

Juan Antonio Moreno Valderrama.

<a href="https://twitter.com/jmorenovade"><img src="https://img.shields.io/twitter/follow/jmorenovalde?label=Twitter&style=social" alt="Twitter"></a>
<a href="https://www.linkedin.com/in/juan-antonio-moreno-valderrama/"><img src="https://img.shields.io/badge/LinkedIn--_.svg?style=social&logo=linkedin" alt="LinkedIn"></a>
<a href="https://github.com/jmorenovalde"><img alt="GitHub followers" src="https://img.shields.io/github/followers/jmorenovalde?style=social"></a>
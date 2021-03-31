# Convención de nombres

En este documento se quiere poner las bases a un estándar para la estandarización de los nombres de las [variables](#variables), [constantes](#constantes), [funciones](#funciones), [clases e interfaces](#clases-e-interfaces).

> _**IMPORTANTE:**_ Los nombres siempre en inglés, ya que suelen ser más fáciles y no usan caracteres no estándars como _ñ_ o _acentos_.

## Variables

Los nombres de las variables han de ser autoexplicativas (_CleanCode_), y usaremos la notificación _lower camelCase_

```typescript
let numberObjectsPerPage = 10;
```

> **Nota:** antiguamente, a las variables privadas se les ponía un _ delante. Esta práctica ya está en desuso, y el linter lo marcará como error.

Dependiendo de la funcionalidad de la variable usaremos unos añadidos a las variables.

### Boolean

En _CleanCode_ se recomienda usar la palabar `is` delante de lo que queremos marcar como `boolean`. Además, se deja implicito que `true` es activo y `false` no activo.

```typescript
public isVisible: boolean;
// isVisible = false => No es visible.
// isVisible = true => Es visible.
```

### Eventos

Para indicar que el contenido de la variable es un elemento se sugiere poner el símbolo `$` al principio de la variable.

```typescript
let $openWindow: Event;
```

De esta forma nos ahorramos poner la variable como:

```typescript
let openWindowEvent: Event;
```

Otro ejemplo de uso:

```html
<button (click)="method($mouseEvent)">Acction</button>
```

### Observables

Para indicar que una variable es un Observable se sugiere poner el símbolo `$` al final de la variable.

```typescript
let openWindow$: Observable;
```

De esta forma nos ahorramos poner la variable como:

```typescript
let openWindowObservable: Observable;
```

### Servicios

Para las variables que se crean en el `constructor` de la clase, se propone usar el nombre del servicio, en _lower camelCase_

```typescript
constructor (private userService: UserService) { }
```

## Constantes

Para las constantes se sugiere usar la convención de nombre *SCREAMING_SNAKE_CASE*.

```typescript
const CONSTANTE = 1;
const NUEVA_CONSTANTE = 2;
```

## Funciones

Para las funciones vamos a usar la convención de nombre _lower camelCase_.

```typescript
public getUsers(): void {}

private updateUser(user: User): void {}
```

## Clases e Interfaces

Para las _clases_ e _interfaces_ vamos a usar la convención de nombre _Upper CamelCase_.

```typescript
export class MiClae {};
export interface MiInterfaz{};
```

> Nota: Evitar el uso de `INombre` para denominar la interfaz _Nombre_.

___
Desarrollado por:

Juan Antonio Moreno Valderrama.

<a href="https://twitter.com/jmorenovade"><img src="https://img.shields.io/twitter/follow/jmorenovalde?label=Twitter&style=social" alt="Twitter"></a>
<a href="https://www.linkedin.com/in/juan-antonio-moreno-valderrama/"><img src="https://img.shields.io/badge/LinkedIn--_.svg?style=social&logo=linkedin" alt="LinkedIn"></a>
<a href="https://github.com/jmorenovalde"><img alt="GitHub followers" src="https://img.shields.io/github/followers/jmorenovalde?style=social"></a>
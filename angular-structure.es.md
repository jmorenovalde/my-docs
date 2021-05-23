# Estructuras de directorios de un proyecto en Angular

El objetivo de este artículo es hacer una estandarización de la estructura de las carpetas de un proyecto en Angular.

Para ello vamos a tomar como base el artículo [How to define a highly scalable folder structure for your Angular project](https://itnext.io/choosing-a-highly-scalable-folder-structure-in-angular-d987de65ec7).

## Estructura del proyecto

La estructura está basada en la funcionalidad de los ficheros, de forma que sea fácil por una persona ajena al proyecto encontrar un fichero.

```
└── src
  ├── app
  | ├── [+] modules
  | ├── [+] core
  | ├── [+] models
  | └── [+] shared
  ├── [+] assets
  └── environments
```

> `[+]` Con este símbolo se indica que puede haber subdirectorios dentro.


### shared

En este directorio introduciremos los distintos elementos que sean comunes a la aplicación.

```
└── [+] shared
  ├── [+] components
  ├── [+] directives
  └── [+] pipes
```

In the `components` folder will stay the components that we will reuse in several _modules_. Each component will be in itself folder. If there will be some components, It is very recommended to create an `index.ts` to do easier the importation of the components (`barrel`).

Following, we see an example of the components:

```
└── components
  ├── loader
  | └── loader.component.ts|html|scss|spec.ts
  ├── buttons
  | ├── favorite-button
  | | └── favorite-button.component.ts|html|scss|spec.ts
  | └── collapse-button
  |   └── collapse-button.component.ts|html|scss|spec.ts
  └── index.ts
```

En las carpetas `directives` y` pipe` deben ir las directivas y las tuberías para las tuberías personalizadas o directivas que usan los componentes de la carpeta _component_ dentro de la carpeta _shared_. Cree una carpeta para cada elemento y un `index.ts` si existe más de un elemento para facilitar la importación de los elementos.


### modules

En esta carpeta irán los distintos módulos de la aplicación. Las páginas que bien cargaremos mediante _Lazy Loading_ o bien en sí están metidos en un modulo para poder ser reutilizados en varias partes de la aplicación.

Dentro podemos encontrar una estructura similar a la de [shared](#shared).


### core

En esta carpeta estarán los elementos que se instanciarán una sola vez en toda la aplicación, como servicios, guardias, ...

```
└── core
  ├── [+] guards
  ├── [+] http
  ├── [+] interceptors
  ├── [+] services
  └── core.module.ts
```

En el directorio `http` es donde irán los servicios que van a comunicarse con las API REST.

En la carpeta `services` deberíamos ver los servicios que no se conectan a las API, por ejemplo un servicio para almacenar datos en _LocalStorage_


### models

En esta carpeta, almacenamos los modelos de los modelos de entidad personalizados, que podríamos usar en la aplicación. Si hay varios archivos, recomiendo crear un _barrel_ llamado `model.ts`.

```
└── models
  ├── models.ts
  ├── post.model.ts
  ├── post-comment.model.ts
  └── user.model.ts
```

Volver al [Readme](./README.es.md).
___
Desarrollado por:

Juan Antonio Moreno Valderrama.

<a href="https://twitter.com/jmorenovade"><img src="https://img.shields.io/twitter/follow/jmorenovalde?label=Twitter&style=social" alt="Twitter"></a>
<a href="https://www.linkedin.com/in/juan-antonio-moreno-valderrama/"><img src="https://img.shields.io/badge/LinkedIn--_.svg?style=social&logo=linkedin" alt="LinkedIn"></a>
<a href="https://github.com/jmorenovalde"><img alt="GitHub followers" src="https://img.shields.io/github/followers/jmorenovalde?style=social"></a>
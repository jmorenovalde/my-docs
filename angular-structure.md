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

`[+]` Con este símbolo se indica que puede haber subdirectorios dentro.

### modules

En esta carpeta irán los distintos módulos de la aplicación. Las páginas que bien cargaremos mediante _Lazy Loading_ o bien en sí están metidos en un modulo para poder ser reutilizados en varias partes de la aplicación.

Dentro podemos encontrar una estructura similar a la de [shared](###shared).

### core

En esta carpeta estarán elementos que se van a ser instanciados una única vez, como los servicios, guards, ...

```
└── core
  ├── [+] guards
  ├── [+] http
  ├── [+] interceptors
  ├── [+] mocks
  ├── [+] services
  └── core.module.ts
```

En el directorio `http` es donde irán los servicios que van a comunicarse con las API REST.

En el directorio `mocks` se inserta el código necesario para trabajar sin servidor, mientras está en desarrollo alguna parte del backend. Le ponemos la extensión spec, puesto que si trabajamos con `sonarqube` nos va a marcar estos ficheros como duplicaciones de código, ya uqe en muchos casos tienen exportaciones de constantes `json`.

```
└── mocks
  ├── language.mock.spec.ts
  └── users.mock.spec.ts
```

En el directorio `services` se crearán los que no se conectan a una API REST, como por ejemplo un servicio que se encargue de leer y escribir en el _LocalStorage_ del navegador.

### models

En este directorio guardamos los modelos de los tipos personalizados que se van a utilizar en nuestra aplicación. A los modelos les ponemos el sufijo model, para indicar que son modelo. Además crearemos un fichero `model.ts` que hará de `barrel`.

```
└── models
  ├── models.ts
  ├── post.model.ts
  ├── post-comment.model.ts
  └── user.model.ts
```

### shared

En este directorio introduciremos los distintos elementos que sean comunes a la aplicación.

```
└── [+] shared
  ├── [+] components
  ├── [+] directives
  └── [+] pipes
```

En el directorio `components` estarán los componentes que se van a reutilizar en varios módulos. Cada componente debe ir en su propia carpeta. Si hay varios, crear un fichero `index.ts` para que la importación sea más sencilla (`barrel`).

A continuación vemos un ejemplo de los componentes:

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

En los directorios `directives` y `pipes` deben ir las directivas y pipes que se creen personalizadas para algún componente y que se usen en componentes del directorio `components`. Crear un directorio por cada elemento. Crear un fichero `index.ts` para que la importación sea más sencilla.

### assets

En este directorio se guardan los recursos que se van a utilizar en el desarrollo, estilos, javascript e imágenes, por ejemplo.

```
└── assets
  └── images
    └── logo.png
```

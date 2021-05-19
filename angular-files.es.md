# Ficheros en Angular

Todos los ficheros deben estar en el formato [kebab-case](https://en.wikipedia.org/wiki/Letter_case#Special_case_styles).

**¿Por qué deberíamos usar el estuche de kebab?** Porque es el formato de archivo que eligió el _Angular Team_, y es una _buena práctica_ respetar esta decisión como estándar.


## Ficheros de Angular
Estos archivos son los ficeros de Angulares normales:

### Componentes

En Angular, un _Componente_ pudría tener 4 archivos (ts, html, css / scss y spec), todos los archivos tienen la misma estructura, `file-name.comonent.type`.
```
my-component.component.ts -> La lógica del componente.
my-component.component.html -> Vista del componente (debe ir dentro de * .ts).
my-component.component.scss -> Estilos del componente (debe ir dentro de * .ts o no existe si es nulo).
my-component.component.spec.ts -> Archivo de prueba unitaria (no puede existir si no realiza la prueba unitaria).
```


### Modelos

Los archivos de _Modelos_ están terminados con `.model.ts`.


### Servicios

Los archivos de _Servicio_ terminan con `.service.ts`. También es posible ver un archivo de prueba unitaria con el archivo de servicio (`.service.spec.ts`).


### Rutas

Los archivos de rutas son muy similares a los _Módulos_, pero solo con la variable de rutas para usar en el módulo con las rutas. Estos archivos están terminados por `route.ts`.


### Gards

En este tipo de ficheros se crean las _Gards_ que permiten acceder a una ruta. Estos ficheros están termiando en `gard.ts`.


### Resolvers

En este tipo de fichero se crean los _Resolvers_ que son usados en las rutas para cargar el detalle de un CRUD (por ejemplo). Estos ficheros están terminados en `resolve.ts`.


### Pipes

En este tipo de ficheros se crean las _Pipes Personalizadas_. Estos ficheros están terminados en `pipe.ts`.


### Directivas

En este tipo de ficheros se crean las _Directivas Personalizadas_. Estos ficheros están terminados en `directive.ts`.


## Archivos regulares no Anguar


### Modelos

Los archivos de _Modelos_ están terminados con `.model.ts`. En estos archivos podemos almacenar una interfaz o una clase dependiendo del contenido del modelo.


### Mock de datos

Este tipo de archivos se utilizan para almacenar datos para las pruebas unitarias (_Datos de prueba_). Yo suelo terminar este tipo de archivos con `.mock.spec.ts` porque **Sonarqube** devuelve un _error de el código repetido_ si termina con `mock.ts`, porque es un tipo de archivo que **Sonarqube** no reconoce.

Volver al [Readme](./README.es.md).
___
Autor:

Juan Antonio Moreno Valderrama.

<a href="https://twitter.com/jmorenovade"><img src="https://img.shields.io/twitter/follow/jmorenovalde?label=Twitter&style=social" alt="Twitter"></a>
<a href="https://www.linkedin.com/in/juan-antonio-moreno-valderrama/"><img src="https://img.shields.io/badge/LinkedIn--_.svg?style=social&logo=linkedin" alt="LinkedIn"></a>
<a href="https://github.com/jmorenovalde"><img alt="GitHub followers" src="https://img.shields.io/github/followers/jmorenovalde?style=social"></a>
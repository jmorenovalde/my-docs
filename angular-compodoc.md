# Documentar el código Angular

Esta parte es una de las más olvidadas, sobre todo en los proyectos personales, cuando es una de las más importantes.

## Comentarios

Se deben comentar las clases, interfaces, variblas, ...

La forma de comentar es la típica de TSDoc `/**` y `*/` para cerrar.

```typescript
/**
 * Indicates if the data is loading.
 */
public isLoading = false;
```

> Recomendación: Escribir los comentarios en Inglés, por si subes el código a un repositorio libre, que pueda llegar a más gente, y te vas acostumbrando a escribir en inglés.

## Compodoc

# Compodoc

**Compodoc** es una _herramienta de creación de documentación automática_ a traves de los comentarios que escribimos en el código para proyectos _Angular_, _Ionic_, _Nest_ o _Stencil_.

![compodoc logo](https://avatars3.githubusercontent.com/u/23202313)

Una de las tareas que menos nos gusta hacer a los programadores, es documentar los desarrollos. Con las herramientas de generación de documentación técnica podemos tener un visión mejor de lo que hacen los desarrollos, así como poder reusar código, en vez de generar código nuevo, puesto que muchas veces hay un código que no está lo debidamente documentado.

Para la gente que haya programado alguna vez en Java, compodoc es como el JavaDoc, pero orientado a Angular y TypeScript.

![Ejemplo de compodoc](https://compodoc.app/assets/img/themes/theme-gitbook.png)

Con compodoc, además podemos tener un registro de la cantidad de recursos que están documentados en un fichero (clases, variables, ...) esto nos permite que nuestra documentación esté lo más detallada posible, [aquí podemos ver un ejemplo](https://compodoc.github.io/compodoc-demo-todomvc-angular/coverage.html).

El código que se genera se puede meter en los desarrollos, de manera que la documentación que se genera es redistribuible con la propia librería, o se puede colgar en un repositorio para ser consultada por el equipo de desarrollo, como podemos ver en el [live demo de compodoc](https://compodoc.github.io/compodoc-demo-todomvc-angular/).

Otra de las ventajas que nos permite _compodoc_ es que nos permite personalizar las páginas a los estilos de nuestro proyecto u organización, así como insertar páginas en documentación adicional escritas en **markdown**. De manera que podemos introducir documentación que deseemos, como un pequeño manual, un documento de contribuciones, licencias o el changelog.

## Instalación

Hay dos formas de trabajar con _compodoc_:

1. Instalación de manera global: El problema es que no podemos automatizar la generación de la documentación al generar las releases.

```bash
# Windows
> npm install -g @compodoc/compodoc

# Linux / macOs
$ sudo npm install -g @compodoc/compodoc
```

2. Instalación local (o dependencia de desarrollo en nuestro proyecto): La ventaja de esta instalación es que se pueden realizar automatizaciones, pero por contra tenemos que hay que tener instalada en cada proyecto la dependencia.

```bash
$ npm install -D @compodoc/compodoc
```

## Documentar el código

Para que _compodoc_ pueda generar una buena documentación, lo que debemos hacer es documentar el código. Para ello _compodoc_ usa la sintaxis de comentarios de _Javascript_ (_JSDoc_).

Si estamos usando [VisualStudio Code](./vscode.md), encima de una propiedad, clase/interfaz, método o función, escribimos `/**` nos rellenará automaticamente el comentario de _JSDoc_. Por alguna razón, en los métodos y las funciones, si devuelve algo, no pone el tag `@return`, pero lo podemos poner nosotros.

Las variables y clases no hace falta que tengan tags, se puede poner un texto para indicar lo que hace o su funcionalidad.
```typescript
/**
 * Esto es una clase.
 */
export class MiClase {
  /** property description (JSDoc comment in one line) */
  public property: string;
  
  // ...
}
```

### Tags soportados

  > Los tags que vamos a ver son los soportados en el momento de realizar esta documentación, en la versión [1.1.11](https://github.com/compodoc/compodoc/blob/develop/CHANGELOG.md) de compodoc

* `@returns`: este tag es usado para indicar la respuesta de un método o función. Su sintaxis es `@returns {Type} Description`. A continauación veremos un ejemplo:

```typescript
/**
 * @returns {number} The processed target number.
 */
function processTarget(target: string): number {
  ... // actions
};
```

* `@ignore`: con este tag lo que hacemos es indicar a _compodoc_ que no tiene que aparecer el objeto que va después en la documentación.

```typescript
/**
 * @ignore
 */
@Component({
    selector: 'app-root',
    templateUrl: './app.component.html',
    styleUrls: ['./app.component.css']
})
export class AppComponent {}
```

* `@param`: en las funciones se usa para describir los parámetros de un métodeo o función. Su sintaxis es `@param {Type} Name Description`. Veamos un ejemplo:

```typescript
/**
 * @param {string} target  The target to process
 * @returns {number} The processed target number.
 */
function processTarget(target: string): number {
  ... // actions
};
```

* `@link`: este tag se usa para insertar links a páginas externas o para enlazar con documentación interna. Lo veremos con un ejemplo:

```typescript
/**
 * {@link Todo|TodoClass}
 * {@link https://github.com GitHub}
 */
```

* `@example`: este tag sirve para indicar un ejemplo de uso de la función. Lo vemos con un ejemplo:

```typescript
/**
 * @example
 * This is a good example
 * processTarget('yo')
 *
 * @param {string} target  The target to process see {@link Todo}
 * @returns The processed target number
 */
function processTarget(target: string): number {
  // actions
}
```

## Ejecución de compodoc

Compodoc se corre desde la línea de comandos mediante **npm** (instalación global) o **npx** (instalación local).

Sintaxis de _compodoc_ (es la misma para **npm** y **npx**):

```bash
# de forma glogal
$ compodoc <ruta_al_proyecto> [opciones]

# de forma local
npx compodoc [optiones]
```

Si vamos a ejecutar _compodoc_ en el directorio de trabajo (donde está el `package.json` no hace falta poner la `ruta_al_proyecto).

En la [documentación de compodoc](https://compodoc.app/guides/options.html) puedes ver todos los parámetros que hay, aquí vamos a exponer algunos.

* `-p` o `--tsconfig [config]`: con esta opción lo que hacemos es indicar el fichero tsconfig.json que vamos a usar, por ejemplo, si queremos hacer la documentación de un librería de _Angular_, es muy útil, ya que en vez el proyecto principal (`app`) seleccionamos el fichero tsconfig.json de la librería a realizar.
```bash
$ compodoc --tsconfig projects/my-library/tsconfig.lib.json
```

* `-w` o `--watch`: con esta opción se queda ejecutandose a la espera de cambios, regenerando la documentación cada vez que hay un cambio.

* `--language [language]`: con esta opción podemos poner la documenación en el idioma que se le pasa (en-US, es-ES, fr-FR, hu-HU, it-IT, ja-JP, nl-NL, pt-BR, zh-CN) (por defecto es en-US).
```bash
$ compodoc --language es-ES
```

* `-t` o `--silent`: Se ejecuta en modo siliencioso, de forma que no escribe en la consola (muy útil para cuando se pasa al un proceso de _CI/CD_.

* `-s` o `--serve`: levanta un servidor local en el puerto 8080.

* `-r` o `--port [port]`: cambiamos el puerto al servidor local (la opción `-s`).
```bash
$ compodoc -s -r 8081
```

* `-d` o `--output [folder]`: esta opción nos permite indicar la ruta de salida de la documentación.
```bash
$ compodoc -d dist/my-library/doc
```

* `--disableCoverage`: con esta opción lo que hacemos es no mostrar el grado de cobertura de la documentación. Es recomendable cuando se publica la documentación.

* `--hideGenerator`: con esta opción quitamos el icono y el texto de generado con _compodoc_.

* `--theme [theme]`: con esta opción podemos cambiar el tema de la generación de la documentación. Por defecto se muestra el tema gitbook, pero hay más temas disponible: laravel, original, material, postmark, readthedocs, stripe, vagrant. En la [documetnación](https://compodoc.app/guides/themes.html) puedes ver un ejemplo de como quedan los temas.

* `-y` o `--extTheme [file]`: esta opción es para añadir un tema personalizado. Para crear un tema, es mejor que vayas a la [documentación](https://compodoc.app/guides/tips-and-tricks.html#styling-the-documentation) o revises el [curso](#cursos) de compodo que viene en esta documentación.

## Recursos

* [Compodoc](https://compodoc.app): Página web de compodoc.
* Ejemplo de apliación [Angular con los comentarios](https://github.com/compodoc/compodoc-demo-todomvc-angular) y su [compodoc](https://compodoc.github.io/compodoc-demo-todomvc-angular/).

## Cursos

* [Compodoc: Crea documentación en proyectos Angular/Ionic/TS](https://www.udemy.com/course/compodoc-crea-documentacion-en-angular-ionic/)
  Crear documentación de calidad y MUY fácil de mantener con Compodoc para proyectos de Angular 2+ / Ionic 2+ / Typescript. Curso gratuito en Udemy

# Documentar el código Angular

Esta parte es una de las más olvidadas, sobre todo en los proyectos personales, cuando es una de las más importantes.

## Comentarios

Se deben comentar las clases, interfaces, variblas, ...

La forma de comentar es la típica de JSDoc `/**` y `*/` para cerrar.

```typescript
/**
 * Indicates if the data is loading.
 */
public isLoading = false;
```

> Recomendación: Escribir los comentarios en Inglés, por si subes el código a un repositorio libre, que pueda llegar a más gente, y te vas acostumbrando a escribir en inglés.

## Compodoc

**Compodoc** es un sistema de creación de documentación automática de la documentación del proyecto de trabajo.

Para que funcione hay que instalarlo con `npm` de manera global:
```bash
npm install -g @compodoc/compodoc
```

En caso de *Linux* o *macOS*, recuerda poner `sudo` antes de npm para que puedas instalarlo como `root`.

Para generar la documentación inicial, hay que hacer lo siguiente:

```bash
compodoc -p tsconfig.json
```

Para luego visualizar la documentación:

```bash
compodoc src -s
```

En el proyecto (`package.json`), se han añadido dos entradas, una para generar la documentación, y otra para verla.

```bash
# Genera la documentación
npm run compdoc
# Ver documentacion. Hay que tener instalado de forma global compodoc.
npm run viewdoc
```

## Cursos

[Compodoc: Crea documentación en proyectos Angular/Ionic/TS](https://www.udemy.com/course/compodoc-crea-documentacion-en-angular-ionic). _**Gratis**_

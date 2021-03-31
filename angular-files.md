# Ficheros en Angular

Todos los ficheros deben estar en [kebab-case](https://en.wikipedia.org/wiki/Letter_case#Special_case_styles).


En este documento se explican los archivos que no son los normales de Angular (_.component.*_, -.service.*_, _.module.ts_, ...).

## Modelos

Para los modelos vamos a usar el sufijo `.model`.

## Mock

En los ficheros mock se guardan los datos para hacer los test, y si hiciera falta, mockear algun serivicio. Para este tipo de ficheros vamos a poner los sufijos `.mock.spec`. Le pongo el _.spec_, puesto que si pasas por las reglas de un _sonarqube_ nos dará un error si no viene con el _.spec_.

## Rutas

Para las rutas que iran en el lazy loading, crearemos un fichero que tendrá el sufijo `.routes`.

___
Desarrollado por:

Juan Antonio Moreno Valderrama.

<a href="https://twitter.com/jmorenovade"><img src="https://img.shields.io/twitter/follow/jmorenovalde?label=Twitter&style=social" alt="Twitter"></a>
<a href="https://www.linkedin.com/in/juan-antonio-moreno-valderrama/"><img src="https://img.shields.io/badge/LinkedIn--_.svg?style=social&logo=linkedin" alt="LinkedIn"></a>
<a href="https://github.com/jmorenovalde"><img alt="GitHub followers" src="https://img.shields.io/github/followers/jmorenovalde?style=social"></a>
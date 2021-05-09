# Changelog

En este documento se quiere hacer una estandarización de los documentos `CHANGELOG.md` de los desarrollos del departamento de Transportes.

En el fichero `CHANGELOG.md` mostramos los cambios que se han producido a lo largo de las distintas versiones del software, a modo de historial de cambios.

## Estrcutura

El fichero se divide en las distintas versiones que se muestran en orden descendente (la más reciente la primera).

Los desarrollos se muestran de igual forma, primero se muestran los que se han realizado en último lugar. Los desarrollos además se van a separar en _Nuevas funcionalidades_ y _Corrección de defectos_.

Vemos un ejemplo:

```markdown
# Changelog

## 1.1.1 - 2018-11-16

### Bugs corregisos:
* [TPIYYY-XX18](https://jira.indra.es/browse/TPIYYY-XX18) Nombre identificativo de la tarea 18.
* [TPIYYY-XX15](https://jira.indra.es/browse/TPIYYY-XX15) Nombre identificativo de la tarea 15.
* [TPIYYY-XX13](https://jira.indra.es/browse/TPIYYY-XX13) Nombre identificativo de la tarea 13.
* [TPIYYY-XX12](https://jira.indra.es/browse/TPIYYY-XX12) Nombre identificativo de la tarea 12.
* [TPIYYY-XX11](https://jira.indra.es/browse/TPIYYY-XX11) Nombre identificativo de la tarea 11.

## 1.1.0 - 2018-10-31

### Nuevas funcionalidades:
* [TPIYYY-XXX8](https://jira.indra.es/browse/TPIYYY-XXX8) Nombre identificativo de la tarea 8.
* [TPIYYY-XXX9](https://jira.indra.es/browse/TPIYYY-XXX9) Nombre identificativo de la tarea 9.
* [TPIYYY-XXX6](https://jira.indra.es/browse/TPIYYY-XXX6) Nombre identificativo de la tarea 6.
* [TPIYYY-XXX5](https://jira.indra.es/browse/TPIYYY-XXX5) Nombre identificativo de la tarea 5.

### Bugs corregisos:
* [TPIYYY-XX10](https://jira.indra.es/browse/TPIYYY-XX10) Nombre identificativo de la tarea 10.
* [TPIYYY-XXX7](https://jira.indra.es/browse/TPIYYY-XXX7) Nombre identificativo de la tarea 7.

## 1.0.0 - 2018-09-28

### Nuevas funcionalidades:
* [TPIYYY-XXX4](https://jira.indra.es/browse/TPIYYY-XXX4) Nombre identificativo de la tarea 4.
* [TPIYYY-XXX2](https://jira.indra.es/browse/TPIYYY-XXX2) Nombre identificativo de la tarea 2.
* [TPIYYY-XXX3](https://jira.indra.es/browse/TPIYYY-XXX3) Nombre identificativo de la tarea 3.
* [TPIYYY-XXX1](https://jira.indra.es/browse/TPIYYY-XXX1) Nombre identificativo de la tarea 1.
```

Además, al hacer el tag en el repositorio GIT, se puede usar los datos de este fichero.

Para cuando estamos desarrollando, como no sabemos si lo que se va a liberar en una versión menor o un parche se recomienda crear un elemento llamado `[Unreleased]` de forma que ahí vamos apuntando los desarrollos y el orden de éstos.

```markdown
# Change Log

## [Unreleased]

### Nuevas funcionalidades:
* [TPIYYY-XX16](https://jira.indra.es/browse/TPIYYY-XX16) Nombre identificativo de la tarea 16.

### Bugs corregisos:
* [TPIYYY-XX17](https://jira.indra.es/browse/TPIYYY-XX17) Nombre identificativo de la tarea 17.


## 1.1.1 - 2018-11-16
...
```

## Versionado.
Para el código de versión, vamos a utilizar el [Versionado Semántico](https://semver.org/spec/v2.0.0.html).
El número de versión se divide en tres números:

```
MAJOR.MINOR.PATCH
```

* MAJOR : Este código de la versión debe ser modificado cuando se añade funcionalidad que hace incompatible la funcionalidad con la anterior versión.
* MINOR : Este código de la versión debe ser modificado cuando se añade funcionalidad y sigue siendo compatible conlas funcionalidades anteriores.
* PATCH : Este código de la versión debe ser modificado cuando sólo se añaden correcciones de errores.

## Quien modifica este fichero

Este fichero lo debe modificar el desarrollador de la historia cuando empiece a desarrollarla, de forma que se coloca en primer lugar. Cuando se vaya a mergear la tarea a develop, si hay que hacer un merge, se pondrá la primera.

Cuando se genere la release, habrá que modificarlo para cambiar el `[Unreleased]` por la versión y la fecha de liberación, y luego añadirlo de nuevo para la rama develop.

## Referencias

* [1] https://keepachangelog.com/es-ES/1.0.0/

* [2] https://gist.githubusercontent.com/juampynr/4c18214a8eb554084e21d6e288a18a2c/raw/6d61b1ced1c66349cf9ef6ce5eb84546ebf6e79d/CHANGELOG.md

* [3] https://standardjs.com/changelog.html

___
Desarrollado por:

Juan Antonio Moreno Valderrama.

<a href="https://twitter.com/jmorenovade"><img src="https://img.shields.io/twitter/follow/jmorenovalde?label=Twitter&style=social" alt="Twitter"></a>
<a href="https://www.linkedin.com/in/juan-antonio-moreno-valderrama/"><img src="https://img.shields.io/badge/LinkedIn--_.svg?style=social&logo=linkedin" alt="LinkedIn"></a>
<a href="https://github.com/jmorenovalde"><img alt="GitHub followers" src="https://img.shields.io/github/followers/jmorenovalde?style=social"></a>
# Files in Angular

All the files must be at [kebab-case](https://en.wikipedia.org/wiki/Letter_case#Special_case_styles) format.

**Why we should use the kebab-case?** Because is the file format that choosed the _Angular Team_, and it's a _good practice_ respect this decision as a standard.


## Angular Files

These files are the normal Angular files:


### Components:

In Angular a _Component_ should have 4 files (ts, html, css/scss and spec), all the files has the same structure, file-name.comonent.type.

```
my-component.component.ts --> The logic of the component.
my-component.component.html --> View of the compoent (should go inside *.ts).
my-component.component.scss --> Styles of the component (should go inside *.ts or not exists if it is void).
my-component.component.spec.ts --> Unit test file (it can´t exists if don't do unit test).
```


### Models

The models files are finished by `.model.ts`.


### Services

The service files are finished by `.service.ts`. It is posible to see an unit test file with the service file too (`.service.spec.ts`).


### Routes

The files of routes are very similar than Modules, but only with the routes variable to use in the module with the routes. This files are finished by `routes.ts`.


### Gards

In this type of file create the Gards to can allow the access to a route. This files are finished by `gard.ts`.


### Resolvers

In this type of file create the Resolvers that use on the routes to load the detail of a CRUD (for example). This files are finished by `resolve.ts`.


### Pipes

In this type of file create the _Custom Pipes_. This files are finished by `pipe.ts`


### Directives

In this type of files create the _Custom Directives_. This files are finished by `directive.ts`


## Non Anguar Regular files


### Models

The _Models_ files are finished by `.model.ts`. In this files we can store an _Interface_ or a _Class_ depence of the content of the model.


### Mock

This type of files are used to store data for the unit test (_Mock Data_). I use to finished this kind of files with `.mock.spec.ts` because _Sonarqube_ return an _error as repeat code_ is finished with `mock.ts`, because is a type of file that _Sonarqube_ not reconice.


Back to [Readme](./README.md).
___
Author:

Juan Antonio Moreno Valderrama.

<a href="https://twitter.com/jmorenovade"><img src="https://img.shields.io/twitter/follow/jmorenovalde?label=Twitter&style=social" alt="Twitter"></a>
<a href="https://www.linkedin.com/in/juan-antonio-moreno-valderrama/"><img src="https://img.shields.io/badge/LinkedIn--_.svg?style=social&logo=linkedin" alt="LinkedIn"></a>
<a href="https://github.com/jmorenovalde"><img alt="GitHub followers" src="https://img.shields.io/github/followers/jmorenovalde?style=social"></a>
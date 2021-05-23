# The Angular Project Structure

The objective of this article is to standardize the structure of the folders of a project in Angular.

For that we take the article [How to define a highly scalable folder structure for your Angular project](https://itnext.io/choosing-a-highly-scalable-folder-structure-in-angular-d987de65ec7) as a base.


## Project structure

The structure is based on the functionality of the files, with this way it is very easy that an outside-project person finds out a file in the project.

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

> `[+]` This symbol should indicate that the folder could have subfolders inside.


### shared

In this folder, introduce the different elements that are common in the application.

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

In the folders `directives` and `pipes` should go the directives and pipes for the custom pipes or directives that use the components of the _component_ folder inside _shared_ folder. Create a folder for each element and an `index.ts` if exists more than one element to do more easier importation of the elements.


### modules

In this folder should be the modules of the application. The components that we want to load as _Lazy Loading_ or components wrap by a module could reuse in other parts of the application.

Inside this folder, we should find out a similar structure of [sharded](#shared).


### core

In this folder, they will be the elements that will be instantiated only one time in all the application, as services, guards, ...

```
└── core
  ├── [+] guards
  ├── [+] http
  ├── [+] interceptors
  ├── [+] services
  └── core.module.ts
```

The `http` folder is the folder to store the services that connect with the APIs.

n the `services` folder, we should see the services that not connect to the APIs, for example, a service to store data in _LocalStorage_


### models


In this folder, we store the models of the custom entity models, that we could use in the application. If there are several files, I recommend creating a _barrel_ named `model.ts`.

```
└── models
  ├── models.ts
  ├── post.model.ts
  ├── post-comment.model.ts
  └── user.model.ts
```

Back to [Readme](./README.md).
___
Desarrollado por:

Juan Antonio Moreno Valderrama.

<a href="https://twitter.com/jmorenovade"><img src="https://img.shields.io/twitter/follow/jmorenovalde?label=Twitter&style=social" alt="Twitter"></a>
<a href="https://www.linkedin.com/in/juan-antonio-moreno-valderrama/"><img src="https://img.shields.io/badge/LinkedIn--_.svg?style=social&logo=linkedin" alt="LinkedIn"></a>
<a href="https://github.com/jmorenovalde"><img alt="GitHub followers" src="https://img.shields.io/github/followers/jmorenovalde?style=social"></a>
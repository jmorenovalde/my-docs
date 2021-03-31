# Angular y Jest

## Jest

__Jest__ es un framework de testing desarrollado por _Facebook_, originalmente para _React_, pero que hoy en día es el más usado con JavaScript (NodeJS, Vue, React) y con TypeScript (NestJS, Svelt, TypeScript).

En este punto podríamos pensar que por qué usar un software desarrollado para otro propósito distinto a _Angular_, que además el equipo de _Google_ encargado en el mantenimiento de _Angular_ apuestan por _Yasmine_ y _Karma_. Desde mi punto de vista, tenemos principalmente dos puntos por los que debemos pensar pasar a _Jest_:

1. Al ser de propósito general va a ser fácil atraer a otros programadores de otras tecnologías a nuestros equipos de desarrollo, o si nosotros queremos cambiar de tecnología, por ejemplo programar en _NestJS_, o por ejemplo si pasamos a _React_, _Vue_, ...

2. _Karma_ con _Yasmine_ ejecutan los test secuencialmente, mientras que _Jest_ puede ejecutar los test en paralelo, con pocos test nos da igual, pero si tenemos una gran batería de tests unitarios, esto nos puede ahorrar mucho tiempo, y en ciclos de CI/CD que están en máquinas dinámicas, ahorra dinero.

Además de estos dos puntos de vista, tenemos también los siguientes:

* Snapshot testingh para la UI, de forma que solo fallan cuando se cambia la UI.

* Ejecución de test más potente: podemos medinte el CLI seleccionar qué test ejecutar, sin necesidad de usar el _focus_.

* Mayor base de ejemplos al ser de propósito general, aunque estemos testeando algo en _Angular_, podremos encontrar test similares para _React_ o _Vue_.

## Instalar Jest en nuestro proyecto Angular.

Actualmente es muy sencillo instalar _Jest_ en nuestro proyecto _Angular_, vasta con instalar y ejecutar un _esquema_ de _Angular_.

Para ello ejecutaremos las siguintes sentencias en nuestro proyecto de _Angular_.

```bash
npm install -D @briebug/jest-schematic
ng g @briebug/jest-schematic:add
```

Si quieres se puede instalar de forma global cambiando el `-D` por `-g`, y solo habrá que instalar una única vez el _esquema_.

Tras este paso, el _esquema_ desarrollado por @briebug, habrá quitado de nuestro proyecto _Karma_, _Yasmine_ y habrá configurado _Jest_.

> __Importante__: Si en el proyecto tenías test unitarios, es probable que algunos te fallen, sobre todo si estabas usando la librarías _Jasmine_ como por ejemplo `jasmine.createSpyObj`.

### Migrar test desde Karma - Jasmine

En _Jest_ se pierde una de las cosas que se podían usar con _Jasmine_ que era poner en los métodos de `toEqual` o `toBeTruthy` (por ejemplo) un texto para cuando aserción fallaba, por ejemplo:
```javascript

// Jasmine test
it('should to be true', () => {
  ...
  expect(response).toBeTruthy('The service does not return a response.');
})

// Jest test
it('should to be true', () => {
  ...
  expect(response).toBeTruthy();
})
```

En _Jest_ no es necesario, puesto que cuando se genera un error, se nos muestra en la consola el lugar exacto del fallo del test.

Si estamos usando los `spyOn` de _Jasmine_ o los `jasmine.createSpyObj` mirar el recurso [Testing Angular with jest](https://ordina-jworks.github.io/testing/2018/08/03/testing-angular-with-jest.html) puesto que se indican las equivalencias a aplicar.

> __Importante__: si vamos a usar el sufijo `.spec` para los test, no podemos usarlos para los datos mock, puesto que Jest requiere que todos los ficheros `.spec` tengan al menos un test unitario. En mis proyectos uso para los datos mock el sufijo `.spec`, puesto que _SonarQube_ se quejaba de código duplicado.

### Proyecto desde cero

Si lo que vamos a crear un proyecto desde cero tenemos dos opciones, la primera es usar el mismo _esquema_ visto antes y la otra opción es usar _Nx_, que por defecto tiene configurado _Jest_ y _Cypress_ (e2e).

## Extensiones para VSCode

* [Jest](https://marketplace.visualstudio.com/items?itemName=Orta.vscode-jest): Esta extensión es muy recomendable para trabajar con Jest, nos marca los test que pasan o fallan.

## Recursos

* [Jest](https://jestjs.io/)

* [Angular-Jest schematic](https://github.com/briebug/jest-schematic).

* [Nx](https://nx.dev/).

* Video de DominiCode en YouTube: [¿Cómo configurar JEST en Angular? - Angular 11](https://www.youtube.com/watch?v=QY0RGkhzJdo).

* [Testing Angular with jest](https://ordina-jworks.github.io/testing/2018/08/03/testing-angular-with-jest.html).

___
Desarrollado por:

Juan Antonio Moreno Valderrama.

<a href="https://twitter.com/jmorenovade"><img src="https://img.shields.io/twitter/follow/jmorenovalde?label=Twitter&style=social" alt="Twitter"></a>
<a href="https://www.linkedin.com/in/juan-antonio-moreno-valderrama/"><img src="https://img.shields.io/badge/LinkedIn--_.svg?style=social&logo=linkedin" alt="LinkedIn"></a>
<a href="https://github.com/jmorenovalde"><img alt="GitHub followers" src="https://img.shields.io/github/followers/jmorenovalde?style=social"></a>